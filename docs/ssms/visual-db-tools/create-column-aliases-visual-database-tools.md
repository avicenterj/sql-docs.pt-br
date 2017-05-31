---
title: Criar aliases de coluna (Visual Database Tools) | Microsoft Docs
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
- columns [SQL Server], aliases
- aliases [SQL Server], columns
ms.assetid: e2e1c166-8ea7-47a2-b6a7-e419bf0fa3bb
caps.latest.revision: 3
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: bbbf69c55fcd0225583c43b3b4ae4089cc2f40ea
ms.contentlocale: pt-br
ms.lasthandoff: 04/11/2017

---
# <a name="create-column-aliases-visual-database-tools"></a>Criar aliases de coluna (Visual Database Tools)
Você pode criar aliases para nomes de coluna para tornar mais fácil o trabalho com nomes de colunas, cálculos e valores de resumo. Por exemplo, você pode criar um alias de coluna para:  
  
-   Criar um nome de coluna, tal como "Total Amount", para uma expressão como `(quantity * unit_price)` ou para uma função de agregação.  
  
-   Criar um formulário resumido de um nome de coluna, como `"d_id"` para `"discounts.stor_id."`  
  
Após ter definido um alias de coluna, você pode usar o alias em uma consulta Select para especificar a saída de consulta.  
  
### <a name="to-create-a-column-alias"></a>Para criar um alias de coluna  
  
1.  No **Painel de Critérios**, localize a linha contendo a coluna de dados para a qual você quer criar um alias e, caso necessário, marque-a para saída. Se a coluna de dados já não estiver na grade, acrescente-a.  
  
2.  Na coluna **Alias** para aquela linha, insira o alias. O alias deve seguir todas as convenções de nomenclatura SQL. Se o nome de alias que você entrar contiver espaços, o Designer de Consulta e Visualização coloca delimitadores automaticamente ao redor dele.  
  
## <a name="see-also"></a>Consulte também  
[Adicionar colunas a consultas &amp;#40;Visual Database Tools&amp;#41;](../../ssms/visual-db-tools/add-columns-to-queries-visual-database-tools.md)  
[Classificar e agrupar resultados da consulta &amp;#40;Visual Database Tools&amp;#41;](../../ssms/visual-db-tools/sort-and-group-query-results-visual-database-tools.md)  
[Resumir resultados da consulta &amp;#40;Visual Database Tools&amp;#41;](../../ssms/visual-db-tools/summarize-query-results-visual-database-tools.md)  
[Executar operações básicas com consultas &amp;#40;Visual Database Tools&amp;#41;](../../ssms/visual-db-tools/perform-basic-operations-with-queries-visual-database-tools.md)  
  
