---
title: Implementando uma extensão de entrega | Microsoft Docs
ms.custom: ''
ms.date: 03/16/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.component: extensions
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- delivery [Reporting Services]
- custom delivery extensions [Reporting Services]
- extensions [Reporting Services], delivery
- delivery extensions [Reporting Services]
ms.assetid: 600cd229-efcd-480e-8c95-3c3c39ff4e7a
caps.latest.revision: 32
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: e4388f157aba6ae590f2bc56109b18696e98ea49
ms.sourcegitcommit: 9cd01df88a8ceff9f514c112342950e03892b12c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2018
ms.locfileid: "40406582"
---
# <a name="implementing-a-delivery-extension"></a>Implementando uma extensão de entrega
  O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] permite que os usuários criem e publiquem relatórios que, uma vez criados e publicados, podem ser entregues em vários locais. Além disso, o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] inclui várias extensões de entrega e uma API de entrega que permite que os desenvolvedores criem extensões de entrega adicionais para estender ainda mais a funcionalidade de entrega do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].  
  
 Para obter uma implementação de exemplo de uma extensão de entrega, consulte [Amostras de produto do SQL Server Reporting Services](http://go.microsoft.com/fwlink/?LinkId=177889).  
  
## <a name="in-this-section"></a>Nesta seção  
 [Visão geral de extensões de entrega](../../../reporting-services/extensions/delivery-extension/delivery-extensions-overview.md)  
 Apresenta como escrever uma extensão de entrega para o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].  
  
 [Preparar para implementar uma entrega de extensão](../../../reporting-services/extensions/delivery-extension/preparing-to-implement-a-delivery-extension.md)  
 Descreve as interfaces e as classes disponíveis durante a implementação de uma extensão de entrega do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], além dos problemas a serem considerados antes da implementação.  
  
 [Criar uma biblioteca de extensões de entrega](../../../reporting-services/extensions/delivery-extension/creating-a-delivery-extension-library.md)  
 Descreve a atribuição de um namespace para a extensão de entrega do seu [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] e a compilação da sua extensão de entrega em uma DLL de biblioteca.  
  
 [Implementar a interface IDeliveryExtension para uma extensão de entrega](../../../reporting-services/extensions/delivery-extension/implementing-the-ideliveryextension-interface-for-a-delivery-extension.md)  
 Descreve os atributos de uma extensão de entrega e como implementar a sua própria classe de extensão de entrega.  
  
 [Usar uma classe de notificação para uma extensão de entrega](../../../reporting-services/extensions/delivery-extension/using-a-notification-class-for-a-delivery-extension.md)  
 Descreve os atributos de uma classe **Notification** e como usá-la na implementação de extensão de entrega.  
  
 [Usar a classe Setting para uma extensão de entrega](../../../reporting-services/extensions/delivery-extension/using-the-setting-class-for-a-delivery-extension.md)  
 Descreve os atributos de uma classe **Setting** e como usá-la na implementação de extensão de entrega.  
  
 [Usar a classe Report para uma extensão de entrega](../../../reporting-services/extensions/delivery-extension/using-the-report-class-for-a-delivery-extension.md)  
 Descreve os atributos de uma classe **Report** e como usá-la na implementação de extensão de entrega.  
  
 [Usar a classe RenderedOutputFile para uma extensão de entrega](../../../reporting-services/extensions/delivery-extension/using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
 Descreve os atributos de uma classe **RenderedOutputFile** e como usá-la na implementação de extensão de entrega.  
  
 [Implantando uma extensão de entrega](../../../reporting-services/extensions/delivery-extension/deploying-a-delivery-extension.md)  
 Descreve como implantar a sua extensão de entrega.  
  
 [Depurar o código de extensão de entrega](../../../reporting-services/extensions/delivery-extension/debugging-delivery-extension-code.md)  
 Descreve como depurar código em sua extensão de entrega.  
  
 [Remover uma extensão de entrega](../../../reporting-services/extensions/delivery-extension/removing-a-delivery-extension.md)  
 Descreve como remover uma extensão de entrega de um servidor de relatório.  
  
## <a name="see-also"></a>Consulte Também  
 [Extensões do Reporting Services](../../../reporting-services/extensions/reporting-services-extensions.md)   
 [Biblioteca de extensões do Reporting Services](../../../reporting-services/extensions/reporting-services-extension-library.md)  
  
  
