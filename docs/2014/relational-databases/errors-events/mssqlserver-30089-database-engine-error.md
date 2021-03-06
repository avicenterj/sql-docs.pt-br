---
title: MSSQLSERVER_30089 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- 9992 (Database Engine error)
ms.assetid: 188e5bde-6865-4740-a2b2-582be8f55c77
caps.latest.revision: 16
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: dcb697263dee7f5fca3904dcda8434a46a91c056
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37425945"
---
# <a name="mssqlserver30089"></a>MSSQLSERVER_30089
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|30089|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|IFTS_FDHOST_TERMINATEDABNORMAL|  
|Texto da mensagem|O processo FDHost (host do daemon de filtro de texto completo) foi interrompido de maneira anormal. Isso poderá ocorrer se um componente linguístico configurado incorretamente ou que não está funcionando bem, como um separador de palavras, lematizador ou filtro, gerou um erro irrecuperável durante a indexação de texto completo ou no processamento de uma consulta. O processo será reiniciado automaticamente.|  
  
## <a name="explanation"></a>Explicação  
 O host do daemon de filtro de texto completo encontrou um problema que forçou seu encerramento de maneira anormal. A causa do problema pode ser um documento malformatado, um bug no filtro ou no separador de palavras ou um problema no daemon de filtro.  
  
## <a name="user-action"></a>Ação do usuário  
 Normalmente, o daemon se recupera do erro. Se ele apresentar falhas constantes, será necessário diagnosticar e solucionar o problema. Tente fazer o seguinte para isolar o problema:  
  
1.  Se um novo componente linguístico foi instalado recentemente, remova-o do sistema.  
  
2.  Consulte o log de rastreamento para identificar qualquer documento novo cuja indexação de texto completo tenha falhado e remova esse documento.  
  
## <a name="see-also"></a>Consulte também  
 [sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql)   
 [Configurar e gerenciar separadores de palavras e lematizadores de pesquisa](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md)   
 [Configurar e gerenciar filtros de pesquisa](../search/configure-and-manage-filters-for-search.md)  
  
  
