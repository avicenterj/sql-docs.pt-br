---
title: Método nodes() (tipo de dados xml) | Microsoft Docs
ms.custom: ''
ms.date: 07/26/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- nodes() method
- nodes method
ms.assetid: 7267fe1b-2e34-4213-8bbf-1c953822446c
caps.latest.revision: 39
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 7d089a5d75a1601e2035f9ac40076023aee04578
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37982328"
---
# <a name="nodes-method-xml-data-type"></a>Método de nós() (Tipo de dados xml)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  O método **nodes()** é útil quando você deseja fragmentar uma instância de tipo de dados **xml** em dados relacionais. Isso permite identificar nós que serão mapeados em uma nova linha.  
  
 Toda instância de tipo de dados **xml** tem um nó de contexto fornecido implicitamente. Para a instância XML armazenada em uma coluna ou variável, esse é o nó de documento. O nó de documento é o nó implícito na parte superior de cada instância de tipo de dados **xml**.  
  
 O resultado do método **nodes()** é um conjunto de linhas que contém cópias lógicas das instâncias de XML originais. Nessas cópias lógicas, o nó de contexto de cada instância de linha é definido como um dos nós identificados com a expressão de consulta, para que as consultas subsequentes possam navegar em relação a esses nós de contexto.  
  
 Você pode recuperar vários valores do conjunto de linhas. Por exemplo, você pode aplicar o método **value()** ao conjunto de linhas retornado por **nodes()** e recuperar vários valores da instância de XML original. Observe que o método **value()**, quando aplicado à instância de XML, retorna somente um valor.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
nodes (XQuery) as Table(Column)  
```  
  
## <a name="arguments"></a>Argumentos  
 *XQuery*  
 É uma cadeia de caracteres literal, uma expressão XQuery. Se a expressão de consulta construir nós, esses nós construídos serão expostos no conjunto de linhas resultante. Se a expressão de consulta resultar em uma sequência vazia, o conjunto de linhas será vazio. Se a expressão de consulta resultar estaticamente em uma sequência que contém valores atômicos em vez de nós, um erro estático será gerado.  
  
 *Table*(*Column*)  
 É o nome de tabela e o nome de coluna para o conjunto de linhas resultante.  
  
## <a name="remarks"></a>Remarks  
 Como um exemplo, suponha que você tenha a seguinte tabela:  
  
```  
T (ProductModelID int, Instructions xml)  
```  
  
 O documento de instruções de fabricação a seguir é armazenado na tabela. Só um fragmento é mostrado. Observe que há três locais fabricação no documento.  
  
```  
<root>  
  <Location LocationID="10"...>  
     <step>...</step>  
     <step>...</step>  
      ...  
  </Location>  
  <Location LocationID="20" ...>  
       ...  
  </Location>  
  <Location LocationID="30" ...>  
       ...  
  </Location>  
</root>  
```  
  
 Uma invocação do método `nodes()` com a expressão de consulta `/root/Location` retorna um conjunto de linhas com três linhas, cada uma contendo uma cópia lógica do documento XML original e com o conjunto de itens de contexto definido como um dos nós `<Location>`:  
  
```  
Product  
ModelID      Instructions  
----------------------------------  
1       <root>  
             <Location LocationID="20" ... />  
             <Location LocationID="30" .../></root>  
1      <root><Location LocationID="10" ... />  
  
             <Location LocationID="30" .../></root>  
1      <root><Location LocationID="10" ... />  
             <Location LocationID="20" ... />  
             </root>  
