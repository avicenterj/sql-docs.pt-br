---
title: cdc_jobs (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-tables
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- cdc_jobs
- cdc_jobs_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- dbo.cdc_jobs
ms.assetid: 85e2d580-1c54-4b81-b7e6-2e12997199fd
caps.latest.revision: 17
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 55bbf5390a79f762c7e247c65c38e58a4bdb35de
ms.sourcegitcommit: a431ca21eac82117492d7b84c398ddb3fced53cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39103484"
---
# <a name="dbocdcjobs-transact-sql"></a>dbo.cdc_jobs (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Armazena os parâmetros de configuração do Change Data Capture para trabalhos de captura e limpeza. Essa tabela é armazenada no **msdb**.  
  
 
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**database_id**|**int**|ID do banco de dados no qual o trabalho está em execução.|  
|**job_type**|**nvarchar(20)**|O tipo de trabalho, 'captura' ou 'limpeza'.|  
|**job_id**|**uniqueidentifier**|ID exclusivo associado ao trabalho.|  
|**maxtrans**|**int**|O número máximo de transações a serem processadas em cada ciclo de verificação.<br /><br /> **maxtrans** é válido somente para trabalhos de captura.|  
|**maxscans**|**int**|O número máximo de ciclos de exame a executar para extrair todas as linhas do log.  <br /><br /> **maxscans** é válido somente para trabalhos de captura.|  
|**contínua**|**bit**|Um sinalizador que indica se o trabalho de captura deve ser executado continuamente (1) ou de uma só vez (0). Para obter mais informações, consulte [sys. sp_cdc_add_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-add-job-transact-sql.md).<br /><br /> **contínua** é válido somente para trabalhos de captura.|  
|**pollinginterval**|**bigint**|O número de segundos entre ciclos de exame de log.<br /><br /> **pollinginterval** é válido somente para trabalhos de captura.|  
|**retention**|**bigint**|O número de minutos que as linhas de alteração serão retidas em tabelas de alteração.<br /><br /> **retenção** é válido somente para trabalhos de limpeza.|  
|**threshold**|**bigint**|O número máximo de entradas de exclusão que podem ser excluídas usando uma única instrução na limpeza.|  
  
## <a name="see-also"></a>Consulte também  
 [sys. sp_cdc_add_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-add-job-transact-sql.md)   
 [sp_cdc_change_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-change-job-transact-sql.md)   
 [sp_cdc_help_jobs &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-help-jobs-transact-sql.md)   
 [sp_cdc_drop_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-drop-job-transact-sql.md)  
  
  
