---
title: Tipo de dados PerspectiveAction (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- PerspectiveAction Data Type
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- PerspectiveAction
helpviewer_keywords:
- PerspectiveAction data type
ms.assetid: a0e4a545-688c-4d4e-b05f-0008d3503349
caps.latest.revision: 34
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 8886962d5b2014d3cdaa466861d4693319d21d34
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37316906"
---
# <a name="perspectiveaction-data-type-assl"></a>Tipo de dados PerspectiveAction (ASSL)
  Define um tipo de dados primitivo que representa informações sobre uma ação em um [perspectiva](../objects/perspective-element-assl.md) elemento.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<PerspectiveAction>  
   <ActionID>...</ActionID>  
   <Annotations>...</Annotations>  
</PerspectiveAction>  
```  
  
## <a name="data-type-characteristics"></a>Características do tipo de dados  
  
|Característica|Description|  
|--------------------|-----------------|  
|Tipos de dados base|Nenhum|  
|Tipos de dados derivados|Nenhum|  
  
## <a name="data-type-relationships"></a>Relação do tipo de dados  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|Nenhum|  
|Elementos filho|[ActionID](../properties/id-element-assl.md), [anotações](../collections/annotations-element-assl.md)|  
|Elementos derivados|[Ação](../objects/action-element-assl.md) ([ações](../collections/actions-element-assl.md) coleção de [perspectiva](../objects/perspective-element-assl.md))|  
  
## <a name="remarks"></a>Remarks  
 O elemento correspondente no modelo de objeto Analysis Management Objects (AMO) é <xref:Microsoft.AnalysisServices.PerspectiveAction>.  
  
## <a name="see-also"></a>Consulte também  
 [Tipos de dados XML de linguagem script do Analysis Services &#40;ASSL&#41;](analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
