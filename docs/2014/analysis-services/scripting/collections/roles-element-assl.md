---
title: Elemento roles (ASSL) | Microsoft Docs
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
- Roles Element
api_location:
- http://schemas.microsoft.com/analysisservices/2003/engine
topic_type:
- apiref
f1_keywords:
- Roles
helpviewer_keywords:
- Roles element
ms.assetid: 4191b7ce-bae4-4200-8550-3904420efafd
caps.latest.revision: 36
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: b6227c72cc4fdd20b8c739bcb6019a83fbaaaa58
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37295576"
---
# <a name="roles-element-assl"></a>Elemento Roles (ASSL)
  Contém a coleção de elementos [Role](../objects/role-element-assl.md) definidos sob o elemento pai.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Database> <!-- or Server -->  
   ...  
   <Roles>  
      <Role>...</Role>  
   </Roles>  
   ...  
</Database>  
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
|Elementos pai|[Database](../objects/database-element-assl.md), [Server](../objects/server-element-assl.md)|  
|Elementos filho|[Função](../objects/role-element-assl.md)|  
  
## <a name="remarks"></a>Remarks  
 O elemento `Roles` associado a um elemento `Server` contém apenas uma função, chamada Administrators, que representa a função do administrador do servidor. A função de administrador de servidor não pode ser alterada nem excluída, nem podem ser adicionadas funções à coleção.  
  
 O elemento `Roles` associado a um elemento `Database` contém as funções definidas para aquele banco de dados.  
  
 O elemento correspondente no modelo de objeto Analysis Management Objects (AMO) é <xref:Microsoft.AnalysisServices.RoleCollection>.  
  
## <a name="see-also"></a>Consulte também  
 [Coleções &#40;ASSL&#41;](collections-assl.md)  
  
  
