---
title: "Especificar várias condições de pesquisa para uma coluna (Visual Database Tools) | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- search criteria [SQL Server], multiple conditions
- multiple search conditions
- search conditions [SQL Server], multiple
- OR operator
- AND, Criteria pane
ms.assetid: 2c006e36-56b1-4992-89b4-c6c0b19808f3
caps.latest.revision: 3
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: a7b140acf1b00f31df0d8c948cdeca8ff6703726
ms.contentlocale: pt-br
ms.lasthandoff: 04/11/2017

---
# <a name="specify-multiple-search-conditions-for-one-column-visual-database-tools"></a>Especificar várias condições de pesquisa para uma coluna (Visual Database Tools)
Em algumas instâncias, você pode querer aplicar vários critérios de pesquisa à mesma coluna de dados. Por exemplo, você pode querer:  
  
-   Pesquisar vários nomes diferentes em uma tabela `employee` ou funcionários que estejam em faixas salariais diferentes. Esse tipo de pesquisa requer um critério OR.  
  
-   Pesquisar o título de um livro que começa com a palavra “O” e tenha a palavra “Cozinheiro”. Esse tipo de pesquisa requer um critério AND.  
  
> [!NOTE]  
> As informações neste tópico se aplicam a critérios de pesquisa nas cláusulas WHERE e HAVING de uma consulta. Os exemplos se concentram em como criar cláusulas WHERE, mas os princípios se aplicam a ambos os tipos de critérios de pesquisa.  
  
Para pesquisar valores alternativos na mesma coluna de dados, você deve especificar um critério OR. Para pesquisar valores que atendem a diversos critérios, você deve especificar um critério AND.  
  
## <a name="specifying-an-or-condition"></a>Especificando um critério OR  
O uso de um critério OR permite que você especifique vários valores alternativos a serem pesquisados em uma coluna. Essa opção expande o escopo da pesquisa e pode retornar mais linhas que a pesquisa de um único valor.  
  
> [!TIP]  
> Geralmente, você pode usar o operador IN em vez de pesquisar vários valores na mesma coluna de dados.  
  
#### <a name="to-specify-an-or-condition"></a>Para especificar um critério OR  
  
1.  No [Painel Critérios](../../ssms/visual-db-tools/criteria-pane-visual-database-tools.md), adicione a coluna a ser pesquisada.  
  
2.  Na coluna **Filtro** da coluna de dados adicionada, especifique o primeiro critério.  
  
3.  Na coluna **Ou...** da mesma coluna de dados, especifique o segundo critério.  
  
O Designer de Consulta e Exibição cria uma cláusula WHERE que contém um critério OR, como o seguinte:  
  
```  
SELECT fname, lname  
FROM employees  
WHERE (salary < 30000) OR (salary > 100000)  
```  
  
## <a name="specifying-an-and-condition"></a>Especificando um critério AND  
O uso do critério AND permite que você especifique que os valores em uma coluna devem atender a dois (ou mais) critérios para a linha a ser incluída no conjunto de resultados. Essa opção restringe o escopo da pesquisa e geralmente retorna menos linhas que a pesquisa de um único valor.  
  
> [!TIP]  
> Se você estiver procurando um intervalo de valores, poderá usar o operador BETWEEN em vez de vincular dois critérios com AND.  
  
#### <a name="to-specify-an-and-condition"></a>Para especificar um critério AND  
  
1.  No painel Critérios, adicione a coluna a ser pesquisada.  
  
2.  Na coluna **Filtro** da coluna de dados adicionada, especifique o primeiro critério.  
  
3.  Adicione a mesma coluna de dados no painel Critérios novamente, colocando-a em uma linha vazia da grade.  
  
4.  Na coluna **Filtro** da segunda instância da coluna de dados, especifique o segundo critério.  
  
O Designer de Consulta e Exibição cria uma cláusula WHERE que contém um critério AND, como o seguinte:  
  
```  
SELECT title_id, title  
FROM titles  
WHERE (title LIKE '%Cook%') AND   
  (title LIKE '%Recipe%')  
```  
  
## <a name="see-also"></a>Consulte também  
[Convenções para combinar critérios de pesquisa no painel Critérios &amp;#40;Visual Database Tools&amp;#41;](../../ssms/visual-db-tools/conventions-combine-search-conditions-in-criteria-pane-visual-db-tools.md)  
[Especificar critérios de pesquisa &amp;#40;Visual Database Tools&amp;#41;](../../ssms/visual-db-tools/specify-search-criteria-visual-database-tools.md)  
  
