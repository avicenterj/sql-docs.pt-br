---
title: Gerenciando transações (XMLA) | Microsoft Docs
ms.date: 05/02/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: xmla
ms.topic: conceptual
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 1f2884d49f03d8557d72d8d6d48cdba432a8c37f
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34022293"
---
# <a name="managing-transactions-xmla"></a>Gerenciando transações (XMLA)
  Cada comando XML for Analysis (XMLA) enviado a uma instância de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] é executado dentro do contexto de uma transação na sessão implícita ou explícita atual. Para gerenciar cada uma dessas transações, você deve usar o [BeginTransaction](../../analysis-services/xmla/xml-elements-commands/begintransaction-element-xmla.md), [CommitTransaction](../../analysis-services/xmla/xml-elements-commands/committransaction-element-xmla.md), e [RollbackTransaction](../../analysis-services/xmla/xml-elements-commands/rollbacktransaction-element-xmla.md) comandos. Ao usar esses comandos, você poderá criar transações implícitas ou explícitas, alterar a contagem de referência de transação, além de iniciar, confirmar ou reverter transações.  
  
## <a name="implicit-and-explicit-transactions"></a>Transações implícitas e explícitas  
 Uma transação é implícita ou explícita:  
  
 **Transação implícita**  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cria um *implícita* transação para um XMLA comando se o **BeginTransaction** comando não especifica o início de uma transação. O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sempre confirma uma transação implícita se o comando é bem-sucedido, e reverte uma transação implícita se o comando falha.  
  
 **Transação explícita**  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cria um *explícita* transação se o **BeginTransaction** comando inicia uma transação. No entanto, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] apenas confirma uma transação explícita se um **CommitTransaction** comando é enviado e reverterá uma transação explícita se um **RollbackTransaction** comando é enviado.  
  
 Além disso, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] reverterá transações implícitas e explícitas se a sessão atual terminar antes da conclusão da transação ativa.  
  
## <a name="transactions-and-reference-counts"></a>Transações e contagens de referência  
 O [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] mantém uma contagem de referência de transação para cada sessão. No entanto, o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] não dá suporte a transações aninhadas já que somente uma transação ativa é mantida por sessão. Se a sessão atual não tiver uma transação ativa, a contagem de referência de transação será definida como zero.  
  
 Em outras palavras, cada **BeginTransaction** comando incrementa a contagem de referência em um, enquanto cada **CommitTransaction** diminui de comando, a contagem de referência por um. Se um **CommitTransaction** comando define a contagem de transação como zero, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] confirma a transação.  
  
 No entanto, o **RollbackTransaction** comando reverte a transação ativa, independentemente do valor atual da contagem de referência de transações. Em outras palavras, um único **RollbackTransaction** comando reverte a transação ativa, não importa quantas **BeginTransaction** comandos ou **CommitTransaction** comandos enviados e define a contagem de referência de transação como zero.  
  
## <a name="beginning-a-transaction"></a>Iniciar uma transação  
 O **BeginTransaction** comando inicia uma transação explícita na sessão atual e incrementa a contagem de referência de transação para a sessão atual em um. Todos os comandos subsequentes serão considerados dentro da transação ativa, até que o suficiente **CommitTransaction** comandos são enviados para confirmar a transação ativa ou um único **RollbackTransaction**comando é enviado para reverter a transação ativa.  
  
## <a name="committing-a-transaction"></a>Confirmando uma transação  
 O **CommitTransaction** comando confirma os resultados dos comandos executados após a **BeginTransaction** comando foi executado na sessão atual. Cada **CommitTransaction** comando diminui a contagem de referência para transações ativas em uma sessão. Se um **CommitTransaction** comando define a contagem de referência como zero, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] confirma a transação ativa. Se não houver nenhuma transação ativa (em outras palavras, a contagem de referência de transação para a sessão atual já está definida como zero), um **CommitTransaction** comando resulta em erro.  
  
## <a name="rolling-back-a-transaction"></a>Revertendo uma transação  
 O **RollbackTransaction** comando reverte os resultados dos comandos executados após a **BeginTransaction** comando foi executado na sessão atual. O **RollbackTransaction** comando reverte a transação ativa, independentemente da contagem de referência de transação atual e define a contagem de referência de transação como zero. Se não houver nenhuma transação ativa (em outras palavras, a contagem de referência de transação para a sessão atual já está definida como zero), um **RollbackTransaction** comando resulta em erro.  
  
## <a name="see-also"></a>Consulte também  
 [Desenvolvendo com XMLA no Analysis Services](../../analysis-services/multidimensional-models-scripting-language-assl-xmla/developing-with-xmla-in-analysis-services.md)  
  
  
