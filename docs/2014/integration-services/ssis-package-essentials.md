---
title: Conceitos básicos de pacote SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- package requirements
ms.assetid: b0c86c35-e3d3-4724-9a96-4087e9d74bf3
caps.latest.revision: 27
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 1efb7be8739413ff1688888f66313cd792d54684
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36117716"
---
# <a name="ssis-package-essentials"></a>Informações essenciais sobre pacotes SSIS
  Um pacote é o objeto que implementa a funcionalidade do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para extrair, transformar e carregar dados. Crie um pacote usando o Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] no [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]. Você também pode criar um pacote executando o Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ou o Assistente para Conexões de Projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] . Para obter mais informações, [criar pacotes no SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) no Designer SSIS e [Assistente de importação de projeto](../../2014/integration-services/import-project-wizard.md).  
  
 Um pacote básico inclui os seguintes elementos:  
  
 **Elementos de fluxo de controle**  
 Esses elementos obrigatórios executam várias funções, fornecem estrutura e controlam a ordem em que os elementos são executados. Os elementos de fluxo de controle principais são as tarefas, os contêineres e as restrições de precedência. Deve haver pelo menos um elemento de fluxo de controle em um pacote.  
  
 Para obter mais informações, consulte [Control Flow](control-flow/control-flow.md).  
  
 **Elementos de fluxo de dados**  
 Esses elementos opcionais extraem, modificam e carregam dados em fontes de dados. Os elementos de fluxo de dados principais são fontes, transformações e destinos. Não é necessário haver elementos de fluxo de dados no pacote.  
  
 Para obter mais informações, consulte [Data Flow](data-flow/data-flow.md).  
  
 Para obter um exemplo de como criar um pacote básico, consulte [lição 1: Criando o projeto e pacote básico](lesson-1-create-a-project-and-basic-package-with-ssis.md).  
  
## <a name="related-tasks"></a>Related Tasks  
  
-   [Criar pacotes nas Ferramentas de Dados do SQL Server](create-packages-in-sql-server-data-tools.md)  
  
-   [Adicionar ou excluir uma tarefa ou um contêiner em um fluxo de controle](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
  
-   [Definir as propriedades de uma tarefa ou contêiner](../../2014/integration-services/set-the-properties-of-a-task-or-container.md)  
  
-   [Adicionar ou excluir um componente em um fluxo de dados](data-flow/add-or-delete-a-component-in-a-data-flow.md)  
  
## <a name="related-content"></a>Conteúdo relacionado  
  
1.  Vídeo, [Criando um pacote básico (vídeo do SQL Server)](http://go.microsoft.com/fwlink/?LinkId=131023), no site MSDN.Microsoft.com  
  
## <a name="see-also"></a>Consulte também  
 [Serviços de integração &#40;SSIS&#41; pacotes](../../2014/integration-services/integration-services-ssis-packages.md)   
 [Restrições de precedência](control-flow/precedence-constraints.md)  
  
  