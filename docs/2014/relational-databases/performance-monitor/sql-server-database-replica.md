---
title: SQL Server, Réplica de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], monitoring
- SQLServer:Database Replica
- performance counters [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], performance counters
ms.assetid: a5f6bdce-2b13-4924-aaeb-b50b57d624d8
caps.latest.revision: 25
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: ff7159adceda1953433b2869fd5d5e05a0b91b94
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37233106"
---
# <a name="sql-server-database-replica"></a>SQL Server, Réplica de Banco de Dados
  O objeto de desempenho **SQLServer:Database Replica** contém contadores de desempenho que relatam informações sobre os bancos de dados secundários na réplica secundária de um grupo de disponibilidade AlwaysOn no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]. Esse objeto só é válido em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda uma réplica secundária.  
  
|Nome do contador|Description|Exibir em...|  
|------------------|-----------------|--------------|  
|**Bytes de Arquivo Recebidos/s**|Quantidade de dados FILESTREAM recebida pela réplica secundária para o banco de dados secundário no último segundo.|Réplica secundária|  
|**Bytes de Log Recebidos/s**|Quantidade registros de log recebida pela réplica secundária para o banco de dados secundário no último segundo.|Réplica secundária|  
|**Log restante para desfazer**|A quantidade de log em quilobytes restante para a conclusão da fase desfazer.|Réplica secundária|  
|**Fila de Envio de Log**|Quantidade de registros de log nos arquivos de log do banco de dados primário, em quilobytes, que ainda não foram enviados à réplica secundária. Esse valor é enviado à réplica secundária da réplica primária. O tamanho da fila não inclui arquivos FILESTREAM enviados a um secundário.|Réplica secundária|  
|**Transação de Gravação Espelhada/s**|Número de transações que foram gravadas no banco de dados primário e depois aguardaram para confirmar até que o log fosse enviado para o banco de dados secundário, no último segundo.|Réplica primária|  
|**Fila de Recuperação**|Quantidade de registros de log nos arquivos de log da réplica secundária que ainda não foram refeitos.|Réplica secundária|  
|**Ações de refazer bloqueadas/s**|Número de vezes que o thread de restauração é bloqueado nos bloqueios mantidos por leitores do banco de dados.|Réplica secundária|  
|**Bytes de Restauração Restantes**|A quantidade de log em quilobytes a ser refeita para concluir a fase de reversão.|Réplica secundária|  
|**Bytes Refeitos/s**|Quantidade de registros de log refeitos no banco de dados secundário no último segundo.|Réplica secundária|  
|**Total de Log a ser desfeito**|Total de quilobytes de log que deve ser desfeito.|Réplica secundária|  
|**Atraso na Transação**|Atraso na espera por reconhecimento de confirmação não terminado, em milissegundos.|Réplica primária|  
  
## <a name="see-also"></a>Consulte também  
 [Monitorar o uso de recursos &#40;Monitor do Sistema&#41;](monitor-resource-usage-system-monitor.md)   
 [SQL Server, Réplica de Disponibilidade](sql-server-availability-replica.md)   
 [SQL Server, objeto Databases](sql-server-databases-object.md)   
 [Grupos de disponibilidade AlwaysOn (SQL Server)](../../database-engine/availability-groups/windows/always-on-availability-groups-sql-server.md)  
  
  
