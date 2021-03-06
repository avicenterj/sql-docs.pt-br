---
title: Administrador de E/S XTP do SQL Server | Microsoft Docs
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
ms.assetid: 91e176fe-c838-44e9-b4fc-2814a0551ca3
caps.latest.revision: 2
author: dagiro
ms.author: v-dagir
manager: craigg
ms.openlocfilehash: c370bb68474c29d04615316ff7782ee1d532a561
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32950692"
---
# <a name="sql-server-xtp-io-governor"></a>Administrador de E/S XTP do SQL Server
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

O objeto de desempenho Administrador de E/S XTP do SQL Server contém contadores relacionados ao Administrador da Taxa de E/S do OLTP in-memory.

Esta tabela descreve os contadores do **Administrador de E/S XTP do SQL Server** .

|Contador|Description|  
|-------------|-----------------|  
|**Esperas de Créditos Insuficientes/s**|Número de esperas devido a créditos insuficientes nos objetos de taxa (por segundo).|
|**E/S emitida/s**|Número de E/Ss emitidas por segundo por threads de liberação.|
|**Blocos de Log/s**|Número de blocos de log processados pelo controlador por segundo.|
|**Slots de Crédito Perdidos**|Número de slots de crédito perdidos devido à espera por créditos do objeto de taxa.|
|**Esperas de Objeto de Taxa Obsoletos/s**|Número de esperas devido a objetos taxa obsoletos (por segundo).|
|**Total de Objetos de Taxa Publicados**|Número total de objetos de Taxa publicados.|
 

## <a name="see-also"></a>Consulte Também  
[Contadores de desempenho XTP &#40;OLTP in-memory&#41; do SQL Server](../../relational-databases/performance-monitor/sql-server-xtp-in-memory-oltp-performance-counters.md)
