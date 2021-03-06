---
title: LEN (Expressão SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- LEN function
- number of characters
ms.assetid: d961398b-e4d0-4936-be17-8f4c5882a640
caps.latest.revision: 36
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 8e0158fef91845d189e9caa0647e23999ab27900
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37195596"
---
# <a name="len-ssis-expression"></a>LEN (Expressão SSIS)
  Retorna o número de caracteres em uma expressão character. Se a cadeia de caracteres incluir espaços em branco à esquerda e à direita, a função os incluirá na contagem. LEN retorna valores idênticos para a mesma cadeia de caracteres de byte único e duplo.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
LEN(character_expression)  
```  
  
## <a name="arguments"></a>Argumentos  
 *character_expression*  
 É a expressão a ser avaliada.  
  
## <a name="result-types"></a>Tipos de resultado  
 DT_I4  
  
## <a name="remarks"></a>Remarks  
 O argumento *character_expression* pode ser um tipo de dados DT_WSTR, DT_TEXT, DT_NTEXT ou DT_IMAGE. Para obter mais informações, consulte [Integration Services Data Types](../data-flow/integration-services-data-types.md).  
  
 Se *character_expression* for um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR, ele será implicitamente convertido para o tipo de dados DT_WSTR antes de LEN executar sua operação. Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR. Para obter mais informações, consulte [Cast &#40;Expressão do SSIS&#41;](cast-ssis-expression.md).  
  
 Se o argumento transmitido para a função LEN tiver um tipo de dados BLOB (Binary Large Object Block), como DT_TEXT, DT_NTEXT ou DT_IMAGE, a função retornará uma contagem de bytes.  
  
 LEN retornará um resultado nulo se o argumento for nulo.  
  
## <a name="expression-examples"></a>Exemplos de expressões  
 Este exemplo retorna o comprimento de uma literal de cadeia de caracteres. O resultado de retorno é 12.  
  
```  
LEN("Ball Bearing")  
```  
  
 Este exemplo retorna a diferença entre o comprimento de valores nas colunas **FirstName** e **LastName** .  
  
```  
LEN(FirstName) - LEN(LastName)  
```  
  
 Retorna o comprimento de um nome do computador que usa a variável de Sistema **MachineName**.  
  
```  
LEN(@MachineName)  
```  
  
## <a name="see-also"></a>Consulte também  
 [Funções &#40;expressão do SSIS&#41;](functions-ssis-expression.md)  
  
  
