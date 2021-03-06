---
title: Dados de carregamento em massa em tabelas em uma publicação de mesclagem (programação Transact-SQL de replicação) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- bulk load [SQL Server replication]
- merge replication bulk loading [SQL Server replication]
- sp_addtabletocontents
ms.assetid: 16e6498a-b449-4051-aec4-ea814a2ad993
caps.latest.revision: 32
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 5fe31b5f7720896c149af4463de3ef9a72cae23b
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37166967"
---
# <a name="bulk-load-data-into-tables-in-a-merge-publication-replication-transact-sql-programming"></a>Carregar dados em massa em tabelas em uma publicação de mesclagem (Programação Transact-SQL de replicação)
  Quando os dados são carregados em tabelas com o comando [bcp Utility](../../tools/bcp-utility.md) ou [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) , por padrão, os gatilhos da replicação de mesclagem que mantêm dados de rastreamento na tabela de sistema [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql) não são acionados. Você pode forçar os gatilhos de replicação de mesclagem para serem acionados enquanto os dados forem carregados ou, você pode inserir os metadados de replicação gerados programaticamente após a operação de cópia em massa usando os procedimentos armazenados de replicação.  
  
### <a name="to-bulk-load-data-into-tables-published-by-merge-replication-using-the-bcp-utility"></a>Para carregar dados em massa em tabelas publicadas por replicação de mesclagem usando o utilitário bcp  
  
1.  No Publicador ou no Assinante, execute [bcp Utility](../../tools/bcp-utility.md) ou [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) para inserir dados em uma tabela publicada usando a replicação de mesclagem.  
  
2.  Use um dos métodos abaixo para assegurar que são gerados os metadados de replicação para os dados inseridos.  
  
    -   Execute a cópia em massa usando a opção FIRE_TRIGGERS.  
  
    -   No banco de dados no qual os dados foram inseridos, execute [sp_addtabletocontents &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addtabletocontents-transact-sql). Especifique o nome da tabela na qual os dados foram inseridos para **@table_name**.  
  
  
