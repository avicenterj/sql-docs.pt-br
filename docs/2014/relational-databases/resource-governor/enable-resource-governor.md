---
title: Habilitar Administrador de Recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, enabling
ms.assetid: 4d17af53-cf11-4ce4-aab4-deda94a49836
caps.latest.revision: 12
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 1d39e6408450deae6a3967471d0ed1c32d85af73
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37248606"
---
# <a name="enable-resource-governor"></a>Habilitar Administrador de Recursos
  O Administrador de Recursos é desativado por padrão. Você pode habilitar o Administrador de Recursos usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou Transact-SQL.  
  
-   **Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions), [Permissions](#Permissions)  
  
-   **To enable Resource Governorn, using:**  [Object Explorer](#RGOnObjEx), [Resource Governor Properties](#RGOnProp), [Transact-SQL](#RGOnTSQL)  
  
##  <a name="BeforeYouBegin"></a> Antes de começar  
 A habilitação do administrador de recursos gera os seguintes resultados:  
  
-   A função de classificação é executada para conexões novas, de forma que as cargas de trabalho possam ser atribuídas a grupos de carga de trabalho.  
  
-   Os limites de recursos especificados na configuração do Administrador de Recursos são cumpridos e impostos.  
  
-   As solicitações existentes antes da habilitação do Administrador de Recursos são afetadas por todas as alterações feitas na configuração quando o Administrador de Recursos foi desabilitado.  
  
###  <a name="LimitationsRestrictions"></a> Limitações e Restrições  
 Você não pode usar a instrução `ALTER RESOURCE GOVERNOR` para habilitar o Administrador de Recursos quando estiver em uma transação de usuário.  
  
###  <a name="Permissions"></a> Permissões  
 Habilitar o Administrador de Recursos exige permissão CONTROL SERVER.  
  
##  <a name="RGOnObjEx"></a> Habilitar o Administrador de Recursos usando o Pesquisador de Objetos  
 **Para habilitar o Administrador de Recursos usando o Pesquisador de Objetos**  
  
1.  No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra o Pesquisador de Objetos e expanda recursivamente o nó **Gerenciamento** para baixo e incluindo o **Administrador de Recursos**.  
  
2.  Clique com o botão direito do mouse em **Resource Governor**e clique em **Habilitar**.  
  
##  <a name="RGOnProp"></a> Habilitar o Administrador de Recursos usando as Propriedades do Administrador de Recursos  
 **Para habilitar o Administrador de Recursos usando a página de propriedades do Administrador de Recursos**  
  
1.  No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra o Pesquisador de Objetos e expanda recursivamente o nó **Gerenciamento** para baixo e incluindo o **Administrador de Recursos**.  
  
2.  Clique com o botão direito do mouse em **Administrador de Recursos** e clique em **Propriedades**, para abrir a página **Propriedades do Administrador de Recursos** .  
  
3.  Clique na caixa de seleção **Habilitar Administrador de Recursos** e, em seguida, clique em **OK**.  
  
##  <a name="RGOnTSQL"></a> Habilitar o Administrador de Recursos usando Transact-SQL  
 **Para habilitar o Administrador de Recursos usando Transact-SQL**  
  
1.  Execute a instrução **ALTER RESOURCE GOVERNOR RECONFIGURE** .  
  
### <a name="example-transact-sql"></a>Exemplo (Transact-SQL)  
 O exemplo a seguir habilita o Administrador de Recursos.  
  
```  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
 [Administrador de Recursos](resource-governor.md)   
 [Desabilitar Administrador de Recursos](disable-resource-governor.md)   
 [Pool de recursos do Administrador de Recursos](resource-governor-resource-pool.md)   
 [Grupos de carga de trabalho do Administrador de Recursos](resource-governor-workload-group.md)   
 [Função de classificação do Administrador de Recursos](resource-governor-classifier-function.md)   
 [ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
