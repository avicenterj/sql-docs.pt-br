---
title: Modificações registradas vs. Não registradas modificações | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], image
- data types [ODBC], text
- logged vs. nonlogged modifications [SQL Server Native Client]
- columns [ODBC]
- ODBC data types, image columns
- nonlogged vs. logged modifications
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: 20aa5b27-4a2c-46e7-8356-beb0eebf4b7e
caps.latest.revision: 28
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 34064aaa2e96a7d610f8709c1f5750bddd62b766
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37420277"
---
# <a name="logged-vs-unlogged-modifications"></a>Modificações registradas vs. Modificações não registradas
  Um aplicativo pode solicitar que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC Native Client não log **texto**, **ntext**, e **imagem** modificações. No entanto, tome cuidado ao usar essa opção. Ele deve ser usado somente para as situações em que o **texto**, **ntext**, ou **imagem** dados não são críticos e os proprietários de dados estão dispostos a trocar a possibilidade de recuperar dados para maior desempenho.  
  
 O registro em log do **texto**, **ntext**, e **imagem** modificações é controlado pela chamada [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) com o  *Atributo* parâmetro definido como sql_sopt_ss _ TEXTPTR_LOGGING e *ValuePtr* definido como SQL_TL_ON ou SQL_TL_OFF.  
  
## <a name="see-also"></a>Consulte também  
 [Gerenciando colunas Text e Image](managing-text-and-image-columns.md)  
  
  
