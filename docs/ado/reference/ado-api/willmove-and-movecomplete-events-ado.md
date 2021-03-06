---
title: WillMove e MoveComplete eventos (ADO) | Microsoft Docs
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
- Recordset::MoveComplete
- WillMove
- MoveComplete
- Recordset::WillMove
helpviewer_keywords:
- MoveComplete event [ADO]
- WillMove event [ADO]
ms.assetid: 1a3d1042-4f30-4526-a0c7-853c242496db
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 30394da01328ad1f533834081cd33f6620c54dd4
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35282885"
---
# <a name="willmove-and-movecomplete-events-ado"></a>WillMove e MoveComplete eventos (ADO)
O **WillMove** evento é chamado antes de uma operação pendente altera a posição atual no [registros](../../../ado/reference/ado-api/recordset-object-ado.md). O **MoveComplete** evento é chamado após a posição atual no **registros** alterações.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
WillMove adReason, adStatus, pRecordset  
MoveComplete adReason, pError, adStatus, pRecordset  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *adReason*  
 Um [EventReasonEnum](../../../ado/reference/ado-api/eventreasonenum.md) valor que especifica o motivo para esse evento. Seu valor pode ser **adRsnMoveFirst**, **adRsnMoveLast**, **adRsnMoveNext**, **adRsnMovePrevious**, **adRsnMove** , ou **adRsnRequery**.  
  
 *pError*  
 Um [erro](../../../ado/reference/ado-api/error-object.md) objeto. Descreve o erro ocorrido se o valor de *adStatus* é **adStatusErrorsOccurred**; caso contrário, o parâmetro não está definido.  
  
 *adStatus*  
 Um [EventStatusEnum](../../../ado/reference/ado-api/eventstatusenum.md) valor de status.  
  
 Quando **WillMove** é chamado, esse parâmetro é definido como **adStatusOK** se a operação que causou o evento foi bem-sucedida. Ele é definido como **adStatusCantDeny** se esse evento não é possível solicitar o cancelamento da operação pendente.  
  
 Quando **MoveComplete** é chamado, esse parâmetro é definido como **adStatusOK** se a operação que causou o evento foi bem-sucedida, ou para **adStatusErrorsOccurred** se a Falha na operação.  
  
 Antes de **WillMove** retorna, defina este parâmetro como **adStatusCancel** para solicitar o cancelamento da operação pendente, ou definir esse parâmetro como **adStatusUnwantedEvent** Para evitar notificações subsequentes.  
  
 Antes de **MoveComplete** retorna, defina este parâmetro como **adStatusUnwantedEvent** para impedir que as notificações subsequentes.  
  
 *pRecordset*  
 Um [registros](../../../ado/reference/ado-api/recordset-object-ado.md) objeto. O **registros** para que esse evento ocorreu.  
  
## <a name="remarks"></a>Remarks  
 Um **WillMove** ou **MoveComplete** evento pode ocorrer devido ao seguinte **registros** operações: [abrir](../../../ado/reference/ado-api/open-method-ado-recordset.md), [mover](../../../ado/reference/ado-api/move-method-ado.md), [MoveFirst](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [MoveLast](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [MoveNext](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [MovePrevious](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md), [AddNew](../../../ado/reference/ado-api/addnew-method-ado.md), e [Requery](../../../ado/reference/ado-api/requery-method.md). Esses eventos podem ocorrer devido as seguintes propriedades: [filtro](../../../ado/reference/ado-api/filter-property.md), [índice](../../../ado/reference/ado-api/index-property.md), [indicador](../../../ado/reference/ado-api/bookmark-property-ado.md), [AbsolutePage](../../../ado/reference/ado-api/absolutepage-property-ado.md)e [AbsolutePosition](../../../ado/reference/ado-api/absoluteposition-property-ado.md). Esses eventos também ocorrem se uma criança **registros** tem **registros** eventos conectados e o pai **Recordset** é movido.  
  
 Você deve definir o *adStatus* parâmetro **adStatusUnwantedEvent** para cada possível *adReason* valor para parar completamente a notificação de eventos para qualquer evento que inclui um *adReason* parâmetro.  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo de modelo de eventos do ADO (VC + +)](../../../ado/reference/ado-api/ado-events-model-example-vc.md)   
 [Resumo de manipulador de eventos de ADO](../../../ado/guide/data/ado-event-handler-summary.md)   
 [Objeto Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)
