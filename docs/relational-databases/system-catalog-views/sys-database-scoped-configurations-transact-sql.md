---
title: database_scoped_configurations (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 05/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- database_scoped_configurations
- database_scoped_configurations_TSQL
- sys.database_scoped_configurations
- sys.database_scoped_configurations_TSQL
helpviewer_keywords:
- sys.database_scoped_configurations catalog view
ms.assetid: 8899310a-3464-4d38-9f2f-88396c4e7dc2
author: VanMSFT
ms.author: vanto
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: e127f8935b10003a1ecfbd70d7237c5911d7f34f
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43107237"
---
# <a name="sysdatabasescopedconfigurations-transact-sql"></a>sys.database_scoped_configurations (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  Contém uma linha por configuração. 
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**configuration_id**|**int**|ID da opção de configuração.|  
|**name**|**nvarchar(60)**|O nome da opção de configuração. Para obter informações sobre as configurações possíveis, consulte [ALTER DATABASE SCOPED CONFIGURATION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md).|  
|**value**|**sqlvariant**|O valor definido para essa opção de configuração para a réplica primária.|  
|**value_for_secondary**|**sqlvariant**|O valor definido para essa opção de configuração para as réplicas secundárias.|  
|**elevate_online**|**nvarchar(60)** |O banco de dados no escopo padrão definido para a opção online para operações de índice |
|**elevate_resumable**|nvarchar(60)|O banco de dados no escopo padrão definido para a opção retomável para operações de índice| 
  
##  <a name="Permissions"></a> Permissões  
 Requer associação à função **pública** .  
  
## <a name="remarks"></a>Remarks  
 Quando NULL é retornado como o valor para **value_for_secondary**, isso significa que o secundário é definido como primário.  
 
 As definições de configurações no escopo do banco de dados serão transferidas para o banco de dados. Isso significa que quando um determinado banco de dados é restaurado ou anexado, as definições de configuração existentes permanecem.
  
## <a name="see-also"></a>Consulte também  
 [ALTER DATABASE SCOPED CONFIGURATION &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-scoped-configuration-transact-sql.md)  
  
  
