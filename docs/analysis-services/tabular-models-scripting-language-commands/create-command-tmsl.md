---
title: Criar um comando (TMSL) | Microsoft Docs
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: tmsl
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 6b2c014d8dc44e0a0e5d7244b5081dfe184d24c3
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34041650"
---
# <a name="create-command-tmsl"></a>Criar um comando (TMSL)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]
  Cria o objeto especificado e todos os objetos descendentes especificados. Se o objeto já existe, o comando gera um erro.  
  
## <a name="request"></a>Solicitação  
 A estrutura da solicitação varia com base no objeto. Um objeto que é um pai deve incluir todos os seus filhos, embora as definições de objeto completo de irmãos e pais não são necessárias.  
  
 [Objeto de banco de dados &#40;TMSL&#41; ](../../analysis-services/tabular-models-scripting-language-objects/database-object-tmsl.md) adicionar um banco de dados a um servidor.  
  
```  
{   
  "create": {   
    "database": {   
      "name": "AdventureworksDW2016",   
      "description": "<description>",   
      "tables": [   
        { },   
        { },   
        { }   
      ],   
      "relationships": [   
        { },   
        { }   
      ]   
    }   
  }   
}  
```  
  
 [Fontes de dados objeto &#40;TMSL&#41;](../../analysis-services/tabular-models-scripting-language-objects/datasources-object-tmsl.md)  
  
```  
{  
  "create": {  
    "parentObject": {  
      "database": "AdventureworksDW2016"  
    },  
    "dataSource": {  
      "name": "SqlServer localhost AdventureworksDW2016",  
      "connectionString": "Provider=SQLNCLI11;Data Source=localhost;Initial Catalog=AdventureworksDW2016;Integrated Security=SSPI;Persist Security Info=false",  
      "impersonationMode": "impersonateAccount",  
      "account": "<account name>",  
      "annotations": [  
        {  
          "name": "ConnectionEditUISource",  
          "value": "SqlServer"  
        }  
      ]  
    }  
  }  
}  
```  
  
 [Objeto Tables &#40;TMSL&#41; ](../../analysis-services/tabular-models-scripting-language-objects/tables-object-tmsl.md) adicionar colunas a uma tabela.  
  
```  
{   
  "create": {   
    "parentObject": {   
      "database": "AdventureworksDW2016",   
      "table": "DimSales"  
    },   
    "columns": {   
      "type": ["calculated"  | "data" ]  
      "name": "\<column-name>",   
       "expression":  "<DAX expression>"  
    }   
  }   
}   
```  
  
 [Objeto de partições &#40;TMSL&#41; ](../../analysis-services/tabular-models-scripting-language-objects/partitions-object-tmsl.md) adicionar uma partição para um objeto da tabela pai.  
  
```  
{  
  "create": {  
    "parentObject": {  
      "database": "AdventureWorksTabular1200",  
      "table": "Date"  
    },  
    "partition": {  
      "name": "Date 2",  
      "source": {  
        "query": "SELECT [dbo].[DimDate].* FROM [dbo].[DimDate]",  
        "dataSource": "SqlServer localhost AdventureworksDW2016"  
      }  
    }  
  }  
}  
```  
  
 [Objeto de funções &#40;TMSL&#41; ](../../analysis-services/tabular-models-scripting-language-objects/roles-object-tmsl.md) adicionar no mínimo uma função para um banco de dados, mas sem associação ou filtros.  
  
```  
{  
  "create": {  
    "parentObject": {  
      "database": "AdventureWorksDW2016"  
    },  
    "role": {  
      "name": "DataReader",  
      "modelPermission": "read"  
    }  
  }  
}  
```  
  
 Exceto para o **banco de dados** do objeto, o objeto que está sendo criado é filho de um **parentObject**. O pai do **banco de dados** objeto é sempre o **Server** objeto.  
  
 Será considerado do contexto. Por exemplo, se você executar o script do Management Studio ou o PowerShell do AMO, a conexão de servidor será especificado na sessão ou como um parâmetro.  
  
## <a name="response"></a>Resposta  
 Retorna um resultado vazio quando o comando terá êxito. Caso contrário, uma exceção XMLA é retornada.  
  
## <a name="examples"></a>Exemplos  
 **Exemplo 1** -adicionar uma função que especifica a associação e um filtro.  
  
```  
{   
   "create":{   
      "parentObject":{   
         "database":"AdventureWorksTabular1200"  
      },  
      "role":{  
         "name":"DataReader",  
         "modelPermission":"read",  
         "members":[   
            {  
               "memberName": "account-01",  
               "memberId":"S-1-5-21-1111111111-2222222222-33333333-444444"  
            },  
            {   
               "memberName": "account-02",  
               "memberId":"S-2-5-21-1111111111-2222222222-33333333-444444"  
            }  
         ],  
         "tablePermissions":[   
            {   
               "name":"Date",  
               "filterExpression":"CalendarYear('2011')"  
            }  
         ]  
      }  
   }  
}  
```  
  
## <a name="usage-endpoints"></a>Uso (pontos de extremidade)  
 Esse elemento de comando é usado em uma instrução do [executar método &#40;XMLA&#41; ](../../analysis-services/xmla/xml-elements-methods-execute.md) chamada por um ponto de extremidade do XMLA, exposto das seguintes maneiras:  
  
-   Como uma janela de XMLA no SQL Server Management Studio (SSMS)  
  
-   Como um arquivo de entrada para o **invoke-ascmd** cmdlet do PowerShell  
  
-   Como uma entrada para um trabalho do SQL Server Agent ou uma tarefa do SSIS  
  
 Você pode gerar um script pronto para este comando do SSMS.  Por exemplo, você pode clique um banco de dados > **Script** > **banco de dados de Script como** > **criar para**.  
  
 O [ \[MS-SSAS-T\]: SQL Server Analysis Services Tabular (protocolo técnicos do SQL Server)](http://go.microsoft.com/fwlink/p/?LinkId=784855) documento inclui seção 3.1.5.2.2 que descreve a estrutura de objetos e comandos de metadados de tabela do JSON. Atualmente, esse documento aborda recursos ainda não implementados no script TMSL e comandos. Consulte o tópico ([linguagem de script de modelo de tabela &#40;TMSL&#41; referência](../../analysis-services/tabular-model-scripting-language-tmsl-reference.md)) para fins de esclarecimento sobre o que tem suporte.  

## <a name="see-also"></a>Consulte também  
 [Referência de TMSL &#40;Linguagem de Scripts de Modelo de Tabela&#41;](../../analysis-services/tabular-model-scripting-language-tmsl-reference.md)  
  
  
