---
title: MSSQLSERVER_2570 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- 2570 (Database Engine error)
ms.assetid: 29800aa9-81aa-4371-992c-487dbb617f46
caps.latest.revision: 20
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 9aff7469725314ec0e8f2c4a4eb41a12ac53b367
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37428815"
---
# <a name="mssqlserver2570"></a>MSSQLSERVER_2570
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|2570|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|DBCC_COLUMN_VALUE_OUT_OF_RANGE|  
|Texto da mensagem|Página P_ID, slot S_ID na ID de objeto O_ID, ID de índice I_ID, ID de partição PN_ID, ID de unidade de alocação A_ID (tipo TYPE). O valor de coluna COLUMN_NAME está fora do intervalo para tipo de dados "DATATYPE". Atualize a coluna para um valor válido.|  
  
## <a name="explanation"></a>Explicação  
 O valor de coluna contido na coluna especificada está fora do intervalo de valores possíveis para o tipo de dados da coluna.  
  
## <a name="user-action"></a>Ação do usuário  
 O erro não é reparável. Atualize a coluna com um valor que esteja dentro do intervalo para o tipo de dados da coluna e execute o comando novamente.  Para obter mais informações, consulte o artigo [923247](http://support.microsoft.com/kb/923247) da Base de Dados de Conhecimento.  
  
## <a name="see-also"></a>Consulte também  
 [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql)   
 [Tipos de dados &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
