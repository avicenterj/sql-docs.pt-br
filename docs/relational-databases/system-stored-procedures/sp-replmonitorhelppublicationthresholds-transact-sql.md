---
title: sp_replmonitorhelppublicationthresholds (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sp_replmonitorhelppublicationthresholds
- sp_replmonitorhelppublicationthresholds_TSQL
helpviewer_keywords:
- sp_replmonitorhelppublicationthresholds
ms.assetid: d6b1aa4b-3369-4255-a892-c0e5cc9cb693
caps.latest.revision: 21
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: d87de8d4ab74bc5c9d776b9d08e9e0680e2530cd
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43032234"
---
# <a name="spreplmonitorhelppublicationthresholds-transact-sql"></a>sp_replmonitorhelppublicationthresholds (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retorna a métrica de limite definida para uma publicação monitorada. Esse procedimento armazenado, usado para monitorar a replicação, é executado no Distribuidor, no banco de dados de distribuição.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_replmonitorhelppublicationthresholds [ @publisher = ] 'publisher'  
        , [ @publisher_db = ] 'publisher_db'  
        , [ @publication = ] 'publication'   
    [ , [ @publication_type = ] publication_type ]   
    [ , [ @thresholdmetricname = ] 'thresholdmetricname'  
```  
  
## <a name="arguments"></a>Argumentos  
 [ **@publisher**=] **'***publisher***'**  
 É o nome do Publicador. *Publisher* está **sysname**, sem padrão.  
  
 [ **@publisher_db**=] **'***publisher_db***'**  
 É o nome do banco de dados publicado. *publisher_db* está **sysname**, sem padrão.  
  
 [ **@publication**=] **'***publicação***'**  
 É o nome da publicação. *publicação* está **sysname**, sem padrão.  
  
 [ **@publication_type**=] *publication_type*  
 Se o tipo de publicação. *publication_type* está **int**, e pode ser um destes valores.  
  
|Valor|Description|  
|-----------|-----------------|  
|**0**|Publicação transacional.|  
|**1**|Publicação de instantâneo.|  
|**2**|Publicação de mesclagem.|  
|NULL (padrão)|A replicação tenta determinar o tipo de publicação.|  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**metric_id**|**int**|ID da métrica de desempenho de replicação, que pode ter um destes valores.<br /><br /> **1expiration** -monitora a expiração iminente de assinaturas para publicações transacionais.<br /><br /> **2latency** -monitora o desempenho de assinaturas para publicações transacionais.<br /><br /> **4mergeexpiration** -monitora a expiração iminente de assinaturas para publicações de mesclagem.<br /><br /> **5mergeslowrunduration** -monitora a duração de sincronizações de mesclagem em conexões de baixa largura de banda (discadas).<br /><br /> **6mergefastrunduration** -monitora a duração de sincronizações de mesclagem em conexões de alta largura de banda (LAN).<br /><br /> **7mergefastrunspeed** -monitora a taxa de sincronizações de mesclagem em conexões de alta largura de banda (LAN).<br /><br /> **8mergeslowrunspeed** -monitora a taxa de sincronizações de mesclagem em conexões de baixa largura de banda (discadas).|  
|**title**|**sysname**|Nome da métrica de desempenho da replicação.|  
|**value**|**int**|O valor de limite da métrica de desempenho.|  
|**shouldalert**|**bit**|É se um alerta deve ser gerado quando a métrica excede o limite definido para esta publicação; um valor de **1** indica que um alerta deve ser gerado.|  
|**IsEnabled**|**bit**|É se o monitoramento está habilitado para esta métrica de desempenho de replicação para esta publicação; um valor de **1** indica que o monitoramento está habilitado.|  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Remarks  
 **sp_replmonitorhelppublicationthresholds** é usado com todos os tipos de replicação.  
  
## <a name="permissions"></a>Permissões  
 Somente os membros dos **db_owner** ou **replmonitor** banco de dados fixa no banco de dados de distribuição podem executar **sp_replmonitorhelppublicationthresholds**.  
  
## <a name="see-also"></a>Consulte também  
 [Monitorar programaticamente a replicação](../../relational-databases/replication/monitor/programmatically-monitor-replication.md)  
  
  
