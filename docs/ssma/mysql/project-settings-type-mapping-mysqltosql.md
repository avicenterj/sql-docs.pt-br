---
title: "Configurações (mapeamento de tipo) do projeto (MySQLToSQL) | Microsoft Docs"
ms.prod: sql-non-specified
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 136fdf6d-657f-447b-af41-49bbc6e0e93e
caps.latest.revision: 13
author: sabotta
ms.author: carlasab
manager: lonnyb
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 269c901b4242ae199f6d83fc7f678c29be39e5e5
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="project-settings-type-mapping-mysqltosql"></a>Configurações (mapeamento de tipo) do projeto (MySQLToSQL)
As configurações de mapeamento de tipo de projeto permitem definir mapeamentos de tipo de padrão para o projeto SSMA.  

Mapeamento de tipo está disponível nas caixas de diálogo Configurações do projeto e configurações de projeto padrão:  
  
-   Use a caixa de diálogo de configurações do projeto para definir opções de configuração para o projeto atual. Para acessar as configurações de mapeamento de tipo, no menu Ferramentas, selecione configurações de projeto e, em seguida, no painel esquerdo, clique em tipo de mapeamento.  
  
-   Use a caixa de diálogo de configurações de projeto padrão para definir opções de configuração para todos os projetos. Para acessar o mapeamento de tipo de configurações, no menu Ferramentas, selecione configurações padrão do projeto, tipo de projeto de migração select para o qual as configurações são necessárias para ser exibido e alterado de **versão de destino de migração** lista suspensa e, em seguida, no painel esquerdo, clique em tipo de mapeamento.  
  
## <a name="options"></a>Opções  
  
##### <a name="source-type"></a>Tipo de Origem  
É o tipo de dados MySQL, que deve ser mapeado para o tipo de dados do banco de dados de destino.  
  
##### <a name="target-type"></a>Tipo de destino  
Tipo de dados do banco de dados de destino para o tipo de dados MySQL especificado.  
  
##### <a name="add"></a>Adicionar  
Clique para adicionar um tipo de dados para a lista de mapeamento.  
  
##### <a name="edit"></a>Editar  
Clique para editar o tipo de dados selecionado na lista de mapeamento.  
  
##### <a name="remove"></a>Remover  
Clique para remover o mapeamento de tipo de dados selecionado da lista de mapeamento.  
  
##### <a name="reset-to-default"></a>Restaurar Padrões  
Clique para redefinir a lista de mapeamento de tipo para os padrões do SSMA.  
  
## <a name="type-mappings"></a>Mapeamentos de tipo  
A tabela a seguir mostra o mapeamento padrão entre tipos de dados de origem e destino  
  
