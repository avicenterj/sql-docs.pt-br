---
title: Monitor de Atividade do Trabalho (configurações de filtro) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.jobactivitymon.filter.f1
ms.assetid: 89cb0055-5262-447f-8464-7203d4caba78
caps.latest.revision: 12
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: d8cdb39e6070e1a7876859d3a620cb852345dbb0
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37205256"
---
# <a name="job-activity-monitor-filter-settings"></a>Monitor de atividade do trabalho (Configurações de Filtro)
  Use esta página para reduzir o número de linhas visíveis no Monitor de Atividade do Trabalho. Insira critérios em uma ou em várias das caixas disponíveis, para exibir apenas as linhas correspondentes aos valores especificados. Algumas das caixas, como **Status** ou **Tipo de Bloqueio** , oferecem um número limitado de valores possíveis em uma lista suspensa. Outras, como a caixa **Aplicativo,** permitem inserir qualquer valor e quantos valores você desejar em uma lista separada por vírgula. Ícones da barra de ferramentas permitem ordenar as caixas disponíveis por categoria ou em ordem alfabética. Clique nos critérios para mostrar uma breve descrição de cada um.  
  
 Para filtrar o Monitor de Atividade do Trabalho, forneça quantos critérios de filtragem desejar, clique em **Aplicar filtro**e em **OK**.  
  
## <a name="all-jobs"></a>Todos os trabalhos  
 Este grupo de critérios de filtragem está disponível ao filtrar o Monitor de Atividade do Trabalho.  
  
 **Nome**  
 Filtra trabalhos por nome.  
  
 **Próxima Execução**  
 Filtra pela próxima data agendada para execução.  
  
 **Executável**  
 Exibe os trabalhos que podem ser executados ou trabalhos que não podem ser executados. Selecione **Sim** para exibir apenas os trabalhos que podem ser executados, selecione **Não** para exibir apenas os trabalhos que não podem ser executados ou selecione **Todos** para exibir tanto os trabalhos que podem ser executados quanto os que não podem.  
  
 **Última Execução**  
 Filtra pela data da última execução.  
  
 **Resultado da Última Execução**  
 Filtra trabalhos pelo status da última vez em que os trabalhos foram executados.  
  
 **Enabled**  
 Exibe apenas os trabalhos habilitados ou não habilitados.  
  
 **Categoria**  
 Filtra os trabalhos pela categoria do trabalho.  
  
 **Agendado**  
 Exibe todos os trabalhos com agendas ou sem agendas.  
  
 **Status**  
 Filtra trabalhos pelo status.  
  
## <a name="description-area"></a>Área de Descrição  
 **Caixa Descritiva**  
 Essa caixa sem-nome fornece uma descrição curta dos critérios à medida que eles são selecionados.  
  
 **Aplicar filtro**  
 Para aplicar o filtro, clique em **Aplicar****filtro** e em **OK**. Para manter as configurações de filtro na caixa de diálogo **Configurações de****Filtro** sem aplicá-las, desmarque a opção **Aplicar****filtro**e clique em **OK**para exibir todas as linhas.  
  
 **Liberada**  
 Retorna as configurações de filtro para as configurações padrão.  
  
## <a name="see-also"></a>Consulte também  
 [Monitorar Atividade do Trabalho](../../ssms/agent/monitor-job-activity.md)  
  
  
