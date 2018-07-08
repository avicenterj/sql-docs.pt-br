---
title: Ferramentas de cálculo (guia KPIs, Designer de cubo) (Analysis Services - dados multidimensionais) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.asvs.cubeeditor.kpisview.calculationtoolspane.f1
ms.assetid: c030c725-7763-4c23-9988-4b274a88fc31
caps.latest.revision: 24
author: Minewiskan
ms.author: owend
manager: mblythe
ms.openlocfilehash: c03f8506de2a1f0744fcc9fcebd025443ffafaa4
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36007166"
---
# <a name="calculation-tools-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a>Ferramentas de Cálculo (guia KPIs, Designer de Cubo) (Analysis Services - Dados Multidimensionais)
  Use o painel **Ferramentas de Cálculo** da guia **KPIs** no Designer de Cubo para explorar metadados, funções e modelos disponíveis para uso em KPIs (indicadores chave de desempenho).  
  
> [!NOTE]  
>  Este painel é exibido apenas na exibição de formulário.  
  
## <a name="options"></a>Opções  
 **Metadados**  
 Exibe os metadados do cubo selecionado.  
  
 Arraste um elemento selecionado para o painel **Editor de Formulário de KPI** para incluir a sintaxe MDX daquele elemento no local selecionado no painel.  
  
 **Funções**  
 Exibe as funções disponíveis para expressões e condições.  
  
 Arraste um elemento selecionado para o painel **Editor de Formulário de KPI** para incluir a sintaxe MDX daquele elemento no local selecionado no painel.  
  
> [!NOTE]  
>  No modo de projeto, a caixa de diálogo **Ferramentas de Cálculo** lê as informações desta opção em um arquivo XML denominado MDXFunctions.xml fornecido com o [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]. Em modo online, informações para esta opção são recuperadas do conjunto de linhas de esquema de MDSCHEMA_FUNCTIONS da instância.  
  
 **Modelos**  
 Exibe os modelos predefinidos disponíveis para KPIs.  
  
 Arraste um elemento selecionado para o painel **Editor de Formulário de KPI** para incluir a sintaxe MDX daquele elemento no local selecionado no painel.  
  
## <a name="context-menu"></a>Menu de contexto  
 As seguintes opções estão disponíveis no menu de contexto exibido ao clicar com o botão direito do mouse em um elemento exibido no painel **Ferramentas de Cálculo** :  
  
 **Copiar**  
 Selecione para copiar o elemento selecionado em **Metadados** ou **Funções** na Área de Transferência.  
  
> [!NOTE]  
>  Esta opção não será exibida se a opção **Modelos** estiver selecionada.  
  
> [!NOTE]  
>  Esta opção será desabilitada se o membro selecionado não puder ser copiado, como a pasta **Conjuntos** de uma dimensão exibida em **Metadados** ou a pasta de grupo de funções de uma função exibida em **Funções**.  
  
 **Filtrar membros**  
 Clique para exibir a caixa de diálogo **Filtrar Membros** e filtrar os membros exibidos para o elemento selecionado em **Metadados**. Para obter mais informações sobre a caixa de diálogo **Filtrar Membros**, consulte [Caixa de diálogo Filtrar Membros &#40;Analysis Services – Dados Multidimensionais&#41;](filter-members-dialog-box-analysis-services-multidimensional-data.md).  
  
> [!NOTE]  
>  Esta opção será exibida apenas se a opção **Metadados** estiver selecionada.  
  
> [!NOTE]  
>  Esta opção estará habilitada apenas se um nível de um atributo estiver selecionado em **Metadados**.  
  
 **Adicionar modelo**  
 Selecione para adicionar um novo membro calculado, conjunto nomeado ou comando de script baseado no modelo selecionado ao script do cubo e exibir a exibição de formulário no **Editor de Formulário de KPI** .  
  
> [!NOTE]  
>  Esta opção será exibida apenas se a opção **Metadados** estiver selecionada.  
  
## <a name="see-also"></a>Consulte também  
 [Designer de cubo &#40;Analysis Services - dados multidimensionais&#41;](cube-designer-analysis-services-multidimensional-data.md)   
 [KPIs &#40;Designer de cubo&#41; &#40;Analysis Services - dados multidimensionais&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md)   
 [Barra de ferramentas &#40;guia KPIs, Designer de cubo&#41; &#40;Analysis Services - dados multidimensionais&#41;](toolbar-kpis-tab-cube-designer-analysis-services-multidimensional-data.md)   
 [Organizador de KPIS &#40;guia KPIs, Designer de cubo&#41; &#40;Analysis Services - dados multidimensionais&#41;](kpi-organizer-kpis-tab-cube-designer-analysis-services-multidimensional-data.md)   
 [Editor de formulário KPI &#40;guia KPIs, Designer de cubo&#41; &#40;Analysis Services - dados multidimensionais&#41;](kpi-form-editor-kpis-tab-cube-designer-analysis-services-multidimensional-data.md)   
 [Navegador KPI &#40;guia KPIs, Designer de cubo&#41; &#40;Analysis Services - dados multidimensionais&#41;](kpi-browser-kpis-tab-cube-designer-analysis-services-multidimensional-data.md)  
  
  