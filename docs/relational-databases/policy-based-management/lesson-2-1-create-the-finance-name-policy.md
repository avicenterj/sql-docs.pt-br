---
title: Criar a política Nome Financeiro | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.component: performance-monitor
ms.reviewer: ''
ms.suite: sql
ms.technology: performance
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- SQL Server 2016
ms.assetid: 56b2c852-fd69-4cd2-9b5d-977467b94fd9
caps.latest.revision: 26
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: b77e28d77f4e968874fd4c378d2c548eed8aed4e
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32955981"
---
# <a name="lesson-2-1---create-the-finance-name-policy"></a>Lição 2-1 – Criar a política Nome Financeiro
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
Nessa tarefa, você criará um banco de dados chamado Finance e uma condição que exige que todas as tabelas comecem com as letras **fintbl**. Em seguida, você criará uma política e uma categoria de políticas para impor um padrão de nomenclatura para as tabelas no banco de dados Finanças.  
  
### <a name="to-create-the-finance-database"></a>Para criar o banco de dados Finanças  
  
1.  Em [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], abra uma janela de consulta e execute a instrução a seguir:  
  
    ```  
    CREATE DATABASE Finance ;  
    GO  
    ```  
  
2.  No Pesquisador de Objetos, clique em **Bancos de Dados**e, em seguida, pressione F5 para atualizar a lista de bancos de dados.  
  
### <a name="to-create-the-finance-tables-condition"></a>Para criar a condição Tabelas de Finanças  
  
1.  No Pesquisador de Objetos, expanda **Gerenciamento**, **Gerenciamento de Política**, clique com o botão direito do mouse em **Condições**e clique em **Nova Condição**.  
  
2.  Na caixa de diálogo **Criar Nova Condição** , na caixa **Nome** , digite **Tabelas de Finanças**.  
  
3.  Na lista **Faceta** , selecione **Nome com Diversas Partes**.  
  
4.  Na caixa de diálogo **Expressão** , na caixa **Campo** , selecione **@Name**; na caixa **Operador** , selecione **Like**; e na caixa **Valor** , digite **'fintbl%'** para forçar todos os nomes de tabelas a começar com as letras **fintbl**.  
  
5.  Na página **Descrição** , digite **Os nomes da tabela de Finanças deve começar com fintbl**e, em seguida, clique em **OK** para criar a condição.  
  
### <a name="to-create-the-finance-name-policy"></a>Para criar a política Nome Financeiro  
  
1.  No Pesquisador de Objetos, clique com o botão direito do mouse em **Políticas**e clique em **Nova Política**.  
  
2.  Na caixa de diálogo **Criar Nova Política** , na caixa **Nome** , digite **Nome de Finanças**.  
  
3.  Na lista **Verificar condição** , selecione **Tabelas de Finanças**. Isso está na área **Nome com Diversas Partes** .  
  
4.  Na área **Contra** você verá uma lista dos objetos de banco de dados que poderiam aplicar essa política. Selecione a caixa de seleção para **Cada Tabela**.  
  
5.  Na área **Cada Banco de Dados** , expanda **Tudo**e clique em **Nova condição**.  
  
6.  Na caixa de diálogo **Criar Nova Condição** , na caixa **Nome** , digite **Banco de Dados de Finanças**.  
  
7.  Na caixa **Expressão**, complete a expressão para incluir **@Name = 'Finance'** e clique em **OK** para fechar a página de condição.  
  
    > [!NOTE]  
    > Você poderia ter a guia fora da caixa **Valor** para habilitar o botão **OK** .  
  
8.  Na lista **Modo de Avaliação** , selecione **Ao alterar: impedir**. Isso aplicará a política criando um gatilho de banco de dados no banco de dados Finanças.  
  
9. Selecione a lista **Habilitado** . (A caixa **Habilitado** não se aplica a políticas **Sob Demanda** .)  
  
10. Na lista **Restrição de servidor** , selecione **Nenhum**.  
  
11. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-create-the-finance-policy-category"></a>Para criar a categoria da política Finanças  
  
1.  Em Pesquisador de Objetos, expanda **Gerenciamento**, clique com o botão direito do mouse em **Gerenciamento de Política**e clique em **Gerenciar Categorias**.  
  
2.  Na caixa de diálogo **Gerenciar Categorias de Política** , em **Nome**, digite **Finanças** na caixa em branco e desmarque **Autorizar Assinaturas de Banco de Dados**. A opção**Autorizar Assinaturas de Banco de Dados** forçará todos os bancos de dados na instância a assinarem as políticas que pertencem a esta categoria de política. Para esta lição, somente o banco de dados Finanças deve assinar a política Nome Financeiro.  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a>Próxima tarefa da lição  
[Assinar e verificar a política Nome Financeiro](../../relational-databases/policy-based-management/lesson-2-2-subscribe-to-and-check-the-finance-name-policy.md)  
  
  
  
