---
title: Monitorar o uso de disco | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: performance-monitor
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- database monitoring [SQL Server], disk usage
- disks [SQL Server]
- monitoring performance [SQL Server], disk usage
- server performance [SQL Server], disk usage
- monitoring [SQL Server], disk activity
- excess paging [SQL Server]
- tuning databases [SQL Server], disk usage
- I/O [SQL Server], monitoring
- disks [SQL Server], monitoring activity
- isolating disk activity [SQL Server]
- database performance [SQL Server], disk usage
- monitoring server performance [SQL Server], disk usage
ms.assetid: 1525449c-ea7d-4222-b294-1ba1fe99c9ac
caps.latest.revision: 23
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: fc5271679852021cf2d18f7d567e13fa5f436c62
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32950681"
---
# <a name="monitor-disk-usage"></a>Monitorar o uso do disco
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  O Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa chamadas de E/S (entrada/saída) do sistema operacional Microsoft Windows para executar operações de leitura e gravação no seu disco. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gerencia quando e como a E/S de disco é executada, mas o sistema operacional Windows executa as operações de E/S subjacentes. O subsistema de E/S compreende o barramento do sistema, as placas do controlador de disco, os discos, as unidades de fita, a unidade de CD-ROM e vários outros dispositivos de E/S. E/S no disco é, muitas vezes, a causa de gargalos em um sistema.  
  
 Monitorar a atividade de disco envolve duas áreas de foco:  
  
-   Monitorar E/S no disco e detectar paginação excessiva  
  
-   Isolar a atividade de disco criada pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  
  
 Para obter mais informações, consulte [Monitorando o uso do disco](http://social.technet.microsoft.com/wiki/contents/articles/monitoring-disk-usage.aspx)  
  
  
