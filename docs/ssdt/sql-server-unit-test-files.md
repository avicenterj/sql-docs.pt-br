---
title: Arquivos de teste de unidade do SQL Server | Microsoft Docs
ms.custom:
- SSDT
ms.date: 02/09/2017
ms.prod: sql
ms.technology: ssdt
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: cee093c9-b97d-4fb0-b80f-806d071259dc
caps.latest.revision: 9
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: b6683425c4965277e4bdd2f7fe3b00c28ad1652b
ms.sourcegitcommit: c8f7e9f05043ac10af8a742153e81ab81aa6a3c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39088238"
---
# <a name="sql-server-unit-test-files"></a>Arquivos de teste de unidade do SQL Server
Como os testes de unidade para o código gerenciado, os testes de unidade do SQL Server residem em projetos de teste. Você pode ver os itens que compõem um teste de unidade do SQL Server na hierarquia de um projeto de teste no **Gerenciador de Soluções**.  
  
Um teste de unidade do SQL Server consiste em vários itens contidos em vários arquivos. A tabela a seguir descreve os arquivos que interagem para formar um teste de unidade do SQL Server.  
  
|**File**|**Descrição**|  
|------------|-------------------|  
|.cs ou .vb|Esse arquivo de código-fonte contém uma classe decorada com o atributo [TestClass]. Essa classe contém um único método de teste para cada um dos testes de unidade do SQL Server independente. Esses métodos são decorados com o atributo [TestMethod].<br /><br />Cada método de teste contém o código apropriado para exercer o script de teste Transact\-SQL. Esse código é gerado quando os métodos de teste são criados, e você pode modificá-lo.<br /><br />**OBSERVAÇÃO:** Se você clicar duas vezes nesse arquivo no **Gerenciador de Soluções**, a classe de teste será aberta no Designer de Teste de Unidade do SQL Server. Para abrir o arquivo .cs ou .vb para ver seu código-fonte, clique com o botão direito do mouse no arquivo no **Gerenciador de Soluções** e clique em **Exibir Código**.|  
|.resx|Este arquivo de recurso contém os scripts Transact\-SQL definidos para todos os testes no arquivo .cs ou .vb associado. Esse grupo de scripts inclui os scripts de pré-teste, de teste e de pós-teste. O arquivo de recurso contém XML, que você pode editar. O arquivo de recurso é compilado no assembly de teste.<br /><br />Você deve codificar os scripts Transact\-SQL usando o **Designer de Teste de Unidade do SQL Server**. Para saber mais sobre os scripts que são usados em testes de unidade do SQL Server, consulte [Scripts nos testes de unidade do SQL Server](../ssdt/scripts-in-sql-server-unit-tests.md).|  
|app.config|Esse arquivo armazena as cadeias de conexão de banco de dados do projeto de teste, além de outras configurações de teste de unidade do SQL Server, como tempo limite do comando. Para saber mais, confira [Scripts nos testes de unidade do SQL Server](../ssdt/scripts-in-sql-server-unit-tests.md).|  
|SQLDatabaseSetup.cs ou SQLDatabaseSetup.vb|Esse arquivo contém uma classe que prepara o ambiente de teste para todos os testes de unidade do SQL Server no projeto de teste. Com base nessas configurações no arquivo app.config, ele pode implantar um Projeto de Banco de Dados do SQL Server para o banco de dados de teste.|  
  
## <a name="see-also"></a>Consulte Também  
[Criando e definindo testes de unidade do SQL Server](../ssdt/creating-and-defining-sql-server-unit-tests.md)  
[Criando e definindo testes de unidade do SQL Server](../ssdt/creating-and-defining-sql-server-unit-tests.md)  
[Verificar o código do banco de dados usando os testes de unidade do SQL Server](../ssdt/verifying-database-code-by-using-sql-server-unit-tests.md)  
[Scripts nos testes de unidade do SQL Server](../ssdt/scripts-in-sql-server-unit-tests.md)  
  
