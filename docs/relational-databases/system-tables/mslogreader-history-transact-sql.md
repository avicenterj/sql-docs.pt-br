---
title: MSlogreader_history (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-tables
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- MSlogreader_history_TSQL
- MSlogreader_history
dev_langs:
- TSQL
helpviewer_keywords:
- MSlogreader_history system table
ms.assetid: 2e399fa1-3591-4c1c-96b7-7964fe82c7c4
caps.latest.revision: 29
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: def5bc1d69a3d5332f96752fcd5e6b1eaedff08e
ms.sourcegitcommit: a431ca21eac82117492d7b84c398ddb3fced53cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39103094"
---
# <a name="mslogreaderhistory-transact-sql"></a>MSlogreader_history (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  O **MSlogreader_history** tabela contém linhas de histórico para o Log Reader Agents associados ao distribuidor local. Esta tabela é armazenada no banco de dados de distribuição.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**agent_id**|**int**|A ID do Log Reader Agent.|  
|**runstatus**|**int**|O status da execução:<br /><br /> 1 = Iniciar.<br /><br /> 2 = Êxito.<br /><br /> 3 = Em andamento.<br /><br /> 4 = Inativo.<br /><br /> 5 = Repetir.<br /><br /> 6 = Falha.|  
|**start_time**|**datetime**|A hora inicial de execução do trabalho.|  
|**time**|**datetime**|A hora de registro da mensagem.|  
|**duration**|**int**|A duração, em segundos, da sessão de mensagem.|  
|**Comentários**|**nvarchar(255)**|O texto da mensagem.|  
|**xact_seqno**|**varbinary(16)**|O último número de sequência da transação processado.|  
|**delivery_time**|**int**|A hora de entrega da primeira transação.|  
|**delivered_transactions**|**int**|O número total de transações entregues na sessão.|  
|**delivered_commands**|**int**|O número total de comandos entregues na sessão.|  
|**average_commands**|**int**|O número médio de comandos entregues na sessão.|  
|**delivery_rate**|**float**|A média de comandos entregues por segundo.|  
|**delivery_latency**|**int**|A latência entre o comando que insere o banco de dados publicado e sendo inserido no banco de dados de distribuição. Em milissegundos.|  
|**error_id**|**int**|A ID do erro na **MSrepl_error** tabela do sistema.|  
|**timestamp**|**timestamp**|A coluna de carimbo de data e hora dessa tabela.|  
|**updateable_row**|**bit**|Definido como **1** se a linha de histórico pode ser substituída.|  
  
## <a name="see-also"></a>Consulte também  
 [Tabelas de replicação &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Exibições de replicação &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
