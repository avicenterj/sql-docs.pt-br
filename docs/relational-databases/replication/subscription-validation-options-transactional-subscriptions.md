---
title: Opções de Validação de Assinatura (assinaturas transacionais) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.component: replication
ms.reviewer: ''
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.rep.validate.options.f1
helpviewer_keywords:
- Subscription Validation Options dialog box
ms.assetid: fd66ad1f-df01-4240-9e89-8f41bff12c1e
caps.latest.revision: 18
author: MashaMSFT
ms.author: mathoma
manager: craigg
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 53a37d0f0a4b416a48558d7569763373ff06b2e9
ms.sourcegitcommit: 4183dc18999ad243c40c907ce736f0b7b7f98235
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43074858"
---
# <a name="subscription-validation-options-transactional-subscriptions"></a>Opções de Validação de Assinatura (assinaturas transacionais)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
  Use a caixa de diálogo **Opções de Validação de Assinatura** para especificar se a validação deve usar somente uma contagem de linha ou uma contagem de linhas e uma soma de verificação binária.  
  
## <a name="options"></a>Opções  
 **Verifique se o Assinante tem o mesmo número de linhas dos dados replicados que o Publicador**  
 Selecione o tipo de validação de contagem de linhas a ser executado. Para publicações Oracle, a única opção disponível é **Calcular uma contagem de linhas real consultando as tabelas diretamente**.  
  
 **Comparar as somas de verificação para verificar os dados da linha**  
 Além de contar o número de linhas no Publicador e no Assinante, uma soma de verificação de todos os dados é calculada usando o algoritmo de soma de verificação binária. Se a contagem de linhas falhar, a soma de verificação não será executada.  
  
 **Interromper o Distribution Agent após a conclusão da validação**  
 Por padrão, o Distribution Agent executa continuamente. Selecione essa opção para interromper o agente depois que validação for executada. Isso permite verificar se validação teve êxito antes de continuar replicando dados para o Assinante.  
  
## <a name="see-also"></a>Consulte Também  
 [Validar dados no assinante](../../relational-databases/replication/validate-data-at-the-subscriber.md)   
 [Validar os dados replicados](../../relational-databases/replication/validate-replicated-data.md)  
  
  
