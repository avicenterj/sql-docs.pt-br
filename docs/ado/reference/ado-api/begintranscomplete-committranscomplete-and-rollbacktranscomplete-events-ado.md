---
title: Eventos de RollbackTrans BeginTrans, CommitTrans e (ADO) | Microsoft Docs
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
- CommitTransComplete
- Connection::BeginTransComplete
- Connection::RollbackTransComplete
- Connection::CommitTransComplete
- RollbackTransComplete
- BeginTransComplete
helpviewer_keywords:
- CommitTransComplete event [ADO]
- RollbackTransComplete event [ADO]
- BeginTransComplete event [ADO]
ms.assetid: ec4e4b38-e9c6-4757-b2ef-4e468ae5f1d8
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 3c440f6bd1a978a820797414ff81e6b9b15da467
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35276055"
---
# <a name="begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado"></a>BeginTransComplete, CommitTransComplete e RollbackTransComplete eventos (ADO)
Esses eventos ser chamados após a operação associada no [Conexão](../../../ado/reference/ado-api/connection-object-ado.md) objeto conclui a execução.  
  
-   **BeginTransComplete** é chamado após o [BeginTrans](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-ado.md) operação.  
  
-   **CommitTransComplete** é chamado após o [CommitTrans](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-ado.md) operação.  
  
-   **RollbackTransComplete** é chamado após o [RollbackTrans](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-ado.md) operação.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
BeginTransComplete TransactionLevel, pError, adStatus, pConnection  
CommitTransComplete pError, adStatus, pConnection  
RollbackTransComplete pError, adStatus, pConnection  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *TransactionLevel*  
 Um **longo** valor que contém o novo nível de transação do **BeginTrans** que causou este evento.  
  
 *pError*  
 Um [erro](../../../ado/reference/ado-api/error-object.md) objeto. Descreve o erro ocorrido se o valor de EventStatusEnum é **adStatusErrorsOccurred**; caso contrário, ele não está definido.  
  
 *adStatus*  
 Um [EventStatusEnum](../../../ado/reference/ado-api/eventstatusenum.md) valor de status. Quando qualquer um desses eventos é chamado, esse parâmetro é definido como **adStatusOK** se a operação que causou o evento foi bem-sucedida, ou para **adStatusErrorsOccurred** se a operação falhou.  
  
 Esses eventos podem impedir que as notificações subsequentes ao definir esse parâmetro **adStatusUnwantedEvent** antes de retorna o evento.  
  
 *pConnection*  
 O **Conexão** de objeto para que esse evento ocorreu.  
  
## <a name="remarks"></a>Remarks  
 No Visual C++, vários **conexões** podem compartilhar o mesmo método de manipulação de eventos. O método usa retornado **Conexão** objeto para determinar qual objeto causou o evento.  
  
 Se o [atributos](../../../ado/reference/ado-api/attributes-property-ado.md) está definida como **adXactCommitRetaining** ou **adXactAbortRetaining**, inicia uma nova transação depois de confirmar ou reverter uma transação. Use o **BeginTransComplete** evento para Ignorar tudo, mas o primeiro evento de início da transação.  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo de modelo de eventos do ADO (VC + +)](../../../ado/reference/ado-api/ado-events-model-example-vc.md)   
 [BeginTrans, CommitTrans e exemplo de métodos RollbackTrans (VB)](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-example-vb.md)   
 [Resumo de manipulador de eventos de ADO](../../../ado/guide/data/ado-event-handler-summary.md)   
 [Métodos BeginTrans, CommitTrans e RollbackTrans (ADO)](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-ado.md)
