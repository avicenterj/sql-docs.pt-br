---
title: Conectar a uma instância do Pesquisador de Objetos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 9803a8a0-a8f1-4b65-87b8-989b06850194
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 19f0ec63f3f2f2372e9f7803b5256692910f6242
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37222506"
---
# <a name="connect-to-an-instance-from-object-explorer"></a>Conectar-se a uma instância do Pesquisador de Objetos
  Para gerenciar objetos usando o Pesquisador de Objetos, primeiro você deve conectar o Pesquisador de Objetos à instância que contém os objetos. Você pode conectar o Pesquisador de Objetos a várias instâncias ao mesmo tempo.  
  
## <a name="connecting-object-explorer-to-a-server"></a>Conectando o Pesquisador de Objetos a um servidor  
 Para usar o Pesquisador de Objetos, você deve primeiro se conectar a um servidor. Clique em **Conectar** na barra de ferramentas do Pesquisador de Objetos e escolha o tipo de servidor na lista suspensa. A caixa de diálogo **Conectar ao Servidor** é exibida. Para se conectar, você deve fornecer pelo menos o nome do servidor e as informações de autenticação corretas.  
  
## <a name="optional-object-explorer-connection-settings"></a>Configurações de conexão opcional do Pesquisador de Objetos  
 Ao se conectar a um servidor, você pode especificar informações adicionais de conexão na caixa de diálogo **Conectar ao Servidor** . A caixa de diálogo **Conectar ao Servidor** reterá as últimas configurações usadas e conexões novas, como novas janelas do editor de códigos, e usará essas configurações.  
  
 Para especificar configurações de conexão opcionais, siga estas etapas:  
  
1.  Clique em **Conectar** na barra de ferramentas do Pesquisador de Objetos e clique no tipo de servidor para fazer a conexão. A caixa de diálogo **Conectar ao Servidor** é exibida.  
  
2.  Na caixa **Nome do Servidor** , digite o nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
3.  Clique em **Opções**. A caixa de diálogo **Conectar ao Servidor** exibe opções adicionais.  
  
4.  Clique na guia **Propriedades da Conexão** para definir as configurações adicionais. As configurações disponíveis variam, dependendo do tipo de servidor. As configurações a seguir estão disponíveis para o [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
    |Configuração|Description|  
    |-------------|-----------------|  
    |**Conectar ao banco de dados**|Escolha um dos bancos de dados disponíveis no servidor. Esta lista só mostrará bancos de dados que você tem permissão para exibição.|  
    |**Protocolo de rede**|Selecione entre Memória Compartilhada, TCP/IP ou Pipes Nomeados.|  
    |**Tamanho do pacote de rede**|Configurar em bytes. A configuração padrão é 4096 bytes.|  
    |**Tempo limite da conexão**|Configurar em segundos. A configuração padrão é 15 segundos.|  
    |**Tempo limite de execução**|Configurar em segundos. A configuração padrão (0) indica que a execução nunca vai expirar.|  
    |**Criptografar conexão**|Força a criptografia.|  
  
5.  Para adicionar o servidor especificado a sua lista de servidores registrados, clique na guia **Servidor Registrado** , clique no local em que você deseja exibir o servidor novo e conclua a conexão.  
  
> [!NOTE]  
>  Use a página **Parâmetros Adicionais de Conexão** para acrescentar mais parâmetros de conexão à cadeia de conexões. Para obter mais informações, consulte [Conectar ao servidor &#40;página Parâmetros de Conexão Adicionais& 41;](../../database-engine/connect-to-server-additional-connection-parameters-page.md).  
  
  
