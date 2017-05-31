---
title: "Consultando uma tabela hierárquica usando métodos de hierarquia | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- SQL Server 2016
helpviewer_keywords:
- HierarchyID
ms.assetid: 3b4f7dae-65b5-4d8d-8641-87aba9aa692d
caps.latest.revision: 18
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: af8bdce0dd68fbf33d364757cbb07d60054b1100
ms.contentlocale: pt-br
ms.lasthandoff: 04/11/2017

---
# <a name="lesson-2-3---querying-a-hierarchical-table-using-hierarchy-methods"></a>Lição 2-3 – Consultando uma tabela hierárquica usando métodos de hierarquia
Agora que a tabela HumanResources.EmployeeOrg está completamente populada, essa tarefa mostrará como consultar a hierarquia usando alguns métodos hierárquicos.  
  
### <a name="to-find-subordinate-nodes"></a>Para localizar nós subordinados  
  
1.  Sariya tem um funcionário subordinado. Para consultar os subordinados de Sara, execute a seguinte consulta, que usa o método [IsDescendantOf](../../t-sql/data-types/isdescendantof-database-engine.md) :  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ;  
  
    SELECT *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.IsDescendantOf(@CurrentEmployee ) = 1 ;  
    ```  
  
    O resultado lista Sariya e Wanida. Sariya é listada porque é a descendente no nível 0. Wanida é a descendente no nível 1.  
  
2.  Você também pode consultar essas informações usando o método [GetAncestor](../../t-sql/data-types/getancestor-database-engine.md) . `GetAncestor` usa um argumento para o nível que você está tentando retornar. Como Wanida está um nível abaixo de Sariya, use `GetAncestor(1)` conforme demonstrado no seguinte código:  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ;  
  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(1) = @CurrentEmployee  
    ```  
  
    Desta vez o resultado lista apenas Wanida.  
  
3.  Agora altere o `@CurrentEmployee` para David (EmployeeID 6) e o nível para 2. Execute o seguinte para retornar também Wanida:  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 6 ;  
  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(2) = @CurrentEmployee  
    ```  
  
    Desta vez, você também recebe Mary que também é subordinada a David, dois níveis abaixo.  
  
### <a name="to-use-getroot-and-getlevel"></a>Para usar GetRoot e GetLevel  
  
1.  À medida que a hierarquia fica maior é mais difícil determinar onde os membros estão na hierarquia. Use o método [GetLevel](../../t-sql/data-types/getlevel-database-engine.md) para localizar quantos níveis abaixo cada linha está na hierarquia. Execute o seguinte código para exibir os níveis de todas as linhas:  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode.GetLevel() AS EmpLevel, *  
    FROM HumanResources.EmployeeOrg ;  
    GO  
  
    ```  
  
2.  Use o método [GetRoot](../../t-sql/data-types/getroot-database-engine.md) para localizar o nó raiz na hierarquia. O seguinte código retorna uma única linha que é a raiz:  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode = hierarchyid::GetRoot() ;  
    GO  
  
    ```  
  
A próxima tarefa reorganizará a hierarquia.  
  
## <a name="next-task-in-lesson"></a>Próxima tarefa da lição  
[Reordenando dados em tabela hierárquica por meio de métodos hierárquicos](../../relational-databases/tables/lesson-2-4-reordering-data-in-a-hierarchical-table-using-hierarchical-methods.md)  
  
  
  
