---
title: "O método de busca | Microsoft Docs"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- Recordset21::Seek
- Recordset21::raw_Seek
helpviewer_keywords:
- Seek method [ADO]
ms.assetid: 129293d2-19d3-4940-bf64-483ee72fb4a1
caps.latest.revision: 12
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: d401bca51d735b2d0d633716cee732ad2ab9a086
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="seek-method"></a>O método de pesquisa
Pesquisa o índice de um [registros](../../../ado/reference/ado-api/recordset-object-ado.md) para localizar rapidamente a linha que corresponde aos valores especificados e altera a posição da linha atual para aquela linha.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
recordset.Seek KeyValues, SeekOption  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *KeyValues*  
 Uma matriz de **Variant** valores. Um índice consiste em uma ou mais colunas e a matriz contém um valor de comparação em cada coluna correspondente.  
  
 *SeekOption*  
 Um [SeekEnum](../../../ado/reference/ado-api/seekenum.md) valor que especifica o tipo de comparação a ser feita entre as colunas do índice e correspondente *KeyValues*.  
  
## <a name="remarks"></a>Comentários  
 Use o **busca** método junto com o [índice](../../../ado/reference/ado-api/index-property.md) propriedade se o provedor subjacente que dá suporte a índices no **registros** objeto. Use o [dá suporte a](../../../ado/reference/ado-api/supports-method.md)**(adSeek)** método para determinar se o provedor subjacente oferece suporte a **busca**e o **Supports(adIndex)** método para determinar se o provedor oferece suporte a índices. (Por exemplo, o [OLE DB Provider for Microsoft Jet](../../../ado/guide/appendixes/microsoft-ole-db-provider-for-microsoft-jet.md) dá suporte a **busca** e **índice**.)  
  
 Se **busca** não localizar a linha desejada, nenhum erro ocorrerá e a linha é posicionado no final do **registros**. Definir o **índice** propriedade para o índice desejada antes de executar esse método.  
  
 Esse método tem suporte apenas com cursores do lado do servidor. Busca não é suportado quando o **registros** do objeto [CursorLocation](../../../ado/reference/ado-api/cursorlocation-property-ado.md) é o valor da propriedade **adUseClient**.  
  
 Esse método só pode ser usado quando o **registros** objeto tenha sido aberto com um [CommandTypeEnum](../../../ado/reference/ado-api/commandtypeenum.md) valor **adCmdTableDirect**.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Recordset (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo de propriedade de índice (VB) e método de busca](../../../ado/reference/ado-api/seek-method-and-index-property-example-vb.md)   
 [Exemplo de propriedade de índice (VC + +) e método de busca](../../../ado/reference/ado-api/seek-method-and-index-property-example-vc.md)   
 [Localizar o método (ADO)](../../../ado/reference/ado-api/find-method-ado.md)   
 [Propriedade Index](../../../ado/reference/ado-api/index-property.md)