---
title: Modificação de dados (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- modifying data [MDX]
- Multidimensional Expressions [Analysis Services], data modifications
- MDX [Analysis Services], data modifications
- data modifications [MDX]
ms.assetid: 363b662c-b839-4971-bbd7-1842f73ce141
caps.latest.revision: 29
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 98d437607eef280696766853f890e3827e000812
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37261383"
---
# <a name="modifying-data-mdx"></a>Modificando dados (MDX)
  Além de usar a linguagem MDX para recuperar e manipular dados de dimensões e cubos, você pode usá-la para atualizar ou executar *write-back* de dados de dimensão e de cubo. Essas atualizações podem ser temporárias, como na análise teórica (ou"what if"), ou permanentes, como quando alterações devem ser feitas com base na análise dos dados.  
  
 As atualizações de dados podem ocorrer no nível de dimensão ou de cubo:  
  
 **Write-backs de dimensão**  
 Use a [Instrução ALTER CUBE (MDX)](/sql/mdx/mdx-data-definition-alter-cube) para alterar os dados de uma dimensão habilitada para gravação e a [Instrução REFRESH CUBE (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) para refletir a exclusão, criação e atualização de valores de atributo. Você também pode usar a instrução ALTER CUBE para executar operações complexas, como excluir uma subárvore inteira de uma hierarquia e promover os filhos de um membro excluído.  
  
 **Write-backs de cubo**  
 Use a instrução [UPDATE CUBE](/sql/mdx/mdx-data-manipulation-update-cube) para fazer atualizações em um cubo habilitado para gravação. A instrução UPDATE CUBE permite atualizar uma tupla com um valor específico. Use a [Instrução REFRESH CUBE (MDX)](/sql/mdx/mdx-data-definition-refresh-cube) para atualizar dados de uma sessão de cliente com dados atualizados do servidor.  
  
 Para obter mais informações, consulte [Usando write-backs de cubo &#40;MDX&#41;](mdx-data-modification-using-cube-writebacks.md).  
  
## <a name="see-also"></a>Consulte também  
 [Conceitos básicos de consulta MDX &#40;Analysis Services&#41;](mdx-query-fundamentals-analysis-services.md)  
  
  
