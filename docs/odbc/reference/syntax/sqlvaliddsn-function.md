---
title: Função SQLValidDSN | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
apiname:
- SQLValidDSN
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLValidDSN
helpviewer_keywords:
- SQLValidDSN [ODBC]
ms.assetid: 930d1d89-337a-4429-85a2-84ee10555ac9
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 0d3dfd7e2b019626e98f8a93611880411e74b86a
ms.sourcegitcommit: c8f7e9f05043ac10af8a742153e81ab81aa6a3c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39082888"
---
# <a name="sqlvaliddsn-function"></a>Função SQLValidDSN
**Conformidade com**  
 Versão introduziu: ODBC 2.0  
  
 **Resumo**  
 **SQLValidDSN** verifica o comprimento e a validade do nome de fonte de dados antes do nome é adicionado às informações do sistema.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
BOOL SQLValidDSN(  
     LPCSTR    lpszDSN);  
```  
  
## <a name="arguments"></a>Argumentos  
 *lpszDSN*  
 [Entrada] Nome a ser verificado da fonte de dados.  
  
## <a name="returns"></a>Retorna  
 A função retorna TRUE se o nome da fonte de dados é válido. Retornará FALSE se o nome da fonte de dados é inválido ou a falha da chamada de função.  
  
## <a name="diagnostics"></a>Diagnóstico  
 Quando **SQLValidDSN** retornar FALSE, um associado  *\*pfErrorCode* valor pode ser obtido chamando **SQLInstallerError**. Um  *\*pfErrorCode* é retornado somente se a chamada de função falha, não se falso foi retornado porque o nome da fonte de dados é inválido. A seguinte tabela lista os  *\*pfErrorCode* valores que podem ser retornados por **SQLInstallerError** e explica cada uma no contexto dessa função.  
  
|*\*pfErrorCode*|Erro|Description|  
|---------------------|-----------|-----------------|  
|ODBC_ERROR_GENERAL_ERR|Erro geral de instalador|Ocorreu um erro para que nenhum erro específico do instalador.|  
|ODBC_ERROR_OUT_OF_MEM|Memória insuficiente|O instalador não foi possível executar a função devido à falta de memória.|  
  
## <a name="comments"></a>Comentários  
 **SQLValidDSN** é chamado por um driver [ConfigDSN](../../../odbc/reference/syntax/configdsn-function.md) para verificar o comprimento do nome de fonte de dados e a validade dos caracteres individuais no nome da fonte de dados. Ele verifica se o comprimento do nome é maior que SQL_MAX_DSN_LENGTH, conforme definido em sqlext. h. (O tamanho da fonte de dados também é verificado pela [SQLWriteDSNToIni](../../../odbc/reference/syntax/sqlwritedsntoini-function.md).) **SQLValidDSN** verifica se qualquer um dos seguintes caracteres inválidos são incluídos no nome da fonte de dados:  
  
 [ ] { } ( ) , ; ? * = ! \@ \  
  
## <a name="related-functions"></a>Funções relacionadas  
  
|Para obter informações sobre|Consulte|  
|---------------------------|---------|  
|Adicionar, modificar ou remover uma fonte de dados|[ConfigDSN](../../../odbc/reference/syntax/configdsn-function.md) (na configuração de DLL)|  
|Adicionar, modificar ou remover uma fonte de dados|[SQLConfigDataSource](../../../odbc/reference/syntax/sqlconfigdatasource-function.md)|  
|Escrever um nome de fonte de dados para as informações do sistema|[SQLWriteDSNToIni](../../../odbc/reference/syntax/sqlwritedsntoini-function.md)|
