---
title: Painel de dados do relatório | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.reportdata.f1
- "10039"
helpviewer_keywords:
- Report Data pane
ms.assetid: aa9614a3-12e7-4e17-9de2-fafccd1f5f9d
caps.latest.revision: 27
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 464bdb206986b01de68b018b8b6128956aee7036
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37270562"
---
# <a name="report-data-pane"></a>painel Dados do Relatório
  Use o painel **Dados do Relatório** para exibir os parâmetros, as fontes de dados, os conjuntos de dados, as coleções de campos e as imagens definidos atualmente no relatório. O Painel Relatório mostra uma exibição hierárquica dos itens que representam dados no relatório. Os nós de nível superior representam campos, parâmetros, imagens e referências de fontes de dados internos. Expanda cada nó para exibir os itens de dados. Por exemplo, ao expandir um nó da fonte de dados, os conjuntos de dados definidos para essa fonte de dados são exibidos. Quando você expande um conjunto de dados, a coleção de campos correspondente é exibida. Arraste os itens para a superfície de design de relatório para vincular os dados aos itens de relatório na página de relatório.  
  
## <a name="options"></a>Opções  
 **Campos internos**  
 Representa campos fornecidos pelo Reporting Services que são comumente usados em um relatório, como nome do relatório ou número da página. Para obter mais informações, consulte [Coleções internas em expressões &#40;Construtor de Relatórios e SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).  
  
 **Parâmetros**  
 Representa a coleção de parâmetros do relatório, cada um dos quais pode ter um valor único ou vários valores. Para obter mais informações, consulte [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).  
  
 **Imagens**  
 Representa o conjunto de imagens usadas no relatório. Para obter mais informações, consulte [Imagens &#40;Construtor de Relatórios e SSRS&#41;](../report-design/images-report-builder-and-ssrs.md).  
  
 **Fonte de dados**  
 Representa a referência a uma única fonte de dados para uma fonte de dados inserida ou compartilhada. No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], as fontes de dados compartilhadas são exibidas no Gerenciador de Soluções na pasta Fontes de Dados Compartilhados. A fonte de dados especifica um dos tipos de fonte de dados que têm suporte do Reporting Services. Uma fonte de dados é o nó pai da coleção de conjuntos de dados baseada nele. Para obter mais informações, consulte [conexões de dados, fontes de dados e cadeias de caracteres de Conexão no Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) .  
  
 **Conjunto de dados**  
 Representa um único conjunto de dados. Um conjunto de dados é o nó pai da coleção de campos especificados pela consulta e que inclui todos os campos calculados. O Reporting Services oferece suporte aos designers de consulta para ajudar a especificar uma consulta. Para obter mais informações, consulte [adicionar dados a um relatório &#40;construtor de relatórios e SSRS&#41; ](report-datasets-ssrs.md) e [ferramentas de Design de consulta no relatório Designer SQL Server Data Tools &#40;SSRS&#41;](query-design-tools-ssrs.md).  
  
## <a name="see-also"></a>Consulte também  
 [Coleção de campos de conjuntos de dados &#40;Construtor de Relatórios e SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md)   
 [Painel Agrupamento](../tools/grouping-pane.md)  
  
  
