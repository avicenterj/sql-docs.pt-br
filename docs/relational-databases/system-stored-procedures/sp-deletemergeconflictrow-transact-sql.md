---
title: sp_deletemergeconflictrow (Transact-SQL) | Microsoft Docs
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
- sp_deletemergeconflictrow
- sp_deletemergeconflictrow_TSQL
helpviewer_keywords:
- sp_deletemergeconflictrow
ms.assetid: 64cf1186-28b8-4cd9-88f1-a7808a9c8d60
caps.latest.revision: 26
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: c4290c07ddb9e7f352c6fe6177205ce6add03ead
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43017389"
---
# <a name="spdeletemergeconflictrow-transact-sql"></a>sp_deletemergeconflictrow (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Exclui linhas de uma tabela de conflitos ou o [MSmerge_conflicts_info &#40;Transact-SQL&#41; ](../../relational-databases/system-tables/msmerge-conflicts-info-transact-sql.md) tabela. Esse procedimento armazenado é executado ao computador onde a tabela de conflitos é armazenada, em qualquer banco de dados.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_deletemergeconflictrow [ [ @conflict_table = ] 'conflict_table' ]  
    [ , [ @source_object = ] 'source_object' ]  
    { , [ @rowguid = ] 'rowguid'  
        , [ @origin_datasource = ] 'origin_datasource' ] }  
    [ , [ @drop_table_if_empty = ] 'drop_table_if_empty' ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@conflict_table=**] **'***conflict_table***'**  
 É o nome da tabela de conflito. *conflict_table* está **sysname**, com um padrão de **%**. Se o *conflict_table* é especificado como NULL ou **%**, o conflito é considerado como um conflito de exclusão e a correspondência de linhas *rowguid* e *origin_datasource* e *source_object* é excluído do [MSmerge_conflicts_info &#40;Transact-SQL&#41; ](../../relational-databases/system-tables/msmerge-conflicts-info-transact-sql.md) tabela.  
  
 [  **@source_object=**] **'***source_object***'**  
 É o nome da tabela de origem. *source_object* está **nvarchar(386)**, com um padrão NULL.  
  
 [  **@rowguid =**] **'***rowguid***'**  
 É o identificador de linha do conflito de exclusão. *ROWGUID* está **uniqueidentifier**, sem padrão.  
  
 [  **@origin_datasource=**] **'***origin_datasource***'**  
 É a origem do conflito. *origin_datasource* está **varchar(255)**, sem padrão.  
  
 [  **@drop_table_if_empty=**] **'***drop_table_if_empty***'**  
 É um sinalizador que indica que o *conflict_table* é removida se estiver vazia. *drop_table_if_empty* está **varchar(10)**, com um padrão de FALSE.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Remarks  
 **sp_deletemergeconflictrow** é usado em replicação de mesclagem.  
  
 [MSmerge_conflicts_info &#40;Transact-SQL&#41; ](../../relational-databases/system-tables/msmerge-conflicts-info-transact-sql.md) tabela é uma tabela do sistema e não é excluída do banco de dados, mesmo se ele estiver vazio.  
  
## <a name="permissions"></a>Permissões  
 Somente os membros dos **sysadmin** função de servidor fixa ou **db_owner** banco de dados fixa podem executar **sp_deletemergeconflictrow**.  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
