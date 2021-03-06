---
title: Sequências de Escape GUID | Microsoft Docs
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
- ODBC escape sequences [ODBC], GUID
- escape sequences [ODBC], guid
- guid escape sequence [ODBC]
ms.assetid: 71d43ef9-4a31-493e-b9e0-f864e9ef3ce6
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 00648aba76f64bc999c4df2a1f60de6e8c1010a1
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32906941"
---
# <a name="guid-escape-sequences"></a>Sequências de Escape GUID
ODBC usa sequências de escape para literais GUID. A sintaxe dessa sequência de escape é da seguinte maneira:  
  
```  
{guid 'nnnnnnnn-nnnn-nnnn-nnnn-nnnnnnnnnnnn'}  
```  
  
## <a name="remarks"></a>Remarks  
 Na notação BNF, a sintaxe é:  
  
 *Escape de ODBC-guid* :: =  
     *Iniciador de esc ODBC guid* '*valor guid*' *terminador de esc ODBC*  
  
 *Iniciador de esc ODBC* :: = {  
  
 *Terminador de esc ODBC* :: =}  
  
 *valor de GUID* :: = *separador relógio baixo valor guid separador intermediária de relógio de valor guid separador do relógio de alto valor guid separador do valor de seq relógio guid nó valor*  
  
 *separador de GUID* :: = -  
  
 *valor de baixo de relógio* :: = *hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit*  
  
 *valor do meio de relógio* :: = *hex_digit hex_digit hex_digit hex_digit*  
  
 *relógio de alto valor* :: = *hex_digit hex_digit hex_digit hex_digit*  
  
 *valor de seq relógio* :: = *hex_digit hex_digit hex_digit hex_digit*  
  
 *valor do nó de relógio* :: = *hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit hex_digit*  
  
 *hex_digit* :: = 0 &#124; 1 &#124; 2 &#124; 3 &#124; 4 &#124; 5 &#124; 6 &#124; 7 &#124; 8 &#124; 9 &#124; um &#124; B &#124; C &#124; D &#124; E &#124; F  
  
 A sequência de escape literal GUID é suportada se o tipo de dados GUID é suportado pela fonte de dados. Um aplicativo deve chamar **SQLGetTypeInfo** para determinar se esse tipo de dados é suportado.
