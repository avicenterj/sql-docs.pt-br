---
title: Guia de transição de Cluster (Visualizador do modelo de mineração) de Clusterização de sequência | Microsoft Docs
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
- sql12.dm.miningmodeleditor.sequenceclustering.transition.f1
ms.assetid: 40aef457-d69f-4905-a2d3-924c37bd3d97
caps.latest.revision: 23
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 307f14f06354195147f32cbcf338d4b04e852b9c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37156877"
---
# <a name="sequence-clustering-cluster-transition-tab-mining-model-viewer"></a>Guia Transição de Cluster do clustering de sequências (Visualizador do Modelo de Mineração)
  A guia **Transições de Estado** no **Visualizador MSC** fornece uma visão mais detalhada das transições entre pares atributo-valor ou estados no cluster selecionado.  
  
 Use esta exibição de um modelo de clustering de sequência para exibir padrões. No diagrama, um link representa a probabilidade de uma transição e um nó representa um estado de sequência.  
  
 **Para obter mais informações:** [Algoritmo MSC](data-mining/microsoft-sequence-clustering-algorithm.md), [Procurar um modelo usando o Visualizador de Cluster de Sequência da Microsoft](data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)  
  
## <a name="options"></a>Opções  
 **Atualizar conteúdo do Visualizador**  
 Recarregue o modelo de mineração no visualizador.  
  
 **Modelo de mineração**  
 Escolha um modelo de mineração para exibir o que está presente na estrutura de mineração atual. O modelo de mineração será aberto no visualizador associado.  
  
 **Visualizador**  
 Escolha um visualizador que será usado para explorar o modelo de mineração selecionado. Você pode usar o visualizador personalizado, ou o **Visualizador de Árvore de Conteúdo Genérica da Microsoft**. Você também pode usar visualizadores de plug-in se houver.  
  
 **Ampliar**  
 Amplie a imagem do diagrama, para ver melhor os estados.  
  
 **Reduza a imagem**  
 Reduza o diagrama para obter uma exibição geral dos estados no cluster.  
  
 **Copiar exibição de gráfico**  
 Copie a seção visível do diagrama para a área de transferência.  
  
 **Copiar gráfico inteiro**  
 Copie todo o diagrama na área de transferência.  
  
 **Cluster**  
 Escolha um cluster para ser exibido no visualizador. Por padrão, **População (Todos)** é selecionada, o que significa que os estados e as transições do modelo inteiro são incluídos no gráfico. Quando você escolhe um cluster específico, somente os estados e as transições que estão naquele cluster são exibidos.  
  
 **Dica:** Você pode renomear clusters usando a guia **Diagrama de Cluster** . Basta selecionar um cluster, clicar com o botão direito do mouse e selecionar **Renomear**. Renomear clusters com um rótulo mais descritivo facilita a comparação de clusters na guia **de Transições de Estado** .  
  
 **Mostrar rótulos de borda**  
 Selecione esta opção para exibir números em cada borda no gráfico que denota a probabilidade da transição.  
  
 **Links**  
 Use o controle deslizante para controlar o número de estados e transições que são exibidos no gráfico. Abaixar o controle deslizante mostra somente os estados e as transições com a probabilidade mais alta.  
  
## <a name="see-also"></a>Consulte também  
 [Algoritmos de mineração de dados &#40;Analysis Services - mineração de dados&#41;](data-mining/data-mining-algorithms-analysis-services-data-mining.md)   
 [Visualizadores do modelo de mineração &#40; Designer do modelo de mineração de dados &#41;](mining-model-viewers-data-mining-model-designer.md)   
 [Visualizadores do modelo de Mineração de dados](data-mining/data-mining-model-viewers.md)  
  
  
