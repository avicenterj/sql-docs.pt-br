---
title: IsNull (tipo de dados geometry) | Microsoft Docs
ms.custom: 
ms.date: 08/03/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- IsNull (geometry Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- IsNull (geometry Data Type)
ms.assetid: f95813a5-26c0-48aa-bfb8-56d2a0980788
caps.latest.revision: 13
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 9136a2caf43fea8d5cccd90d8dba85d815511afe
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="isnull-geometry-data-type"></a>IsNull (tipo de dados geometry)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

O tipo de um **geometria** instância é nula. Retornará 0 se a instância não for nula.
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
.IsNull  
```  
  
## <a name="return-types"></a>Tipos de retorno  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]tipo: **bits**  
  
 Tipo CLR: **SqlBoolean**  
  
## <a name="remarks"></a>Comentários  
 `IsNull`pode ser usado para testar se um **geometria** instância é nula. O resultado pode ser um pouco confuso, retornando 0 se a instância não for nula, mas null se a instância for nula.  
  
 Esse método é usado basicamente pela infraestrutura do SQL Server; é recomendável o uso de `IsNull` para testar se uma instância é nula.  
  
## <a name="examples"></a>Exemplos  
  
## <a name="see-also"></a>Consulte também  
 [Métodos estendidos em instâncias de geometria](../../t-sql/spatial-geometry/extended-methods-on-geometry-instances.md)  
  
  

