---
title: Revise o uso de agregação (Assistente de Design de agregação) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.asvs.aggregationdesignwizard.reviewusage.f1
ms.assetid: 107ee872-3df2-4931-b56c-af11e38f6745
caps.latest.revision: 8
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 1c0027b2bceada8bfe84f0ee835395dd62686d16
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37332806"
---
# <a name="review-aggregation-usage-aggregation-design-wizard"></a>Revisar Uso de Agregação (Assistente de Design de Agregação)
  Use a página **Revisar Uso de Agregação** para efetuar configurações do uso de agregação.  
  
## <a name="options"></a>Opções  
 **Default**  
 Selecione para definir a configuração do uso de agregação do atributo como Padrão. Quando essa configuração é utilizada, o designer aplica uma regra padrão com base no tipo de atributo e dimensão.  
  
 `Full`  
 Selecione para definir a configuração de uso de agregação do atributo a ser `Full`. Quando essa configuração é utilizada, cada agregação para o cubo deve incluir esse atributo ou um atributo relacionado inferior na cadeia de atributos. O `Full` configuração de uso de agregação deve ser evitada quando um atributo contiver muitos membros. Se for especificada para vários atributos ou atributos que têm muitos membros, essa configuração poderá impedir a criação de agregações por causa do seu tamanho excessivo.  
  
 **Nenhuma**  
 Selecione para definir a configuração do uso de agregação do atributo como Nenhum. Quando essa configuração é utilizada, nenhuma agregação para o cubo pode incluir esse atributo.  
  
 `Unrestricted`  
 Selecione para definir a configuração de uso de agregação do atributo a ser `Unrestricted`. Quando essa configuração é utilizada , não são impostas restrições sobre o designer de agregação; porém, o atributo ainda deve ser avaliado para determinar se é um candidato de agregação valioso.  
  
 **Definir tudo como padrão**  
 Selecione para definir a configuração do uso de agregação de todos os atributos como Padrão.  
  
## <a name="see-also"></a>Consulte também  
 [Ajuda de F1 do Assistente de Design de agregação](aggregation-design-wizard-f1-help.md)   
 [Assistentes do Analysis Services &#40;dados multidimensionais&#41;](analysis-services-wizards-multidimensional-data.md)  
  
  
