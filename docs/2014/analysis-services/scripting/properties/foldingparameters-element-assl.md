---
title: Elemento FoldingParameters (ASSL) | Microsoft Docs
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
topic_type:
- apiref
f1_keywords:
- FoldIndex
- FoldCount
- MaxCases
- FoldingParameters
- FoldTargetAttribute
helpviewer_keywords:
- FoldingParameters element
ms.assetid: 5f5c5a3e-4aed-48fb-bca5-e67f421bef2f
caps.latest.revision: 16
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: 12cae8f4ad02f57f63fd168ff41503f233f53c4c
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36122741"
---
# <a name="foldingparameters-element-assl"></a>Elemento FoldingParameters (ASSL)
  Especifica os parâmetros usados pelo servidor do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] durante a execução de uma validação cruzada de modelos de mineração.  
  
> [!NOTE]  
>  Esses parâmetros são apenas para uso interno. As informações fornecidas aqui servem apenas para referência.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<MiningModel>  
   ...  
   <ddl100_100:FoldingParameters>...  
      <ddl100_100:FoldIndex>...</ddl100_100:FoldIndex>  
      <ddl100_100:FoldCount>...</ddl100_100:FoldCount>  
      <ddl100_100:MaxCases>...</ddl100_100:MAxCases>  
      <ddl100_100:FoldTargetAttribute>...</ddl100_100:FoldTargetAttribute  
...</ddl100_100:FoldingParameters>  
</MiningStructure>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|*FoldIndex*|Inteiro que indica a posição inicial da partição que é usada para validação cruzada.|  
|*FoldCount*|Inteiro que indica o número de partições no modelo depois da validação cruzada.|  
|*MaxCases*|Inteiro que indica quantos casos de modelo são usados para validação cruzada.<br /><br /> Um valor 0 indica que todos os casos são usados.|  
|*FoldTargetAttribute*|Cadeia de caracteres que indica a ID da coluna de modelo que contém o atributo previsível.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elemento pai|[MiningModel](../objects/miningmodel-element-assl.md)|  
|Elementos filho|*FoldIndex*<br /><br /> *FoldCount*<br /><br /> *MaxCases*<br /><br /> *FoldTargetAttribute*|  
  
## <a name="remarks"></a>Remarks  
 Essas propriedades são apenas para uso interno e não são suportadas para serem usadas em instruções DDL.  
  
 Para obter informações sobre como usar a validação cruzada no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], consulte [medidas no relatório de validação cruzada](../../data-mining/measures-in-the-cross-validation-report.md).  
  
 Para obter informações sobre como executar a validação cruzada usando [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] procedimentos armazenados, consulte [mineração de dados armazenados, procedimentos &#40;Analysis Services - mineração de dados&#41;](/sql/analysis-services/data-mining/data-mining-stored-procedures-analysis-services-data-mining).  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades &#40;ASSL&#41;](properties-assl.md)  
  
  