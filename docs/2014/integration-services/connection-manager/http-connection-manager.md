---
title: Gerenciador de conexões HTTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- HTTP connection manager
- Web site connections [Integration Services]
- connection managers [Integration Services], HTTP
- Web server connections [Integration Services]
- connections [Integration Services], HTTP
ms.assetid: 26b2b3e1-d02c-46ca-8d31-7aef2bbc3c53
caps.latest.revision: 44
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 02df4c5dff88988bd6a233208646e9eb9a7f0e2d
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37314446"
---
# <a name="http-connection-manager"></a>Gerenciador de conexões HTTP
  Uma conexão HTTP permite que um pacote acesse um servidor Web usando o HTTP para enviar ou receber arquivos. A tarefa Serviço da Web incluída no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usa esse gerenciador de conexões.  
  
 Quando você adiciona um gerenciador de conexões HTTP a um pacote, o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] cria um gerenciador de conexões que resolverá uma conexão HTTP em tempo de execução, define as propriedades do gerenciador de conexões e adiciona o gerenciador de conexões à coleção `Connections` no pacote.  
  
 O `ConnectionManagerType` propriedade do Gerenciador de conexão é definida como `HTTP.`  
  
 Você pode configurar um gerenciador de conexões HTTP das seguintes maneiras:  
  
-   Use credenciais. Se o gerenciador de conexões HTTP usar credenciais, suas propriedades incluirão o nome de usuário, a senha e o domínio.  
  
    > [!IMPORTANT]  
    >  O gerenciador de conexões HTTP dá suporte apenas para autenticação anônima e autenticação básica. Ele não suporta a Autenticação do Windows.  
  
-   Use um certificado do cliente. Se o gerenciador de conexões usar um certificado do cliente, suas propriedades incluirão o nome de certificado.  
  
-   Forneça um tempo limite para conexão com o servidor e um tamanho da parte para gravar dados.  
  
-   Use um servidor proxy. O servidor proxy também pode ser configurado para usar credenciais e ignorar o servidor proxy com o uso de endereços locais em seu lugar.  
  
## <a name="configuration-of-the-http-connection-manager"></a>Configuração do gerenciador de conexões HTTP  
 Você pode definir propriedades pelo Designer do [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou programaticamente.  
  
 Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique em um dos seguintes tópicos:  
  
-   [Editor do Gerenciador de Conexão HTTP &#40;página do servidor&#41;](../http-connection-manager-editor-server-page.md)  
  
-   [Editor do Gerenciador de Conexão HTTP &#40;página de Proxy&#41;](../http-connection-manager-editor-proxy-page.md)  
  
 Para obter informações sobre como configurar um gerenciador de conexões de forma programática, consulte <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.  
  
## <a name="see-also"></a>Consulte também  
 [Tarefa serviço da Web](../control-flow/web-service-task.md)   
 [Serviços de integração &#40;SSIS&#41; conexões](integration-services-ssis-connections.md)  
  
  
