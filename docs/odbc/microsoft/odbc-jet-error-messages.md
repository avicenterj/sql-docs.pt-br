---
title: Mensagens de erro de Jet ODBC | Microsoft Docs
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
- error messages (ODBC driver for oracle)
ms.assetid: f8d2a8f2-0316-42c4-bc34-5367661634ae
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0f487fce920dd82fc36e460467733393ffdbbc36
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32901411"
---
# <a name="odbc-jet-error-messages"></a>Mensagens de erro de Jet de ODBC
Para erros que ocorrem na fonte de dados, o driver ODBC retorna uma mensagem de erro retornada a ele pela biblioteca de arquivo do ODBC. Para erros que ocorrem no driver ODBC ou o Gerenciador de Driver, retorna o driver que uma mensagem de erro com base no texto associado a SQLSTATE.  
  
 Mensagens de erro têm o seguinte formato:  
  
```  
[vendor][ODBC-component][data-source]message-text  
```  
  
 Os prefixos de colchetes ([]) identificam o local do erro. Quando o erro ocorre no Gerenciador de Driver, *fonte de dados* não for fornecido. Quando o erro ocorre na fonte de dados, o [*fornecedor*] e [*componentes ODBC*] prefixos de identificam o fornecedor e o nome do componente ODBC que recebeu o erro da fonte de dados.  
  
 A tabela a seguir mostra as mensagens de erro retornadas pelo Gerenciador de Driver e o driver ISAM:  
  
|Mensagem de erro|Local do erro|  
|-------------------|--------------------|  
|[Microsoft] [Gerenciador de Driver ODBC] *texto da mensagem*|Gerenciador de driver (Odbc32. dll)|  
|[Microsoft] [ODBC *nome do driver*]*texto da mensagem*|O driver ISAM (consulte ISAMs Driver)|
