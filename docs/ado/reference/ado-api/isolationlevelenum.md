---
title: IsolationLevelEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- IsolationLevelEnum
helpviewer_keywords:
- IsolationLevelEnum enumeration [ADO]
ms.assetid: 8e17a7bc-b8a3-4ae2-b6c9-ce088ad31fdf
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 8fbf9db6b578bc886862069ddc31bc07f18d673b
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35279155"
---
# <a name="isolationlevelenum"></a>IsolationLevelEnum
Especifica o nível de isolamento da transação para um [Conexão](../../../ado/reference/ado-api/connection-object-ado.md) objeto.  
  
|Constante|Valor|Description|  
|--------------|-----------|-----------------|  
|**adXactUnspecified**|-1|Indica que o provedor está usando um nível de isolamento diferente do especificado, mas que não é possível determinar o nível.|  
|**adXactChaos**|16|Indica que as alterações mais altamente isolado transações pendentes não pode ser substituído.|  
|**adXactBrowse**|256|Indica a partir de uma transação é possível exibir as alterações não confirmadas em outras transações.|  
|**adXactReadUncommitted**|256|Mesmo que **adXactBrowse**.|  
|**adXactCursorStability**|4096|Indica a partir de uma transação é possível exibir as alterações em outras transações somente depois de terem sido confirmados.|  
|**adXactReadCommitted**|4096|Mesmo que **adXactCursorStability**.|  
|**adXactRepeatableRead**|65536|Indica que a partir de uma transação, você não pode ver as alterações feitas em outras transações, mas que repetir a consulta pode recuperar novos **registros** objetos.|  
|**adXactIsolated**|1048576|Indica que as transações sejam realizadas em isolamento de outras transações.|  
|**adXactSerializable**|1048576|Mesmo que **adXactIsolated**.|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC equivalente  
 Pacote: **com.ms.wfc.data**  
  
|Constante|  
|--------------|  
|AdoEnums.IsolationLevel.UNSPECIFIED|  
|AdoEnums.IsolationLevel.CHAOS|  
|AdoEnums.IsolationLevel.BROWSE|  
|AdoEnums.IsolationLevel.READUNCOMMITTED|  
|AdoEnums.IsolationLevel.CURSORSTABILITY|  
|AdoEnums.IsolationLevel.READCOMMITTED|  
|AdoEnums.IsolationLevel.REPEATABLEREAD|  
|AdoEnums.IsolationLevel.ISOLATED|  
|AdoEnums.IsolationLevel.SERIALIZABLE|  
  
## <a name="applies-to"></a>Aplica-se a  
 [Propriedade IsolationLevel](../../../ado/reference/ado-api/isolationlevel-property.md)
