---
title: Elemento Binding (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- Binding Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- microsoft.xml.analysis.binding
- http://schemas.microsoft.com/analysisservices/2003/engine#Binding
- urn:schemas-microsoft-com:xml-analysis#Binding
helpviewer_keywords:
- Binding element
ms.assetid: d5acd8d4-8551-449a-ae30-d0ba828cc02d
caps.latest.revision: 13
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: ec223f5a56ea32388a3485f39db0bbbc494fda85
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37203963"
---
# <a name="binding-element-xmla"></a>Elemento Binding (XMLA)
  Define uma associação fora de linha para um [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] objeto, como um atributo em uma dimensão, para o [associações](bindings-element-xmla.md) coleção de um [lote](../xml-elements-commands/batch-element-xmla.md) ou [ Processo](../xml-elements-commands/process-element-xmla.md) comando.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Bindings>  
   <Binding xsi:type="DimensionAttributeBinding">...</Binding>  
   <!-- or -->  
   <Binding xsi:type="MeasureGroupAttributeBinding">...</Binding>  
   <!-- or -->  
   <Binding xsi:type="PartitionBinding">...</Binding>  
</Bindings>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|[DimensionAttributeBinding](../../scripting/data-type/dimensionattributebinding-data-type-out-of-line-assl.md), [MeasureGroupAttributeBinding](../../scripting/data-type/measuregroupattributebinding-data-type-out-of-line-assl.md), [PartitionBinding](../../scripting/data-type/binding-data-type-assl.md)|  
|Valor padrão|Nenhum|  
|Cardinalidade|0-n: Elemento opcional que pode ocorrer mais de uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Associações](bindings-element-xmla.md)|  
|Elementos filho|Nenhum|  
  
## <a name="remarks"></a>Remarks  
 Os elementos `Binding` definem associações fora de linha, diferentes da fonte de dados e das exibições da fonte de dados, para objetos a serem processados por um comando [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] `Batch` ou `Process`. Para obter mais informações sobre processamento de objetos, consulte [processamento de objetos do &#40;XMLA&#41;](../xml-elements-objects.md).  
  
 Para obter mais informações sobre associações fora de linha, consulte [fontes de dados e associações &#40;Multidimensional do SSAS&#41;](../../multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades &#40;XMLA&#41;](xml-elements-properties.md)  
  
  
