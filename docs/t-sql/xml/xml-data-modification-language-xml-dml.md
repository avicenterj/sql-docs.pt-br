---
title: XML DML (linguagem de modificação de dados XML) | Microsoft Docs
ms.custom: ''
ms.date: 03/16/2017
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- modifying data [SQL Server], XML DML
- XML [SQL Server], DML
- XML DML [SQL Server]
- data modification language [XML DML]
- data modifications [XML DML]
- DML [XML in SQL Server]
- XQuery, XML DML
- xml data type [SQL Server], XML DML
ms.assetid: 20ce50d2-c07b-4e41-93a7-1380d2cd49cb
caps.latest.revision: 29
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: a4f97feca852401303c15b9dc232035319cb527e
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37995108"
---
# <a name="xml-data-modification-language-xml-dml"></a>Linguagem de modificação de dados XML (XML DML)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  A linguagem de Modificação de Dados XML (XML DML) é uma extensão da linguagem XQuery. Como definido por W3C, a linguagem XQuery é desprovida da parte de Manipulação de Dados (DML). A XML DML apresentada neste tópico, além da linguagem XQuery, oferece uma consulta totalmente funcional e uma linguagem de modificação de dados que pode ser usada com o tipo de dados **xml**.  
  
 A XML DML acrescenta as seguintes palavras-chave que diferenciam maiúsculas e minúsculas à XQuery:  
  
-   **insert**  
  
-   **delete**  
  
-   **replace value of**  
  
 Conforme descrito em [Tipo de dados e colunas XML &#40;SQL Server&#41;](../../relational-databases/xml/xml-data-type-and-columns-sql-server.md), você pode criar variáveis e colunas do tipo **xml** e atribuir documentos ou fragmentos XML a elas. Para modificar ou atualizar essas instâncias de XML, faça o seguinte:  
  
-   Use o [Método modify() (tipo de dados xml)](../../t-sql/xml/modify-method-xml-data-type.md) do tipo de dados **xml**.  
  
-   Especifique as instruções XML DML apropriadas dentro do método **modify()**.  
  
 Observe que há alguns atributos que não podem ser inseridos, excluídos ou ter seus valores modificados. Por exemplo:  
  
-   Para **xml** tipado ou não tipado, os atributos são **xmlns**, **xmlns:\*** e **xml:base**.  
  
-   Somente para **xml** tipado, os atributos são **xsi:nil**, and **xsi:type**.  
  
 Outras restrições incluem o seguinte:  
  
-   Para **xml** tipado ou não tipado, haverá falha na inserção do atributo **xml:base**.  
  
-   Para **xml** tipado, haverá falha na exclusão e modificação do atributo **xsi:nil**. Para **xml** não tipado, você poderá excluir o atributo ou modificar seu valor.  
  
-   Para **xml** tipado, haverá falha na modificação do valor do atributo **xs:type**. Para **xml** não tipado, você poderá modificar o valor do atributo.  
  
 Quando você modifica uma instância XML digitada, o formato final deve ser uma instância válida desse tipo. Caso contrário, será retornado um erro de validação.  
  
## <a name="see-also"></a>Consulte Também  
 [insert &#40;XML DML&#41;](../../t-sql/xml/insert-xml-dml.md)   
 [delete &#40;XML DML&#41;](../../t-sql/xml/delete-xml-dml.md)   
 [replace value of &#40;XML DML&#41;](../../t-sql/xml/replace-value-of-xml-dml.md)   
 [Comparar XML digitado com XML não digitado](../../relational-databases/xml/compare-typed-xml-to-untyped-xml.md)   
 [Criar instâncias de dados XML](../../relational-databases/xml/create-instances-of-xml-data.md)   
 [Métodos de Tipos de Dados XML](../../t-sql/xml/xml-data-type-methods.md)  
  
  
