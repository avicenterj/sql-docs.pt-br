---
title: Classe SoapException do Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/16/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.component: report-server-web-service-net-framework-exception-handling
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- exceptions [Reporting Services], SoapException class
- SoapException class
ms.assetid: 2cec49ee-20b1-40eb-a75b-0908d9c05b34
caps.latest.revision: 33
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 12d98493c8e83688ee0eb5938e1ee078103bc5fe
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "33024633"
---
# <a name="reporting-services-soapexception-class"></a>Classe SoapException do Reporting Services
  Você deve tratar de erros específicos do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] que sabe que podem acontecer. Por exemplo, em um aplicativo onde você solicita que o usuário crie uma pasta, pode ser possível que ele tente criar uma pasta que já exista. Como desenvolvedor, você não tem controle sobre o que o usuário digita no nome da pasta e nos campos de caminho do seu aplicativo, mas tem controle sobre o que o usuário experimenta quando alguém incidentalmente tenta criar um item já existente.  
  
 Para facilitar a captura de condições de erro específicas, o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] classifica um código de erro para a exceção e retorna a classificação do erro usando propriedades da classe **SoapException**. Para obter mais informações, consulte “Classe SoapException” na documentação do SDK do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].  
  
 A tabela a seguir lista as propriedades públicas da classe **SoapException**.  
  
|Propriedade pública|Description|  
|---------------------|-----------------|  
|**Actor**|O código que causou a exceção. O valor é a URL para o método do serviço Web.|  
|**Detail**|Informações de erro específicas do aplicativo. O valor é definido pelo servidor de relatório e está em formato XML. Para obter mais informações, consulte [Propriedade Detail](../../../reporting-services/report-server-web-service-net-framework-exception-handling/soapexception-class/detail-property.md) e [Usando a propriedade Detail para tratar erros específicos](../../../reporting-services/report-server-web-service-net-framework-exception-handling/best-practices/using-the-detail-property-to-handle-specific-errors.md).|  
|**HelpLink**|Uma URL ou URN para um arquivo de Ajuda associado ao erro. O valor é normalmente definido pelo serviço Web e define uma URL como Ajuda e Suporte do [!INCLUDE[msCoName](../../../includes/msconame-md.md)]. Como o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] dá suporte a diversos links de ajuda para erros ocorridos, o servidor de relatório define informações de link de ajuda como parte da propriedade **Detail**. Para obter mais informações, consulte [Elemento HelpLink](../../../reporting-services/report-server-web-service-net-framework-exception-handling/soapexception-class/helplink-element.md).|  
|**Mensagem**|Uma mensagem descritiva e localizada que descreve o erro. Esse texto poderia aparecer na interface do usuário do aplicativo.|  
  
## <a name="see-also"></a>Consulte Também  
 [Introdução ao tratamento de exceção no Reporting Services](../../../reporting-services/report-server-web-service-net-framework-exception-handling/introducing-exception-handling-in-reporting-services.md)   
 [Tabela de erros de SoapException](../../../reporting-services/report-server-web-service-net-framework-exception-handling/soapexception-class/soapexception-errors-table.md)  
  
  
