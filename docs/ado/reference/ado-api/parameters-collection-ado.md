---
title: A coleção de parâmetros (ADO) | Microsoft Docs
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
- Command15::get_Parameters
- Command15::Parameters
- Command15::GetParameters
helpviewer_keywords:
- Parameters collection [ADO]
ms.assetid: 497cae10-3913-422a-9753-dcbb0a639b1b
caps.latest.revision: 20
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: b7c59411e1aeeaa32e2b1904e2503b26a92c829b
ms.sourcegitcommit: 62826c291db93c9017ae219f75c3cfeb8140bf06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35280646"
---
# <a name="parameters-collection-ado"></a>Coleção de parâmetros (ADO)
Contém todos os [parâmetro](../../../ado/reference/ado-api/parameter-object.md) objetos de um [comando](../../../ado/reference/ado-api/command-object-ado.md) objeto.  
  
## <a name="remarks"></a>Remarks  
 Um **comando** objeto tem um **parâmetros** coleção composta de **parâmetro** objetos.  
  
 Usando o [atualizar](../../../ado/reference/ado-api/refresh-method-ado.md) método em um **comando** do objeto **parâmetros** coleção recupera informações de parâmetro de provedor para o procedimento armazenado ou uma consulta parametrizada especificado no **comando** objeto. Alguns provedores dão suporte a chamadas de procedimento armazenado ou consultas parametrizadas; chamando o **atualizar** método o **parâmetros** coleção ao usar esse provedor será retornado um erro.  
  
 Se você não tiver definido sua própria **parâmetro** objetos e você acessar o **parâmetros** coleção antes de chamar o **atualizar** , ADO será automaticamente da chamada do método as método e popular a coleção para você.  
  
 Você pode minimizar as chamadas ao provedor para melhorar o desempenho se você souber que as propriedades dos parâmetros associados com o procedimento armazenado ou consulta parametrizada que você deseja chamar. Use o [CreateParameter](../../../ado/reference/ado-api/createparameter-method-ado.md) método para criar **parâmetro** objetos com as configurações de propriedade apropriado e use o [Append](../../../ado/reference/ado-api/append-method-ado.md) método para adicioná-los para o  **Parâmetros** coleção. Isso permite definir e retornar valores de parâmetro sem a necessidade de chamar o provedor para obter as informações de parâmetro. Se você estiver escrevendo um provedor que não fornece informações de parâmetro, você deve preencher manualmente o **parâmetros** coleção usando esse método para ser capaz de usar parâmetros. Use o [excluir](../../../ado/reference/ado-api/delete-method-ado-parameters-collection.md) método para remover **parâmetro** de objetos a partir de **parâmetros** coleção, se necessário.  
  
 Os objetos no **parâmetros** coleção de um **registros** vá fora do escopo (portanto fique indisponível) quando o **Recordset** está fechado.  
  
 Ao chamar um procedimento armazenado com **comando**, o parâmetro de valor de retorno e saída de um procedimento armazenado é recuperado da seguinte maneira:  
  
1.  Ao chamar um procedimento armazenado que não tem parâmetros, o **atualizar** método no **parâmetros** coleção deve ser chamada antes de chamar o **Execute** método no **Comando** objeto.  
  
2.  Ao chamar um procedimento armazenado com parâmetros e acrescentando explicitamente um parâmetro para o **parâmetros** coleção com **Append**, o parâmetro de valor de retorno e saída deve ser anexado a **Parâmetros** coleção. O valor de retorno deve ser anexado pela primeira vez para o **parâmetros** coleção. Use **Append** para adicionar os outros parâmetros para o **parâmetros** coleção na ordem de definição. Por exemplo, o procedimento armazenado SPWithParam tem dois parâmetros. O primeiro parâmetro, *InParam*, é um parâmetro de entrada definido como adVarChar (20) e o segundo parâmetro, *OutParam*, é um parâmetro de saída definido como adVarChar (20). Você pode recuperar o parâmetro de valor de retorno e saída com o código a seguir.  
  
    ```  
    ' Open Connection Conn  
    set ccmd = CreateObject("ADODB.Command")  
    ccmd.Activeconnection= Conn  
  
    ccmd.CommandText="SPWithParam"  
    ccmd.commandType = 4 'adCmdStoredProc  
  
    ccmd.parameters.Append ccmd.CreateParameter(, adInteger, adParamReturnValue, , NULL)   ' return value  
    ccmd.parameters.Append ccmd.CreateParameter("InParam", adVarChar, adParamInput, 20, "hello world")   ' input parameter  
    ccmd.parameters.Append ccmd.CreateParameter("OutParam", adVarChar, adParamOuput, 20, NULL)   ' output parameter  
  
    ccmd.execute()  
  
    ' Access ccmd.parameters(0) as return value of this stored procedure  
    ' Access ccmd.parameters("OutParam") as the output parameter of this stored procedure.  
  
    ```  
  
3.  Ao chamar um procedimento armazenado com parâmetros e configurar os parâmetros ao chamar o **Item** método o **parâmetros** coleção, o parâmetro de valor de retorno e saída do procedimento armazenado pode ser recuperado do **parâmetros** coleção. Por exemplo, o procedimento armazenado SPWithParam tem dois parâmetros. O primeiro parâmetro, *InParam*, é um parâmetro de entrada definido como adVarChar (20) e o segundo parâmetro, *OutParam*, é um parâmetro de saída definido como adVarChar (20). Você pode recuperar o parâmetro de valor de retorno e saída com o código a seguir.  
  
    ```  
    ' Open Connection Conn  
    set ccmd = CreateObject("ADODB.Command")  
    ccmd.Activeconnection= Conn  
  
    ccmd.CommandText="SPWithParam"  
    ccmd.commandType = 4 'adCmdStoredProc  
  
    ccmd.parameters.Item("InParam").value = "hello world" ' input parameter  
    ccmd.execute()  
  
    ' Access ccmd.parameters(0) as return value of stored procedure  
    ' Access ccmd.parameters(2) or ccmd.parameters("OutParam") as the output parameter.  
    ```  
  
 Esta seção contém o tópico a seguir.  
  
-   [Eventos, métodos e propriedades de coleção de parâmetros](../../../ado/reference/ado-api/parameters-collection-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Consulte também  
 [(ADO) do método append](../../../ado/reference/ado-api/append-method-ado.md)   
 [Método CreateParameter (ADO)](../../../ado/reference/ado-api/createparameter-method-ado.md)   
 [Objeto Parameter](../../../ado/reference/ado-api/parameter-object.md)
