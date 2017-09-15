---
title: "Função Floor (XQuery) | Microsoft Docs"
ms.custom: 
ms.date: 03/09/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
dev_langs:
- XML
helpviewer_keywords:
- floor function [XQuery]
- fn:floor function
ms.assetid: 4ace57dd-b66e-4b60-a2b9-a1b0f1a0831d
caps.latest.revision: 27
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 4ebc7cd706986a4be284a0788b1976898fb5d313
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="numeric-values-functions---floor"></a>Funções de valores numéricas - floor
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Retorna o maior número sem parte de fração que não seja maior que o valor de seu argumento. Se o argumento for uma sequência vazia, ele retornará a sequência vazia.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
fn:floor ($arg as numeric?) as numeric?  
```  
  
## <a name="arguments"></a>Argumentos  
 *$arg*  
 Número ao qual a função é aplicada.  
  
## <a name="remarks"></a>Comentários  
 Se o tipo de *$arg* é um de três tipos base numéricos, **xs: float**, **xs: Double**, ou **xs: decimal**, o tipo de retorno é igual a *$arg* tipo. Se o tipo de *$arg* é um tipo que é derivado de um dos tipos numéricos, o tipo de retorno é o tipo numérico básico.  
  
 Se a entrada para as funções fn: Floor, FN: Ceiling ou FN: round for **XDT: untypedatomic**, dados não digitados, ela será convertida implicitamente para **xs: Double**. Qualquer outro tipo gera um erro estático.  
  
## <a name="examples"></a>Exemplos  
 Este tópico fornece exemplos de XQuery em instâncias XML que são armazenados em várias **xml** colunas de tipo de banco de dados de exemplo AdventureWorks.  
  
 Você pode usar o exemplo de funcionamento do [função ceiling (XQuery)](../xquery/numeric-values-functions-ceiling.md) para o **Floor ()** função XQuery. Tudo o que você precisa fazer é substituir a **Ceiling** função na consulta com o **Floor ()** função.  
  
## <a name="implementation-limitations"></a>Limitações de implementação  
 Estas são as limitações:  
  
-   O **Floor ()** função mapeia todos os valores inteiros para xs: decimal.  
  
## <a name="see-also"></a>Consulte também  
 [limite de função &#40; XQuery &#41;](../xquery/numeric-values-functions-ceiling.md)   
 [Função &#40; ida e volta XQuery &#41;](../xquery/numeric-values-functions-round.md)   
 [Funções XQuery em Tipos de Dados XML](../xquery/xquery-functions-against-the-xml-data-type.md)  
  
  