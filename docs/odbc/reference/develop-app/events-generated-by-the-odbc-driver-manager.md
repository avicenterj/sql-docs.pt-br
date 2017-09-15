---
title: Eventos gerados pelo Gerenciador de Driver ODBC | Microsoft Docs
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
- driver manager [ODBC], events generated by
- Visual Studio Analyzer [ODBC], driver manager events
ms.assetid: 8c6efbbd-2c7d-4342-aa7b-201f94b3e3e3
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: e110747e53b5c64702b6103e47942c85858901aa
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="events-generated-by-the-odbc-driver-manager"></a>Eventos gerados pelo Gerenciador de Driver ODBC
> [!IMPORTANT]  
>  Suporte para Visual Studio Analyzer foi removido a partir do Windows 8 (Visual Studio Analyzer foi incluído somente nas versões anteriores do Visual Studio.). Para obter uma alternativa mecanismo de solução de problemas, use o rastreamento BID.  
  
 Eventos gerados pelo Gerenciador de Driver ODBC são registrados quando o botão Iniciar o Visual Studio Analyzer é clicado. A própria ferramenta oferece a capacidade de criar eventos personalizados e de eventos definidos pelo sistema. Para obter mais informações sobre eventos, consulte o *guia de referência do Visual Studio Analyzer* no pacote do Visual Studio da documentação.  
  
|Eventos do Visual Studio Analyzer|Description|  
|----------------------------------|-----------------|  
|**Chamada**|Gerado em cada entrada de API ODBC.|  
|**ReturnException**|Gerado em cada retorno de API ODBC se o código de retorno SQL_ERROR.|  
|**ReturnNormal**|Gerado em cada retorno de API ODBC se o código de retorno não é SQL_ERROR.|  
|**Iniciar Conexão**|Indica que uma conexão foi iniciado; gerado quando o Gerenciador de Driver ODBC chama de conexão do driver APIs.|  
|**Conexão concluída**|Indica que uma conexão foi concluída; gerado quando a conexão do driver APIs retornam para o Gerenciador de Driver ODBC.|  
|**Início da desconexão**|Gerado quando o Gerenciador de Driver ODBC chama o driver **SQLDisconnect** função.|  
|**Desconexão concluída**|Gerado quando o driver **SQLDisconnect** função retorna para o Gerenciador de Driver ODBC.|  
|**QuerySend**|Gerado quando o Gerenciador de Driver ODBC chama o driver **SQLPrepare**, **SQLExecute**, **SQLExecDirect** funções, bem como funções de catálogo como **SQLTables** e **SQLColumns**.|  
|**QueryResult**|Gerado quando o driver retornará um resultado definido para o Gerenciador de Driver ODBC para funções que envolvem consultas.|  
|**TransactionStart**|Gerado quando um aplicativo define o valor de SQL_ATTR_AUTOCOMMIT como SQL_AUTOCOMMIT_OFF, ou depois que um aplicativo com êxito chama **SQLEndTran**.|  
|**TransactionCommit**|Gerado quando um aplicativo chama **SQLEndTran** para confirmar uma transação local.|  
|**TransactionRollback**|Gerado quando um aplicativo chama **SQLEndTran** para reverter uma transação local.|  
|**JoinDTC**|Gerado quando um aplicativo une o coordenador de transações distribuídas (DTC).|  
|**LeaveDTC**|Gerado quando um aplicativo deixa o coordenador de transações distribuídas (DTC).|