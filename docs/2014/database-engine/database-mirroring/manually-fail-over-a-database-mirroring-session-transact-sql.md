---
title: Fazer failover manual de uma sessão de espelhamento de banco de dados (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- failover [SQL Server], database mirroring
- manual failover [SQL Server]
- database mirroring [SQL Server], failover
ms.assetid: 36218d61-b5f5-4194-905a-608e0e903db4
caps.latest.revision: 32
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: a75d6fdf1939c3b53fc82c7ce98ce986b0ed29e3
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37295236"
---
# <a name="manually-fail-over-a-database-mirroring-session-transact-sql"></a>Executar failover manualmente em uma sessão de espelhamento de banco de dados (Transact-SQL)
  Quando o banco de dados espelho for sincronizado (ou seja, quando o banco de dados estiver no estado SYNCHRONIZED), o proprietário do banco de dados poderá iniciar failover manual para o servidor espelho. O failover manual só pode ser iniciado do servidor principal.  
  
### <a name="to-manually-fail-over-a-database-mirroring-session"></a>Para efetuar manualmente o failover de uma sessão de espelhamento de banco de dados  
  
1.  Conecte-se ao servidor principal.  
  
2.  Defina o contexto do banco de dados como o banco de dados **mestre** :  
  
     `USE master;`  
  
3.  Emita a seguinte instrução no servidor principal:  
  
     [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) *database_name* SET PARTNER FAILOVER, em que *database_name* é o banco de dados espelhado.  
  
     Isso inicia uma transição imediata do servidor espelho para a função principal.  
  
 No principal anterior, clientes são desconectados do banco de dados e são revertidos em transações de voo.  
  
> [!NOTE]  
>  As transações que forem preparadas usando o Coordenador de Transações Distribuídas da [!INCLUDE[msCoName](../../includes/msconame-md.md)] , mas que ainda não estiverem confirmadas quando ocorrer um failover, serão consideradas anuladas depois da falha do banco de dados.  
  
## <a name="see-also"></a>Consulte também  
 [Espelhamento de banco de dados ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring)   
 [Fazer failover manual de uma sessão de espelhamento de banco de dados &#40;SQL Server Management Studio&#41;](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md)   
 [Troca de função durante uma sessão de espelhamento de banco de dados &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md)  
  
  
