---
title: Compilando pacotes programaticamente | Microsoft Docs
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
ms.assetid: 7474b1f4-7607-4f28-a6fd-67f7db1dd3f8
caps.latest.revision: 26
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 4a8ade977c971766c8f716ae5f33cac606c8e22d
ms.openlocfilehash: b80495b726ac6fdac713ba028629633bf84cc004
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="building-packages-programmatically"></a>Compilando pacotes programaticamente
  Se precisar criar pacotes dinamicamente ou gerenciar e executar pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] fora do ambiente de desenvolvimento, você poderá manipular pacotes programaticamente. Nessa abordagem, você tem uma série de opções:  
  
-   Carregue e execute um pacote existente sem modificação.  
  
-   Carregue um pacote existente, reconfigure-o (por exemplo, para uma fonte de dados diferente) e execute-o.  
  
-   Crie um pacote novo, adicione e configure os componentes, objeto por objeto e propriedade por propriedade, salve-o e execute-o.  
  
 É possível usar o modelo de objeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para escrever um código que crie, configure e execute pacotes em qualquer linguagem de programação gerenciada. Por exemplo, talvez você queira criar pacotes orientados a metadados que configurem suas conexões ou fontes de dados, transformações e destinos com base na fonte de dados selecionada e em suas tabelas e colunas.  
  
 Essa seção descreve e demonstra como criar e configurar um pacote programaticamente linha a linha. Em menos complexo final do intervalo de pacote de opções de programação, você pode simplesmente carregar e executar um pacote existente sem modificação, conforme descrito em [executando e Gerenciando pacotes programaticamente](../../integration-services/run-manage-packages-programmatically/running-and-managing-packages-programmatically.md).  
  
 Uma opção intermediária não descrita aqui é o carregamento de um pacote existente como um modelo, sua reconfiguração (por exemplo, para outra fonte de dados) e sua execução. Você também pode usar as informações dessa seção para modificar os objetos existentes em um pacote.  
  
> [!NOTE]  
>  Ao usar um pacote existente como modelo e modificar colunas existentes no fluxo de dados, talvez você precise remover colunas existentes e chamar o método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> de componentes afetados.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Criando um pacote programaticamente](../../integration-services/building-packages-programmatically/creating-a-package-programmatically.md)  
 Descreve como criar um pacote programaticamente.  
  
 [Adicionando tarefas programaticamente](../../integration-services/building-packages-programmatically/adding-tasks-programmatically.md)  
 Descreve como adicionar tarefas ao pacote.  
  
 [Conectando tarefas programaticamente](../../integration-services/building-packages-programmatically/connecting-tasks-programmatically.md)  
 Descreve como controlar a execução dos contêineres e tarefas em um pacote com base no resultado da execução de uma tarefa ou contêiner anterior.  
  
 [Adicionando conexões programaticamente](../../integration-services/building-packages-programmatically/adding-connections-programmatically.md)  
 Descreve como adicionar gerenciadores de conexões a um pacote.  
  
 [Trabalhando com variáveis programaticamente](../../integration-services/building-packages-programmatically/working-with-variables-programmatically.md)  
 Descreve como adicionar e usar variáveis durante a execução de pacotes.  
  
 [Manipulando eventos programaticamente](../../integration-services/building-packages-programmatically/handling-events-programmatically.md)  
 Descreve como tratar eventos de pacotes e tarefas.  
  
 [Habilitar o log programaticamente](../../integration-services/building-packages-programmatically/enabling-logging-programmatically.md)  
 Descreve como habilitar o registro de log para um pacote ou tarefa, e como aplicar filtros personalizados em eventos de log.  
  
 [Adicionando a tarefa de fluxo de dados programaticamente](../../integration-services/building-packages-programmatically/adding-the-data-flow-task-programmatically.md)  
 Descreve como adicionar e configurar a tarefa Fluxo de Dados e seus componentes.  
  
 [Descobrindo componentes de fluxo de dados programaticamente](../../integration-services/building-packages-programmatically/discovering-data-flow-components-programmatically.md)  
 Descreve como detectar os componentes que são instalados no computador local.  
  
 [Adicionando componentes de fluxo de dados programaticamente](../../integration-services/building-packages-programmatically/adding-data-flow-components-programmatically.md)  
 Descreve como adicionar um componente a uma tarefa de fluxo de dados.  
  
 [Conectando componentes de fluxo de dados programaticamente](../../integration-services/building-packages-programmatically/connecting-data-flow-components-programmatically.md)  
 Descreve como conectar dois componentes de fluxo de dados.  
  
 [Selecionando colunas de entrada de forma programática](../../integration-services/building-packages-programmatically/selecting-input-columns-programmatically.md)  
 Descreve como selecionar colunas de entrada dentre aquelas que são fornecidas a um componente pelos componentes upstream do fluxo de dados.  
  
 [Salvando um pacote programaticamente](../../integration-services/building-packages-programmatically/saving-a-package-programmatically.md)  
 Descreve como salvar um pacote programaticamente.  
  
## <a name="reference"></a>Referência  
 [Referência de mensagens e erros do Integration Services](../../integration-services/integration-services-error-and-message-reference.md)  
 Lista os códigos de erro predefinidos do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] com seus nomes simbólicos e descrições.  
  
## <a name="related-sections"></a>Seções relacionadas  
 [Estendendo pacotes com scripts](../../integration-services/extending-packages-scripting/extending-packages-with-scripting.md)  
 Discute como estender o fluxo de controle usando a tarefa Script, e como estender o fluxo de dados usando o componente Script.  
  
 [Estendendo pacotes com objetos personalizados](../../integration-services/extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
 Discute como criar tarefas personalizadas de programa, componentes de fluxo de dados e outros objetos de pacote para uso em vários pacotes.  
  
 [Executando e Gerenciando pacotes programaticamente](../../integration-services/run-manage-packages-programmatically/running-and-managing-packages-programmatically.md)  
 Discute como enumerar, executar e gerenciar pacotes e as pastas nas quais eles são armazenados.  
  
## <a name="external-resources"></a>Recursos externos  
  
-   Exemplos do CodePlex, [Exemplos de Produtos do Integration Services](http://go.microsoft.com/fwlink/?LinkID=131204), em www.codeplex.com/MSFTISProdSamples  
  
-   Entrada de blog, [Criação de perfil de desempenho de suas extensões personalizadas](http://go.microsoft.com/fwlink/?LinkId=238831), em blogs.msdn.com.  

## <a name="see-also"></a>Consulte também  
 [SQL Server Integration Services](../../integration-services/sql-server-integration-services.md)  
  
  