---
title: MSSQLSERVER_3156 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- 3156 (Database Engine error)
ms.assetid: 345d8ed4-177e-4ec3-bab3-25d30000e323
caps.latest.revision: 12
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 3827aebb4acb40882d273609916df216be33f8e2
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37409785"
---
# <a name="mssqlserver3156"></a>MSSQLSERVER_3156
    
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|ID do evento|3156|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|LDDB_CANT_WRITE|  
|Texto da mensagem|O arquivo '%ls' não pode ser restaurado para '%ls'. Use WITH MOVE para identificar um local válido para o arquivo.|  
  
## <a name="explanation"></a>Explicação  
 Esta mensagem geral identifica os nomes de arquivo lógicos ou físicos dos arquivos que não puderam ser restaurados devido a um problema com o local especificado.  
  
### <a name="possible-causes"></a>Causas possíveis  
 As causas possíveis incluem as seguintes:  
  
-   Talvez seja preciso acessar o diretório especificado do Windows.  
  
-   Você pode ter digitado incorretamente o caminho ou pode ter especificado um caminho que não existe.  
  
-   O nome de arquivo pode estar sendo usado por um arquivo que não pode ser substituído.  
  
## <a name="user-action"></a>Ação do usuário  
 Veja nos logs de erros outras mensagens mais detalhadas.  
  
 Corrija o problema com o local especificado, por exemplo, concedendo acesso, ou use a opção WITH MOVE em sua instrução RESTORE para realocar o arquivo.  
  
## <a name="see-also"></a>Consulte também  
 [Restaurar um banco de dados em um novo local &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md)   
 [Restaurar arquivos para um novo local &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md)   
 [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
