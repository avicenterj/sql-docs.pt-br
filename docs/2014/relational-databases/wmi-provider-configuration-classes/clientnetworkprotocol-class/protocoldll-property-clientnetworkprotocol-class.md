---
title: Propriedade ProtocolDLL (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- ProtocolDLL Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ProtocolDLL property
ms.assetid: fe8650d5-7b9d-46f8-bf74-baf1d9d2a06a
caps.latest.revision: 36
author: CarlRabeler
ms.author: carlrab
manager: craigg
ms.openlocfilehash: ab5e3ff06ea7549d75b1a8c30575168663ae1a30
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37234796"
---
# <a name="protocoldll-property-clientnetworkprotocol-class"></a>Propriedade ProtocolDLL (classe ClientNetworkProtocol)
  Obtém o nome do arquivo .dll exigido pelo protocolo de rede especificado pela opção [Configurar protocolos de cliente](http://technet.microsoft.com/library/ms181035.aspx).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
object  
.ProtocolDLL [= value]  
```  
  
## <a name="parts"></a>Partes  
 *object*  
 A [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) que representa o protocolo de rede usado pelo cliente do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .  
  
## <a name="property-valuereturn-value"></a>Valor da propriedade/Valor do retorno  
 Um valor da cadeia de caracteres que especifica o protocolo do arquivo .dll que é exigido pelo protocolo de rede do cliente.  
  
## <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>Consulte também  
 [Configurando protocolos de rede do cliente e bibliotecas de rede](http://technet.microsoft.com/library/ms181035.aspx)  
  
  
