---
title: Detalhes de conversão (guia traduções, Designer de dimensão) (Analysis Services - dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.asvs.dimensiondesigner.translations.translationpane.tranlationdetails.f1
ms.assetid: 0aa61df3-f2b0-4703-a63b-124da672dcc3
caps.latest.revision: 31
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: c3fea9b837915fff37bad632780544bcf7ebb1a5
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36122717"
---
# <a name="translation-details-translations-tab-dimension-designer-analysis-services---multidimensional-data"></a>Detalhes de conversão (guia Conversões, Designer de Dimensão) (Analysis Services - Dados multidimensionais)
  Use o painel **Detalhes da conversão** na guia **Conversões** do Designer de Dimensão para definir e gerenciar conversões da dimensão atualmente selecionada.  
  
 **Para exibir o painel de detalhes da conversão**  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e então abra a dimensão desejada.  
  
2.  Clique na guia **Conversões** .  
  
## <a name="options"></a>Opções  
 **Idioma Padrão**  
 Define os nomes dos objetos de dimensão no idioma padrão.  
  
 **Tipo de objeto**  
 Exibe a propriedade que será traduzida. Só podem ser convertidos objetos e propriedades para os quais foram especificados valores. As seguintes propriedades podem ser traduzidas:  
  
-   Dimensão  
  
     `Caption` e `AttributeAllMember` propriedades  
  
-   attribute  
  
     `Caption`, `AttributeHierarchyDisplayFolder`, e `NamingTemplate` propriedades  
  
    > [!NOTE]  
    >  A propriedade `NamingTemplate` só está disponível para atributos pai.  
  
-   Hierarquia  
  
     `Caption` e `AllMemberName` propriedades  
  
-   Nível  
  
     `Caption` propriedade  
  
 **\<Idioma >**  
 Digite ou selecione o valor de propriedade do objeto de dimensão na linguagem selecionada. Clicar no botão de reticências (**...**) abre caixas de diálogo adicionais, dependendo da propriedade que está sendo editada:  
  
-   `NamingTemplate` propriedade  
  
     Exibe a [Caixa de diálogo Modelo de Nomeação de Nível &#40;Analysis Services - Dados Multidimensionais&#41;](level-naming-template-dialog-box-analysis-services-multidimensional-data.md).  
  
-   `Caption` propriedade (atributos)  
  
     Exibe a [Caixa de diálogo Tradução de Dados de Atributo &#40;Analysis Services - Dados Multidimensionais&#41;](attribute-data-translation-dialog-box-analysis-services-multidimensional-data.md).  
  
## <a name="shortcut-menu"></a>Menu de atalho  
 As opções seguintes estão disponíveis no menu de atalho exibido ao clicar com o botão direito do mouse em uma conversão no painel **Detalhes de Conversão** :  
  
 **Nova tradução**  
 Selecione para exibir a caixa de diálogo **Selecionar Idioma** e criar uma nova tradução. A conversão aparecerá como uma coluna nova na grade **Detalhes de Conversão** .  
  
 **Excluir tradução**  
 Selecione para excluir a tradução selecionada.  
  
> [!NOTE]  
>  A opção só está habilitada se você clicou com o botão direito do mouse em uma célula para excluir a conversão.  
  
 **Nova coluna de legendas**  
 Selecione para exibir a caixa de diálogo **Conversão de Dados de Atributo** e definir uma nova coluna de legendas quando você modificar um atributo na grade **Detalhes de Conversão** . Para habilitar esta opção, é preciso selecionar uma célula na coluna de conversão de um atributo na grade **Detalhes de Conversão** .  
  
> [!NOTE]  
>  A opção só está habilitada se você clicou com o botão direito do mouse em uma célula para excluir a coluna de conversão de um atributo.  
  
 **Editar coluna de legendas**  
 Selecione para exibir a caixa de diálogo **Conversão de Dados de Atributo** e modificar uma coluna de legendas existente quando você modificar um atributo na grade **Detalhes de Conversão** .  
  
> [!NOTE]  
>  A opção só será habilitada se uma célula em uma coluna de conversão que contém a coluna de legendas de um atributo tiver que ser selecionada na grade **Detalhes de Conversão** .  
  
 **Excluir coluna de legendas**  
 Selecione para excluir a coluna de legendas para o atributo selecionado na grade **Detalhes de Conversão** .  
  
> [!NOTE]  
>  A opção só está habilitada se você clicou com o botão direito em uma célula em uma coluna de conversão que contém uma coluna de legendas para um atributo.  
  
 **Mostrar todos os atributos**  
 Selecione para alternar a exibição de todos os atributos definidos para a dimensão selecionada, inclusive atributos para os quais as hierarquias de atributo estão desabilitadas.  
  
## <a name="see-also"></a>Consulte também  
 [Traduções &#40;Designer de dimensão&#41; &#40;Analysis Services - dados multidimensionais&#41;](translations-dimension-designer-analysis-services-multidimensional-data.md)  
  
  