---
title: Escolher a conta de serviço do agente para ambientes multisservidor | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.component: ssms-agent
ms.reviewer: ''
ms.suite: sql
ms.technology: ssms
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- multiserver environments [SQL Server], SQL Server Agent service account behavior
ms.assetid: a07e2f38-281c-495b-965b-13fad03ba548
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: d97f052c165bc3efb557c9c6b2e768804509ac4b
ms.sourcegitcommit: 603d2e588ac7b36060fa0cc9c8621ff2a6c0fcc7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42774494"
---
# <a name="choose-the-right-sql-server-agent-service-account-for-multiserver-environments"></a>Escolher a conta de serviço do SQL Server Agent certa para ambientes multisservidor
[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]

> [!IMPORTANT]  
> No momento, na [Instância Gerenciada do Banco de Dados SQL do Azure](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance), a maioria dos recursos do SQL Server Agent é compatível, mas não todos. Consulte [Azure SQL Database Managed Instance T-SQL differences from SQL Server](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) (Diferenças entre o T-SQL da Instância Gerenciada do Banco de Dados SQL do Azure e o SQL Server) para obter detalhes.

A conta do Windows escolhida para o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent pode afetar o comportamento de um ambiente multisservidor, da seguinte maneira:  
  
-   Se você executar o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sob uma conta que não seja membro do grupo Administradores do Windows local, a inscrição de servidores de destino em servidores mestre poderá falhar. Se isso acontecer, a seguinte mensagem de erro será retornada:  
  
    "A operação de inscrição falhou".  
  
    Reinicie os serviços do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent para resolver o problema.  
  
-   Quando o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent é executado com a conta Sistema Local, só haverá suporte a operações de servidor mestre e servidor de destino se ambos residirem no mesmo computador. Se você usar essa configuração, a seguinte mensagem será retornada quando você inscrever servidores de destino para um servidor mestre:  
  
    "Verifique se a conta de inicialização de agente de *<target_server_computer_name>* tem direitos para fazer logon como um servidor de destino".  
  
    Você pode ignorar essa mensagem informativa. A operação de inscrição deve ser concluída com êxito.  
  
Para obter mais informações sobre como escolher uma conta para o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, veja [Selecionar uma conta para o serviço do SQL Server Agent](../../ssms/agent/select-an-account-for-the-sql-server-agent-service.md).  
  
