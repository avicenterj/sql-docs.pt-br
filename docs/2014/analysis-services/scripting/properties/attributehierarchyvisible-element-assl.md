---
title: Elemento AttributeHierarchyVisible (ASSL) | Microsoft Docs
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
- AttributeHierarchyVisible Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- AttributeHierarchyVisible
helpviewer_keywords:
- AttributeHierarchyVisible element
ms.assetid: a3289a9a-dbd6-43e8-a7ca-ee8a1da92a32
caps.latest.revision: 36
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: bb0f2e335a9c8aeb9cdca6e0c95003942800dad9
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37185133"
---
# <a name="attributehierarchyvisible-element-assl"></a>Elemento AttributeHierarchyVisible (ASSL)
  Determina se a hierarquia de atributo é visível a aplicativos cliente.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<DimensionAttribute> <!-- or CubeAttribute or PerspectiveAttribute -->  
   ...  
   <AttributeHierarchyVisible>...</AttributeHierarchyVisible>  
   ...  
</DimensionAttribute>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Booliano|  
|Valor padrão|`True`|  
|Cardinalidade|0-1: elemento opcional que pode ocorrer apenas uma única vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elemento pai|[CubeAttribute](../data-type/cubeattribute-data-type-assl.md), [DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md), [PerspectiveAttribute](../data-type/perspectiveattribute-data-type-assl.md)|  
|Elementos filho|Nenhum|  
  
## <a name="remarks"></a>Remarks  
 O elemento `AttributeHierarchyVisible` determina se a hierarquia de atributo associada ao atributo é visível aos aplicativos cliente. Se este elemento for definido como `False`, a hierarquia de atributo ainda poderá ser usada para criar hierarquias definidas pelo usuário e poderá ser consultada pelas instruções MDX (Multidimensional Expressions).  
  
 Os elementos que correspondem aos pais de `AttributeHierarchyVisible` no modelo de objeto AMO (Objetos de Gerenciamento de Análise) são <xref:Microsoft.AnalysisServices.CubeAttribute>, <xref:Microsoft.AnalysisServices.DimensionAttribute> e <xref:Microsoft.AnalysisServices.PerspectiveAttribute>.  
  
## <a name="see-also"></a>Consulte também  
 [Elemento AttributeHierarchyEnabled &#40;ASSL&#41;](enabled-element-assl.md)   
 [Propriedades &#40;ASSL&#41;](properties-assl.md)  
  
  
