---
title: O objeto de modelo (TMSL) | Microsoft Docs
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 6f60b0998dd344cdc3151da1a1c8920495b36917
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34043200"
---
# <a name="model-object-tmsl"></a>Objeto de modelo (TMSL)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
  Define um modelo de tabela. Há um modelo para cada banco de dados e apenas um banco de dados que pode ser especificado em qualquer comando fornecido. Um objeto de banco de dados é o objeto pai.  
  
 Definições de modelo são muito grandes para reproduzir a sintaxe completa em um tópico. Por esse motivo, uma sintaxe parcial, realce as principais partes pode ser encontrada abaixo, com links para os objetos filho.  
  
 Talvez a melhor maneira de entender uma definição de modelo é iniciar com um modelo de tabela que você conhece bem. Use o **Exibir código** opção no SQL Server Data Tools para exibir sua definição. Lembre-se de instalar um editor de JSON para que você possa exibir o código. Você pode obter um editor de JSON no Visual Studio por [baixando a edição Community](https://www.visualstudio.com/downloads/download-visual-studio-vs.aspx) ou outra edição do Visual Studio.  
  
> [!NOTE]  
>  Em qualquer script pode ser referenciado apenas um banco de dados no momento. Para qualquer objeto que não seja o próprio banco de dados, a propriedade de banco de dados é opcional se você especificar o modelo. Há um mapeamento entre um modelo e um banco de dados que pode ser usado para deduzir o nome do banco de dados se ele não foi explicitamente é fornecido.   
> Da mesma forma, você pode deixar o modelo, defina suas propriedades no banco de dados.  
  
## <a name="object-definition"></a>Definição do objeto  
 Todos os objetos têm um conjunto comum de propriedades, incluindo nome, tipo, descrição, uma coleção de propriedades e anotações. **Modelo** objetos também têm as seguintes propriedades.  
  
 storageLocation  
 O local no disco para colocar o modelo.  
  
 defaultMode  
 O método padrão para disponibilizar dados na partição.  
  
 defaultDataView  
 Para modelos no modo DirectQuery, essa propriedade determina quais partições são usadas para executar consultas no modelo.  Os valores válidos incluem completo e exemplo.  
  
 cultura  
 A cultura a ser usada para formatação.  
  
 agrupamento  
 A sequência de agrupamento. Consulte [cenários de globalização para Analysis Services](../../analysis-services/globalization-scenarios-for-analysis-services.md) para obter mais informações.  
  
 tabelas  
 O conjunto completo de tabelas no modelo, incluindo partições, colunas, medidas, KPIs e anotações. Consulte [objeto Tables &#40;TMSL&#41; ](../../analysis-services/tabular-models-scripting-language-objects/tables-object-tmsl.md) para obter detalhes.  
  
 relações  
 Especifica a relação entre cada par de tabelas, incluindo propriedades que definem a direção do filtro e segurança. Consulte [objeto relações &#40;TMSL&#41; ](../../analysis-services/tabular-models-scripting-language-objects/relationships-object-tmsl.md) para obter detalhes.  
  
 fontes de dados  
 Uma ou mais conexões com bancos de dados externos fornecendo dados para o modelo ou usado para passam através de consultas. Consulte [fontes de dados objeto &#40;TMSL&#41; ](../../analysis-services/tabular-models-scripting-language-objects/datasources-object-tmsl.md) para obter detalhes.  
  
 roles  
 Objetos que associam uma permissão de banco de dados, contas de membro e, opcionalmente, filtros de segurança no DAX para controle de acesso personalizados.  
  
## <a name="usage"></a>Uso  
 **Modelo** objetos contêm um modelo inteiro. Você precisa especificar um modelo e/ou seu objeto de banco de dados pai na maioria dos comandos.  
  
 Ao criar, substituir ou alterar um objeto de modelo, especifica todas as propriedades de leitura / gravação da definição de objeto. A omissão de uma propriedade de leitura / gravação é considerada uma exclusão.  
  
## <a name="partial-syntax"></a>Sintaxe parcial  
 Esta definição de objeto for muito grande, somente as primeiro níveis propriedades estão listadas. Consulte [definições de objeto na linguagem de script de modelo de tabela &#40;TMSL&#41; ](../../analysis-services/tabular-models-scripting-language-objects/tmsl-reference-tabular-objects.md) para obter uma lista de objetos filho.  
  
```  
    "model": {  
      "description": "Model object of a Tabular database",  
      "type": "object",  
      "properties": {  
          "name": {  },  
          "description": {  },  
         "storageLocation": {  },  
         "defaultMode":  {  },  
         "defaultDataView": {  },  
         "culture": {  },  
         "collation": {  },  
         "annotations": {  },  
         "tables": {  },  
         "relationships": {  },  
         "dataSources": {  },  
         "perspectives": {  },  
            "cultures": {  },  
         "roles": {  }  
    }  
  
```  
  
## <a name="see-also"></a>Consulte também  
 [Referência de TMSL &#40;Linguagem de Scripts de Modelo de Tabela&#41;](../../analysis-services/tabular-model-scripting-language-tmsl-reference.md)   
 [Nível de compatibilidade para modelos de tabela no Analysis Services](../../analysis-services/tabular-models/compatibility-level-for-tabular-models-in-analysis-services.md)  
  
  
