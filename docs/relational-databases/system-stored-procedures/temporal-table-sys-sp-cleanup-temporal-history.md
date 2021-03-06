---
title: sys. sp_cleanup_temporal_history | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: ''
ms.prod_service: sql-database
ms.service: sql-database
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 6eff30b4-b261-4f1f-b93c-1f69d754298d
caps.latest.revision: 4
author: CarlRabeler
ms.author: carlrab
manager: craigg
monikerRange: = azuresqldb-current || = sqlallproducts-allversions
ms.openlocfilehash: 6216ca6584c2bf6d78bb66096145cd49428398dc
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38051191"
---
# <a name="sysspcleanuptemporalhistory-transact-sql"></a>sys. sp_cleanup_temporal_history (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md.md)]

 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Ícone de link do tópico") [Convenções de sintaxe de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  

Remove todas as linhas da tabela de histórico temporal que correspondem ao período HISTORY_RETENTION configurado em uma única transação.
  
## <a name="syntax"></a>Sintaxe  
```  
sp_cleanup_temporal_history [@schema_name = ] schema_name, [@table_name = ] table_name [, [@row_count=] @row_count_var [OUTPUT]]
```  
  
## <a name="arguments"></a>Argumentos  

*@table_name*

O nome da tabela temporal para qual a retenção de limpeza é invocada.

*schema_name*

O nome do esquema ao qual tabela temporal atual pertence a

*row_count_var* [saída]

O parâmetro de saída que retorna o número de linhas excluídas. Se a tabela de histórico com índice columnstore clusterizado, este parâmetro retornará sempre 0.
  
## <a name="remarks"></a>Remarks
Esse procedimento armazenado pode ser usado somente com tabelas temporais que o período de retenção finito especificados.
Use esse procedimento armazenado apenas se você precisar limpar imediatamente todas as linhas antigas da tabela de histórico. Você deve saber que ele pode ter um impacto significativo sobre o log de banco de dados e o subsistema de e/s como ele exclui todas as linhas qualificadas dentro da mesma transação. 

É recomendável sempre confiar em uma tarefa em segundo plano interno de limpeza que remove antigos linhas com o impacto mínimo sobre as cargas de trabalho regulares e o banco de dados em geral.

## <a name="permissions"></a>Permissões  
 Exige permissões db_owner.  

## <a name="example"></a>Exemplo

```
declare @rowcnt int
EXEC sys.sp_cleanup_temporal_history 'dbo', 'Department', @rowcnt output
select @rowcnt
```

## <a name="see-also"></a>Confira também

[Política de retenção de tabelas temporais](https://docs.microsoft.com/azure/sql-database/sql-database-temporal-tables-retention-policy)
