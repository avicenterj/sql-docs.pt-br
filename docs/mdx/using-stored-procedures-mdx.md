---
title: Usando procedimentos armazenados (MDX) | Microsoft Docs
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- kbMDX
helpviewer_keywords:
- user-defined functions [MDX]
- stored procedures [MDX]
ms.assetid: 818fb2ad-f88b-4d0c-9f70-f378aed42e8e
caps.latest.revision: 27
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 2c24641d2be7e4e2130d21881b94a9bcd1698fd7
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="using-stored-procedures-mdx"></a>Usando procedimentos armazenados (MDX)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Você pode estender a funcionalidade do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e da linguagem MDX gravando procedimentos armazenados .NET ou funções definidas pelo usuário. Para obter mais informações, consulte [programação de servidor do ADOMD.NET](../analysis-services/multidimensional-models-adomd-net-server/adomd-net-server-programming.md)  
  
 Quando você faz referência ou chama um procedimento armazenado, você especifica o nome da função seguido por parênteses. Dentro dos parênteses, você pode especificar expressões chamadas argumentos que fornecem dados a serem transmitidos nos parâmetros. Quando você chama uma função, deve fornecer valores de argumentos para todos os parâmetros e especificar os valores de argumentos na mesma sequência na qual os parâmetros são definidos na função definida pelo usuário.  
  
 A consulta de exemplo a seguir supõe que você tem um assembly nomeado SampleAssembly registrado no seu [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Server:  
  
```  
SELECT SampleAssembly.RandomSample([Geography].[State-Province].Members, 5) on ROWS,   
[Date].[Calendar].[Calendar Year] on COLUMNS  
FROM [Adventure Works]  
WHERE [Measures].[Reseller Freight Cost]  
```  
  
> [!NOTE]  
>  *Procedimento armazenado* é a terminologia usada no [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] para esses tipos de funções. Versões anteriores do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] chamado esses tipos de funções como *funções definidas pelo usuário*.  
  
## <a name="types-of-stored-procedures"></a>Tipos de procedimentos armazenados  
 O [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] oferece suporte a assemblies COM e CLR. Recomenda-se assemblies CLR por causa da segurança reforçada disponível para assemblies CLR. Se o Microsoft Office Excel estiver instalado no servidor, as funções do Excel também estarão disponíveis.  
  
> [!NOTE]  
>  Os assemblies COM do Microsoft Visual Basic for Applications (VBA) são automaticamente registrados.  
  
## <a name="see-also"></a>Consulte também  
 [Funções &#40; Sintaxe MDX &#41;](../mdx/functions-mdx-syntax.md)  
  
  
