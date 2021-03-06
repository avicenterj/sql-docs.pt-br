---
title: sp_helpsrvrole (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/20/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_helpsrvrole_TSQL
- sp_helpsrvrole
dev_langs:
- TSQL
helpviewer_keywords:
- sp_helpsrvrole
ms.assetid: 5c7f39f3-c261-4f70-8beb-08242d4ac242
caps.latest.revision: 30
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 03da770b709c30d02ef785f747bde2d4c403b105
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43020751"
---
# <a name="sphelpsrvrole-transact-sql"></a>sp_helpsrvrole (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retorna uma lista de funções de servidor fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_helpsrvrole [ [ @srvrolename = ] 'role' ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@srvrolename=** ] **'***função***'**  
 É o nome da função de servidor fixa. *função* está **sysname**, com um padrão NULL. *função* pode ser um dos valores a seguir.  
  
|Função de servidor fixa|Description|  
|-----------------------|-----------------|  
|sysadmin|Administradores de sistema|  
|securityadmin|Administradores de segurança|  
|serveradmin|Administradores de servidor|  
|setupadmin|Administradores de configuração|  
|processadmin|Administradores de processo|  
|diskadmin|Administradores de disco|  
|dbcreator|Criadores de banco de dados|  
|bulkadmin|Pode executar instruções BULK INSERT|  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 0 (êxito) ou 1 (falha)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|ServerRole|**sysname**|Nome da função de servidor|  
|Description|**sysname**|Descrição do ServerRole|  
  
## <a name="remarks"></a>Remarks  
 As funções de servidor fixas são definidas no nível de servidor e possuem permissões para executar atividades administrativas específicas no nível de servidor. A funções de servidor fixas não podem ser adicionadas, removidas ou alteradas.  
  
 Para adicionar ou membros removidos das funções de servidor, consulte [ALTER SERVER ROLE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-server-role-transact-sql.md).  
  
 Todos os logons são membros do público. sp_helpsrvrole não reconhece a função pública porque, internamente, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não implementa pública como uma função.  
  
 sp_helpsrvrole não leva a uma função de servidor definida pelo usuário como um argumento. Para listar as funções de servidor definidas pelo usuário, consulte os exemplos na [ALTER SERVER ROLE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-server-role-transact-sql.md).  
  
## <a name="permissions"></a>Permissões  
 Requer associação à função public.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-listing-the-fixed-server-roles"></a>A. Listando as funções de servidor fixas  
 A consulta a seguir retorna a lista de funções de servidor fixas.  
  
```  
EXEC sp_helpsrvrole ;  
```  
  
### <a name="b-listing-fixed-and-user-defined-server-roles"></a>B. Listando as funções de servidor fixas e definidas pelo usuário  
 A consulta a seguir retorna uma lista de funções de servidor fixas e definidas pelo usuário.  
  
```  
SELECT * FROM sys.server_principals WHERE type = 'R' ;  
```  
  
### <a name="c-returning-a-description-of-a-fixed-server-role"></a>C. Retornando uma descrição de uma função de servidor fixa  
 A consulta a seguir retorna o nome e a descrição de funções de servidor fixas `diskadmin`.  
  
```  
sp_helpsrvrole 'diskadmin' ;  
```  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos de segurança armazenados &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/security-stored-procedures-transact-sql.md)   
 [Funções de nível de servidor](../../relational-databases/security/authentication-access/server-level-roles.md)   
 [sp_addsrvrolemember &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addsrvrolemember-transact-sql.md)   
 [sp_dropsrvrolemember &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dropsrvrolemember-transact-sql.md)   
 [sp_helpsrvrolemember &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helpsrvrolemember-transact-sql.md)   
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
