---
title: Elemento DataSourceType (XMLA) | Microsoft Docs
ms.date: 05/08/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 015a4cfbb70ddb29216a079dffdfd928029033d3
ms.sourcegitcommit: 808d23a654ef03ea16db1aa23edab496b73e5072
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34575668"
---
# <a name="datasourcetype-element-xmla"></a>Elemento DataSourceType (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]
  Indica se um [local](../../../analysis-services/xmla/xml-elements-properties/location-element-xmla.md) elemento especificado para um [restaurar](../../../analysis-services/xmla/xml-elements-commands/restore-element-xmla.md) ou [sincronizar](../../../analysis-services/xmla/xml-elements-commands/synchronize-element-xmla.md) comando é local ou remoto.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Location>  
   ...  
   <DataSourceType>...</DataSourceType>  
   ...  
</Location>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Cadeia de caracteres (enumeração)|  
|Valor padrão|*remoto*|  
|Cardinalidade|0-1: elemento opcional que pode ocorrer apenas uma única vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Local](../../../analysis-services/xmla/xml-elements-properties/location-element-xmla.md)|  
|Elementos filho|Nenhum|  
  
## <a name="remarks"></a>Remarks  
 O elemento **DataSourceType** determina se a fonte de dados definida pelo elemento **Location** contém uma fonte de dados local ou remota. Para obter mais informações sobre backup e restaurando partições remotas, consulte [fazendo backup, restaurando e sincronizando bancos de dados &#40;XMLA&#41;](../../../analysis-services/multidimensional-models-scripting-language-assl-xmla/backing-up-restoring-and-synchronizing-databases-xmla.md).  
  
 O valor desse elemento é limitado a uma das cadeias de caracteres listadas na tabela a seguir.  
  
|Valor|Description|  
|-----------|-----------------|  
|*local*|O elemento **Location** define uma fonte de dados local. Se este valor for usado, os comandos **Restore** e **Synchronize** usarão as informações definidas no elemento **Location** para atualizar a fonte de dados, recuperada a partir de um arquivo de backup especificado no elemento **File** do comando **Backup** ou de um banco de dados especificado no elemento **Source** do comando **Synchronize** , identificado no elemento **DataSourceID** do elemento **Location** .<br /><br /> Este valor permite que os objetos usem o armazenamento OLAP (ROLAP), após a recuperação ou a sincronização, com o objetivo de usar um banco de dados diferente para seus dados e metadados.<br /><br /> Observação: Dados ROLAP, como dados em tabelas de dimensões ou tabelas de write-back não é restaurados ou sincronizados. Somente os metadados de objetos ROLAP são recuperados ou sincronizados.|  
|*remoto*|O elemento **Location** define uma fonte de dados remota. Se este valor for usado, os comandos **Restore** e **Synchronize** usarão as informações definidas no elemento **Location** para recuperar ou sincronizar partições remotas, recuperadas a partir de um arquivo de backup especificado no elemento **File** do comando **Backup** ou de um banco de dados especificado no elemento **Source** do comando **Synchronize** , da instância remota identificada em **DataSourceID** do elemento **Location** .|  
  
## <a name="see-also"></a>Confira também
 [Elemento ConnectionString &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/connectionstring-element-xmla.md)   
 [Elemento DataSourceID &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/datasourceid-element-xmla.md)   
 [Propriedades &#40;XMLA&#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
