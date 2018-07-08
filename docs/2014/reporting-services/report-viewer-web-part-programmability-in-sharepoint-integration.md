---
title: Programação da web part do Visualizador de Relatórios na integração do SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 714017b7-1bd6-4950-a3c6-d0df8450a877
caps.latest.revision: 7
author: douglaslM
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 43c0988abc3ea5043873421054fc370a58ed9347
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36115166"
---
# <a name="report-viewer-web-part-programmability-in-sharepoint-integration"></a>Programabilidade do Web Part do Visualizador de Relatórios na Integração do SharePoint
  A Web Part do Visualizador de Relatórios é um controle de servidor de `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart` que contém um conjunto de APIs (interfaces de programação de aplicativos) públicas, permitindo que os desenvolvedores criem aplicativos de SharePoint personalizados. Você pode criar Web Parts personalizadas que fornecem o caminho do relatório e parâmetros para a Web Part do Visualizador de Relatórios que usa conexões de Web Part. Você também pode inserir a Web Part em uma página personalizada de Web Parts do SharePoint e personalizá-la usando a API pública.  
  
## <a name="connecting-to-report-viewer-web-part-with-custom-web-parts"></a>Conectando-se a uma Web Part do Visualizador de Relatórios com Web Parts personalizadas  
 A Web Part do Visualizador de Relatórios é um consumidor de conexão para Web Parts de SharePoint que implementam <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> ou `T:Microsoft.SharePoint.WebPartPages.IFilterValues`. Uma Web Part <xref:System.Web.UI.WebControls.WebParts.IWebPartRow>, como **Documents**, pode fornecer um caminho de relatório para uma Web Part do Visualizador de Relatórios quando colocada na mesma página de Web Part da Web Part do Visualizador de Relatórios. Da mesma forma, um `T:Microsoft.SharePoint.WebPartPages.IFilterValues` Web Part, como o **filtro de texto** ou **escolher filtro**, pode fornecer um parâmetro de relatório para um relatório de Web Part do visualizador quando colocada na mesma página de Web Part como o Visualizador de relatório da Web Parte.  
  
### <a name="implementing-a-report-path-provider-with-iwebpartrow"></a>Implementando um provedor de caminho de relatório com IWebPartRow  
 Para fornecer um caminho de relatório à Web Part do Visualizador de Relatórios através de conexões de Web Parts, faça o seguinte:  
  
1.  Crie uma Web Part que implemente a interface <xref:System.Web.UI.WebControls.WebParts.IWebPartRow>.  
  
2.  Adicione a Web Part à mesma página de Web Parts da Web Part do Visualizador de Relatórios.  
  
3.  Conecte sua Web Part à Web Part do Visualizador de Relatórios na interface de usuário de design de Web Parts na Web.  
  
    > [!NOTE]  
    >  Você pode conectar somente uma Web Part de <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> à Web Part do Visualizador de Relatórios por vez, e não pode conectar uma Web Part de <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> e uma Web Part de `T:Microsoft.SharePoint.WebPartPages.IFilterValues` à Web Part do Visualizador de Relatórios ao mesmo tempo.  
  
 Para que a sua Web Part <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> funcione corretamente com a `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart`, faça o seguinte no método <xref:System.Web.UI.WebControls.WebParts.IWebPartRow.GetRowData%2A>:  
  
-   Invoque o método de retorno de chamada com um objeto <xref:System.Data.DataRowView> como o parâmetro de entrada.  
  
-   Verifique se o objeto <xref:System.Data.DataRowView> contém uma coluna chamada "DocUrl", que contém o caminho do relatório.  
  
    > [!NOTE]  
    >  A Web Part do Visualizador de Relatórios no suplemento do [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2010 também permite o recebimento do caminho do relatório, utilizando a coluna "FileRef."  
  
### <a name="implementing-a-report-parameter-provider-with-ifiltervalues"></a>Implementando um provedor de parâmetro de relatório com IFilterValues  
 Uma Web Part que implementa o `T:Microsoft.SharePoint.WebPartPages.IFilterValues` pode fornecer um valor de parâmetro à Web Part do Visualizador de Relatórios. O valor de parâmetro enviado à Web Part do Visualizador de Relatórios está sujeito às mesmas restrições impostas ao parâmetro de relatório especificadas na definição do relatório, como tipo de dados, valores válidos, etc.  
  
 Para fornecer um parâmetro de relatório à Web Part do Visualizador de Relatórios, faça o seguinte:  
  
1.  Crie uma Web Part que implemente a interface `T:Microsoft.SharePoint.WebPartPages.IFilterValues`.  
  
2.  Adicione a Web Part à mesma página do `T:Microsoft.ReportingServices.SharePoint.UI.WebParts.ReportViewerWebPart`.  
  
3.  Conecte sua Web Part `T:Microsoft.SharePoint.WebPartPages.IFilterValues` à Web Part do Visualizador de Relatórios na interface de usuário de design de Web Parts na Web.  
  
    > [!NOTE]  
    >  Você pode conectar várias Web Parts de `T:Microsoft.SharePoint.WebPartPages.IFilterValues` à Web Part do Visualizador de Relatórios por vez. No entanto, você não pode conectar uma Web Part de <xref:System.Web.UI.WebControls.WebParts.IWebPartRow> e uma Web Part de `T:Microsoft.SharePoint.WebPartPages.IFilterValues` à Web Part do Visualizador de Relatórios ao mesmo tempo.  
  
## <a name="see-also"></a>Consulte também  
 [Interface IFilterValues](https://msdn.microsoft.com/en-us/library/office/microsoft.sharepoint.webpartpages.ifiltervalues\(v=office.15\).aspx)  
  
  