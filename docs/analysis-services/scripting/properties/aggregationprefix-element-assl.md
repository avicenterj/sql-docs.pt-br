---
title: Elemento AggregationPrefix (ASSL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- AggregationPrefix Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- AggregationPrefix
helpviewer_keywords:
- AggregationPrefix element
ms.assetid: 1581e0df-ae8e-41ce-9c92-f0f7cac487f2
caps.latest.revision: 36
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 8ef1688e23bddf1136775474c93ae62a05bb97ab
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="aggregationprefix-element-assl"></a>Elemento AggregationPrefix (ASSL)
  Define o prefixo comum a ser usado para nomes de agregação no elemento pai associado.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Cube> <!-- or Database, MeasureGroup, Partition -->  
   ...  
   <AggregationPrefix>...</AggregationPrefix>  
   ...  
</Database>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|String|  
|Valor padrão|Nenhuma|  
|Cardinalidade|0-1: elemento obrigatório que pode ocorrer apenas uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Cubo](../../../analysis-services/scripting/objects/cube-element-assl.md), [banco de dados](../../../analysis-services/scripting/objects/database-element-assl.md), [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md), [partição](../../../analysis-services/scripting/objects/partition-element-assl.md)|  
|Elementos filho|Nenhuma|  
  
## <a name="remarks"></a>Comentários  
 Prefixos de agregação geram os nomes de agregação em [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]e também gerar nomes de tabela no banco de dados relacional para agregações armazenadas em uma partição OLAP (ROLAP) relacional.  
  
 Um nome de agregação completamente expandido tem as partes a seguir:  
  
 *\<DatabasePrefix >\<CubePrefix >\<MeasureGroupPrefix >\<PartitionPrefix >\<AggregationID >*  
  
 As primeiras quatro partes do nome de agregação compõem o prefixo de agregação. O usuário fornece as primeiras quatro partes:  
  
-   *DatabasePrefix* representa o valor do elemento **AggregationPrefix** associado a um elemento **Database** .  
  
-   *CubePrefix* representa o valor do elemento **AggregationPrefix** associado a um elemento **Cube** .  
  
-   *MeasureGroupPrefix* representa o valor do elemento **AggregationPrefix** associado a um elemento **MeasureGroup** .  
  
-   *PartitionPrefix* representa o valor do elemento **AggregationPrefix** associado a um elemento **Partition** .  
  
 A quinta parte do nome, *AggregationID*, é uma ID definida pelo sistema, e os usuários não têm nenhum controle sobre essa parte do nome.  
  
 Os elementos que correspondem aos pais de **AggregationPrefix** no modelo de objeto de Analysis Management Objects (AMO) são <xref:Microsoft.AnalysisServices.Cube>, <xref:Microsoft.AnalysisServices.Database>, <xref:Microsoft.AnalysisServices.MeasureGroup>, e <xref:Microsoft.AnalysisServices.Partition>.  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  