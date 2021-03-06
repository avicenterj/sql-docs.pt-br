---
title: 'Etapa 3: testar o pacote da Lição 6 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: c184c92d-948f-4037-a502-5fabd909c84c
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 77fa6d4f000f58322524b7a32917ed7e29144b8f
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37271142"
---
# <a name="step-3-testing-the-lesson-6-package"></a>Etapa 3: Testando o pacote da Lição 6
  Em tempo de execução, seu pacote irá obter o valor para a propriedade Diretório a partir do parâmetro VarFolderName.  
  
 Para verificar se, em tempo de execução, o pacote atualizou corretamente o Diretório com o novo valor, simplesmente execute o pacote. Devido a serem copiados apenas três arquivos de dados de exemplo para o novo diretório, o fluxo de dados irá executar apenas três vezes ao invés de interagir com 14 arquivos da pasta original.  
  
## <a name="checking-the-package-layout"></a>Verificando o layout do pacote  
 Antes de testar o pacote deve-se verificar se os fluxos de controle e de dados do pacote da Lição 6 contêm os objetos mostrados nos diagramas a seguir. O fluxo de controle deve ser idêntico ao fluxo de controle da lição 5. O fluxo de dados deve ser idêntico ao fluxo de dados na lição 5.  
  
 **Fluxo de Controle**  
  
 ![Controlar fluxo](../../2014/tutorials/media/task3lesson6control.jpg "fluxo de controle")  
  
 **Fluxo de Dados**  
  
 ![Fluxo de dados](../../2014/tutorials/media/task3lesson6data.jpg "fluxo de dados")  
  
### <a name="to-test-the-lesson-6-tutorial-package"></a>Para testar o pacote de tutorial da Lição 6  
  
1.  No menu Depurar, clique em Iniciar Depuração.  
  
2.  Terminada a execução do pacote, no menu Depurar, clique em Parar Depuração.  
  
## <a name="next-task-in-lesson"></a>Próxima tarefa da lição  
 [Etapa 4: Implantando o pacote da Lição 6](../integration-services/lesson-6-4-deploying-the-lesson-6-package.md)  
  
  
