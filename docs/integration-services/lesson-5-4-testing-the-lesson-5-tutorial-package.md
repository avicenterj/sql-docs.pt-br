---
title: 'Etapa 4: testar o pacote de tutoriais da Lição 5 | Microsoft Docs'
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.suite: sql
ms.technology: integration-services
ms.tgt_pltfrm: ''
ms.topic: tutorial
applies_to:
- SQL Server 2016
ms.assetid: 5215b77d-c2ec-4b25-a3de-ca49ea197d74
caps.latest.revision: 25
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 00864c10954c01c37e03d2a4f8d5dda05af1b6bf
ms.sourcegitcommit: cc46afa12e890edbc1733febeec87438d6051bf9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2018
ms.locfileid: "35408108"
---
# <a name="lesson-5-4---testing-the-lesson-5-tutorial-package"></a>Lição 5-4 – testar o pacote de tutoriais da Lição 5
Em tempo de execução, o pacote irá obter o valor da propriedade **Directory** de uma variável atualizada em tempo de execução, ao invés de utilizar o nome original de diretório que foi especificado quando você criou o pacote. O valor da variável é populado pelo arquivo SSISTutorial.dtsConfig.  
  
Para verificar se, em tempo de execução, o pacote atualizou corretamente o Diretório com o novo valor, simplesmente execute o pacote. Devido a serem copiados apenas três arquivos de dados de exemplo para o novo diretório, o fluxo de dados irá executar apenas três vezes ao invés de interagir com 14 arquivos da pasta original.  
  
## <a name="checking-the-package-layout"></a>Verificando o layout do pacote  
Antes de testar o pacote, deve-se verificar se os fluxos de controle e de dados do pacote da Lição 5 contêm os objetos mostrados nos diagramas a seguir. O fluxo de controle deve ser idêntico ao fluxo de controle da Lição 4. O fluxo de dados deve ser idêntico ao fluxo de dados da lição 4.  
  
**Fluxo de Controle**  
  
![Fluxo de controle no pacote](../integration-services/media/task4lesson2control.gif "Fluxo de controle no pacote")  
  
**Fluxo de Dados**  
  
![Fluxo de dados no pacote](../integration-services/media/task9lesson1data.gif "Fluxo de dados no pacote")  
  
### <a name="to-test-the-lesson-5-tutorial-package"></a>Para testar o pacote de tutorial da Lição 5  
  
1.  No menu **Depurar** , clique em **Iniciar Depuração**.  
  
2.  Terminada a execução do pacote, no menu **Depurar** , clique em **Parar Depuração**.  
  
## <a name="next-lesson"></a>Próxima lição  
[Lição 6: Usando parâmetros com o modelo de implantação de projetos no SSIS](../integration-services/lesson-6-using-parameters-with-the-project-deployment-model-in-ssis.md)  
  
  
  
