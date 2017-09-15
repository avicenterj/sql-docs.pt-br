---
title: "Tipo de dados (ASSL) de dimensão | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Dimension Data Type
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- Dimension data type
ms.assetid: 3fe6adc2-5206-44c3-a689-a731705f43ca
caps.latest.revision: 17
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 3db273659dd3401684dbad1fa19b11a92a47f874
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="dimension-data-type-assl"></a>Tipo de dados Dimension (ASSL)
  Define um tipo de dados primitivo que representa uma dimensão de banco de dados.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Dimension>  
   <Name>...</Name>  
   <ID>...</ID>  
   <CreatedTimestamp>...</CreatedTimestamp>  
   <LastSchemaUpdate>...</LastSchemaUpdate>  
   <Description>...</Description>  
   <Source>...</Source>  
   <MiningModelID>...</MiningModelID>  
   <Type>...</Type>  
   <UnknownMember>...</UnknownMember>  
   <MdxMissingMemberMode>...</MdxMissingMemberMode>  
   <ErrorConfiguration>...</ErrorConfiguration>  
   <StorageMode>...</StorageMode>  
   <WriteEnabled>...</WriteEnabled>  
   <ProcessingPriority>...</ProcessingPriority>  
   <LastProcessed>...</LastProcessed>  
   <DimensionPermissions>...</DimensionPermissions>  
   <DependsOnDimensionID>...</DependsOnDimensionID>  
   <Language>...</Language>  
   <Collation>...</Collation>  
   <UnknownMemberName>...</UnknownMemberName>  
   <UnknownMemberTranslations>...</UnknownMemberTranslations>  
   <State>...</State>  
   <ProactiveCaching>...</ProactiveCaching>  
   <ProcessingMode>...</ProcessingMode>  
   <CurrentStorageMode>...</CurrentStorageMode>  
   <Translations>...</Translations>  
   <Attributes>...</Attributes>  
   <AttributeAllMemberName>...</AttributeAllMemberName>  
   <AttributeAllMemberTranslations>...</AttributeAllMemberTranslations>  
   <Hierarchies>...</Hierarchies>  
   <Relationships>...</Annotations>  
   <Annotations>...</Annotations>  
</Dimension>  
```  
  
## <a name="data-type-characteristics"></a>Características do tipo de dados  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|Tipos de dados base|Nenhuma|  
|Tipos de dados derivados|Nenhuma|  
  
## <a name="data-type-relationships"></a>Relação do tipo de dados  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|Nenhuma|  
|Elementos filho|[Annotations](../../../analysis-services/scripting/collections/annotations-element-assl.md), [AttributeAllMemberName](../../../analysis-services/scripting/properties/attributeallmembername-element-assl.md), [AttributeAllMemberTranslations](../../../analysis-services/scripting/collections/attributeallmembertranslations-element-assl.md), [Attributes](../../../analysis-services/scripting/collections/attributes-element-assl.md), [Collation](../../../analysis-services/scripting/properties/collation-element-assl.md), [CreatedTimestamp](../../../analysis-services/scripting/properties/createdtimestamp-element-assl.md), [CurrentStorageMode](../../../analysis-services/scripting/properties/currentstoragemode-element-assl.md), [DependsOnDimensionID](../../../analysis-services/scripting/properties/dependsondimensionid-element-assl.md), [Description](../../../analysis-services/scripting/properties/description-element-assl.md), [DimensionPermissions](../../../analysis-services/scripting/collections/dimensionpermissions-element-assl.md), [ErrorConfiguration](../../../analysis-services/scripting/objects/errorconfiguration-element-assl.md), [Hierarchies](../../../analysis-services/scripting/collections/hierarchies-element-assl.md), [ID](../../../analysis-services/scripting/properties/id-element-assl.md), [Language](../../../analysis-services/scripting/properties/language-element-assl.md), [LastProcessed](../../../analysis-services/scripting/properties/lastprocessed-element-assl.md), [LastSchemaUpdate](../../../analysis-services/scripting/properties/lastschemaupdate-element-assl.md), [MdxMissingMemberMode](../../../analysis-services/scripting/properties/mdxmissingmembermode-element-assl.md), [MiningModelID](../../../analysis-services/scripting/properties/miningmodelid-element-assl.md), [Name](../../../analysis-services/scripting/properties/name-element-assl.md), [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md), [ProcessingMode](../../../analysis-services/scripting/properties/processingmode-element-assl.md), [ProcessingPriority](../../../analysis-services/scripting/properties/processingpriority-element-assl.md), [Relationships](../../../analysis-services/scripting/collections/relationships-element-assl.md), [Source](../../../analysis-services/scripting/properties/source-element-binding-assl.md), [State](../../../analysis-services/scripting/properties/state-element-assl.md), [StorageMode](../../../analysis-services/scripting/properties/storagemode-element-assl.md), [Translations](../../../analysis-services/scripting/collections/translations-element-assl.md), [Type](../../../analysis-services/scripting/properties/type-element-dimension-assl.md), [UnknownMember](../../../analysis-services/scripting/properties/unknownmember-element-assl.md), [UnknownMemberName](../../../analysis-services/scripting/properties/unknownmembername-element-assl.md), [UnknownMemberTranslations](../../../analysis-services/scripting/collections/unknownmembertranslations-element-assl.md), [WriteEnabled](../../../analysis-services/scripting/properties/writeenabled-element-assl.md)|  
|Elementos derivados|[Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md)|  
  
## <a name="remarks"></a>Comentários  
 Este tipo de dados tem as validações a seguir nos valores 1 (SharePoint) e 2 (Tabular) de DeploymentMode.  
  
-   *WriteEnabled* deve ser definido como **False**  
  
-   *UnknownMember* deve ser definido como **AutomaticNull**  
  
-   Todos os atributos exclusivos devem ter elemento filho *NullProcessing* definido como **Error**  
  
 Não há suporte para os atributos filho a seguir sob os valores 1 (SharePoint) e 2 (Tabular) de DeploymentMode.  
  
-   *DimensionPermissions*  
  
-   *MiningModelID*  
  
-   *ProactiveCaching*  
  
 Os elementos correspondentes no modelo de objeto Analysis Management Objects (AMO) são <xref:Microsoft.AnalysisServices.Dimension>, <xref:Microsoft.AnalysisServices.AggregationDimension>, <xref:Microsoft.AnalysisServices.AggregationDesignDimension>, <xref:Microsoft.AnalysisServices.CubeDimension>, <xref:Microsoft.AnalysisServices.MeasureGroupDimension>, e <xref:Microsoft.AnalysisServices.PerspectiveDimension>.  
  
## <a name="see-also"></a>Consulte também  
 [Tipos de dados XML de linguagem de script &#40; do Analysis Services ASSL &#41;](../../../analysis-services/scripting/data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  