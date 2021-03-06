---
title: Propriedade Dialect | Microsoft Docs
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
- _Command::Dialect
helpviewer_keywords:
- Dialect property
ms.assetid: 329c3a71-ba88-4009-b04f-2f52195a5957
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 638d02511078028fa6c5b1337fdb1b095d8e5c85
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35277915"
---
# <a name="dialect-property"></a>Propriedade Dialect
Indica o dialeto do [CommandText](../../../ado/reference/ado-api/commandtext-property-ado.md) ou [CommandStream](../../../ado/reference/ado-api/commandstream-property-ado.md) propriedades. O dialeto define a sintaxe e regras gerais que o provedor usa para analisar a cadeia de caracteres ou fluxo.  
  
## <a name="settings-and-return-values"></a>Configurações e valores de retorno  
 O **dialeto** propriedade contém um GUID válido que representa o dialeto do texto de comando ou fluxo. O valor padrão desta propriedade é {C8B521FB-5CF3-11CE-ADE5-00AA0044773D}, que indica que o provedor deve escolher como interpretar o texto de comando ou o fluxo.  
  
## <a name="remarks"></a>Remarks  
 ADO não consultar o provedor quando o usuário lê o valor dessa propriedade; Retorna uma representação de cadeia de caracteres do valor armazenado atualmente no [comando](../../../ado/reference/ado-api/command-object-ado.md) objeto.  
  
 Quando o usuário define o **dialeto** propriedade ADO valida o GUID e gera um erro se o valor fornecido não é um GUID válido. Consulte a documentação do provedor determinar os valores GUID com suporte a **dialeto** propriedade.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Command (ADO)](../../../ado/reference/ado-api/command-object-ado.md)  
  
## <a name="see-also"></a>Consulte também  
 [Método Execute (comando ADO)](../../../ado/reference/ado-api/execute-method-ado-command.md)
