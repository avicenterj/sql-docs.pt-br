---
title: SQLGetDescField e SQLGetDescRec (biblioteca de Cursor) | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQLGetDescField function [ODBC], Cursor Library
- SQLGetDescRec function [ODBC], Cursor Library
ms.assetid: 1a801f22-6fea-48aa-a723-3187a2ad852b
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: ff32edcc14799980c1d8ec9e05bd27456d71a132
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="sqlgetdescfield-and-sqlgetdescrec-cursor-library"></a>SQLGetDescField e SQLGetDescRec (biblioteca de Cursor)
> [!IMPORTANT]  
>  Este recurso será removido em uma versão futura do Windows. Evite usar esse recurso em desenvolvimentos novos e planeje modificar os aplicativos que atualmente o utilizam. A Microsoft recomenda o uso da funcionalidade de cursor do driver.  
  
 Este tópico discute o uso do **SQLGetDescField** e **SQLGetDescRec** funções na biblioteca de cursor. Para obter informações gerais sobre essas funções, consulte [função SQLGetDescField](../../../odbc/reference/syntax/sqlgetdescfield-function.md) e [função SQLGetDescRec](../../../odbc/reference/syntax/sqlgetdescrec-function.md).  
  
 A biblioteca de cursores executa **SQLGetDescRec** para retornar os metadados de colunas de indicador. A biblioteca de cursores executa **SQLGetDescField** para retornar os mesmos campos retornados por **SQLGetDescRec**, que são SQL_DESC_NAME, SQL_DESC_TYPE, SQL_DESC_DATETIME_INTERVAL_CODE, SQL_DESC_OCTET_ COMPRIMENTO, SQL_DESC_PRECISION, SQL_DESC_SCALE e SQL_DESC_NULLABLE. Para manter a consistência, **SQLGetDescField** também retorna SQL_DESC_UNNAMED.  
  
 A biblioteca de cursores executa **SQLGetDescField** quando ele é chamado para retornar o valor dos seguintes campos que são definidos para colunas de indicador de associação: SQL_DESC_DATA_PTR, SQL_DESC_INDICATOR_PTR, SQL_DESC_OCTET_LENGTH_PTR, e SQL_DESC_LENGTH.  
  
 A biblioteca de cursores executa **SQLGetDescField** quando ele é chamado para retornar o valor do campo SQL_DESC_BIND_OFFSET_PTR, SQL_DESC_BIND_TYPE, SQL_DESC_ROW_ARRAY_SIZE ou SQL_DESC_ROW_STATUS_PTR. Esses campos podem ser retornados para uma linha, não apenas a linha do indicador.  
  
 Se um aplicativo chamar **SQLGetDescField** para retornar o valor de qualquer campo que não sejam aqueles mencionados anteriormente, a biblioteca de cursores passará a chamada para o driver.