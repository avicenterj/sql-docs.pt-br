---
title: Atributo de elemento (ASSL) | Microsoft Docs
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
- Attribute Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- Attribute
helpviewer_keywords:
- Attribute element
ms.assetid: 079ec9f8-a314-4e3c-821a-b42c65cc7363
caps.latest.revision: 34
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 8e94fcb4fdffacfad0bbf735bfc2fe3c7b19b798
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37171457"
---
# <a name="attribute-element-assl"></a>Elemento Attribute (ASSL)
  Contém a descrição de um atributo.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Attributes>  
   <Attribute xsi:type="AggregationAttribute">...</Attribute> <!-- ancestor: AggregationDimension -->  
   <!-- or -->  
   <Attribute xsi:type="AggregationDesignAttribute">...</Attribute> <!-- ancestor: AggregationDesignDimension -->  
   <!-- or -->  
   <Attribute xsi:type="AggregationInstanceAttribute">...</Attribute> <!-- ancestor: AggregationInstanceCubeDimension -->  
   <!-- or -->  
   <Attribute xsi:type="CubeAttribute">...</Attribute> <!--ancestor:  CubeDimension -->  
   <!-- or -->  
   <Attribute xsi:type="DimensionAttribute">...</Attribute> <!-- ancestor: Dimension -->  
   <!-- or -->  
   <Attribute xsi:type="MeasureGroupAttribute">...</Attribute> <!-- ancestor: RegularMeasureGroupDimension -->  
   <!-- or -->  
   <Attribute xsi:type="PerspectiveAttribute">...</Attribute> <!-- ancestor: PerspectiveDimension -->  
   <!-- or -->  
   <Attribute>  
      <AttributeID>...</AttributeID>  
   </Attribute> <!-- ancestor: RelationshipEnd -->  
</Attributes>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
 Valor padrão: nenhum  
  
 Cardinalidade: 0-1: elemento opcional que pode ocorrer apenas uma vez.  
  
|Ancestral ou pai|Tipo de Dados|  
|------------------------|---------------|  
|[AggregationDesignDimension](../data-type/aggregationdesignattribute-data-type-assl.md)|  
|[AggregationDimension](../data-type/aggregationattribute-data-type-assl.md)|  
|[AggregationInstanceCubeDimension](../data-type/aggregationinstanceattribute-data-type-assl.md)|  
|[CubeDimension](../data-type/cubeattribute-data-type-assl.md)|  
|[Dimension](../data-type/dimensionattribute-data-type-assl.md)|  
|[RegularMeasureGroupDimension](../data-type/measuregroupattribute-data-type-assl.md)|  
|[PerspectiveDimension](../data-type/perspectiveattribute-data-type-assl.md)|  
|[RelationshipEnd](../data-type/relationshipend-data-type-assl.md)|\<Atributo ><br />      \<[AttributeID](../properties/id-element-assl.md)>... \</AttributeID > \< /atributo >|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Atributos](../collections/attributes-element-assl.md)|  
|Elementos filho|Nenhum|  
  
## <a name="remarks"></a>Remarks  
 Os elementos correspondentes no modelo de objeto Analysis Management Objects (AMO) são <xref:Microsoft.AnalysisServices.AggregationDesignAttribute>, <xref:Microsoft.AnalysisServices.AggregationAttribute>, <xref:Microsoft.AnalysisServices.CubeAttribute>, <xref:Microsoft.AnalysisServices.DimensionAttribute>, <xref:Microsoft.AnalysisServices.MeasureGroupAttribute>, e <xref:Microsoft.AnalysisServices.PerspectiveAttribute>.  
  
## <a name="see-also"></a>Consulte também  
 [Objetos &#40;ASSL&#41;](objects-assl.md)  
  
  
