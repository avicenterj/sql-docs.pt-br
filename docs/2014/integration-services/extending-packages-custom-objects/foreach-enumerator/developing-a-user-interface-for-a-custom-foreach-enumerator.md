---
title: Desenvolver uma interface do usuário para um enumerador ForEach personalizado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- integration-services
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- custom user interface [Integration Services], custom foreach enumerators
- custom foreach enumerators [Integration Services], developing custom user interface
ms.assetid: 8aa4aa80-c9ba-42b3-ba87-ae5ea5d3cac3
caps.latest.revision: 21
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 8cba9c34f0e296f43ff09b8a2f29ac54e6107c55
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37171037"
---
# <a name="developing-a-user-interface-for-a-custom-foreach-enumerator"></a>Desenvolvendo uma interface do usuário para um enumerador ForEach personalizado
  Depois de ter substituído a implementação das propriedades e dos métodos da classe base para ter sua funcionalidade personalizada, convém que você crie uma interface de usuário personalizada para o enumerador Foreach. Se você não criar uma interface de usuário personalizada, os usuários só poderão configurar o novo enumerador Foreach personalizado usando a janela Propriedades.  
  
 Em um projeto ou assembly de interface de usuário personalizada, você cria uma classe que implementa <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumeratorUI>. Essa classe deriva de System.Windows.Forms.UserControl, que normalmente é usado para criar um controle de composição para hospedar outros controles do Windows Forms. O controle que você cria é exibido na área **Configuração do enumerador** da guia **Coleção** do **Editor de Loop Foreach**.  
  
> [!IMPORTANT]  
>  Depois de assinar e criar sua interface do usuário personalizada e instalá-la no cache de assembly global, conforme descrito em [Compilar, implantar e depurar objetos personalizados](../building-deploying-and-debugging-custom-objects.md), lembre-se de fornecer o nome totalmente qualificado desta classe na propriedade <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute.UITypeName%2A> do <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>.  
  
## <a name="coding-the-user-interface-control-class"></a>Codificando a classe de controle de interface do usuário  
  
### <a name="initializing-the-user-interface"></a>Inicializando a interface do usuário   
 Você substitui o método <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumeratorUI.Initialize%2A> para referências de cache ao objeto de host e às coleções de gerenciadores de conexões e variáveis definidas no pacote.  
  
### <a name="setting-properties-on-the-user-interface-control"></a>Definindo propriedades no controle de interface do usuário  
 A classe UserControl, cuja classe de interface do usuário é derivada, destina-se a ser utilizada como um controle de composição para hospedar outros controles do Windows Forms. Como essa classe hospeda outros controles, você poderá criar sua interface de usuário personalizada arrastando e soltando os controles, organizando-os, definindo suas propriedades e respondendo em tempo de execução a seus eventos como em qualquer aplicativo do Windows Forms.  
  
### <a name="saving-settings"></a>Salvando configurações  
 Você substitui o método <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumeratorUI.SaveSettings%2A> para copiar os valores selecionados pelo usuário dos controles para as propriedades do enumerador quando o usuário fecha o editor.  
  
![Ícone do Integration Services (pequeno)](../../media/dts-16.gif "ícone do Integration Services (pequeno)")**mantenha-se para cima até o momento com o Integration Services  **<br /> Para obter os downloads, artigos, exemplos e vídeos mais recentes da Microsoft, assim como soluções selecionadas pela comunidade, visite a página do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] no MSDN:<br /><br /> [Visite a página do Integration Services no MSDN](http://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> Para receber uma notificação automática dessas atualizações, assine os RSS feeds disponíveis na página.  
  
## <a name="see-also"></a>Consulte também  
 [Criar um enumerador Foreach personalizado](creating-a-custom-foreach-enumerator.md)   
 [Codificar um enumerador Foreach personalizado](coding-a-custom-foreach-enumerator.md)  
  
  
