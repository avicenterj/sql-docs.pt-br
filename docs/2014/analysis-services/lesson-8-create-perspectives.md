---
title: 'Lição 9: Criar perspectivas | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55b0f0d0-1cdf-4876-9c3d-d0c848be3f5d
caps.latest.revision: 18
author: Minewiskan
ms.author: owend
manager: jhubbard
ms.openlocfilehash: fe2e746ec290aeb3b8690f818875616f2b9dd2f1
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36120020"
---
# <a name="lesson-9-create-perspectives"></a>Lição 9: Criar perspectivas
  Nesta lição, você criará uma perspectiva de Vendas pela Internet. Uma perspectiva define um subconjunto exibível de um modelo que fornece pontos de vista concentrados, específicos à empresa ou específicos ao aplicativo. Quando um usuário se conecta a um modelo usando uma perspectiva, ele vê apenas os objetos de modelo (tabelas, colunas, medidas e KPIs) como campos definidos nessa perspectiva.  
  
 A perspectiva Vendas pela Internet que você criou nesta lição excluirá o objeto de tabela Cliente. Quando você cria uma perspectiva que exclui determinados objetos da exibição, esse objeto ainda existe no modelo; porém, não está visível em uma lista de campo de cliente de relatório. Colunas calculadas e medidas incluídas ou não em uma perspectiva ainda podem ser calculadas de dados de objeto que são excluídos.  
  
 A finalidade desta lição é descrever como criar perspectivas e se familiarizar com as ferramentas de criação de modelo de tabela. Se você expandir este modelo posteriormente para incluir tabelas adicionais, poderá criar perspectivas adicionais para definir diferentes pontos de vista do modelo; por exemplo, Inventário e Força de Vendas.  
  
 Para saber mais, consulte [Perspectivas &#40;SSAS Tabular&#41;](tabular-models/perspectives-ssas-tabular.md).  
  
 Tempo estimado para concluir esta lição: **5 minutos**  
  
## <a name="prerequisites"></a>Prerequisites  
 Este tópico faz parte de um tutorial de modelo de tabela, que deve ser concluído na ordem. Antes de executar as tarefas desta lição, você deve ter concluído a lição anterior: [Lição 8: Criar Indicadores Chave de Desempenho](lesson-7-create-key-performance-indicators.md).  
  
## <a name="create-perspectives"></a>Criar perspectivas  
  
#### <a name="to-create-an-internet-sales-perspective"></a>Para criar uma perspectiva Vendas pela Internet  
  
1.  No designer de modelo, clique o **modelo** menu e clique **perspectivas**.  
  
2.  Na caixa de diálogo **Perspectivas** , clique em **Nova Perspectiva**.  
  
3.  Para renomear a perspectiva, clique duas vezes o **nova perspectiva 1** título de coluna e digite `Internet Sales`.  
  
4.  Em **campos**, selecione as tabelas a seguir **data**, **geografia**, **produto**, **categoria de produto**, **Subcategoria de produto**, e `Internet Sales`.  
  
     Observe que você excluiu a tabela Cliente e todas as suas colunas desta perspectiva. Posteriormente, na Lição 12, você usará o recurso Analisar no Excel para testar esta perspectiva. A Lista de Campos da Tabela Dinâmica do Excel incluirá cada tabela exceto a tabela Cliente.  
  
5.  Verifique as seleções, garantindo que a tabela **Customer** não está marcada e clique em **OK**  
  
## <a name="next-steps"></a>Próximas etapas  
 Para continuar este tutorial, vá para a próxima lição: [Lição 10: Criar hierarquias](lesson-9-create-hierarchies.md).  
  
  