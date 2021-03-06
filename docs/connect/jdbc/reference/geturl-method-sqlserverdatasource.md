---
title: Método getURL (SQLServerDataSource) | Microsoft Docs
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
- SQLServerDataSource.getURL
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: dd0d5d2c-91fe-4b0f-a162-69d898ba176e
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0a506fbfd0c35ae57d2d027724b4d671092398de
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32838901"
---
# <a name="geturl-method-sqlserverdatasource"></a>Método getURL (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retorna a URL usada para se conectar à fonte de dados.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public java.lang.String getURL()  
```  
  
## <a name="return-value"></a>Valor de retorno  
 Um **cadeia de caracteres** que contém a URL.  
  
## <a name="remarks"></a>Remarks  
 Por motivos de segurança, você não deve incluir a senha na URL que é fornecida para o [setURL](../../../connect/jdbc/reference/seturl-method-sqlserverdatasource.md) método. Isso porque os Servidores de Aplicativos Java de terceiros muito frequentemente exibirão o valor definido para a propriedade URL em suas respectivas interfaces de usuário da configuração da fonte de dados. Em vez disso, use o [setPassword](../../../connect/jdbc/reference/setpassword-method-sqlserverdatasource.md) método para definir o valor da senha. Os Servidores de Aplicativos Java não exibirão uma senha que é definida em suas respectivas fontes de dados na interface de usuário da configuração.  
  
> [!NOTE]  
>  Se o método setURL não é chamado antes de chamar o método getURL, getURL retorna o valor padrão de "JDBC: / /".  
  
## <a name="see-also"></a>Consulte também  
 [Membros de SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Classe SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
