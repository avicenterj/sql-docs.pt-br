---
title: "Método getSendStringParametersAsUnicode (SQLServerDataSource) | Microsoft Docs"
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
- SQLServerDataSource.getSendStringParametersAsUnicode
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 3836d0ab-c3fb-41ff-bb89-10389594ae51
caps.latest.revision: 15
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 520e40a43f47536b34ef68ebebde73f199c8e915
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="getsendstringparametersasunicode-method-sqlserverdatasource"></a>Método getSendStringParametersAsUnicode (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retorna um **booliano** valor que indica se o envio de parâmetros de cadeia de caracteres para o servidor no formato UNICODE está habilitado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public boolean getSendStringParametersAsUnicode()  
```  
  
## <a name="return-value"></a>Valor de retorno  
 **True** se os parâmetros de cadeia de caracteres são enviados para o servidor no formato UNICODE. Caso contrário, **false**.  
  
## <a name="remarks"></a>Comentários  
 Se a propriedade sendStringParametersAsUnicode for definida como **true**, que é o valor padrão, parâmetros string serão enviados para o servidor no formato UNICODE. Se sendStringParametersAsUnicode for definido como **false**, parâmetros string serão enviados para o servidor em um formato ASCII/MBCS, e não em UNICODE. Se sendStringParametersAsUnicode não for definida, getSendStringParametersAsUnicode retornará o valor padrão de **true**.  
  
 Para obter mais informações sobre a propriedade de conexão sendStringParametersAsUnicode, consulte [definindo as propriedades de Conexão](../../../connect/jdbc/setting-the-connection-properties.md).  
  
## <a name="see-also"></a>Consulte também  
 [Membros de SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Classe SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  