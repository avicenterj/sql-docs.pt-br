---
title: Adicionar tabelas a diagramas (Ferramentas de Banco de Dados Visual) | Microsoft Docs
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
- inserting tables
- adding tables
ms.assetid: 5440fdf7-ac04-4325-9f32-181f4cd402e5
caps.latest.revision: 5
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: ae6c38826ce111508e88de0948ffe8e1ecb35c24
ms.contentlocale: pt-br
ms.lasthandoff: 04/11/2017

---
# <a name="add-tables-to-diagrams-visual-database-tools"></a>Adicionar tabelas a diagramas (Visual Database Tools)
Você pode adicionar uma tabela a seu diagrama de banco de dados para editar sua estrutura ou relacioná-la a outras tabelas no diagrama. Você pode adicionar tabelas de banco de dados existentes a um diagrama ou inserir uma tabela nova que ainda não foi definida no banco de dados.  
  
### <a name="to-insert-a-new-table-into-a-diagram"></a>Para inserir uma tabela nova em um diagrama  
  
1.  Verifique se você está conectado ao banco de dados em que deseja criar a tabela.  
  
    Para criar uma tabela em seu diagrama atual, clique no botão **Nova Tabela** na barra de ferramentas.  
  
    –ou–  
  
    Clique com o botão direito do mouse no diagrama e selecione **Nova Tabela**.  
  
2.  Altere ou aceite o nome de tabela atribuído pelo sistema, na caixa de diálogo **Escolher Nome** e escolha **OK**.  
  
    Uma nova tabela será exibida no diagrama na exibição Padrão.  
  
3.  Na primeira célula da nova tabela, digite um nome de coluna. Depois, pressione a tecla TAB para ir para a próxima célula.  
  
4.  Em **Tipo de Dados**, selecione um tipo de dados para a coluna. Cada coluna deve ter um nome e um tipo de dados.  
  
    Você pode definir as outras propriedades da coluna no Designer de Tabela.  
  
5.  Repita as etapas 3 e 4 para cada coluna que deseja adicionar à tabela.  
  
> [!NOTE]  
> Quando você salvar o diagrama de banco de dados, a nova tabela será adicionada ao seu banco de dados.  
  
### <a name="to-add-an-existing-table-to-a-diagram"></a>Para adicionar uma tabela existente a um diagrama  
  
1.  Verifique se você está conectado ao banco de dados cujas tabelas deseja editar.  
  
2.  Selecione uma tabela na pasta **Tabelas** .  
  
3.  Arraste a tabela para seu diagrama de banco de dados.  
  
4.  Solte o botão do mouse.  
  
> [!NOTE]  
> Se existirem relações entre a tabela escolhida e as outras tabelas de seu diagrama, as linhas de relação serão desenhadas automaticamente.  
  
### <a name="to-add-related-tables-to-a-diagram"></a>Para adicionar tabelas relacionadas a um diagrama  
  
1.  Selecione uma ou mais tabelas com restrições de chave estrangeira no diagrama de banco de dados.  
  
2.  Clique com o botão direito do mouse em qualquer tabela selecionada e escolha **Adicionar Tabelas Relacionadas**.  
  
> [!NOTE]  
> As duas tabelas referenciadas por uma restrição de chave estrangeira da tabela selecionada e aquelas que referenciam a tabela selecionada com uma restrição de chave estrangeira são adicionadas ao diagrama.  
  
## <a name="see-also"></a>Consulte também  
[Trabalhar com diagramas de banco de dados (Visual Database Tools)](../../ssms/visual-db-tools/work-with-database-diagrams-visual-database-tools.md)  
[Trabalhar com tabelas no diagrama de banco de dados (Visual Database Tools)](../../ssms/visual-db-tools/work-with-tables-in-database-diagram-visual-database-tools.md)  
  
