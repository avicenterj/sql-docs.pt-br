---
title: Service Broker com grupos de disponibilidade AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: high-availability
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Service Broker, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 881c20e5-1c99-44eb-b393-09fc5ea0f122
caps.latest.revision: 11
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: e7dc427aaf045a2cd62925ac23a017875302f276
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37261382"
---
# <a name="service-broker-with-alwayson-availability-groups-sql-server"></a>Service Broker com grupos de disponibilidade AlwaysOn (SQL Server)
  Este tópico contém informações sobre como configurar o Service Broker para funcionar com o [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].  
  
 **Neste tópico:**  
  
-   [Requisitos para um serviço em um grupo de disponibilidade para receber mensagens remotas](#ReceiveRemoteMessages)  
  
-   [Requisitos para enviar mensagens para um serviço remoto em um grupo de disponibilidade](#SendRemoteMessages)  
  
##  <a name="ReceiveRemoteMessages"></a> Requisitos para um serviço em um grupo de disponibilidade para receber mensagens remotas  
  
1.  **Verifique se o grupo de disponibilidade tem um ouvinte.**  
  
     Para obter mais informações, consulte [Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).  
  
2.  **Verifique se o ponto de extremidade do Service Broker existe e se está configurado corretamente.**  
  
     Em toda instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda uma réplica de disponibilidade para o grupo de disponibilidade, configure o ponto de extremidade do Service Broker, da seguinte maneira:  
  
    -   Defina LISTENER_IP como 'ALL'. Esta configuração habilitará conexões em qualquer endereço IP válido que estiver associado ao ouvinte do grupo de disponibilidade.  
  
    -   Defina a PORT do Service Broker como o mesmo número de porta em todas as instâncias do servidor de host.  
  
        > [!TIP]  
        >  Para exibir o número da porta do ponto de extremidade do Service Broker em determinada instância de servidor, consulte a coluna **port** da exibição de catálogo [sys.tcp_endpoints](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) , em que **type_desc** = 'SERVICE_BROKER'.  
  
     O exemplo a seguir cria um ponto de extremidade do Service Broker autenticado do Windows que usa a porta de Service Broker padrão (4022) e escuta todos os endereços IP válidos.  
  
    ```  
    CREATE ENDPOINT [SSBEndpoint]  
        STATE = STARTED  
        AS TCP  (LISTENER_PORT = 4022, LISTENER_IP = ALL )  
        FOR SERVICE_BROKER (AUTHENTICATION = WINDOWS)  
    ```  
  
     Para obter mais informações, veja [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).  
  
3.  **Conceda a permissão CONNECT no ponto de extremidade.**  
  
     Conceda permissão CONNECT no ponto de extremidade do Service Broker para PUBLIC ou para um logon.  
  
     O exemplo a seguir concede a conexão em um ponto de extremidade do Service Broker nomeado `broker_endpoint` para PUBLIC.  
  
    ```  
    GRANT CONNECT ON ENDPOINT::[broker_endpoint] TO [PUBLIC]  
    ```  
  
     Para obter mais informações, veja [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).  
  
4.  **Verifique se msdb contém uma rota AutoCreatedLocal ou uma rota para o serviço específico.**  
  
    > [!NOTE]  
    >  Por padrão, cada banco de dados de usuário, inclusive **msdb**, contém a rota **AutoCreatedLocal**. Essa rota corresponde a qualquer nome de serviço e instância do broker e especifica que a mensagem deve ser entregue na instância atual. **AutoCreatedLocal** tem prioridade inferior a rotas que especificam explicitamente um serviço que se comunica com uma instância remota.  
  
     Para obter informações sobre como criar rotas, veja [Exemplos de roteamento do Service Broker](http://msdn.microsoft.com/library/ms166090\(SQL.105\).aspx) (na versão do [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] dos Manuais Online) e [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).  
  
##  <a name="SendRemoteMessages"></a> Requisitos para enviar mensagens para um serviço remoto em um grupo de disponibilidade  
  
1.  **Criar uma rota para o serviço de destino.**  
  
     Configure a rota da seguinte maneira:  
  
    -   Defina ADDRESS como o endereço IP de ouvinte de grupo de disponibilidade que hospeda o banco de dados de serviço.  
  
    -   Defina PORT como a porta que você especificou no ponto de extremidade do Service Broker de cada instância remota do SQL Server.  
  
     O exemplo a seguir cria uma rota nomeada `RouteToTargetService` para o serviço `ISBNLookupRequestService` . A rota destina-se ao ouvinte do grupo de disponibilidade, `MyAgListener`, que usa a porta 4022.  
  
    ```  
    CREATE ROUTE [RouteToTargetService] WITH   
    SERVICE_NAME = 'ISBNLookupRequestService',   
    ADDRESS = 'TCP://MyAgListener:4022';  
  
    ```  
  
     Para obter mais informações, veja [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql).  
  
2.  **Verifique se msdb contém uma rota AutoCreatedLocal ou uma rota para o serviço específico.** (Para obter mais informações, veja [Requisitos para que um serviço em um grupo de disponibilidade receba mensagens remotas](#ReceiveRemoteMessages), acima neste tópico.)  
  
##  <a name="RelatedTasks"></a> Tarefas relacionadas  
  
-   [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql)  
  
-   [CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql)  
  
-   [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql)  
  
-   [Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;](create-or-configure-an-availability-group-listener-sql-server.md).  
  
-   [Criação e configuração de grupos de disponibilidade &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md)  
  
-   [Configurar contas de logon para espelhamento de banco de dados ou grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](../../database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability.md)  
  
## <a name="see-also"></a>Consulte também  
 [Visão geral dos grupos de disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md)   
 [Ouvintes do grupo de disponibilidade, conectividade de cliente e failover de aplicativo &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md)   
 [SQL Server Service Broker](../../configure-windows/sql-server-service-broker.md)  
  
  
