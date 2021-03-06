---
title: sp_add_notification (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 08/09/2016
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_add_notification_TSQL
- sp_add_notification
dev_langs:
- TSQL
helpviewer_keywords:
- sp_add_notification
ms.assetid: 0525e0a2-ed0b-4e69-8a4c-a9e3e3622fbd
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: d17936912a9adca46ddf64724401432c7ef9d43f
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43038286"
---
# <a name="spaddnotification-transact-sql"></a>sp_add_notification (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Configura uma notificação para um alerta.  
  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_add_notification [ @alert_name = ] 'alert' ,   
    [ @operator_name = ] 'operator' ,   
    [ @notification_method = ] notification_method  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@alert_name=** ] **'***alerta***'**  
 O alerta para esta notificação. *alerta* está **sysname**, sem padrão.  
  
 [  **@operator_name=** ] **'***operador***'**  
 O operador a ser notificado quando o alerta ocorrer. *operador* está **sysname**, sem padrão.  
  
 [  **@notification_method=** ] *notification_method*  
 O método através do qual o operador é notificado. *notification_method* está **tinyint**, sem padrão. *notification_method* pode ser um ou mais desses valores combinados com um **OR** operador lógico.  
  
|Valor|Description|  
|-----------|-----------------|  
|**1**|Email|  
|**2**|Pager|  
|**4**|**net send**|  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 None  
  
## <a name="remarks"></a>Remarks  
 **sp_add_notification** deve ser executado a partir de **msdb** banco de dados.  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] fornece um modo fácil e gráfico para gerenciar o sistema de alertas inteiro. Usar o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] é o modo recomendado de configuração de sua infraestrutura de alerta.  
  
 Para enviar uma notificação em resposta a um alerta, primeiro você deve configurar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para enviar email.  
  
 Se ocorrer uma falha ao enviar uma mensagem de email ou uma notificação de pager, a falha será relatada no log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.  
  
## <a name="permissions"></a>Permissões  
 Somente os membros dos **sysadmin** pode executar a função de servidor fixa **sp_add_notification**.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir adiciona uma notificação de email para o alerta especificado (`Test Alert`).  
  
> **Observação:** Este exemplo supõe que `Test Alert` já existe e que `François Ajenstat` é um nome de operador válido.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_add_notification  
 @alert_name = N'Test Alert',  
 @operator_name = N'François Ajenstat',  
 @notification_method = 1 ;  
GO  
```  
  
## <a name="see-also"></a>Confira também  
 [sp_delete_notification &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-delete-notification-transact-sql.md)   
 [sp_help_notification &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-help-notification-transact-sql.md)   
 [sp_update_notification &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-update-notification-transact-sql.md)   
 [sp_add_operator &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-add-operator-transact-sql.md)   
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
