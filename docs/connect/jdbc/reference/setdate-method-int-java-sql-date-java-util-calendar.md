---
title: Método setDate a data e calendário - int | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- SQLServerPreparedStatement.setDate (int, java.sql.Date, java.util.Calendar)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 2c46f694-6dc4-429f-a037-a3bad369a7c8
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 8a1c995909200a7eef7173b3a642b6d19aa13547
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32842721"
---
# <a name="setdate-method-int-javasqldate-javautilcalendar"></a>Método setDate (int, java.sql.Date, java.util.Calendar)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Define o parâmetro designado como os valores de data e calendário fornecidos.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public final void setDate(int n,  
                          java.sql.Date x,  
                          java.util.Calendar cal)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *n*  
  
 Um **int** que indica o número do parâmetro.  
  
 *x*  
  
 Um objeto de data.  
  
 *CAL*  
  
 Um objeto de calendário.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 Esse método setDate é especificado pelo método setDate na interface PreparedStatement.  
  
## <a name="see-also"></a>Consulte também  
 [Método setDate &#40;SQLServerPreparedStatement&#41;](../../../connect/jdbc/reference/setdate-method-sqlserverpreparedstatement.md)   
 [Membros de SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)   
 [Classe SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)  
  
  