```  
  
 Você pode fazer consultas nesse conjunto de linhas usando métodos de tipo de dados **xml**. A consulta a seguir extrai a subárvore do item de contexto para cada linha gerada:  
  
```  
SELECT T2.Loc.query('.')  
FROM   T  
CROSS APPLY Instructions.nodes('/root/Location') as T2(Loc)   
```  
  
 Este é o resultado:  
  
```  
ProductModelID  Instructions  
----------------------------------  
1        <Location LocationID="10" ... />  
1        <Location LocationID="20" ... />  
1        <Location LocationID="30" .../>  
```  
  
 Observe que o conjunto de linhas retornado manteve as informações de tipo. Você pode aplicar métodos de tipo de dados **xml**, como **query()**, **value()**, **exist()** e **nodes()**, ao resultado de um método **nodes()**. Entretanto, você não pode aplicar o método **modify()** para modificar a instância de XML.  
  
 Além disso, o nó de contexto no conjunto de linhas não pode ser materializado. Quer dizer, você não pode usá-lo em uma instrução SELECT. Entretanto, é possível usá-lo em IS NULL e COUNT(*).  
  
 Os cenários para uso do método **nodes()** são os mesmos que para [OPENXML &#40;Transact-SQL&#41;](../../t-sql/functions/openxml-transact-sql.md). Isso fornece uma exibição de conjunto de linhas do XML. Entretanto, não é preciso usar cursores ao usar o método **nodes()** em uma tabela que contém várias linhas de documentos XML.  
  
 Observe que o conjunto de linhas retornado pelo método **nodes()** é um conjunto de linhas sem nome. Por isso, ele deve ser nomeado explicitamente usando alias.  
  
 A função **nodes()** não pode ser se aplicada diretamente aos resultados de uma função definida pelo usuário. Para usar a função **nodes()** com o resultado de uma função escalar definida pelo usuário, atribua o resultado da função definida pelo usuário a uma variável ou use uma tabela derivada para atribuir um alias de coluna ao valor retornado da função definida pelo usuário e, em seguida, use CROSS APPLY para selecionar uma opção no alias.  
  
 O exemplo a seguir mostra uma maneira de usar `CROSS APPLY` para selecionar do resultado de uma função definida pelo usuário.  
  
```  
USE AdventureWorks;  
GO  
  
CREATE FUNCTION XTest()  
RETURNS xml  
AS  
BEGIN  
RETURN '<document/>';  
END;  
GO  
  
SELECT A2.B.query('.')  
FROM  
(SELECT dbo.XTest()) AS A1(X)   
CROSS APPLY X.nodes('.') A2(B);  
GO  
  
DROP FUNCTION XTest;  
GO  
```  
  
## <a name="examples"></a>Exemplos  
  
### <a name="using-nodes-method-against-a-variable-of-xml-type"></a>Usando o método nodes() em uma variável do tipo xml  
 No exemplo a seguir, há um documento XML com um elemento de nível superior <`Root`> e três elementos filho <`row`>. A consulta usa o método `nodes()` para definir nós de contexto separados, um para cada elemento <`row`>. O método `nodes()` retorna um conjunto de linhas com três linhas. Cada linha tem uma cópia lógica do XML original, com cada nó de contexto identificando um elemento <`row`> diferente no documento original.  
  
 A consulta retorna o nó de contexto de cada linha:  
  
```  
DECLARE @x xml   
SET @x='<Root>  
    <row id="1"><name>Larry</name><oflw>some text</oflw></row>  
    <row id="2"><name>moe</name></row>  
    <row id="3" />  
</Root>'  
SELECT T.c.query('.') AS result  
FROM   @x.nodes('/Root/row') T(c)  
GO  
```  
  
 O seguinte é o resultado. Neste exemplo, o método de consulta retorna o item de contexto e seu conteúdo:  
  
```  
<row id="1"><name>Larry</name><oflw>some text</oflw></row>  
<row id="2"><name>moe</name></row>  
<row id="3"/>  
```  
  
 Aplicando o acessador pai nos nós de contexto, o elemento <`Root`> é retornado para os três:  
  
```  
SELECT T.c.query('..') AS result  
FROM   @x.nodes('/Root/row') T(c)  
go  
```  
  
 Este é o resultado:  
  
```  
<Root>  
    <row id="1"><name>Larry</name><oflw>some text</oflw></row>  
    <row id="2"><name>moe</name></row>  
    <row id="3" />  
</Root>  
<Root>  
    <row id="1"><name>Larry</name><oflw>some text</oflw></row>  
    <row id="2"><name>moe</name></row>  
    <row id="3" />  
</Root>  
<Root>  
    <row id="1"><name>Larry</name><oflw>some text</oflw></row>  
    <row id="2"><name>moe</name></row>  
    <row id="3" />  
