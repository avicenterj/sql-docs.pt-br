---
title: Exemplo de conjunto de registros para examinar dados | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- record location [ADO]
- current record [ADO]
ms.assetid: e770e626-68b1-4ddf-a217-d7b30311e2ee
caps.latest.revision: 13
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 8a6bb3eb784c3979dd136f237c5d153547d30027
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35272485"
---
# <a name="sample-recordset-for-examining-data"></a>Exemplo de conjunto de registros para examinar dados
Primeiro, vamos examinar o **registros** objeto conforme retornadas usando a seguinte consulta SQL, executada em relação aos dados de exemplo Northwind base no Microsoft SQL Server.  
  
```  
SELECT ProductID,ProductName,UnitPrice   
FROM Products   
WHERE CategoryID = 7    
```  
  
 O RSoP **registros** objeto contém todos os produz no banco de dados mostrados na tabela a seguir.  
  
|ProductID|ProductName|UnitPrice|  
|---------------|-----------------|---------------|  
|7|Peras secas orgânicos de tio de Bob|30.0000|  
|14|Tofu|23.2500|  
|28|Rssle chucrute|45.6000|  
|51|Maçãs Secas Manjimup|53.0000|  
|74|Longlife Tofu|10.0000|  
  
 Se você estiver interessado em obter esses resultados por conta própria, tente o seguinte exemplo de JScript:  
  
-   [Exemplo de JScript para retornar um conjunto de registros](../../../ado/guide/data/jscript-code-example-to-return-a-recordset.md)
