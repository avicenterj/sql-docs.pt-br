---
title: Classificar Linhas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.component: ssms-visual-db
ms.reviewer: ''
ms.suite: sql
ms.technology: ssms
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- sorting rows [SQL Server]
- sorting query results [SQL Server]
ms.assetid: 780ef467-f96e-4373-8235-6dacbedb05a2
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 34fbc35b427862e469e6f6b617f819c475495b16
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38040124"
---
# <a name="sort-rows-visual-database-tools"></a>Classificar linhas (Visual Database Tools)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
Você pode classificar linhas em um resultado de consulta. Isto é, você pode nomear uma coluna particular ou conjunto de colunas cujos valores determinam a classificação das linhas no conjunto de resultados.  
  
> [!NOTE]  
> A ordem de classificação é determinada em parte pela sequência de agrupamento da coluna. Você pode alterar a sequência de agrupamento na [Caixa de Diálogo de Agrupamento](../../ssms/visual-db-tools/collation-dialog-box-visual-database-tools.md).  
  
Existem vários modos onde você pode classificar resultados de consulta:  
  
-   **Você pode organizar linhas em ordem crescente ou decrescente** . Por padrão, o SQL usa colunas classificar por para organizar linhas em ordem crescente. Por exemplo, para organizar os títulos de livros por preço crescente, simplesmente classifique as linhas pela coluna de preço. O SQL resultante pode ter esta aparência:  
  
    ```  
    SELECT *  
    FROM titles  
    ORDER BY price  
    ```  
  
    Por outro lado, se você quiser organizar os títulos com os livros mais caros primeiro, você poderá especificar expressamente uma classificação de primeiro os mais caros. Isto é, você indica se as linhas de resultado devem ser organizadas pelos valores decrescentes da coluna de preço. O SQL resultante pode ter esta aparência:  
  
    ```  
    SELECT *  
    FROM titles  
    ORDER BY price DESC  
    ```  
  
-   **Você pode fazer a classificação por várias colunas** .   Por exemplo, você pode criar um conjunto de resultados com uma linha para cada autor, classificando primeiro por estado e, em seguida, por cidade. O SQL resultante pode ter esta aparência:  
  
    ```  
    SELECT *  
    FROM authors   
    ORDER BY state, city  
    ```  
  
-   **Você pode classificar por colunas que não aparecem no conjunto de resultados** .   Por exemplo, você pode criar um conjunto de resultados com os títulos mais caros primeiro, mesmo se os preços não aparecerem. O SQL resultante pode ter esta aparência:  
  
    ```  
    SELECT title_id, title  
    FROM titles  
    ORDER BY price DESC  
    ```  
  
-   **Você pode classificar por colunas derivadas** .   Por exemplo, você pode criar um conjunto de resultados onde cada linha contenha um título de livro – com os livros que pagam royalty mais alto por cópia aparecendo primeiro. O SQL resultante pode ter esta aparência:  
  
    ```  
    SELECT title, price * royalty / 100 as royalty_per_unit  
    FROM titles  
    ORDER BY royalty_per_unit DESC  
    ```  
  
    (A fórmula para calcular royalty que cada livro ganha por cópia está destacada.)  
  
    Para calcular uma coluna derivada, você pode usar sintaxe SQL, como no exemplo anterior, ou pode usar uma função definida pelo usuário que retorna um valor escalar. Para obter mais informações sobre funções definidas pelo usuário, consulte a documentação do SQL Server.  
  
-   **Você pode classificar linhas agrupadas** .   Por exemplo; você pode criar um conjunto de resultados onde cada linha descreve uma cidade, mais o número de autores naquela cidade – com as cidades contendo muitos autores que aparecem primeiro. O SQL resultante pode ter esta aparência:  
  
    ```  
    SELECT city, state, COUNT(*)  
    FROM authors  
    GROUP BY city, state  
    ORDER BY COUNT(*) DESC, state  
    ```  
  
    Observe que a consulta usa `state` como uma coluna de classificação secundária. Assim, se dois estados tiverem o mesmo número de autores, esses estados aparecerão em ordem alfabética.  
  
-   **Você pode classificar usando dados internacionais** .   Isto é, você pode classificar uma coluna usando convenções de exame que diferem das convenções padrão daquela coluna. Por exemplo, você pode escrever uma consulta que recupera todos os títulos de livro de Jaime Patiño. Para exibir os títulos em ordem alfabética, você usa uma sequência de exame espanhol para a coluna de título. O SQL resultante pode ter esta aparência:  
  
    ```  
    SELECT title  
    FROM   
        authors   
        INNER JOIN   
            titleauthor   
            ON authors.au_id   
            =  titleauthor.au_id   
            INNER JOIN  
                titles   
                ON titleauthor.title_id   
                =  titles.title_id   
    WHERE   
         au_fname = 'Jaime' AND   
         au_lname = 'Patiño'  
    ORDER BY   
         title COLLATE SQL_Spanish_Pref_CP1_CI_AS  
    ```  
  
## <a name="see-also"></a>Consulte Também  
[Classificar e agrupar resultados da consulta &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/sort-and-group-query-results-visual-database-tools.md)  
[Tópicos de instruções de como criar consultas e exibições &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
