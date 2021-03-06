---
title: PERCENTILE_DISC (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 10/20/2015
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.suite: sql
ms.technology: t-sql
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- PERCENTILE_DISC
- PERCENTILE_DISC_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- PERCENTILE_DISC function
- analytic functions,PERCENTILE_DISC
ms.assetid: b545413d-c4f7-4c8e-8617-607599a26680
caps.latest.revision: 23
author: MashaMSFT
ms.author: mathoma
manager: craigg
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 4d7e39f1405ee94f786ceaf3116fe652402db69a
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43058618"
---
# <a name="percentiledisc-transact-sql"></a>PERCENTILE_DISC (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-all-md](../../includes/tsql-appliesto-ss2012-all-md.md)]

  Computa um percentil específico para obter valores classificados em um conjunto de linhas inteiro ou dentro de partições distintas de um conjunto de linhas no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Para um determinado valor de percentil *P*, PERCENTILE_DISC classifica os valores da expressão na cláusula ORDER BY e retorna o valor com o menor valor de CUME_DIST (com relação à mesma especificação de classificação) que é maior que ou igual a *P*. Por exemplo, PERCENTILE_DISC (0.5) computará os 50º percentil (isto é, o mediano) de uma expressão. PERCENTILE_DISC calcula o percentil baseado em uma distribuição discreta dos valores da coluna; o resultado é igual a um valor específico na coluna.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL &#40;Transact-SQL&#41;](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
PERCENTILE_DISC ( numeric_literal ) WITHIN GROUP ( ORDER BY order_by_expression [ ASC | DESC ] )  
    OVER ( [ <partition_by_clause> ] )  
```  
  
## <a name="arguments"></a>Argumentos  
 *literal*  
 O percentil a ser computado. O valor deve variar entre 0,0 e 1,0.  
  
 WITHIN GROUP **(** ORDER BY *order_by_expression* [ **ASC** | DESC ]**)**  
 Especifica uma lista de valores sobre os quais classificar e calcular o percentil. Apenas uma *order_by_expression* é permitida. A ordem de classificação padrão é crescente. A lista de valores pode ser de qualquer um dos tipos de dados válidos para a operação de classificação.  
  
 OVER **(** \<partition_by_clause> **)**  
 Divide o conjunto de resultados produzido pela cláusula FROM nas partições às quais a função de percentil é aplicada. Para obter mais informações, consulte [Cláusula OVER &#40;Transact-SQL&#41;](../../t-sql/queries/select-over-clause-transact-sql.md). A \<cláusula ORDER BY> e a \<cláusula rows ou range> não podem ser especificadas em uma função PERCENTILE_DISC.  
  
## <a name="return-types"></a>Tipos de retorno  
 O tipo de retorno é determinado pelo tipo *order_by_expression*.  
  
## <a name="compatibility-support"></a>Suporte de compatibilidade  
 Sob o nível de compatibilidade 110 e superior, WITHIN GROUP é uma palavra-chave reservada. Para obter mais informações, veja [Nível de compatibilidade de ALTER DATABASE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql-compatibility-level.md).  
  
## <a name="general-remarks"></a>Comentários gerais  
 Todos os nulos do conjunto de dados são ignorados.  
  
 PERCENTILE_DISC é não determinística. Para obter mais informações, veja [Funções determinísticas e não determinísticas](../../relational-databases/user-defined-functions/deterministic-and-nondeterministic-functions.md).  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-basic-syntax-example"></a>A. Exemplo de sintaxe básica  
 O exemplo a seguir usa PERCENTILE_CONT e PERCENTILE_DISC para localizar o salário médio dos funcionários de cada departamento. Observe que essas funções podem não retornar o mesmo valor. Isso é porque PERCENTILE_CONT interpola o valor apropriado, quer ele exista ou não no conjunto de dados, enquanto PERCENTILE_DISC sempre retorna um valor real do conjunto.  
  
```  
USE AdventureWorks2012;  
  
SELECT DISTINCT Name AS DepartmentName  
      ,PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY ph.Rate)   
                            OVER (PARTITION BY Name) AS MedianCont  
      ,PERCENTILE_DISC(0.5) WITHIN GROUP (ORDER BY ph.Rate)   
                            OVER (PARTITION BY Name) AS MedianDisc  
FROM HumanResources.Department AS d  
INNER JOIN HumanResources.EmployeeDepartmentHistory AS dh   
    ON dh.DepartmentID = d.DepartmentID  
INNER JOIN HumanResources.EmployeePayHistory AS ph  
    ON ph.BusinessEntityID = dh.BusinessEntityID  
WHERE dh.EndDate IS NULL;  
```  
  
 Este é um conjunto de resultados parcial.  
  
 ```
DepartmentName        MedianCont    MedianDisc
--------------------   ----------   ----------
Document Control       16.8269      16.8269
Engineering            34.375       32.6923
Executive              54.32695     48.5577
Human Resources        17.427850    16.5865
```
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemplos: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] e [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="b-basic-syntax-example"></a>B. Exemplo de sintaxe básica  
 O exemplo a seguir usa PERCENTILE_CONT e PERCENTILE_DISC para localizar o salário médio dos funcionários de cada departamento. Observe que essas funções podem não retornar o mesmo valor. Isso é porque PERCENTILE_CONT interpola o valor apropriado, quer ele exista ou não no conjunto de dados, enquanto PERCENTILE_DISC sempre retorna um valor real do conjunto.  
  
```  
-- Uses AdventureWorks  
  
SELECT DISTINCT DepartmentName  
       ,PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY BaseRate)  
        OVER (PARTITION BY DepartmentName) AS MedianCont  
       ,PERCENTILE_DISC(0.5) WITHIN GROUP (ORDER BY BaseRate)  
        OVER (PARTITION BY DepartmentName) AS MedianDisc  
FROM dbo.DimEmployee;  
  
```  
  
 Este é um conjunto de resultados parcial.  
  
 ```
DepartmentName        MedianCont    MedianDisc  
--------------------   ----------   ----------  
Document Control       16.826900    16.8269  
Engineering            34.375000    32.6923  
Human Resources        17.427850    16.5865  
Shipping and Receiving  9.250000     9.0000
```  
  
## <a name="see-also"></a>Consulte Também  
 [PERCENTILE_CONT &#40;Transact-SQL&#41;](../../t-sql/functions/percentile-cont-transact-sql.md)  
  
  


