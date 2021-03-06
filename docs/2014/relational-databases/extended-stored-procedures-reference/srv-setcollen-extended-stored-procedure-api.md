---
title: srv_setcollen (API de Procedimento Armazenado Estendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- srv_setcollen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setcollen
ms.assetid: 3c60f1c3-4562-463a-a259-12df172788bd
caps.latest.revision: 30
author: rothja
ms.author: jroth
manager: craigg
ms.openlocfilehash: 668e6e0af87ac1a2c240c5b6a636b0529d23615c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37272692"
---
# <a name="srvsetcollen-extended-stored-procedure-api"></a>srv_setcollen (API de procedimento armazenado estendido)
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Em vez disso, use a Integração CLR.  
  
 Especifica o comprimento dos dados em bytes de uma coluna de comprimento variável ou de uma coluna que aceita valores NULL.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
int srv_setcollen (  
SRV_PROC *  
srvproc  
,  
int   
column  
,  
int  
len   
);  
  
```  
  
## <a name="arguments"></a>Argumentos  
 *srvproc*  
 É um ponteiro para a estrutura SRV_PROC que atua como identificador de uma conexão de cliente específica. A estrutura contém informações que a biblioteca de APIs de procedimento armazenado estendido usa para gerenciar a comunicação e os dados entre o aplicativo e o cliente.  
  
 *column*  
 Indica o número da coluna para a qual o comprimento dos dados está sendo especificado. As colunas são numeradas a partir de 1.  
  
 *len*  
 Indica o comprimento, em bytes, dos dados da coluna. Um comprimento igual a 0 significa que o valor dos dados da coluna é nulo.  
  
## <a name="returns"></a>Retorna  
 SUCCEED ou FAIL.  
  
## <a name="remarks"></a>Remarks  
 Cada coluna da linha deve ser definida primeiro com **srv_describe**. O tamanho dos dados da coluna é definido pela última chamada a **srv_describe** ou **srv_setcollen**. Se os dados de comprimento variável (dados que terminam em nulo) forem alterados em uma linha, **srv_setcollen** deverá ser usado para defini-los com o novo tamanho antes de chamar **srv_sendrow**. No caso de uma coluna que aceita valores nulos, **srv_describe** deve ter sido chamado com *desttype* definido com um tipo de dados que aceita nulos (como SRVINTN) e dados nulos são especificados chamando **srv_setcollen** com *len* definido como 0. Os dados com comprimento zero não podem ser especificados com a API de procedimento armazenado estendido.  
  
 Observe que quando o tipo de dados da coluna tem comprimento variável, *len* não é verificado. Essa função retornará FAIL se for chamada para uma coluna de comprimento fixo.  
  
> [!IMPORTANT]  
>  Você deve examinar totalmente o código-fonte de procedimentos armazenados estendidos e deve testar as DLLs compiladas antes de instalá-las em um servidor de produção. Para obter informações sobre revisão e testes de segurança, consulte este [site da Microsoft](http://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409http://msdn.microsoft.com/security/).  
  
## <a name="see-also"></a>Consulte também  
 [srv_describe &#40;API de Procedimento Armazenado Estendido&#41;](srv-describe-extended-stored-procedure-api.md)  
  
  
