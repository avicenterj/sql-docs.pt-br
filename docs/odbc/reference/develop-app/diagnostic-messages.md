---
title: "Mensagens de diagnóstico | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- diagnostic information [ODBC], diagnostic messages messages
- error messages [ODBC], diagnostic messages
- diagnostic messages [ODBC]
ms.assetid: 98027871-9901-476e-a722-ee58b7723c1f
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: ddec8b5d5f658e4f6119c1962d785232bf44d985
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="diagnostic-messages"></a>Mensagens de diagnóstico
Uma mensagem de diagnóstico é retornada com cada SQLSTATE. O SQLSTATE mesmo geralmente é retornado com um número de mensagens diferentes. Por exemplo, o SQLSTATE 42000 (sintaxe ou violação de acesso) é retornado para a maioria dos erros de sintaxe SQL. No entanto, cada erro de sintaxe costuma ser descrita por uma mensagem diferente.  
  
 Exemplos de mensagens de diagnósticos são listados na coluna de erro na tabela de SQLSTATEs no Apêndice A e em cada função. Embora drivers podem retornar essas mensagens, eles são mais prováveis de retornar qualquer mensagem que é passada a eles pela fonte de dados.  
  
 Aplicativos geralmente exibem mensagens de diagnóstico para o usuário, juntamente com o SQLSTATE e o código de erro nativo. Isso ajuda o usuário e a equipe de suporte determinar a causa de problemas. As informações de componente inseridas na mensagem serão particularmente útil ao fazer isso.  
  
 Mensagens de diagnóstico vêm de fontes de dados e componentes em uma conexão ODBC, como drivers, gateways e o Gerenciador de Driver. Normalmente, fontes de dados dão suporte diretamente ODBC. Consequentemente, se um componente em uma conexão ODBC recebe uma mensagem de uma fonte de dados, ele deve identificar a fonte de dados como a origem da mensagem. Ele deve também se identificar como o componente que recebeu a mensagem.  
  
 Se a fonte de um erro ou aviso é um componente em si, a mensagem de diagnóstica deve explicar isso. Portanto, o texto de mensagens tem dois formatos diferentes. Para erros e avisos que não ocorram em uma fonte de dados, a mensagem de diagnóstica deve usar este formato:  
  
 **[** *identificador de fornecedor* **] [** *identificador de componente de ODBC* **]** * texto fornecido pelo componente*  
  
 Para erros e avisos que ocorrem em uma fonte de dados, a mensagem de diagnóstica deve usar este formato:  
  
 **[** *identificador de fornecedor* **] [** *identificador de componente de ODBC* **] [** * Identificador da fonte de dados* **]** *dados--fornecido-texto de origem*  
  
 A tabela a seguir mostra o significado de cada elemento.  
  
|Elemento|Significado|  
|-------------|-------------|  
|*Identificador de fornecedor*|Identifica o fornecedor do componente no qual ocorreu o erro ou aviso ou que recebeu o erro ou aviso diretamente da fonte de dados.|  
|*Identificador de componente de ODBC*|Identifica o componente no qual ocorreu o erro ou aviso ou que recebeu o erro ou aviso diretamente da fonte de dados.|  
|*Identificador da fonte de dados*|Identifica a fonte de dados. Para drivers baseados em arquivo, isso geralmente é um formato de arquivo, como os drivers baseados em DBMS para Xbase [1], este é o produto do DBMS.|  
|*texto fornecido pelo componente*|Gerado pelo componente do ODBC.|  
|*dados de origem-fornecido-texto*|Gerado pela fonte de dados.|  
  
 [1] nesse caso, o driver está atuando como o driver e a fonte de dados.  
  
 Colchetes (**[]**) deve ser incluído na mensagem e não indicam itens opcionais.