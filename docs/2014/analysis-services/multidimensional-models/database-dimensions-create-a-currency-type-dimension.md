---
title: Criar uma dimensão de tipo de moeda | Microsoft Docs
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
- dimensions [Analysis Services], currency
- currency [Analysis Services]
- converting currency
- currency dimensions [Analysis Services]
ms.assetid: b1f037d1-ce47-4e47-a1c2-5ec9e781cff6
caps.latest.revision: 16
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 7b9eb36a77501a7195c18138eab0d767fc7aed63
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37232016"
---
# <a name="create-a-currency-type-dimension"></a>Criar uma dimensão de tipo de moeda
  No [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], uma dimensão de tipo de moeda é aquela cujos atributos representam uma lista de moedas para uso em relatórios financeiros.  
  
 Uma dimensão de moeda permite a inclusão de recursos de conversão de moeda em um cubo do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Para adicionar a conversão de moeda a um cubo, use o Assistente de Business Intelligence para definir um comando de script MDX que converte medidas monetárias nos valores apropriados para a localidade do aplicativo cliente. Para criar esse script MDX, o Assistente de Business Intelligence precisa das seguintes informações:  
  
-   Uma dimensão de moeda que representa as moedas de origem. (Essa dimensão é a dimensão de moeda de origem.)  
  
-   Um grupo de medidas que representa as taxas de câmbio que serão usadas.  
  
 Com essas informações, o Assistente de Business Intelligence criará o processo de conversão de moedas que identificará a dimensão da moeda de destino apropriada (a dimensão de moeda que representa as moedas de destino). Dependendo do número de conversões de moeda que a solução de business intelligence precisar, o Assistente de Business Intelligence pode definir várias dimensões de moeda de destino. Para obter mais informações sobre como definir conversões de moeda, consulte [Conversões de moeda &#40;Analysis Services&#41;](../currency-conversions-analysis-services.md).  
  
 Para identificar uma dimensão como dimensão de moeda, defina as `Type` propriedade da dimensão como `Currency`.  
  
## <a name="dimension-structure"></a>Estrutura da Dimensão  
 Uma dimensão de moeda contém, no mínimo, um atributo de chave que identifica cada moeda da tabela de dimensões da dimensão de moeda. O valor do atributo de chave é diferente nas dimensões de moeda de origem e destino:  
  
-   Para identificar um atributo como atributo de chave de uma dimensão de moeda de origem, defina a propriedade `Type` do atributo como `CurrencySource`.  
  
-   Para identificar um atributo como dimensão de moeda de destino, defina as `Type` propriedade do atributo a ser `CurrencyDestination`.  
  
 Para geração de relatório, tanto a dimensão de moeda de origem como a de destino podem conter, opcionalmente, os seguintes atributos:  
  
-   Um atributo de nome da moeda.  
  
     Para identificar um atributo como nome da moeda, defina a propriedade `Type` do atributo como `CurrencyName`.  
  
-   Um atributo de origem da moeda.  
  
     Para identificar um atributo como atributo de origem da moeda, defina a propriedade `Type` do atributo como `CurrencySource`.  
  
-   Um código de moeda da Organização de Padronização Internacional (ISO).  
  
     Para identificar um atributo como atributo de código ISO da moeda, defina as `Type` propriedade do atributo a ser `CurrencyIsoCode`.  
  
 Para obter mais informações sobre tipos de atributos, consulte [Configurar tipos de atributo](attribute-properties-configure-attribute-types.md).  
  
## <a name="defining-account-intelligence-with-the-business-intelligence-wizard"></a>Definindo inteligência de conta com o Assistente de Business Intelligence  
 Depois de configurar a dimensão de conta e adicioná-la a um cubo, você pode usar o Assistente de Business Intelligence para adicionar à dimensão funcionalidades de inteligência de conta, como identificação e mapeamento de tipos de conta. Para obter mais informações, consulte [Adicionar inteligência de conta a uma dimensão](bi-wizard-add-account-intelligence-to-a-dimension.md).  
  
## <a name="see-also"></a>Consulte também  
 [Atributos e hierarquias de atributo](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md)   
 [Ajuda de F1 do Assistente do Business Intelligence](../business-intelligence-wizard-f1-help.md)   
 [Tipos de dimensão](../multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
