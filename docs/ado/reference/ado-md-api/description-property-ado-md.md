---
title: Propriedade Description (ADO MD) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Member::Description
- Level::Description
- CubeDef::Description
- Hierarchy::Description
- Description
- Dimension::Description
helpviewer_keywords:
- Description property [ADO MD]
ms.assetid: 6d626d35-0bf3-4f24-9934-ad9c9c91273a
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b073b4719de6554159947502a525d242f37e6707
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35284065"
---
# <a name="description-property-ado-md"></a>Propriedade Description (ADO MD)
Retorna uma explicação do texto do objeto atual.  
  
## <a name="return-values"></a>Valores de retorno  
 Retorna um **cadeia de caracteres** e é somente leitura.  
  
## <a name="remarks"></a>Remarks  
 Para [membro](../../../ado/reference/ado-md-api/member-object-ado-md.md) objetos, **descrição** só se aplica a medidas e membros de fórmula. **Descrição** retorna uma cadeia de caracteres vazia ("") para todos os outros tipos de membros. Para obter mais informações sobre os vários tipos de membros, consulte o [tipo](../../../ado/reference/ado-md-api/type-property-ado-md.md) propriedade.  
  
 Essa propriedade só é suportada em **membro** objetos que pertencem a um [nível](../../../ado/reference/ado-md-api/level-object-ado-md.md) objeto. Ocorre um erro quando essa propriedade é referenciada em **membro** objetos que pertencem a um [posição](../../../ado/reference/ado-md-api/position-object-ado-md.md) objeto.  
  
## <a name="applies-to"></a>Aplica-se a  
  
||||  
|-|-|-|  
|[Objeto CubeDef (ADO MD)](../../../ado/reference/ado-md-api/cubedef-object-ado-md.md)|[Objeto Dimension (ADO MD)](../../../ado/reference/ado-md-api/dimension-object-ado-md.md)|[Objeto Hierarchy (ADO MD)](../../../ado/reference/ado-md-api/hierarchy-object-ado-md.md)|  
|[Objeto Level (ADO MD)](../../../ado/reference/ado-md-api/level-object-ado-md.md)|[Objeto Member (ADO MD)](../../../ado/reference/ado-md-api/member-object-ado-md.md)||
