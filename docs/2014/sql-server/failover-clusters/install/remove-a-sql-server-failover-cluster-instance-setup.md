---
title: Renomear uma instância do cluster de failover do SQL Server (Configuração) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- clusters [SQL Server], removing failover clustered instance
- failover clustering [SQL Server], removing failover clustered instance
- uninstalling failover clustered instances
- removing failover clustered instances
ms.assetid: bf63353b-69cf-4c5c-98ea-7b151e36537f
caps.latest.revision: 37
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 8bab3fe033857578977519f1893b80ae6c37cfef
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37251158"
---
# <a name="remove-a-sql-server-failover-cluster-instance-setup"></a>Remover uma instância de cluster de failover do SQL Server (instalação)
  Use esse procedimento para desinstalar uma instância clusterizada de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .  
  
> [!IMPORTANT]  
>  Para atualizar ou remover um cluster de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , você deve ter privilégios de administrador local com permissão para efetuar logon como um serviço em todos os nós do cluster de failover.  
  
 **Antes de começar**  
  
 Considere os seguintes pontos importantes antes de desinstalar um cluster de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :  
  
-   Se o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client for desinstalado por acidente, os recursos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] não poderão ser iniciados. Para reinstalar o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, execute o programa de instalação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para instalar os pré-requisitos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .  
  
-   Se você optar por desinstalar um cluster de failover que tenha mais de um recurso de cluster IP do SQL, deverá remover os recursos IP adicionais do SQL usando o administrador de cluster.  
  
 Para obter informações sobre a sintaxe de prompt de comando, consulte [instalar o SQL Server 2014 do Prompt de comando](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).  
  
### <a name="to-uninstall-a-includessnoversionincludesssnoversion-mdmd-failover-cluster"></a>Para desinstalar um cluster de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .  
  
1.  Para desinstalar um cluster de failover do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , use a função Remover Nó fornecida na instalação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para remover cada nó individualmente. Para obter mais informações, consulte [Adicionar ou remover nós em um cluster de failover do SQL Server &#40;Instalação&#41;](add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).  
  
## <a name="see-also"></a>Consulte também  
 [Exibir e ler arquivos de log da Instalação do SQL Server](../../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)  
  
  
