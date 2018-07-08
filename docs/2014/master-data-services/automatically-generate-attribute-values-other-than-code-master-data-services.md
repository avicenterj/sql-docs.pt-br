---
title: Gerar automaticamente valores de atributo diferentes de código (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b82f6f81-6e9c-4918-9ea9-4ab5f5d11b15
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 9d895f2270f28ff3da8aabfa2a8701c589b1829e
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36120164"
---
# <a name="automatically-generate-attribute-values-other-than-code-master-data-services"></a>Gerar automaticamente valores de atributo diferentes de código (Master Data Services)
  No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], gera automaticamente valores para os valores de atributo da entidade quando você deseja atribuir um inteiro automaticamente como o valor sempre que as regras de negócio são aplicadas.  
  
## <a name="prerequisites"></a>Prerequisites  
 Para executar esse procedimento:  
  
-   Você deve ter permissão para acessar a área funcional **Administração do Sistema** .  
  
-   Você deve ser um administrador de modelo. Para obter mais informações, veja [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).  
  
-   Um atributo numérico deve existir. Para obter mais informações, consulte [Criar um atributo numérico &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md).  
  
### <a name="to-automatically-generate-an-attribute-value"></a>Para gerar automaticamente um valor de atributo  
  
1.  No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Administração do Sistema**.  
  
2.  Na barra de menus, aponte para **Gerenciar** e clique em **Regras de Negócios**.  
  
3.  Na página **Manutenção de Regra de Negócio** , na lista **Modelo** , selecione um modelo.  
  
4.  Na lista **Entidade** , selecione uma entidade.  
  
5.  Na lista **Tipo de Membro** , selecione um tipo de membro ao qual a regra de negócio será aplicada.  
  
6.  Na lista **Atributo** , deixe o valor padrão **Todos**.  
  
7.  Clique em **Adicionar regra de negócio**.  
  
8.  Clique em **Editar regra de negócio selecionada**.  
  
9. No painel **Componentes** , expanda o nó **Ações** .  
  
10. No nó Valor Padrão, clique em **padrões para um valor gerado** e arraste-o até o rótulo **Ações** do painel **THEN** .  
  
11. No painel **Atributos** , clique no atributo com o valor que você deseja gerar e arraste-o para o rótulo **Selecionar atributo** do painel **Editar Ação** .  
  
12. Digite um valor nas caixas **Iniciar com** e **Incrementar por** . Se os membros já existirem, o valor será definido com base no valor existente mais alto. Por exemplo, se o valor existente mais alto for 299 e você definir **Incrementar por** como **1**, o valor do próximo membro será definido como 300.  
  
13. No painel **Editar Ação** , clique em **Salvar item**.  
  
14. Clique em **Voltar**.  
  
15. Opcionalmente, na página **Manutenção de Regra de Negócio** , na linha que contém sua regra de negócio, clique duas vezes em uma célula da coluna **Nome**, **Descrição**ou **Notificação** para atualizar o valor.  
  
16. Clique em **Publicar regras de negócio**.  
  
17. Na caixa de diálogo de confirmação, clique em **OK**. O status da regra mudará para **Ativo**.  
  
## <a name="next-steps"></a>Próximas etapas  
  
-   [Validar membros específicos em relação a regras de negócios &#40;Master Data Services&#41;](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
-   [Validar uma versão em relação a regras de negócios &#40;Master Data Services&#41;](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a>Consulte também  
 [Criação automática de código &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md)   
 [Regras de negócio &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md)   
 [Validação &#40;Master Data Services&#41;](../../2014/master-data-services/validation-master-data-services.md)  
  
  