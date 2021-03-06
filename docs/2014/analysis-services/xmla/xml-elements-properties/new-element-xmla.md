---
title: Elemento New (XMLA) | Microsoft Docs
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
- New Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#New
- microsoft.xml.analysis.new
- urn:schemas-microsoft-com:xml-analysis#New
helpviewer_keywords:
- New element
ms.assetid: 1321adcb-67f7-40f0-8f20-b17c1d3e3f17
caps.latest.revision: 11
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: f93da2c5c9dab8b8d7542db68e70df67a87afbe8
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37203976"
---
# <a name="new-element-xmla"></a>Elemento New (XMLA)
  Contém o novo local de armazenamento de sistema de arquivos usado por um [pasta](folder-element-xmla.md) elemento.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Folder>  
   ...  
   <New>...</New>  
   ...  
</Folder>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Cadeia de caracteres|  
|Valor padrão|Nenhum|  
|Cardinalidade|1-1: elemento obrigatório que ocorre apenas uma única vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Pasta](folder-element-xmla.md)|  
|Elementos filho|Nenhum|  
  
## <a name="remarks"></a>Remarks  
 O elemento `New` contém um caminho UNC que substitui o valor do elemento `Original` contido pelo elemento pai `Folder` para todos os objetos restaurados ou sincronizados, respectivamente, durante um comando `Restore` ou `Synchronize`. O valor do elemento `Original` é comparado ao valor do elemento `StorageLocation` para cada cubo, grupo de medidas ou partição e, se for encontrada uma correspondência, o valor deste elemento será usado para atualizar `StorageLocation` do objeto durante a restauração ou sincronização.  
  
 Para obter mais informações sobre backup e restauração de objetos, consulte [fazendo backup e restaurando objetos (XMLA)](../../multidimensional-models-scripting-language-assl-xmla/backing-up-restoring-and-synchronizing-databases-xmla.md).  
  
## <a name="see-also"></a>Consulte também  
 [Elemento original &#40;XMLA&#41;](original-element-xmla.md)   
 [Restaurar o elemento &#40;XMLA&#41;](../xml-elements-commands/restore-element-xmla.md)   
 [Elemento StorageLocation &#40;ASSL&#41;](../../scripting/properties/storagelocation-element-assl.md)   
 [Elemento Synchronize &#40;XMLA&#41;](../xml-elements-commands/synchronize-element-xmla.md)   
 [Propriedades &#40;XMLA&#41;](xml-elements-properties.md)  
  
  
