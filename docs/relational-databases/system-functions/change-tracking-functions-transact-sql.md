---
title: Funções (Transact-SQL) de controle de alterações | Microsoft Docs
ms.custom: ''
ms.date: 08/08/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: system-functions
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- functions [SQL Server], change tracking
- change tracking [SQL Server], functions
ms.assetid: 04eb53c4-8b69-414e-9696-185d227fea35
caps.latest.revision: 10
author: rothja
ms.author: jroth
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 51b3ce0d29aaf8a868396563caba1062bc7be4ad
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43074448"
---
# <a name="change-tracking-functions-transact-sql"></a>Funções de controle de alterações (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Os registros de controle de alterações inserem, atualizam e excluem atividades aplicadas a tabelas controladas, fornecendo detalhes das alterações em um formato relacional facilmente consumido. As seguintes funções retornam informações sobre as alterações.  
  
|Função|Description|  
|--------------|-----------------|  
|[FUNÇÃO CHANGETABLE (CHANGES.)](../../relational-databases/system-functions/changetable-transact-sql.md)|Retorna informações de controle de todas as alterações efetuadas em uma tabela desde uma versão especificada.|  
|[CHANGETABLE (VERSION)](../../relational-databases/system-functions/changetable-transact-sql.md)|Retorna as informações de controle de alterações mais recentes de uma linha especificada.|  
|[CHANGE_TRACKING_MIN_VALID_VERSION()](../../relational-databases/system-functions/change-tracking-min-valid-version-transact-sql.md)|Retorna a versão mínima válida para usar na obtenção de informações controle de alterações da tabela especificada quando você estiver usando o [CHANGETABLE](../../relational-databases/system-functions/changetable-transact-sql.md) função.|  
|[CHANGE_TRACKING_CURRENT_VERSION](../../relational-databases/system-functions/change-tracking-current-version-transact-sql.md)|Obtém uma versão que está associada à última transação confirmada. Você pode usar esta versão da próxima vez que enumerar as alterações usando CHANGETABLE.|  
|[CHANGE_TRACKING_IS_COLUMN_IN_MASK](../../relational-databases/system-functions/change-tracking-is-column-in-mask-transact-sql.md)|Interpreta o valor SYS_CHANGE_COLUMNS retornado pela função CHANGETABLE (CHANGES ...).|  
|[WITH CHANGE_TRACKING_CONTEXT](../../relational-databases/system-functions/with-change-tracking-context-transact-sql.md)|Habilita a especificação de um contexto de alteração, como um ID do originador, quando um aplicativo altera os dados.|  
  
## <a name="see-also"></a>Consulte também  
 [Controle de alterações de dados &#40;SQL Server&#41;](../../relational-databases/track-changes/track-data-changes-sql-server.md)  
  
  
