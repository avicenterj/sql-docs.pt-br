---
title: Relatório de migração de dados (DB2ToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 46ebada7-db36-4ae9-b7ae-baa4b854b237
caps.latest.revision: 4
author: Shamikg
ms.author: Shamikg
manager: craigg
ms.openlocfilehash: 689c37383a9fee4e0bd38cedb33009d3406c1677
ms.sourcegitcommit: 603d2e588ac7b36060fa0cc9c8621ff2a6c0fcc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2018
ms.locfileid: "40394380"
---
# <a name="data-migration-report-db2tosql"></a>Relatório de migração de dados (DB2ToSQL)
O **relatório de migração de dados** caixa de diálogo é exibida após a migração de dados a serem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="options"></a>Opções  
**Status**  
Mostra o status da migração da fonte de dados no banco de dados de destino.  
  
**De**  
A tabela de origem.  
  
**Para**  
A tabela de destino.  
  
**Número total de linhas**  
O número de linhas de dados na tabela de origem.  
  
**Número de linhas migradas com êxito**  
O número de linhas de dados migrados com êxito para a tabela de destino.  
  
**Taxa de**  
A porcentagem de linhas foi migrado com êxito.  
  
**Detalhes**  
Se a falha na migração de dados, clique para exibir detalhes da migração para a linha selecionada no relatório. O SSMA exibirá o motivo da falha.  
  
**Salvar relatório**  
Salva o relatório para um. CSV, arquivo (valores separados por vírgula), que pode ser examinado usando o Microsoft Excel.  
  
