---
title: Implementando IDENTITY em uma tabela otimizada em memória | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: in-memory-oltp
ms.reviewer: ''
ms.suite: sql
ms.technology: in-memory-oltp
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: c0a704a3-3a31-4c2c-b967-addacda62ef8
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: ded28f392cf8eed66b56aea391e048015a707547
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43098620"
---
# <a name="implementing-identity-in-a-memory-optimized-table"></a>Implementando IDENTITY em uma tabela otimizada em memória
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]

Há suporte para IDENTITY em uma tabela com otimização de memória, desde que a semente e o incremento sejam 1 (padrão). Não há suporte em tabelas com otimização de memória para colunas de identidade com definição de IDENTITY(x, y), em que x != 1 ou y != 1.   
    
Para aumentar a semente de IDENTITY, insira uma nova linha com um valor explícito para a coluna de identidade, usando a opção de sessão `SET IDENTITY_INSERT table_name ON`. Com a inserção da linha, a semente de IDENTITY é alterada para o valor inserido explicitamente, mais 1. Por exemplo, para aumentar a semente para 1.000, insira uma linha com valor 999 na coluna de identidade. Os valores de identidade gerados serão iniciados em 1.000.     
  
## <a name="see-also"></a>Consulte Também  
 [Migrando para OLTP na memória](../../relational-databases/in-memory-oltp/migrating-to-in-memory-oltp.md)  
  
  
