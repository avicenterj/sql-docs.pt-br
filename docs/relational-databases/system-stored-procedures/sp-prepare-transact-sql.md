---
title: sp_prepare (Transact SQL) | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2018
ms.prod: sql
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_cursor_prepare_TSQL
- sp_cursor_prepare
dev_langs:
- TSQL
helpviewer_keywords:
- sp_prepare
ms.assetid: f328c9eb-8211-4863-bafa-347e1bf7bb3f
caps.latest.revision: 9
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: '>=aps-pdw-2016||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: c8076964472d973ab1ed76c92afc8f13477e4f44
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43065035"
---
# <a name="spprepare-transact-sql"></a>sp_prepare (Transact SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

  Prepara um parametrizada [!INCLUDE[tsql](../../includes/tsql-md.md)] instrução e retorna uma instrução *manipular* para execução. sp_prepare é invocado pela especificação de ID = 11 em um pacote do protocolo TDS.  
  
 ![Ícone do link do artigo](../../database-engine/configure-windows/media/topic-link.gif "Ícone do link do tópico") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_prepare handle OUTPUT, params, stmt, options  
```  
  
## <a name="arguments"></a>Argumentos  
 *Identificador*  
 É gerado um SQL Server *identificador preparado* identificador. *manipular* é um parâmetro obrigatório com um **int** valor de retorno.  
  
 *params*  
 Identifica instruções parametrizadas. O *params* definição de variáveis é substituída para marcadores de parâmetro na instrução. *params* é um parâmetro obrigatório que chama uma **ntext**, **nchar**, ou **nvarchar** valor de entrada. Insira um valor NULL se a instrução não for parametrizada.  
  
 *stmt*  
 Define o conjunto de resultados do cursor. O *stmt* parâmetro é obrigatório e chamadas para um **ntext**, **nchar**, ou **nvarchar** valor de entrada.  
  
 *Opções*  
 Um parâmetro opcional que retorna uma descrição das colunas do conjunto de resultados de cursor. *opções* requer o seguinte valor de entrada de int:  
  
|Valor|Description|  
|-----------|-----------------|  
|0x0001|RETURN_METADATA|  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir prepara e executa uma instrução simples.  
  
```  
Declare @P1 int;  
Exec sp_prepare @P1 output,   
    N'@P1 nvarchar(128), @P2 nvarchar(100)',  
    N'SELECT database_id, name FROM sys.databases WHERE name=@P1 AND state_desc = @P2';  
Exec sp_execute @P1, N'tempdb', N'ONLINE';  
EXEC sp_unprepare @P1;  
```  

  
## <a name="see-also"></a>Consulte também  
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  