</Root>  
```  
  
### <a name="specifying-the-nodes-method-against-a-column-of-xml-type"></a>Especificando o método nodes() em uma coluna do tipo xml  
 As instruções de fabricação da bicicleta são usadas neste exemplo e armazenadas na coluna Instructions do tipo **xml** da tabela **ProductModel**.  
  
 No exemplo a seguir, o método `nodes()` é especificado na coluna `Instructions` do tipo **xml** na tabela `ProductModel`.  
  
 O método `nodes()` define os elementos <`Location`> como nós de contexto especificando o caminho `/MI:root/MI:Location`. O conjunto de linhas resultante inclui cópias lógicas do documento original, uma para cada nó <`Location`> no documento, com o conjunto de nós de contexto definido como o elemento <`Location`>. Portanto, a função `nodes()` oferece um conjunto de nós de contexto <`Location`>.  
  
 O método `query()` nesse conjunto de linhas solicita `self::node` e, então, retorna o elemento `<Location>` em cada linha.  
  
 Nesse exemplo, a consulta define cada <`Location`> como um nó de contexto no documento de instruções de fabricação de um modelo de produto específico. É possível usar esses nós de contexto para recuperar valores conforme a seguir:  
  
-   Localizar IDs de local em cada <`Location`>  
  
-   Recuperar etapas de fabricação (elementos filho <`step`>) em cada <`Location`>  
  
 Essa consulta retorna o item de contexto, no qual a sintaxe abreviada `'.'` para `self::node()` é especificada, no método `query()`.  
  
 Observe o seguinte:  
  
-   O método `nodes()` é aplicado à coluna Instructions e retorna um conjunto de linhas, `T (C)`. Esse conjunto de linhas contém cópias lógicas do documento de instruções de fabricação original com `/root/Location` como o item de contexto.  
  
-   CROSS APPLY aplica `nodes()` a cada linha da tabela `Instructions` e retorna somente as linhas que produzem um conjunto de resultados.  
  
    ```  
    SELECT C.query('.') as result  
    FROM Production.ProductModel  
    CROSS APPLY Instructions.nodes('  
    declare namespace MI="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
    /MI:root/MI:Location') as T(C)  
    WHERE ProductModelID=7  
    ```  
  
     Este é o resultado parcial:  
  
    ```  
    <MI:Location LocationID="10"  ...>  
       <MI:step ... />  
          ...  
    </MI:Location>  
    <MI:Location LocationID="20"  ... >  
        <MI:step ... />  
          ...  
    </MI:Location>  
    ...  
    ```  
  
### <a name="applying-nodes-to-the-rowset-returned-by-another-nodes-method"></a>Aplicando nodes() ao conjunto de linhas retornado por outro método nodes()  
 O código a seguir faz uma consulta nos documentos XML sobre as ordens de fabricação na coluna `Instructions` da tabela `ProductModel`. A consulta retorna um conjunto de linhas contendo a ID de modelo de produto, locais de fabricação e etapas de fabricação.  
  
 Observe o seguinte:  
  
-   O método `nodes()` é aplicado à coluna `Instructions` e retorna o conjunto de linhas `T1 (Locations)`. Esse conjunto de linhas contém cópias lógicas do documento de instruções de fabricação original, com o elemento `/root/Location` como o item de contexto.  
  
-   `nodes()` é aplicado ao conjunto de linhas `T1 (Locations)` e retorna o conjunto de linhas `T2 (steps)`. Esse conjunto de linhas contém cópias lógicas do documento de instruções de fabricação original, com o elemento `/root/Location/step` como o item de contexto.  
  
```  
SELECT ProductModelID, Locations.value('./@LocationID','int') as LocID,  
steps.query('.') as Step         
FROM Production.ProductModel         
CROSS APPLY Instructions.nodes('         
declare namespace MI="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";         
/MI:root/MI:Location') as T1(Locations)         
CROSS APPLY T1.Locations.nodes('         
declare namespace MI="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";         
./MI:step ') as T2(steps)         
WHERE ProductModelID=7         
GO         
```  
  
 Este é o resultado:  
  
```  
ProductModelID LocID Step         
----------------------------         
7      10   <step ... />         
7      10   <step ... />         
...         
7      20   <step ... />         
7      20   <step ... />         
7      20   <step ... />         
...         
```  
  
 A consulta declara o prefixo `MI` duas vezes. Em vez disso, você pode usar `WITH XMLNAMESPACES` para declarar o prefixo uma vez e usá-lo na consulta:  
  
```  
WITH XMLNAMESPACES (  
   'http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions'  AS MI)  
  
SELECT ProductModelID, Locations.value('./@LocationID','int') as LocID,  
steps.query('.') as Step         
FROM Production.ProductModel         
CROSS APPLY Instructions.nodes('         
/MI:root/MI:Location') as T1(Locations)         
CROSS APPLY T1.Locations.nodes('         
./MI:step ') as T2(steps)         
WHERE ProductModelID=7         
GO    
```  
  
## <a name="see-also"></a>Consulte Também  
 [Adicionar namespaces a consultas com WITH XMLNAMESPACES](../../relational-databases/xml/add-namespaces-to-queries-with-with-xmlnamespaces.md)   
 [Criar instâncias de dados XML](../../relational-databases/xml/create-instances-of-xml-data.md)   
 [Métodos de Tipos de Dados XML](../../t-sql/xml/xml-data-type-methods.md)  
  
  
