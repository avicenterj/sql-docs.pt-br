---
title: "parâmetro de método (java.util.Calendar) getDate | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SQLServerCallableStatement.getDate (java.util.Calendar)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 6d0deaf2-6f12-4a6e-b537-a51fa3478059
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: ecd0f399f5ce123de78e037bfb9696f598da89bc
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="getdate-method-javalangstring-javautilcalendar"></a>Método getDate (java.lang.String, java.util.Calendar)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera o valor do parâmetro designado como um objeto Java.SQL. Date na linguagem de programação Java considerando o nome do parâmetro e o objeto de calendário.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public java.sql.Date getDate(java.lang.String sCol,  
                             java.util.Calendar cal)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *sCol*  
  
 Um **cadeia de caracteres** que contém o nome do parâmetro.  
  
 *CAL*  
  
 Um objeto de calendário.  
  
## <a name="return-value"></a>Valor de retorno  
 Um objeto de data.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentários  
 Esse método getDate é especificado pelo método na interface do CallableStatement getDate.  
  
 Esse método retorna uma parte de data válida de um [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] tipo de dados datetime ou smalldatetime, com a parte de hora definida como a linha de base de tempo de Java de 00:00 (meia-noite).  
  
## <a name="see-also"></a>Consulte também  
 [Método getDate &#40; SQLServerCallableStatement &#41;](../../../connect/jdbc/reference/getdate-method-sqlservercallablestatement.md)   
 [Membros SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [Classe SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  