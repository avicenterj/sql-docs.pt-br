---
title: Executar um pacote no servidor SSIS usando o SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56dc1bf8-99d4-41dc-bdc4-f64f1ccfd688
caps.latest.revision: 8
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: ceb26afb244264adb4eb003d32e1f1c5fbc8f8ba
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36116616"
---
# <a name="run-a-package-on-the-ssis-server-using-sql-server-management-studio"></a>Executar um pacote no servidor SSIS usando o SQL Server Management Studio
  Depois de implantar o projeto no servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , você pode executar o pacote no servidor.  
  
 Você pode usar relatórios de operações para exibir informações sobre pacotes que foram executados, ou que estão em execução no momento, no servidor. Para saber mais, confira [Reports for the Integration Services Server](../../2014/integration-services/reports-for-the-integration-services-server.md).  
  
### <a name="to-run-a-package-on-the-server-using-sql-server-management-studio"></a>Para executar um pacote no servidor usando o SQL Server Management Studio  
  
1.  Abra o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e conecte-se com a instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que contém o catálogo do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .  
  
2.  No Explorador de Objetos, expanda o nó **Catálogo do Integration Services** , expanda o nó **SSISDB** e navegue até o pacote contido no projeto que você implantou.  
  
3.  Clique com o botão direito do mouse no nome do pacote e selecione **Executar**.  
  
4.  Configure a execução de pacote usando as configurações nas guias **Parâmetros**, **Gerenciadores de Conexões**e **Avançado** na caixa de diálogo **Executar Pacote** .  
  
5.  Clique em **OK** para executar o pacote.  
  
     -ou-  
  
     Use procedimentos armazenados para executar o pacote. Clique em **Script** para gerar a instrução Transact-SQL que cria uma instância da execução e inicia uma instância da execução. A instrução inclu uma chamada para os procedimentos armazenados catalog.create_execution, catalog.set_execution_parameter_value e catalog.start_execution. Para obter mais informações sobre esses procedimentos armazenados, consulte [catalog.create_execution &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-create-execution-ssisdb-database), [catalog.set_execution_parameter_value &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-set-execution-parameter-value-ssisdb-database) e [catalog.start_execution &#40;Banco de dados SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-start-execution-ssisdb-database).  
  
  