---
title: Protegendo aplicativos do JDBC Driver | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 90724ec6-a9cb-43ef-903e-793f89410bc0
caps.latest.revision: 19
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 091c7a2e7df6a073f7404af9b512a9b6404e6324
ms.sourcegitcommit: 603d2e588ac7b36060fa0cc9c8621ff2a6c0fcc7
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42785877"
---
# <a name="securing-jdbc-driver-applications"></a>Protegendo aplicativos do JDBC Driver

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

Aprimorar a segurança de um aplicativo do [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] envolve mais que evitar armadilhas de codificação comuns. Um aplicativo que acessa dados tem muitos pontos potenciais de falha que um invasor pode explorar para recuperar, manipular, ou destruir dados confidenciais. É importante entender todos os aspectos de segurança, do processo de modelagem de ameaça durante a fase de design de seu aplicativo à implantação consequente, e continuando pela manutenção contínua.  
  
Os tópicos nesta seção descrevem algumas preocupações comuns de segurança inclusive cadeias de caracteres de conexão, validação de entrada do usuário e segurança geral de aplicativo.  
  
## <a name="in-this-section"></a>Nesta seção  
  
| Tópico                                                                            | Descrição                                                                                                                                                           |
| -------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Protegendo cadeias de conexão](../../connect/jdbc/securing-connection-strings.md) | Descreve técnicas para ajudar a proteger informações usadas para conectar a uma fonte de dados.                                                                                    |
| [Validando entradas de usuário](../../connect/jdbc/validating-user-input.md)             | Descreve técnicas para validar a entrada do usuário.                                                                                                                          |
| [Segurança do aplicativo](../../connect/jdbc/application-security.md)               | Descreve como usar permissões de política de Java para ajudar a proteger um aplicativo do driver JDBC.                                                                                |
| [Usando criptografia SSL](../../connect/jdbc/using-ssl-encryption.md)               | Descreve como estabelecer um canal de comunicação seguro com um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o protocolo SSL. |
| [Modo FIPS](../../connect/jdbc/fips-mode.md)                                     | Descreve como usar o JDBC driver em modo compatível com FIPS.                                                                                                              |
  
## <a name="see-also"></a>Consulte Também  

 [Visão geral do JDBC Driver](../../connect/jdbc/overview-of-the-jdbc-driver.md)  
