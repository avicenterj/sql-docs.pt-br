---
title: sys.DM tran_database_transactions (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 06/09/2017
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
- dm_tran_database_transactions
- sys.dm_tran_database_transactions_TSQL
- dm_tran_database_transactions_TSQL
- sys.dm_tran_database_transactions
dev_langs: TSQL
helpviewer_keywords: sys.dm_tran_database_transactions dynamic management view
ms.assetid: 82a44295-4cbc-4a5b-891a-8ebaf307b8f5
caps.latest.revision: "33"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 56421d77a4ca75f75f87667d6a52c42de4f817b6
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmtrandatabasetransactions-transact-sql"></a>sys.dm_tran_database_transactions (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Retorna informações sobre transações no nível do banco de dados.  
  
> [!NOTE]  
>  Para chamar esse DMV do [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] ou [!INCLUDE[ssPDW](../../includes/sspdw-md.md)], use o nome **sys.dm_pdw_nodes_tran_database_transactions**.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|transaction_id|**bigint**|ID da transação no nível da instância, e não no nível do banco de dados. Somente é exclusiva em todos os bancos de dados em uma instância, mas não em todas as instâncias de servidor.|  
|database_id|**int**|ID do banco de dados associado à transação.|  
|database_transaction_begin_time|**datetime**|Hora na qual o banco de dados foi envolvido na transação. Especificamente, é a hora do primeiro registro de log no banco de dados da transação.|  
|database_transaction_type|**int**|1 = Transação de leitura/gravação<br /><br /> 2 = Transação somente leitura<br /><br /> 3 = Transação de sistema|  
|database_transaction_state|**int**|1 = A transação não foi inicializada.<br /><br /> 3 = A transação foi inicializada mas não gerou registros de log.<br /><br /> 4 = A transação gerou registros de log.<br /><br /> 5 = A transação foi preparada.<br /><br /> 10 = A transação foi confirmada.<br /><br /> 11 = A transação foi revertida.<br /><br /> 12 = A transação está sendo confirmada. (O registro de log está sendo gerado, mas não foi materializado nem persistente.)|  
|database_transaction_status|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|database_transaction_status2|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|database_transaction_log_record_count|**bigint**|**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> Número de registros de log gerados no banco de dados para a transação.|  
|database_transaction_replicate_record_count|**int**|**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> Número de registros de log gerados no banco de dados para a transação que é replicada.|  
|database_transaction_log_bytes_used|**bigint**|**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> Número de bytes usados até o momento no log do banco de dados para a transação.|  
|database_transaction_log_bytes_reserved|**bigint**|**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> Número de bytes reservados para uso no log do banco de dados para a transação.|  
|database_transaction_log_bytes_used_system|**int**|**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> Número de bytes usados até o momento no log do banco de dados para as transações do sistema em nome da transação.|  
|database_transaction_log_bytes_reserved_system|**int**|**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> Número de bytes reservados para uso no log do banco de dados para as transações do sistema em nome da transação.|  
|database_transaction_begin_lsn|**numeric(25,0)**|**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> Número de sequência do log (LSN) do registro de início para a transação no log de banco de dados.|  
|database_transaction_last_lsn|**numeric(25,0)**|**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> LSN do registro de log mais recente para a transação no log de banco de dados.|  
|database_transaction_most_recent_savepoint_lsn|**numeric(25,0)**|**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> LSN do ponto de salvamento mais recente para a transação no log de banco de dados.|  
|database_transaction_commit_lsn|**numeric(25,0)**|**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> LSN do registro de log de confirmação para a transação no log de banco de dados.|  
|database_transaction_last_rollback_lsn|**numeric(25,0)**|**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> LSN que foi revertido mais recentemente. Se não tiver ocorrido reversão, o valor será MaxLSN.|  
|database_transaction_next_undo_lsn|**numeric(25,0)**|**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].<br /><br /> LSN do próximo registro a ser desfeito.|  
|pdw_node_id|**int**|**Aplica-se a**: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)],[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]<br /><br /> O identificador para o nó que essa distribuição é no.|  
  
## <a name="permissions"></a>Permissões  
Em [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)], requer `VIEW SERVER STATE` permissão.   
Em [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] camadas Premium, requer o `VIEW DATABASE STATE` no banco de dados. Em [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] camadas Standard e Basic, requer o **administrador do servidor** ou um **administrador do Active Directory do Azure** conta.  
 

  
## <a name="see-also"></a>Consulte também  
 [sys.DM tran_active_transactions &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-tran-active-transactions-transact-sql.md)   
 [sys.DM tran_session_transactions &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-tran-session-transactions-transact-sql.md)   
 [Exibições e funções de gerenciamento dinâmico &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Funções e exibições de gerenciamento dinâmico relacionadas à transação &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/transaction-related-dynamic-management-views-and-functions-transact-sql.md)  
  
  