|||  
|-|-|  
|**Tipo de dados MySQL**|**Tipo de dados do SQL Server**|  
|bigint|bigint|  
|bigint [*...255]|bigint|  
|binary|binário [1]|  
|binário [entre 0 e 1]|binário [1]|  
|binário [2..255]|binário [*]|  
|bit|binário [1]|  
|bits [0..8]|binário [1]|  
|bits [17..24]|binário [3]|  
|bits [25..32]|binário [4]|  
|bits [33..40]|binário [5]|  
|bits [41..48]|binário [6]|  
|bits [49..56]|binário [7]|  
|bits [57..64]|binário [8]|  
|bits [9..16]|binário [2]|  
|blob|varbinary(max)|  
|blob [entre 0 e 1]|varbinary [1]|  
|blob [2..8000]|varbinary [*]|  
|blob [8001...*]|varbinary(max)|  
|bool|bit|  
|booleano|bit|  
|char|nchar [1]|  
|bytes de caractere|binário [1]|  
|bytes de char [entre 0 e 1]|binário [1]|  
|bytes de char [2..255]|binário [*]|  
|char [entre 0 e 1]|nchar [1]|  
|char [2..255]|nchar [*]|  
|character|nchar [1]|  
|caractere variável [entre 0 e 1]|nvarchar [1]|  
|caractere variável [2..255]|nvarchar|  
|caracteres [entre 0 e 1]|nchar [1]|  
|caracteres [2..255]|nchar [*]|  
|date|date|  
|datetime|datetime2 [0]|  
|dec|Decimal|  
|DEC [*...65]|decimal [*] [0]|  
|DEC [*...65][\*..30]|decimal [*] [\*]|  
|Decimal|Decimal|  
|decimal [*...65]|decimal [*] [0]|  
|decimal [*...65][\*..30]|decimal [*] [\*]|  
|double|float [53]|  
|precisão dupla|float [53]|  
|precisão dupla [*...255][\*..30]|numérico [*] [\*]|  
|Double [*...255][\*..30]|numérico [*] [\*]|  
|fixo|numeric|  
|fixo [*...65][\*..30]|numérico [*] [\*]|  
|float|float [24]|  
|float [*...255][\*..30]|numérico [*] [\*]|  
|float [*...53]|float [53]|  
|int|int|  
|int [*...255]|int|  
|inteiro|int|  
|inteiro [*...255]|int|  
|longblob|varbinary(max)|  
|LONGTEXT|nvarchar(max)|  
|mediumblob|varbinary(max)|  
|mediumint|int|  
|mediumint [*...255]|int|  
|mediumtext|nvarchar(max)|  
|National char|nchar [1]|  
|National char [entre 0 e 1]|nchar [1]|  
|National char [2..255]|nchar [*]|  
|caracteres nacionais|nchar [1]|  
|variável de caracteres nacionais|nvarchar [1]|  
|caracteres nacionais, variando [entre 0 e 1]|nvarchar [1]|  
|variáveis [2..4000] de caracteres nacionais|nvarchar [*]|  
|variável de caractere nacional [4001...*]|nvarchar(max)|  
|caracteres nacionais [entre 0 e 1]|nchar [1]|  
|caracteres nacionais [2..255]|nchar [*]|  
|varchar nacional|nvarchar [1]|  
|National varchar [entre 0 e 1]|nvarchar [1]|  
|National varchar [2..4000]|nvarchar [*]|  
|National varchar [4001...*]|nvarchar(max)|  
|nchar|nchar [1]|  
|nchar varchar|nvarchar [1]|  
|nchar varchar [entre 0 e 1]|nvarchar [1]|  
|nchar varchar [2..4000]|nvarchar [*]|  
|nchar varchar [4001...*]|nvarchar(max)|  
|nchar [entre 0 e 1]|nchar [1]|  
|nchar [2..255]|nchar [*]|  
|numeric|numeric|  
|numérico [*...65]|numérico [*] [0]|  
|numérico [*...65][\*..30]|numérico [*] [\*]|  
|nvarchar|nvarchar [1]|  
|nvarchar [entre 0 e 1]|nvarchar [1]|  
|nvarchar [2..4000]|nvarchar [*]|  
|nvarchar [4001...*]|nvarchar(max)|  
|real|float [53]|  
|real [*...255][\*..30]|numérico [*] [\*]|  
|serial|bigint|  
|smallint|smallint|  
|smallint [*...255]|smallint|  
|text|nvarchar(max)|  
|texto [entre 0 e 1]|nvarchar [1]|  
|texto [2..4000]|nvarchar [*]|  
|texto [4001...*]|nvarchar(max)|  
|time|time|  
|timestamp|datetime|  
|tinyblob|varbinary [255]|  
|tinyint|smallint|  
|tinyint [*...255]|smallint|  
|tinytext|nvarchar [255]|  
|bigint não assinado|bigint|  
|não assinado bigint [*...255]|bigint|  
|dec não assinado|Decimal|  
|dec não assinado [*...65]|decimal [*] [0]|  
|dec não assinado [*...65][\*..30]|decimal [*] [\*]|  
|decimal sem sinal|Decimal|  
|decimal sem assinatura [*...65]|decimal [*] [0]|  
|decimal sem assinatura [*...65][\*..30]|decimal [*] [\*]|  
|duplo não assinado|float [53]|  
|sem sinal de precisão dupla|float [53]|  
|não assinado de precisão dupla [*...255][\*..30]|numérico [*] [\*]|  
|não assinado double [*...255][\*..30]|numérico [*] [\*]|  
|não assinado fixa|numeric|  
|não assinado fixa [*...65][\*..30]|numérico [*] [\*]|  
|float não assinado|float [24]|  
|float não assinado [*...255][\*..30]|numérico [*] [\*]|  
|float não assinado [*...53]|float [53]|  
|int não assinado|bigint|  
|int não assinado [*...255]|bigint|  
|inteiro não assinado|bigint|  
|inteiro sem sinal [*...255]|bigint|  
|mediumint não assinado|int|  
|mediumint não assinado [*...255]|int|  
|numérico sem sinal|numeric|  
|sem sinal numérico [*...65]|numérico [*] [0]|  
|sem sinal numérico [*...65][\*..30]|numérico [*] [\*]|  
|sem sinal real|float [53]|  
|sem sinal real [*...255[[\*..30]|numérico [*] [\*]|  
|smallint não assinado|int|  
|smallint não assinado [*...255]|int|  
|tinyint não assinado|tinyint|  
|não assinado tinyint [*...255]|tinyint|  
|varbinary [entre 0 e 1]|varbinary [1]|  
|varbinary [2..8000]|varbinary [*]|  
|varbinary [8001...*]|varbinary(max)|  
|varchar [entre 0 e 1]|nvarchar [1]|  
|varchar [2..4000]|nvarchar [*]|  
|varchar [4001...*]|nvarchar(max)|  
|year|smallint|  
|ano [2..2]|smallint|  
|ano [4..4]|smallint|  
  
##### <a name="add"></a>Adicionar  
Clique para adicionar um tipo de dados para a lista de mapeamento.  
  
##### <a name="edit"></a>Editar  
Clique para editar um tipo de dados na lista de mapeamento.  
  
##### <a name="remove"></a>Remover  
Clique para remover o mapeamento de tipo de dados selecionado da lista de mapeamento.  
  
##### <a name="reset-to-default"></a>Restaurar Padrões  
Clique para restaurar todos os mapeamentos de tipo de dados para os padrões do SSMA.  
  
