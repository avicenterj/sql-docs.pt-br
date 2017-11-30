---
title: sys.DM exec_query_optimizer_info (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- dm_exec_query_optimizer_info_TSQL
- dm_exec_query_optimizer_info
- sys.dm_exec_query_optimizer_info_TSQL
- sys.dm_exec_query_optimizer_info
dev_langs: TSQL
helpviewer_keywords: sys.dm_exec_query_optimizer_info dynamic management view
ms.assetid: 1d72cef1-22d8-4ae0-91db-6694fe918c9e
caps.latest.revision: "30"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 5d954f21d2cfe9a99701f81a9439c9b4a82bd30a
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmexecqueryoptimizerinfo-transact-sql"></a>sys.dm_exec_query_optimizer_info (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Retorna estatísticas detalhadas sobre a operação do otimizador de consulta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Você pode usar esta exibição ao ajustar uma carga de trabalho para identificar problemas ou melhorias na otimização de consulta. Por exemplo, você pode usar o número total de otimizações, o valor de tempo decorrido e o valor de custo final para comparar as otimizações de consulta de carga de trabalho atual e quaisquer mudanças observadas durante o processo de ajuste. Alguns contadores fornecem dados que são relevantes apenas para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uso do diagnóstico interno. Esses contadores são marcados como "Somente interno”.  
  
> [!NOTE]  
>  Para chamar essa de [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] ou [!INCLUDE[ssPDW](../../includes/sspdw-md.md)], use o nome **sys.dm_pdw_nodes_exec_query_optimizer_info**.  
  
|Nome|Tipo de dados|Description|  
|----------|---------------|-----------------|  
|**contador**|**nvarchar(4000)**|Nome do evento de estatísticas do otimizador.|  
|**ocorrência**|**bigint**|Número de ocorrências do evento de otimização para este contador.|  
|**valor**|**float**|Valor de propriedade médio por ocorrência de evento.|  
|**pdw_node_id**|**int**|**Aplica-se a**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)],[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> O identificador para o nó que essa distribuição é no.|  
  
## <a name="permissions"></a>Permissões  
 Em [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requer a permissão VIEW SERVER STATE no servidor.  
  
 Em [!INCLUDE[ssSDS](../../includes/sssds-md.md)] camadas Premium requer a permissão VIEW DATABASE STATE no banco de dados. Em [!INCLUDE[ssSDS](../../includes/sssds-md.md)] camadas Standard e Basic requer o [!INCLUDE[ssSDS](../../includes/sssds-md.md)] conta de administrador.  
  
## <a name="remarks"></a>Comentários  
 **sys.DM exec_query_optimizer_info** contém as seguintes propriedades (contadores). Todos os valores de ocorrência são cumulativos, e são definidos em 0 na reinicialização de sistema. Todos os valores dos campos de valores são definidos em NULL, na reinicialização de sistema. Todos os valores da coluna de valor especificam um uso médio do valor de ocorrência da mesma linha como o denominador no cálculo da média. Todas as otimizações de consulta são avaliados quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] determina mudanças em **dm_exec_query_optimizer_info**, incluindo as duas consultas geradas pelo usuário e ao sistema. Execução de um plano já armazenado em cache não altera valores em **dm_exec_query_optimizer_info**, só otimizações são significantes.  
  
|Contador|Ocorrência|Valor|  
|-------------|----------------|-----------|  
|otimizações|Número total de otimizações.|Não aplicável|  
|tempo decorrido|Número total de otimizações.|Tempo médio decorrido por otimização de uma instrução individual (consulta), em segundos.|  
|custo final|Número total de otimizações.|Custo estimado médio para um plano otimizado em unidades de custo interno.|  
|plano trivial|Somente interno|Somente interno|  
|tarefas|Somente interno|Somente interno|  
|nenhum plano|Somente interno|Somente interno|  
|pesquisar 0|Somente interno|Somente interno|  
|pesquisar 0 vez|Somente interno|Somente interno|  
|pesquisar 0 tarefa|Somente interno|Somente interno|  
|pesquisar 1|Somente interno|Somente interno|  
|pesquisar 1 vez|Somente interno|Somente interno|  
|pesquisar 1 tarefa|Somente interno|Somente interno|  
|pesquisa 2|Somente interno|Somente interno|  
|pesquisar 2 vezes|Somente interno|Somente interno|  
|pesquisar 2 tarefas|Somente interno|Somente interno|  
|estágio de ganho 0 para estágio 1|Somente interno|Somente interno|  
|estágio de ganho 1 para estágio 2|Somente interno|Somente interno|  
|tempo limite|Somente interno|Somente interno|  
|limite de memória excedido|Somente interno|Somente interno|  
|insert stmt|Número de otimizações existentes para instruções INSERT.|Não aplicável|  
|delete stmt|Número de otimizações existentes para instruções DELETE.|Não aplicável|  
|update stmt|Número de otimizações existentes para instruções UPDATE.|Não aplicável|  
|contém subconsulta|Número de otimizações para uma consulta que contém ao menos uma subconsulta.|Não aplicável|  
|unnest falhou|Somente interno|Somente interno|  
|tabelas|Número total de otimizações.|Calcule o número médio de tabelas referenciadas por consulta otimizada.|  
|dicas|Número de vezes que alguma dica foi especificada. Dicas contadas incluem: dicas de consulta JOIN, GROUP, UNION e FORCE ORDER, a opção definida FORCE PLAN e dicas de associação.|Não aplicável|  
|dica order|Número de vezes que dica de ordem de força foi especificada.|Não aplicável|  
|dica de associação|Número de vezes que o algoritmo de junção foi forçado por uma dica de associação.|Não aplicável|  
|exibir referência|Número de vezes que uma exibição foi referenciada em uma consulta.|Não aplicável|  
|consulta remota|Número de otimizações em que a consulta referencia ao menos uma fonte de dados remota, como uma tabela com um nome de quatro partes ou um resultado OPENROWSET.|Não aplicável|  
|DOP máximo|Número total de otimizações.|Valor efetivo médio MAXDOP para um plano otimizado. Por padrão, MAXDOP efetivo é determinado pelo **grau máximo de paralelismo** configuração do servidor de opção e pode ser substituído para uma consulta específica pelo valor da dica de consulta MAXDOP.|  
|nível máximo de recursão|Número de otimizações em que um nível MAXRECURSION maior que 0 foi especificado com a dica de consulta.|Nível MAXRECURSION médio em otimizações onde um nível máximo de recursão especificado com a dica de consulta.|  
|exibições indexadas carregadas|Somente interno|Somente interno|  
|exibições indexadas correspondentes|Número de otimizações em que uma ou mais exibições indexadas foram correspondidas.|Número médio de exibições correspondentes.|  
|exibições indexadas usadas|Número de otimizações em que uma ou mais exibições indexadas são usadas no plano de saída depois de correspondidas.|Número médio de exibições usadas.|  
|exibições indexadas atualizadas|Número de otimizações de uma instrução DML que produzem um plano que mantém uma ou mais exibições indexadas.|Número médio de exibições mantidas.|  
|solicitação de cursor dinâmico|Número de otimizações em que uma solicitação de cursor dinâmico foi especificada.|Não aplicável|  
|solicitação de cursor de avanço rápido|Número de otimizações em que uma solicitação de cursor de avanço rápido foi especificada.|Não aplicável|  
|merge stmt|Número de otimizações existentes para instruções MERGE.|Não aplicável|  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-viewing-statistics-on-optimizer-execution"></a>A. Exibindo estatísticas de execução do otimizador  
 Quais são as estatísticas de execução do otimizador atuais para esta instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]?  
  
