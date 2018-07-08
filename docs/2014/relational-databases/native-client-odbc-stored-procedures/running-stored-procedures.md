---
title: Executando procedimentos armazenados | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- ODBC, stored procedures
- stored procedures [ODBC], running
- SQL Server Native Client ODBC driver, stored procedures
- stored procedures [ODBC], executing
ms.assetid: 866b6dd3-2acd-4dfb-aeca-a0352b2d4c6a
caps.latest.revision: 35
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 02fa416b3c472179dbf5801a0b06406309db6b61
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36120347"
---
# <a name="running-stored-procedures"></a>Executando procedimentos armazenados
  Um procedimento armazenado é um objeto executável armazenado em um banco de dados. O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oferece suporte a:  
  
-   Procedimentos armazenados:  
  
     Uma ou mais instruções SQL pré-compiladas em um único procedimento executável.  
  
-   Procedimentos armazenados estendidos:  
  
     DLLs (bibliotecas de vínculo dinâmico) C ou C++ escritas para a API Open Data Services do SQL Server para procedimentos armazenados estendidos. A API Open Data Services estende os recursos de procedimentos armazenados para incluir código C ou C++.  
  
 Ao executar instruções, chamar um procedimento armazenado na fonte de dados (em vez de executar ou preparar diretamente uma instrução no aplicativo cliente) pode oferecer:  
  
-   Maior desempenho  
  
     Instruções SQL são analisadas e compiladas quando procedimentos são criados. Esta sobrecarga é então salva quando os procedimentos são executados.  
  
-   Menor sobrecarga da rede  
  
     A execução de um procedimento em vez de enviar consultas complexas pela rede pode reduzir o tráfego de rede. Se um aplicativo ODBC usa a sintaxe ODBC { CALL } para executar um procedimento armazenado, o driver ODBC faz otimizações adicionais que eliminam a necessidade de converter dados de parâmetros.  
  
-   Maior consistência  
  
     Se as regras de uma organização forem implementadas em um recurso central, como um procedimento armazenado, elas poderão ser codificadas, testadas e depuradas de uma vez. Programadores individuais podem então usar os procedimentos armazenados testados em vez de desenvolver suas próprias implementações.  
  
-   Maior exatidão  
  
     Como geralmente os procedimentos armazenados são desenvolvidos por programadores experientes, existe a tendência de que sejam mais eficientes e tenham menos erros que o código desenvolvido várias vezes por programadores com diversos níveis de habilidade.  
  
-   Maior funcionalidade  
  
     Os procedimentos armazenados estendidos podem usar recursos do C e do C++ não disponíveis em instruções [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
     Para obter um exemplo de como chamar um procedimento armazenado, consulte [processar códigos de retorno e parâmetros de saída &#40;ODBC&#41;](../native-client-odbc-how-to/running-stored-procedures-process-return-codes-and-output-parameters.md).  
  
## <a name="in-this-section"></a>Nesta seção  
  
-   [Chamando um procedimento armazenado](calling-a-stored-procedure.md)  
  
-   [Processando em lote as chamadas de procedimento armazenado](batching-stored-procedure-calls.md)  
  
-   [Processando resultados do procedimento armazenado](processing-stored-procedure-results.md)  
  
## <a name="see-also"></a>Consulte também  
 [SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md)   
 [Tópicos de instruções de procedimentos armazenados de execução &#40;ODBC&#41;](../../database-engine/dev-guide/running-stored-procedures-how-to-topics-odbc.md)  
  
  