---
title: Confirmar uma versão (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- committing versions [Master Data Services]
- versions [Master Data Services], committing
ms.assetid: 6b967a39-b333-4b84-9e5f-4fb07e156826
caps.latest.revision: 5
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: b65d604e3ca82294248437b1d21b0a41f6629251
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37205766"
---
# <a name="commit-a-version-master-data-services"></a>Confirmar uma versão (Master Data Services)
  No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], confirme uma versão de um modelo para evitar alterações para os membros do modelo e seus atributos. As versões confirmadas não podem ser desbloqueadas.  
  
## <a name="prerequisites"></a>Prerequisites  
 Para executar esse procedimento:  
  
-   Você deve ter permissão para acessar a área funcional **Gerenciamento de Versões** .  
  
-   Você deve ser um administrador de modelo. Para obter mais informações, veja [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).  
  
-   O status da versão deverá ser **Bloqueado**. Para obter mais informações, veja [Lock a Version &#40;Master Data Services&#41;](../../2014/master-data-services/lock-a-version-master-data-services.md).  
  
-   Todos os membros devem ter validado com êxito.  
  
### <a name="to-commit-a-version"></a>Para confirmar uma versão  
  
1.  No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Gerenciamento de Versões**.  
  
2.  Na página **Gerenciar Versões** , na barra de menus, clique em **Validar Versão**.  
  
3.  Na página **Validar Versão** , selecione o modelo e a versão que deseja confirmar.  
  
4.  Clique em **Confirmar**.  
  
5.  Na caixa de diálogo de confirmação, clique em **OK**.  
  
## <a name="next-steps"></a>Próximas etapas  
  
-   [Criar um sinalizador de versão &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md)  
  
-   [Atribuir um sinalizador a uma versão &#40;Master Data Services&#41;](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
-   [Copiar uma versão &#40;Master Data Services&#41;](../../2014/master-data-services/copy-a-version-master-data-services.md)  
  
## <a name="see-also"></a>Consulte também  
 [Versões de &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md)  
  
  
