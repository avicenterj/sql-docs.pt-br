---
title: "Operar a instância de cluster de failover - SQL Server no Linux | Microsoft Docs"
description: 
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
ms.date: 08/28/2017
ms.topic: article
ms.prod: sql-linux
ms.technology: database-engine
ms.assetid: 
ms.translationtype: MT
ms.sourcegitcommit: 834bba08c90262fd72881ab2890abaaf7b8f7678
ms.openlocfilehash: a8595b61afd374d6127f6cc7b9b363f325a257b5
ms.contentlocale: pt-br
ms.lasthandoff: 10/02/2017

---
# <a name="operate-failover-cluster-instance---sql-server-on-linux"></a>Operar a instância de cluster de failover - SQL Server no Linux

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

Este artigo explica como operar uma instância de cluster de failover (FCI) do SQL Server no Linux. Se você não tiver criado um FCI do SQL Server no Linux, consulte [configurar instância de cluster de failover - SQL Server no Linux](sql-server-linux-shared-disk-cluster-configure.md). 

## <a name="failover"></a>Failover

Failover para FCIs é semelhante a um cluster de failover do Windows Server (WSFC). Se o nó de cluster que hospeda a FCI tiver algum tipo de falha, a FCI automaticamente deve executar failover para outro nó. Ao contrário de um WSFC, não é possível definir os proprietários preferenciais para que Pacemaker seleciona o nó que será o novo host para a FCI.

Há ocasiões, que talvez você queira executar manualmente a FCI para outro nó. O processo não é o mesmo assim como acontece com FCIs em um WSFC. Em um WSFC, você deve fazer failover recursos no nível de função. Em Pacemaker, escolha um recurso para mover e supondo que todas as restrições estão corretas, tudo será movido também. 

A forma de failover depende da distribuição de Linux. Siga as instruções para a distribuição de linux.

- [RHEL ou Ubuntu](#rhelFailover)
- [SLES](#slesFailover)

## <a name = "#rhelFailover"></a>Failover manual (RHEL ou Ubuntu)

Para executar um failover manual, onn Red Hat Enterprise Linux (RHEL) ou servidores Ubuntu execute as etapas a seguir.
1.  Execute o seguinte comando: 

   ```bash
   sudo pcs resource move <FCIResourceName> <NewHostNode> 
   ```

   \<FCIResourceName > é o nome do recurso de Pacemaker para a FCI do SQL Server.

   \<NewHostNode > é o nome do nó do cluster que você deseja hospedar a FCI. 

   Você não terá nenhuma confirmação.

2.  Durante um failover manual, Pacemaker cria uma restrição de local do recurso que foi escolhido para mover manualmente. Para ver essa restrição, execute `sudo pcs constraint`.

3.  Após o failover estiver concluído, remova a restrição emitindo `sudo pcs resource clear <FCIResourceName>`. 

\<FCIResourceName > é o nome do recurso Pacemaker para a FCI. 

## <a name = "#slesFailover"></a>Failover manual (SLES)


No Suse Linux Enterprise Server (SLES), use o `migrate` de comando para o failover manualmente um FCI do SQL Server. Por exemplo:

```bash
crm resource migrate <FCIResourceName> <NewHostNode>
```

\<FCIResourceName > é o nome de recurso para a instância de cluster de failover. 

\<NewHostNode > é o nome do novo host de destino. 


<!---
|Distribution |Topic 
|----- |-----
|**Red Hat Enterprise Linux with HA add-on** |[Configure](sql-server-linux-shared-disk-cluster-red-hat-7-configure.md)<br/>[Operate](sql-server-linux-shared-disk-cluster-red-hat-7-operate.md)
|**SUSE Linux Enterprise Server with HA add-on** |[Configure](sql-server-linux-shared-disk-cluster-sles-configure.md)
--->

## <a name="next-steps"></a>Próximas etapas

- [Configurar a instância de cluster de failover - SQL Server no Linux](sql-server-linux-shared-disk-cluster-configure.md)

<!--Image references-->
