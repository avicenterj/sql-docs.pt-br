---
title: catalog.environment (Banco de Dados SSISDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: ''
ms.topic: language-reference
ms.assetid: 7014c0e3-65dc-4a46-842e-4decf3737748
caps.latest.revision: 16
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 55122a93fe990445285ace9f7c73eac2109bdc9e
ms.sourcegitcommit: de5e726db2f287bb32b7910831a0c4649ccf3c4c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2018
ms.locfileid: "35329880"
---
# <a name="catalogenvironments-ssisdb-database"></a>catalog.environments (Banco de Dados SSISDB)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Exibe os detalhes de ambiente para todos os ambientes no catálogo do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]. Os ambientes contêm variáveis que podem ser referenciadas por projetos do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
|Nome da coluna|Tipo de dados|Descrição|  
|-----------------|---------------|-----------------|  
|environment_id|**bigint**|O ID (identificador exclusivo) do ambiente.|  
|NAME|**sysname**|O nome do ambiente.|  
|folder_id|**bigint**|O ID exclusivo da pasta na qual o ambiente reside.|  
|descrição|**nvarchar(1024)**|A descrição do ambiente. Esse valor é opcional.|  
|created_by_sid|**varbinary(85)**|O SID (identificador de segurança) do usuário que criou o ambiente.|  
|created_by_name|**nvarchar(128)**|O nome de usuário que criou o ambiente.|  
|created_time|**datetimeoffset**|A data e hora em que o ambiente foi criado.|  
  
## <a name="remarks"></a>Remarks  
 Essa exibição mostra uma linha para cada ambiente no catálogo. Nomes de ambiente somente são exclusivos em relação à pasta na qual estão localizados. Por exemplo, um ambiente denominado `E1` pode existir em mais de uma pasta no catálogo, mas cada pasta pode ter apenas um ambiente denominado `E1`.  
  
## <a name="permissions"></a>Permissões  
 Esta exibição requer uma das seguintes permissões:  
  
-   Permissão READ no ambiente  
  
-   Associação à função de banco de dados **ssis_admin**  
  
-   Associação à função de servidor **sysadmin**  
  
> [!NOTE]  
>  A segurança em nível de linha é imposta; somente as linhas para as quais você tem permissão de exibição são exibidas.  
  
  
