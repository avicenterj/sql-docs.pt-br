---
title: Verificar a integridade do banco de dados com páginas suspeitas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3b1ec9fe-f6c5-46f7-aa63-6e671be1572d
caps.latest.revision: 10
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 58be64be62903502cc6f585148b168d2e03227bd
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36019161"
---
# <a name="check-integrity-of-database-with-suspect-pages"></a>Verificar a integridade do banco de dados com páginas suspeitas
  Esta regra verifica os bancos de dados de usuários que têm o status do banco de dados definido como suspeito. Quando o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] lê uma página do banco de dados que contém um erro 824, a página é considerada suspeita, sua ID é registrada na tabela suspect_pages do msdb e o banco de dados que a contém é definido como suspeito.  
  
 O erro 824 indica que um erro de consistência lógico foi detectado durante uma operação de leitura. Esse erro frequentemente indica a corrupção de dados causada por um componente de subsistema de E/S defeituoso. Este é um erro grave que ameaça a integridade do banco de dados e deve ser corrigido imediatamente.  
  
## <a name="best-practices-recommendations"></a>Práticas Recomendadas  
  
-   Revise o log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para obter os detalhes do erro 824 para esse banco de dados.  
  
-   Execute uma verificação de consistência completa do banco de dados ([DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)).  
  
-   Implemente as ações de usuário definidas em [MSSQLSERVER_824](http://go.microsoft.com/fwlink/?LinkId=81397).  
  
## <a name="for-more-information"></a>Para obter mais informações  
 [Gerenciar a tabela suspect_pages &#40;SQL Server&#41;](../backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  