---
title: Always Encrypted (desenvolvimento do cliente) | Microsoft Docs
ms.custom: ''
ms.date: 07/29/2016
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: security
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- CSharp
ms.assetid: 9595eb66-284c-4474-828f-8961a05ce989
author: stevestein
ms.author: sstein
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017
ms.openlocfilehash: 3f2d372307528366248c5830626aee2b8fd14816
ms.sourcegitcommit: 4cd008a77f456b35204989bbdd31db352716bbe6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39547146"
---
# <a name="always-encrypted-client-development"></a>Always Encrypted (desenvolvimento de cliente)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]

O[Always Encrypted](../../../relational-databases/security/encryption/always-encrypted-database-engine.md) é uma tecnologia de criptografia do lado do cliente que garante que os dados confidenciais (e as chaves de criptografia relacionadas) nunca são revelados para o SQL Server nem para o Banco de Dados SQL do Azure. Com o Always Encrypted, um driver de cliente criptografa de forma transparente os dados confidenciais antes de passá-los para o Mecanismo de Banco de Dados e descriptografa de forma transparente os dados recuperados de colunas de banco de dados criptografadas.

Para obter detalhes sobre como desenvolver aplicativos que usam bancos de dados protegidos pelo Always Encrypted e quais drivers de cliente e versões de driver dão suporte ao Always Encrypted, veja:

- [Usando o Always Encrypted com o Provedor de Dados .NET Framework para SQL Server](../../../relational-databases/security/encryption/develop-using-always-encrypted-with-net-framework-data-provider.md)
- [Use Always Encrypted com o Driver JDBC](../../../connect/jdbc/using-always-encrypted-with-the-jdbc-driver.md)
- [Como usar Always Encrypted com o driver ODBC do Windows](../../../connect/odbc/using-always-encrypted-with-the-odbc-driver.md)



## <a name="see-also"></a>Consulte Também

[Always Encrypted (mecanismo de banco de dados)](../../../relational-databases/security/encryption/always-encrypted-database-engine.md)

