---
title: Elemento ReadWriteMode | Microsoft Docs
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
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- ReadWriteMode command
ms.assetid: 379bcaca-bb7e-4934-a9e7-21f8ede2fdc7
caps.latest.revision: 13
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 3075b7834f7e24004811ce3802dd5fcb55b56f6c
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="readwritemode-element"></a>Elemento ReadWriteMode
  A propriedade do banco de dados **ReadWriteMode** especifica se o banco de dados está no modo **ReadWrite** ou no modo **ReadOnly** . Estes são os únicos dois possíveis valores da propriedade.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Database>  
...  
   <ddlns_100_0:ReadWriteMode>...</ddlns_100_0:ReadWriteMode>  
...  
</Database>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Cadeia de caracteres (enumeração)|  
|Valor padrão|ReadWrite|  
|Cardinalidade|0-1: Elemento opcional que pode ocorrer mais de uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Banco de dados](../../../analysis-services/xmla/xml-elements-properties/database-element-xmla.md)|  
|Elementos filho|Nenhuma|  
  
## <a name="remarks"></a>Comentários  
 Bancos de dados são criados somente no modo **ReadWrite** . Não podem ser criados Bancos de dados em modo **ReadOnly** .  
  
 O valor do elemento **ReadWriteMode** é limitado a uma das cadeias de caracteres listadas na tabela a seguir.  
  
|Valor|Description|  
|-----------|-----------------|  
|*Somente leitura*|Nenhuma alteração nem atualização pode ser aplicada ao banco de dados.|  
|*ReadWrite*|Alterações e atualizações podem ser aplicadas ao banco de dados.|  
  
## <a name="see-also"></a>Consulte também  
 [Elemento Attach](../../../analysis-services/xmla/xml-elements-commands/attach-element.md)   
 [Anexar e desanexar bancos de dados do Analysis Services](../../../analysis-services/multidimensional-models/attach-and-detach-analysis-services-databases.md)   
 [Mover um banco de dados do Analysis Services](../../../analysis-services/multidimensional-models/move-an-analysis-services-database.md)   
 [Banco de dados ReadWriteModes](../../../analysis-services/multidimensional-models/database-readwritemodes.md)   
 [Alternar um banco de dados do Analysis Services entre os modos ReadOnly e ReadWrite](../../../analysis-services/multidimensional-models/switch-an-analysis-services-database-between-readonly-and-readwrite-modes.md)  
  
  