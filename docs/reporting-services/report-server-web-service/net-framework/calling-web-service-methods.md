---
title: Chamando métodos do serviço Web | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.component: report-server-web-service
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- Web service [Reporting Services], calls
- calling Web service
- Report Server Web service, SOAP
- XML Web service [Reporting Services], calls
- Report Server Web service, calls
- XML Web service [Reporting Services], SOAP
- SOAP [Reporting Services], calls
ms.assetid: f6f0c6e3-8bb5-4c44-9d19-1872edc72746
caps.latest.revision: 38
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: d830acb82476d743972ca1378d62a7cec5b5e05a
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "33024163"
---
# <a name="calling-web-service-methods"></a>Chamando métodos do serviço Web
  Quando você usa uma classe proxy do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] para chamar as operações do serviço Web, você faz isso usando os métodos dessa classe. Esses métodos respondem como qualquer outro método de uma classe da biblioteca de classes [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Todos os métodos do serviço Web têm acesso público e exigem que você forneça o número e tipos de argumentos adequados. Depois de criar uma instância da classe de proxy em seu projeto, você poderá chamar os métodos para realizar operações de relatório por meio do servidor de relatório. O código C# a seguir ilustra o uso do método <xref:ReportService2010.ReportingService2010.ListChildren%2A> da classe proxy <xref:ReportService2010.ReportingService2010>. Esse código é usado para realizar uma chamada recursiva para o serviço Web que retorna uma matriz dos objetos <xref:ReportService2010.CatalogItem> que contém uma lista de todos os itens do banco de dados do servidor de relatório:  
  
```vb  
Dim rs As New ReportingService2010()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
Dim items As CatalogItem() = rs.ListChildren("/", True)  
```  
  
```csharp  
ReportingService2010 rs = new ReportingService2010();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
CatalogItem[] items = rs.ListChildren("/", true);  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Criando aplicativos usando o serviço Web e o .NET Framework](../../../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)   
 [Serviço Web do Servidor de Relatório](../../../reporting-services/report-server-web-service/report-server-web-service.md)   
 [Referência técnica &#40;SSRS&#41;](../../../reporting-services/technical-reference-ssrs.md)  
  
  
