---
title: sqlsrv_get_config | Microsoft Docs
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
- sqlsrv_get_config
apitype: NA
helpviewer_keywords:
- API Reference, sqlsrv_get_config
- sqlsrv_get_config
ms.assetid: ce2befc2-af98-45bb-8d41-60f1674dccfc
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 60437df28456c949d3a03cb58cef89136acbdf2d
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37991278"
---
# <a name="sqlsrvgetconfig"></a>sqlsrv_get_config
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Retorna o valor atual da definição de configuração especificada.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sqlsrv_get_config( string $setting )  
```  
  
#### <a name="parameters"></a>Parâmetros  
*$setting*: a definição de configuração para a qual o valor é retornado. Para obter uma lista das definições configuráveis, consulte [sqlsrv_configure](../../connect/php/sqlsrv-configure.md).  
  
## <a name="return-value"></a>Valor retornado  
O valor da configuração especificada pelo parâmetro *$setting* . Se uma configuração inválida for especificada, será retornado **false** e um erro será adicionado à coleção de erros.  
  
## <a name="remarks"></a>Remarks  
Se **false** for retornado por **sqlsrv_get_config**, você deverá chamar [sqlsrv_errors](../../connect/php/sqlsrv-errors.md) para determinar se ocorreu um erro ou se **false** é o valor da configuração especificada pelo parâmetro *$setting* .  
  
## <a name="see-also"></a>Consulte Também  
[Referência da API do driver SQLSRV](../../connect/php/sqlsrv-driver-api-reference.md)  

[sqlsrv_configure](../../connect/php/sqlsrv-configure.md)  

[sqlsrv_errors](../../connect/php/sqlsrv-errors.md)  
  
