---
title: Conectar ao Servidor (página Logon) Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.swb.connecttodtsserver.login.f1
- sql12.swb.connecttodts.login.f1
ms.assetid: 402c2de4-f4ea-40b0-909f-3ddf3bd59950
caps.latest.revision: 23
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e41104462b18f9d236a289dbea0196f981006f44
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36118189"
---
# <a name="connect-to-server-login-page-integration-services"></a>Conectar-se ao Servidor (página Logon) Integration Services
  Use essa guia para exibir ou especificar as seguintes opções ao se conectar ao [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].  
  
## <a name="options"></a>Opções  
 **Tipo de servidor**  
 Ao registrar um servidor a partir do Pesquisador de Objetos, selecione o tipo de servidor ao qual se conectar: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services ou Integration Services. O restante da caixa de diálogo mostra somente as opções que válidas ao tipo de servidor selecionado. Ao registrar um servidor de Servidores Registrados, a caixa **Tipo de servidor** é somente leitura e corresponde ao tipo de servidor exibido no componente Servidores Registrados. Para registrar outro tipo de servidor, selecione [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services ou Integration Services na barra de ferramentas Servidores Registrados antes de iniciar o registro de um novo servidor.  
  
 **Nome do servidor**  
 Selecione o servidor ao qual conectar-se. Por padrão, é exibida a instância de servidor usada na última conexão.  
  
> [!NOTE]  
>  Não use  *\<servername >*\\*\<instancename >*, pois [!INCLUDE[ssIS](../includes/ssis-md.md)] não oferece suporte a várias instâncias em um computador.  
  
 **Autenticação**  
 Somente a Autenticação do [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows está disponível para o [!INCLUDE[ssIS](../includes/ssis-md.md)]. Windows permite que um usuário conecte-se por meio de uma conta de usuário do Windows.  
  
 **Nome de usuário**  
 Essa opção não está disponível porque só a Autenticação do Windows está disponível para o [!INCLUDE[ssIS](../includes/ssis-md.md)].  
  
 **Senha**  
 Essa opção não está disponível porque só a Autenticação do Windows está disponível para o [!INCLUDE[ssIS](../includes/ssis-md.md)].  
  
 **Lembrar senha**  
 Essa opção não está disponível porque só a Autenticação do Windows está disponível para o [!INCLUDE[ssIS](../includes/ssis-md.md)].  
  
 **Connect**  
 Conecte-se com o servidor selecionado acima.  
  
 **Opções**  
 Clique para alterar a caixa de diálogo e ocultar as opções de conexão de servidor adicionais, como lembrar a senha.  
  
  