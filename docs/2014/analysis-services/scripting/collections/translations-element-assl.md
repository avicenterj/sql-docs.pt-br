---
title: Elemento translations (ASSL) | Microsoft Docs
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
- Translations Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- Translations
helpviewer_keywords:
- Translations element
ms.assetid: 7f6b8ff2-e834-44d3-a176-216203158a8d
caps.latest.revision: 38
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 215928497bdaaf85a0672f05e94d69baae56eabb
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37210136"
---
# <a name="translations-element-assl"></a>Elemento Translations (ASSL)
  Contém a coleção de [tradução](../objects/translation-element-assl.md) elementos associados ao elemento pai.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Action><!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <Translations>  
      <Translation>...</Translation>  
      <!-- or -->  
      <Translation xsi:type="AttributeTranslation">...</Translation><!-- parent: DimensionAttribute or ScalarMiningStructureColumn -->  
      <!-- or -->  
      <Translation xsi:type="RelationshipEndTranslation">...</Translation><!-- parent: RelationshipEnd -->  
   </Translations>  
   ...  
</Action>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhum|  
|Valor padrão|Nenhum|  
|Cardinalidade|0-1: elemento opcional que pode ocorrer apenas uma única vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Ação](../objects/action-element-assl.md), [AttributeRelationship](../objects/attributerelationship-element-assl.md), [CalculationProperty](../objects/calculationproperty-element-assl.md), [cubo](../objects/cube-element-assl.md), [CubeDimension](../data-type/dimension-data-type-assl.md), [ Banco de dados](../objects/database-element-assl.md), [dimensão](../objects/dimension-element-assl.md), [DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md), [hierarquia](../objects/hierarchy-element-assl.md), [Kpi](../objects/kpi-element-assl.md), [ Nível](../objects/level-element-assl.md), [medida](../objects/measure-element-assl.md), [MiningModel](../objects/miningmodel-element-assl.md), [MiningModelColumn](../data-type/miningmodelcolumn-data-type-assl.md), [MiningStructure](../objects/miningstructure-element-assl.md), [Perspectiva](../objects/perspective-element-assl.md), [RelationshipEnd](../data-type/relationshipend-data-type-assl.md), [ScalarMiningStructureColumn](../data-type/miningstructurecolumn-data-type-assl.md), [TableMiningStructureColumn](../data-type/tableminingstructurecolumn-data-type-assl.md)|  
  
 **Elementos filho**  
  
|Ancestral ou pai|Elemento filho|  
|------------------------|-------------------|  
|[DimensionAttribute](../data-type/dimensionattribute-data-type-assl.md) ou [ScalarMiningStructureColumn](../data-type/miningstructurecolumn-data-type-assl.md)|[Tradução](../objects/translation-element-assl.md) do tipo [AttributeTranslation](../data-type/translation-data-type-assl.md)|  
|[RelationshipEnd](../data-type/relationshipendtranslation-element-assl.md) do tipo [RelationshipEndTranslation](../data-type/relationshipendtranslation-element-assl.md)|  
|Todos os outros|[Tradução](../objects/translation-element-assl.md)|  
  
## <a name="remarks"></a>Remarks  
 Os elementos correspondentes no modelo de objeto AMO (Objetos de Gerenciamento de Análise) são <xref:Microsoft.AnalysisServices.TranslationCollection> e <xref:Microsoft.AnalysisServices.AttributeTranslationCollection>.  
  
## <a name="see-also"></a>Consulte também  
 [Coleções &#40;ASSL&#41;](collections-assl.md)  
  
  
