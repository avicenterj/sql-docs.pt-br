---
title: 'Alternativas: Usando instruções SQL | Microsoft Docs'
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: ado
ms.technology:
- drivers
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- SQL statements [ADO]
- editing data [ADO], sql statements
- ADO, SQL statements
ms.assetid: 8b528b23-063d-45ea-8dea-6a90d4060b20
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 09f2220a4dc896858923013a087d5e52c373809f
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="alternatives-using-sql-statements"></a>Alternativas: Usando instruções SQL
ADO também permite usar comandos como alternativas para suas propriedades internas e métodos para a edição de dados. Dependendo do seu provedor, todas as operações mencionadas nesta seção podem também ser feitas ao passar comandos para a fonte de dados. Por exemplo, instruções de atualização do SQL podem ser usadas para modificar os dados sem usar o **valor** propriedade de um **campo**. Instruções SQL INSERT podem ser usadas para adicionar novos registros de uma fonte de dados, em vez do método ADO **AddNew**. Para obter mais informações sobre a linguagem de manipulação de dados do provedor ou o SQL, consulte a documentação da fonte de dados.  
  
 Por exemplo, você pode passar uma cadeia de caracteres SQL que contém uma instrução DELETE para um banco de dados, conforme mostrado no código a seguir:  
  
```  
'BeginSQLDelete  
strSQL = "DELETE FROM Shippers WHERE ShipperID = " & intId  
objConn1.Execute strSQL, , adCmdText + adExecuteNoRecords  
'EndSQLDelete  
```