---
title: MSSQLSERVER_10521 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- 10521 (Database Engine error)
ms.assetid: ba2d7e44-207c-4428-b5f0-c975ac122c0d
caps.latest.revision: 10
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 18d823ff21a38c3eeee8df725c9a38172080d40e
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37421075"
---
# <a name="mssqlserver10521"></a>MSSQLSERVER_10521
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|10521|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|PG_PARAM_NEEDED|  
|Texto da mensagem|Não é possível criar guia de plano ' %. \*ls' porque `@type` foi especificado como '%ls' e o parâmetro '%ls' é NULL. Esse tipo requer um valor não NULL para o parâmetro. Especifique um valor não NULL para o parâmetro ou altere o tipo para um que permita um valor NULL para o parâmetro.|  
  
## <a name="explanation"></a>Explicação  
 O tipo especificado em `@type` requer um valor não NULL para o parâmetro especificado; entretanto, foi fornecido um valor NULL.  
  
## <a name="user-action"></a>Ação do usuário  
 Especifique um valor não NULL para o parâmetro ou altere o tipo para um que permita um valor NULL para o parâmetro.  
  
## <a name="see-also"></a>Consulte também  
 [sp_create_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-transact-sql)   
 [Guias de plano](../performance/plan-guides.md)   
 [sp_create_plan_guide_from_handle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-create-plan-guide-from-handle-transact-sql)  
  
  
