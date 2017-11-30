---
title: sys.DM io_cluster_shared_drives (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, pdw
ms.service: 
ms.component: dmv's
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.dm_io_cluster_shared_drives_TSQL
- sys.dm_io_cluster_shared_drives
- dm_io_cluster_shared_drives_TSQL
- dm_io_cluster_shared_drives
dev_langs: TSQL
helpviewer_keywords: sys.dm_io_cluster_shared_drives dynamic management view
ms.assetid: c8fcced8-c780-49dc-99bd-6beb3ca532c4
caps.latest.revision: "30"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 66e4e1de40aee22313bd8950986079e176f5278d
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="sysdmioclustershareddrives-transact-sql"></a>sys.dm_io_cluster_shared_drives (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-pdw-md.md)]

  Esta exibição retornará o nome da unidade de cada unidade compartilhada se a instância de servidor atual for um servidor clusterizado. Se a instância de servidor atual não for uma instância clusterizada, ela retornará um conjunto de linhas vazio.  
  
> [!NOTE]  
>  Para chamar essa de [!INCLUDE[ssPDW](../../includes/sspdw-md.md)], use o nome **sys.dm_pdw_nodes_io_cluster_shared_drives**.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**Nome da unidade**|**nchar(2)**|O nome da unidade (a letra da unidade) que representa um disco individual que faz parte da matriz de disco compartilhado de cluster. A coluna não é anulável.|  
|**pdw_node_id**|**int**|**Aplica-se a**: ssPDW<br /><br /> O identificador para o nó que essa distribuição é no.|  
  
## <a name="remarks"></a>Comentários  
 Quando a clusterização é habilitada, a instância de cluster de failover requer que os arquivos de dados e de log estejam em discos compartilhados para que possam ser acessados depois que a instância falhar em outro nó. Cada linha nessa exibição representa um único disco compartilhado que é usado por essa instância clusterizada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Somente os discos listados por essa exibição podem ser usados para armazenar dados ou arquivos de log para essa instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Os discos listados nessa exibição são aqueles que estão no grupo de recursos de cluster associados à instância.  
  
> [!NOTE]  
>  Essa exibição seja substituída em uma versão futura. Recomendamos que você use [sys.DM io_cluster_valid_path_names &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-io-cluster-valid-path-names-transact-sql.md) em vez disso.  
  
## <a name="permissions"></a>Permissões  
 O usuário deve ter a permissão VIEW SERVER STATE para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir usa sys.dm_io_cluster_shared_drives para determinar as unidades compartilhadas em uma instância de servidor clusterizado:  
  
```  
SELECT * FROM sys.dm_io_cluster_shared_drives;  
```  
  
 Este é o conjunto de resultados:  
  
 DriveName  
  
 --------\-  
  
 m  
  
 n  
  
## <a name="see-also"></a>Consulte também  
 [sys.DM io_cluster_valid_path_names &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-io-cluster-valid-path-names-transact-sql.md)   
 [sys.DM os_cluster_nodes &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-cluster-nodes-transact-sql.md)   
 [sys.fn_servershareddrives &#40; Transact-SQL &#41;](../../relational-databases/system-functions/sys-fn-servershareddrives-transact-sql.md)   
 [Exibições e funções de gerenciamento dinâmico &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)  
  
  