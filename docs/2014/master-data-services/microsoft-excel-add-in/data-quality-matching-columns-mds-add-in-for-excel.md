---
title: Colunas de correspondência de qualidade de dados (Suplemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: f683fdc6-0d4c-4793-8143-567616cb2094
caps.latest.revision: 8
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 97395c646ce05f3946b036eda5df922c91580b18
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37172877"
---
# <a name="data-quality-matching-columns-mds-add-in-for-excel"></a>Colunas de correspondência de qualidade de dados (Suplemento do MDS para Excel)
  No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], após a correspondência de dados, no grupo **Qualidade de Dados** na faixa de opções, você pode clicar em **Mostrar Detalhes** para exibir colunas que fornecem detalhes correspondentes.  
  
 A tabela a seguir mostra as colunas que são exibidas durante a correspondência de dados.  
  
|Nome|Description|  
|----------|-----------------|  
|**CLUSTER_ID**|Um identificador exclusivo usado para agrupar registros semelhantes. Todas as linhas semelhantes têm a mesma **CLUSTER_ID**. Se nenhum **CLUSTER_ID** é exibido para uma linha, nenhum registro semelhante foi encontrado.|  
|**RECORD_ID**|Um identificador exclusivo usado para identificar registros. Semelhante ao valor de Código armazenado no repositório do MDS é um valor usado para identificar um registro. É gerado automaticamente a cada correspondência de hora.|  
|**PIVOT_MARK**|Um registro arbitrário com o qual outros registros são comparados; não tem um valor de pontuação.|  
|**SCORE**|Representa o grau de similaridade dos registros no grupo com o registro dinâmico. Essa pontuação é determinada pelo DQS. Se nenhuma pontuação for exibida, o registro será dinâmico para outros registros ou nenhuma correspondência será encontrada.|  
  
## <a name="see-also"></a>Consulte também  
 [Qualidade de dados correspondente no suplemento MDS para Excel](data-quality-matching-in-the-mds-add-in-for-excel.md)   
 [Corresponder dados semelhantes &#40;Suplemento MDS para Excel&#41;](match-similar-data-mds-add-in-for-excel.md)   
 [Correspondência de dados](../../data-quality-services/data-matching.md)  
  
  
