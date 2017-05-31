---
title: Recursos no SQL Server Management Studio | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], about SQL Server Management Studio
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: e75504b9-7968-4e3b-8411-fd79fe09021e
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 82a8f1c09d51ad35b9d61e68b6878dc90b7d617c
ms.contentlocale: pt-br
ms.lasthandoff: 04/11/2017

---
# <a name="features-in-sql-server-management-studio"></a>Recursos do SQL Server Management Studio
[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] inclui os seguintes recursos gerais:  
  
-   Dá suporte à maior parte das tarefas administrativas do [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)].  
  
-   Um único ambiente integrado para gerenciamento e criação no [!INCLUDE[ssDEnoversion](../includes/ssdenoversion_md.md)] .  
  
-   Caixas de diálogo para gerenciar objetos no [!INCLUDE[ssDEnoversion](../includes/ssdenoversion_md.md)], no [!INCLUDE[ssASnoversion](../includes/ssasnoversion_md.md)]e no [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion_md.md)], que permitem executar ações imediatamente, enviá-las ao Editor de Códigos ou criar scripts delas para posterior execução.  
  
-   Caixas de diálogo redimensionáveis e não modais permitem acesso a várias ferramentas enquanto uma caixa de diálogo estiver aberta.  
  
-   Uma caixa de diálogo de agendamento, comum permite a execução do gerenciamento de caixas de diálogo posteriormente.  
  
-   Registro de servidor para exportação e importação do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] de um ambiente do [!INCLUDE[ssManStudio](../includes/ssmanstudio_md.md)] para outro.  
  
-   Salve ou imprima arquivos de deadlock ou plano de execução de XML gerados pelo SQL Server Profiler, revise-os depois ou envie-os aos administradores para análise.  
  
-   Uma nova caixa de texto de erro e com informações que apresenta muito mais conteúdo, permite que você envie à [!INCLUDE[msCoName](../includes/msconame_md.md)] comentários sobre as mensagens, copie mensagens na área de transferência e envie emails facilmente a sua equipe de suporte.  
  
-   Um navegador da Web integrado para navegação rápida do MSDN ou da ajuda online.  
  
-   Integração da Ajuda de comunidades online.  
  
-   Um tutorial no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] para ajudá-lo a se beneficiar dos vários novos recursos e se tornar mais produtivo imediatamente.  
  
-   Um novo monitor de atividade com filtragem e atualização automática.  
  
-   Interfaces de mensagens de banco de dados integradas.  
  
## <a name="new-scripting-capabilities"></a>Novos recursos de script  
O componente Editor de Códigos do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] contém editores de script integrados para criar [!INCLUDE[tsql](../includes/tsql_md.md)], MDX, DMX e XML/A. Ele oferece:  
  
-   Ajuda dinâmica para acesso imediato a informações relevantes enquanto você trabalha.  
  
-   Um conjunto sofisticado de modelos com capacidade para criar modelos personalizados.  
  
-   Suporte para escrita e edição de consultas ou scripts sem exigir conexão com um servidor.  
  
-   Suporte a script para consultas de SQLCMD e scripts.  
  
-   Uma nova interface para exibição de resultados em XML.  
  
-   Controle de código-fonte integrado para projetos de script e solução, que dá suporte à armazenagem e manutenção de cópias de scripts à medida que evoluem ao longo do tempo.  
  
-   [!INCLUDE[msCoName](../includes/msconame_md.md)] Suporte ao IntelliSense para instruções MDX.  
  
## <a name="object-explorer-features"></a>Recursos do Pesquisador de Objetos  
O componente Pesquisador de Objetos do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] é uma ferramenta integrada para exibir e administrar objetos em todos os tipos de servidor. Ele oferece:  
  
-   Filtragem por todo ou parte de um nome, esquema ou data.  
  
-   A população assíncrona de objetos, com a capacidade de filtragem de objetos com base em metadados.  
  
-   Acesso ao [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)] Agent em servidores de replicação para administração.  
  
Para obter mais informações, veja [Pesquisador de Objetos](../ssms/object/object-explorer.md).  
  
## <a name="extensibility"></a>Extensibilidade  
[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] foi criado com base no Shell Isolado do Visual Studio, que dá suporte inerente à extensibilidade (suplementos/plug-ins). É possível tocar nos serviços de extensibilidade do Visual Studio para reproduzir recursos personalizados no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)]; no entanto, não há suporte para essa extensibilidade.  
  
Há alguns usuários e terceiros que desenvolveram extensões para o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)]. Embora não desestimulemos isso, tenha em mente que não há suporte para extensibilidade. Portanto, pode haver problemas de compatibilidade com versões anteriores/futuras. A Microsoft não publica documentação para estender o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)]. No entanto, há blogs da comunidade e códigos de exemplo que você pode aproveitar.  
  
A Microsoft não oferece suporte para instalações do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] com extensões do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] presentes, portanto, se você tiver instalado extensões do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] , talvez queira removê-las antes de ligar para o Atendimento ao Cliente Microsoft para falar sobre um problema do [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] .  
  
## <a name="see-also"></a>Consulte também  
[Usar o SQL Server Management Studio](../ssms/use-sql-server-management-studio.md)  
  
