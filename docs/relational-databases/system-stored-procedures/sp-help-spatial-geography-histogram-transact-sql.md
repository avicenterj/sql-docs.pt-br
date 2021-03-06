---
title: sp_help_spatial_geography_histogram (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology: system-objects
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_help_spatial_geography_histogram_TSQL
- sp_help_spatial_geography_histogram
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help_spatial_geography_histogram
ms.assetid: 5c5bd319-055d-4cd6-8c5a-06354cc056cc
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: b360ca6fef4f5dd77762f844a900b7f8a89217d1
ms.sourcegitcommit: 182b8f68bfb345e9e69547b6d507840ec8ddfd8b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43026084"
---
# <a name="sphelpspatialgeographyhistogram-transact-sql"></a>sp_help_spatial_geography_histogram (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Facilita o chaveamento dos parâmetros de grade de um índice espacial.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_help_spatial_geography_histogram [ @tabname =] 'tabname'   
     [ , [ @colname = ] 'columnname' ]   
     [ , [ @resolution = ] 'resolution' ]  
     [ , [ @sample = ] 'tablesample' ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@tabname =**] **'***tabname***'**  
 É o nome qualificado ou não da tabela para a qual o índice espacial foi especificado.  
  
 As aspas somente serão requeridas se uma tabela qualificada for especificada. Se um nome completamente qualificado, incluindo um nome de banco de dados, for fornecido, o nome do banco de dados deverá ser o nome do banco de dados atual. *tabname* está **sysname**, sem padrão.  
  
 [  **@colname =** ] **'***columnname***'**  
 É o nome da coluna espacial especificada. *ColumnName* é um **sysname**, sem padrão.  
  
 [  **@resolution =** ] **'***resolução***'**  
 É a resolução da caixa delimitadora. Os valores válidos são de 10 a 5000. *resolução* é um **tinyint**, sem padrão.  
  
 [  **@sample =** ] **'***exemplo***'**  
 É a porcentagem da tabela usada. Os valores válidos são de 0 a 100. *TABLESAMPLE* é um **float**. Valor padrão é 100.  
  
## <a name="property-valuereturn-value"></a>Valor da propriedade/Valor do retorno  
 Um valor de tabela é retornado. A grade a seguir descreve o conteúdo da coluna da tabela.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**cellid**|**int**|Representa a identificação exclusiva de cada célula, com uma contagem inicial a partir de 1.|  
|**célula**|**geografia**|É um polígono retangular que representa cada célula. A forma de célula é idêntica à forma de célula usada para a indexação espacial.|  
|**row_count**|**bigint**|Indica o número de objetos espaciais que estão tocando ou contendo a célula.|  
  
## <a name="permissions"></a>Permissões  
 Usuário deve ser um membro do **pública** função. Requer permissão READ ACCESS no servidor e no objeto.  
  
## <a name="remarks"></a>Remarks  
 A guia SSMS espacial mostra uma representação gráfica dos resultados. Você pode consultar os resultados em relação à janela espacial para obter um número aproximado dos itens do resultado.  
  
> [!NOTE]  
>  Os objetos da tabela podem abranger mais de uma célula, portanto, a soma das células na tabela pode ser maior que o número de objetos reais.  
  
 A caixa delimitadora para o **geografia** tipo é o globo inteiro.  
  
## <a name="examples"></a>Exemplos  
 A exemplo a seguir chama **sp_help_spatial_geography_histogram** sobre o `Person.Address` na tabela a [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] banco de dados.  
  
```  
EXEC sp_help_spatial_geography_histogram @tabname = Person.Address, @colname = SpatialLocation, @resolution = 64, @sample = 30;  
```  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos armazenados de índice espacial &#40;Transact-SQL&#41;](http://msdn.microsoft.com/library/1be0f34e-3d5a-4a1f-9299-bd482362ec7a)  
  
  
