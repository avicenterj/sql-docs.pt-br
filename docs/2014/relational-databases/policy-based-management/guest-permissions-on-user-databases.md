---
title: Permissões de convidado em bancos de dados de usuários | Microsoft Docs
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
- Best Practices [Database Engine]
ms.assetid: 540f1c6d-df51-497e-958a-3a0f429d2920
caps.latest.revision: 8
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 51f08e85c6ebd06c7cfcfb1922312accd8203246
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37230746"
---
# <a name="guest-permissions-on-user-databases"></a>Permissões de convidado em bancos de dados de usuários
  Esta regra determina se o usuário convidado tem permissão para acessar o banco de dados. Esta regra só se aplica a bancos de dados de usuários.  
  
## <a name="best-practices-recommendations"></a>Práticas Recomendadas  
 Revogue a permissão de usuário convidado para acessar o banco de dados se não for necessária.  
  
 O usuário convidado não pode ser descartado, mas pode ser desabilitado revogando sua permissão CONNECT com a execução de REVOKE CONNECT FROM GUEST em qualquer banco de dados que não seja mestre, tempdb ou msdb.  
  
## <a name="for-more-information"></a>Para obter mais informações  
 [Protegendo o SQL Server](../security/securing-sql-server.md)  
  
## <a name="see-also"></a>Consulte também  
 [Monitorar e impor práticas recomendadas usando o Gerenciamento Baseado em Políticas](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
