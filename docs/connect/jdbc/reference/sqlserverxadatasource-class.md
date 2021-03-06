---
title: Classe SQLServerXADataSource | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 95fc7b07-2498-4a7e-8f7f-ee0d86b598b4
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b69edd13e84599e4e3e11ba56a3a1c34ee1d36ae
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32850521"
---
# <a name="sqlserverxadatasource-class"></a>Classe SQLServerXADataSource
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Representa uma fábrica para [SQLServerXAConnection](../../../connect/jdbc/reference/sqlserverxaconnection-class.md) objetos que são usados internamente.  
  
 **Pacote:** com.microsoft.sqlserver.jdbc  
  
 **Estende:** [SQLServerConnectionPoolDataSource](../../../connect/jdbc/reference/sqlserverconnectionpooldatasource-class.md)  
  
 **Implementa:** javax.SQL. xadatasource  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public class SQLServerXADataSource  
```  
  
## <a name="remarks"></a>Remarks  
 Um objeto que implementa a interface SQLServerXADataSource normalmente é registrado com um serviço de nomeação que usa a JNDI Java Naming and Directory Interface ().  
  
 A classe SQLServerXADataSource fornece conexões de banco de dados para uso em transações distribuídas (XA). A classe SQLServerXADataSource também oferece suporte ao pool de conexão de conexões físicas. As interfaces SQLServerXADataSource e SQLServerXAConnection, que são definidas no pacote javax.sql, são implementadas por [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)].  
  
 Um objeto SQLServerXAConnection é uma conexão em pool que pode participar de uma transação distribuída. Mais precisamente, SQLServerXAConnection estende a interface SQLServerPooledConnection adicionando o método [getXAResource](../../../connect/jdbc/reference/getxaresource-method-sqlserverxaconnection.md). Esse método gera uma [SQLServerXAResource](../../../connect/jdbc/reference/sqlserverxaresource-class.md) objeto que pode ser usado por um Gerenciador de transações para coordenar o trabalho feito essa conexão com os outros participantes na transação distribuída. Como eles estendem a interface de SQLServerPooledConnection, objetos SQLServerXAConnection suportam todos os métodos de objetos SQLServerPooledConnection. Eles são conexões físicas reutilizáveis com uma fonte de dados subjacente e geram identificadores de conexão lógica que podem ser transmitidos de volta a um aplicativo JDBC.  
  
 Objetos SQLServerXAConnection são produzidos por um objeto SQLServerXADataSource. Objetos de SQLServerConnectionPoolDataSource e SQLServerXADataSource são semelhantes porque eles são implementados abaixo de uma camada de fonte de dados que é visível para o aplicativo JDBC. Essa arquitetura permite que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] suporte a transações distribuídas de maneira transparente para o aplicativo. SQLServerXADataSource pode ser configurado para se integrar [!INCLUDE[msCoName](../../../includes/msconame_md.md)] processamento de transações do coordenador de transações distribuídas (DTC) para proporcionar um verdadeiro, distribuído.  
  
## <a name="see-also"></a>Consulte também  
 [Membros de SQLServerXADataSource](../../../connect/jdbc/reference/sqlserverxadatasource-members.md)   
 [Referência da API do Driver JDBC](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