```  
SELECT * FROM sys.dm_exec_query_optimizer_info;  
```  
  
### <a name="b-viewing-the-total-number-of-optimizations"></a>B. Exibindo o número total de otimizações  
 Quantas otimizações foram executadas?  
  
```  
SELECT occurrence AS Optimizations FROM sys.dm_exec_query_optimizer_info  
WHERE counter = 'optimizations';  
```  
  
### <a name="c-average-elapsed-time-per-optimization"></a>C. Tempo médio decorrido por otimização  
 Qual o tempo médio decorrido por otimização?  
  
```  
SELECT ISNULL(value,0.0) AS ElapsedTimePerOptimization  
FROM sys.dm_exec_query_optimizer_info WHERE counter = 'elapsed time';  
```  
  
### <a name="d-fraction-of-optimizations-that-involve-subqueries"></a>D. Fracionamento de otimizações que envolvem subconsultas  
 Que fração de consultas otimizadas continha uma subconsulta?  
  
```  
SELECT (SELECT CAST (occurrence AS float) FROM sys.dm_exec_query_optimizer_info WHERE counter = 'contains subquery') /  
       (SELECT CAST (occurrence AS float)   
        FROM sys.dm_exec_query_optimizer_info WHERE counter = 'optimizations')  
        AS ContainsSubqueryFraction;  
```  
  
## <a name="see-also"></a>Consulte também  
 [Exibições e funções de gerenciamento dinâmico &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Funções e exibições de gerenciamento dinâmico &#40; relacionadas à execução Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/execution-related-dynamic-management-views-and-functions-transact-sql.md)  
  
  

