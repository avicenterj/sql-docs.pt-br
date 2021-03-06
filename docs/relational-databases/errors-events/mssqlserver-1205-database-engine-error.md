---
title: MSSQLSERVER_1205 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 1205 (Database Engine error)
ms.assetid: 9fe3f67c-df3c-4642-a3a4-ccc0e138b632
caps.latest.revision: 20
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 606e2f948dbbef82b07bba46184d07ef12f8c50f
ms.sourcegitcommit: ee661730fb695774b9c483c3dd0a6c314e17ddf8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2018
ms.locfileid: "34318727"
---
# <a name="mssqlserver1205"></a>MSSQLSERVER_1205
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|1205|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|LK_VICTIM|  
|Texto da mensagem|A transação (ID do processo %d) entrou em deadlock em %.*ls recursos com outro processo e foi escolhida como a vítima do deadlock. Execute a transação novamente.|  
  
## <a name="explanation"></a>Explicação  
Os recursos foram acessados em ordem conflitante em transações separadas, causando um deadlock. Por exemplo:  
  
-   Transaction1 atualiza **Table1.Row1**, enquanto Transaction2 atualiza **Table2.Row2**.  
  
-   Transaction1 tenta atualizar **Table2.Row2**, mas é bloqueada, porque Transaction2 ainda não foi confirmada.  
  
-   Transaction2 agora tenta atualizar **Table1.Row1**, mas é bloqueada porque Transaction1 ainda não foi confirmada.  
  
-   Um deadlock acontece porque a Transação1 está esperando a conclusão da Transação2, mas a Transação2 está esperando a conclusão da Transação1.  
  
O sistema detectará esse deadlock, escolherá uma das transações envolvidas como 'vítima', emitirá essa mensagem e reverterá a transação da vítima.  
  
## <a name="user-action"></a>Ação do usuário  
Execute a transação novamente. Você também pode revisar o aplicativo para evitar deadlocks. A transação escolhida como vítima pode ser testada novamente e, provavelmente, terá êxito, dependendo de quais operações estiverem sendo executadas simultaneamente.  
  
Para impedir ou evitar a ocorrência de deadlocks, faça com que todas as transações acessem as linhas na mesma ordem (**Table1** e, depois, **Table2**); desse modo, embora possa acontecer um bloqueio, não ocorrerá um deadlock.  
  
