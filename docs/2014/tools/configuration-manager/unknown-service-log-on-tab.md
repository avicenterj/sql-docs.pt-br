---
title: Serviço desconhecido (guia fazer logon) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- configmgr-client
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9b35cb5-d8ae-42ea-b59e-deedc99c4823
caps.latest.revision: 15
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: 7c69029b006c4fde006a83a8849e104cc5a74ea2
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36019477"
---
# <a name="unknown-service-log-on-tab"></a>Serviço desconhecido (guia Fazer Logon)
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager não pode identificar este serviço.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager recebe informações de serviço do provedor WMI no computador que está executando o serviço. Ocorreu um erro ao ler as propriedades do serviço ou essas propriedades não estão completas. Para resolver o problema, tente fechar e reabrir o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager ou verifique o provedor WMI no computador que está executando o serviço.  
  
 O provedor WMI é um componente do Windows. Para obter informações sobre como verificar as permissões no provedor WMI, consulte "Como configurar o WMI para que mostre o status do servidor nas ferramentas do SQL Server" nos Manuais Online do SQL Server.  
  
 Se você achar que está exibindo o serviço correto, use a guia **Fazer Logon** da caixa de diálogo **Propriedades de Serviço Desconhecido** para especificar a conta usada por esse serviço e para iniciar e parar o serviço.  
  
## <a name="options"></a>Opções  
 **Conta Sistema Local**  
 Especifique uma conta Sistema Local que não requeira uma senha. No entanto, ela pode impedir a interação do serviço com outros servidores, dependendo dos privilégios concedidos a ela.  
  
 **Esta conta**  
 Especifique um local ou conta de usuário do domínio que utilize Autenticação do Windows. É recomendável usar uma conta de usuário do domínio com direitos mínimos para serviços. Para obter informações sobre como selecionar uma conta, consulte "Configurando as contas de serviço do Windows" nos Manuais Online do SQL Server.  
  
 **Nome da Conta**  
 Especifique o nome da conta local ou de usuário de domínio.  
  
 **Senha**  
 Digite a senha da conta.  
  
 **Confirmar senha**  
 Digite a senha da conta novamente.  
  
 **Iniciar**  
 Inicie o serviço.  
  
 **Parar**  
 Parar o serviço.  
  
 **Pausar**  
 Pausar o serviço.  
  
 **Retomar**  
 Retomar um serviço pausado.  
  
  