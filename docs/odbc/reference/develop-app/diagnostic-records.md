---
title: Registros de diagnóstico | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- diagnostic information [ODBC], diagnostic records
- handles [ODBC], diagnostic records
- header records [ODBC]
- status records [ODBC]
- diagnostic records [ODBC]
ms.assetid: 92c73f9b-3ed7-410d-9cec-2771004aae60
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: d6395d87e5691dc33b5a08267ef83c459f94c0d1
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32909311"
---
# <a name="diagnostic-records"></a>Registros de diagnóstico
Associadas a cada ambiente, identificador do descritor de conexão e instrução estão *registros de diagnóstico*. Esses registros contêm informações de diagnóstico sobre a última função chamada que é usado um identificador específico. Os registros são substituídos somente quando outra função seja chamada usando esse identificador. Não há nenhum limite para o número de registros de diagnóstico que podem ser armazenados em qualquer momento.  
  
 Há dois tipos de registros de diagnóstico: um *registro de cabeçalho* e zero ou mais *registros de status*. O registro de cabeçalho é registro 0; os registros de status são registros 1 e acima. Registros de diagnóstico são compostos de um número de campos separados, que são diferentes para o registro de cabeçalho e os registros de status. Além disso, os componentes ODBC podem definir seus próprios campos de registro de diagnóstico.  
  
 Embora os registros de diagnóstico podem ser pensados como estruturas, não há nenhum requisito para que eles possam ser realmente estruturas; como um driver armazena as informações de diagnóstico é específica do driver.  
  
 Campos nos registros de diagnósticos são recuperados com **SQLGetDiagField**. O SQLSTATE, número de erro nativo e campos de mensagem de diagnóstico de registros de status podem ser recuperados em uma única chamada com **SQLGetDiagRec**.  
  
 Esta seção contém os tópicos a seguir.  
  
-   [Registro de cabeçalho](../../../odbc/reference/develop-app/header-record.md)  
  
-   [Registros de status](../../../odbc/reference/develop-app/status-records.md)
