---
title: O objeto de usuário (ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.tgt_pltfrm: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- User
helpviewer_keywords:
- User object [ADOX]
ms.assetid: f68e32ce-ef7c-407d-bdb5-d280947ae0e2
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 206d8fb122b9c2f28370a56f3a4acaeabebf111b
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35287365"
---
# <a name="user-object-adox"></a>Objeto de usuário (ADOX)
Representa uma conta de usuário que tenha permissões de acesso dentro de um banco de dados protegido.  
  
## <a name="remarks"></a>Remarks  
 O [usuários](../../../ado/reference/adox-api/users-collection-adox.md) coleção de um [catálogo](../../../ado/reference/adox-api/catalog-object-adox.md) representa usuários todos do catálogo. O **usuários** coleção para um [grupo](../../../ado/reference/adox-api/group-object-adox.md) representa apenas os usuários do grupo específico.  
  
 Com as propriedades, coleções e métodos de um **usuário** do objeto, você pode:  
  
-   Identificar o usuário com o [nome](../../../ado/reference/adox-api/name-property-adox.md) propriedade.  
  
-   Alterar a senha de um usuário com o [ChangePassword](../../../ado/reference/adox-api/changepassword-method-adox.md) método.  
  
-   Determinar se um usuário tem de leitura, gravação ou exclusão de permissões com a [GetPermissions](../../../ado/reference/adox-api/getpermissions-method-adox.md) e [SetPermissions](../../../ado/reference/adox-api/setpermissions-method-adox.md) métodos.  
  
-   O acesso os grupos aos quais um usuário pertence com o [grupos](../../../ado/reference/adox-api/groups-collection-adox.md) coleção.  
  
-   Acessar as propriedades específicas do provedor com o [propriedades](../../../ado/reference/ado-api/properties-collection-ado.md) coleção.  
  
-   Determinar a [ParentCatalog](../../../ado/reference/adox-api/parentcatalog-property-adox.md) para um usuário.  
  
 Esta seção contém o tópico a seguir.  
  
-   [Propriedades, Métodos e Eventos do objeto User](../../../ado/reference/adox-api/user-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo de métodos de SetPermissions (VB) e GetPermissions](../../../ado/reference/adox-api/getpermissions-and-setpermissions-methods-example-vb.md)   
 [Coleção de grupos (ADOX)](../../../ado/reference/adox-api/groups-collection-adox.md)   
 [Coleção Users (ADOX)](../../../ado/reference/adox-api/users-collection-adox.md)
