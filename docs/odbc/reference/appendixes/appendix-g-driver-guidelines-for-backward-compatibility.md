---
title: 'Apêndice g: diretrizes de Driver para compatibilidade com versões anteriores | Microsoft Docs'
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
- ODBC drivers [ODBC], backward compatibility
- backward compatibility [ODBC], drivers
- compatibility [ODBC], drivers
ms.assetid: 911cd335-f2c0-4d03-9739-1078308a678a
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 810aa157ef88ba264ff24e3242fea794b3e2e475
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32906022"
---
# <a name="appendix-g-driver-guidelines-for-backward-compatibility"></a>Apêndice g: diretrizes de Driver para compatibilidade com versões anteriores
Este apêndice fornece informações para os autores de driver trabalhando em ODBC 3. *x* drivers que precisam dar suporte a ODBC 2. *x* aplicativos. Para obter mais informações sobre compatibilidade com versões anteriores, consulte [compatibilidade com versões anteriores e a conformidade com padrões](../../../odbc/reference/develop-app/backward-compatibility-and-standards-compliance.md).  
  
 Esta seção contém os tópicos a seguir.  
  
-   [Cursores em bloco, cursores roláveis e compatibilidade com versões anteriores para os Drivers ODBC 3. x](../../../odbc/reference/appendixes/block-cursors-scrollable-cursors-and-backward-compatibility.md) – novos recursos são recursos que existem no ODBC 3. *x* e não no ODBC 2. *x*. ODBC 3. *x* drivers geralmente não precisam se preocupar sobre compatibilidade com versões anteriores com novos recursos, como ODBC 2. *x* aplicativos nunca usá-los. As única exceções são recursos relacionados a **SQLFetch**, **SQLFetchScroll**, **SQLSetPos**, e **SQLExtendedFetch**; para obter mais informações obter informações, consulte, posteriormente neste apêndice.  
  
-   [Mapeando funções preterido](../../../odbc/reference/appendixes/mapping-deprecated-functions.md) — duplicado recursos são recursos que são implementados de maneira diferente em ODBC 3. *x* e ODBC 2. *x*. ODBC 3. *x* drivers não precisam se preocupar sobre compatibilidade com versões anteriores com recursos duplicados porque o Gerenciador de Driver sempre mapeia ODBC 2. *x* recursos ODBC 3. *x* recursos ao chamar um ODBC 3. *x* driver. Portanto, um ODBC 3. *x* driver vê somente ODBC 3. *x* recursos. Para obter mais informações sobre esses mapeamentos, consulte, posteriormente neste apêndice.  
  
-   [Alterações de comportamento e os Drivers ODBC 3. x](../../../odbc/reference/appendixes/behavioral-changes-and-odbc-3-x-drivers.md) — alterações de comportamento são recursos que são tratados de maneira diferente em ODBC 3. *x* e ODBC 2. *x*. ODBC 3. *x* drivers precisam se preocupar sobre alterações de comportamento e agir em resposta ao ambiente SQL_ATTR_ODBC_VERSION atributo definido pelo aplicativo.
