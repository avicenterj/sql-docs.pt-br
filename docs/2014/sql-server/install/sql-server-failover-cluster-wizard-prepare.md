---
title: Assistente de Cluster de Failover do SQL Server - preparação | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c446730a-cc71-4aaa-b142-99fd004ffb1a
caps.latest.revision: 15
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: df6ad4cd8df0f5714c8d0d97e2613eb6816ecf58
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36011727"
---
# <a name="sql-server-failover-cluster-wizard---prepare"></a>Assistente de cluster de failover do SQL Server - Preparação
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Valida a configuração do computador antes da operação de instalação ser concluída. Durante a Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o SCC (Verificador de Configuração do Sistema) examina o computador em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será instalado. O SCC verifica se existem condições que impedem uma operação de instalação com êxito do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Antes que a Instalação inicie o Assistente de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o SCC recupera o status de cada item. Em seguida, compara o resultado com condições necessárias e fornece orientação para a remoção de problemas de bloqueio.  
  
 A verificação da configuração do sistema gera um relatório que contém uma breve descrição de cada regra executada, bem como o status de execução. O relatório de verificação de configuração do sistema está localizado em % programfiles %\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\< YYYYMMDD_HHMM >\\.  
  
 Antes de executar a operação de instalação, reveja os seguintes tópicos:  
  
1.  [Requisitos de hardware e software para a instalação do SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [Recursos com suporte nas edições do SQL Server 2014](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [Considerações sobre segurança para uma instalação do SQL Server](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [Versões de idiomas locais no SQL Server](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 Outras referências:  
  
1.  [Atualizações de versão e edição com suporte](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [Antes de instalar o cluster de failover](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a>Consulte também  
 [As regras de instalação](../../../2014/sql-server/install/install-rules.md)  
  
  