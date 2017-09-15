---
title: ALTER FULLTEXT STOPLIST (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ALTER FULLTEXT STOPLIST
- ALTER_FULLTEXT_STOPLIST_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- stoplists [full-text search]
- full-text search [SQL Server], stoplists
- ALTER FULLTEXT STOPLIST statement
- full-text search [SQL Server], stopwords
- stopwords [full-text search]
ms.assetid: f6ad87d5-6a34-435a-8456-8244947c5c83
caps.latest.revision: 37
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 314e41c5b885ee5441dbc4c88db14c22fc50e7b7
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="alter-fulltext-stoplist-transact-sql"></a>ALTER FULLTEXT STOPLIST (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Insere ou exclui uma palavra irrelevante na lista de palavras irrelevantes de texto completo padrão do banco de dados atual.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
ALTER FULLTEXT STOPLIST stoplist_name  
{   
        ADD [N] 'stopword' LANGUAGE language_term    
  | DROP   
    {  
        'stopword' LANGUAGE language_term   
      | ALL LANGUAGE language_term   
      | ALL  
     }  
;  
```  
  
## <a name="arguments"></a>Argumentos  
 *stoplist_name*  
 É o nome da lista de palavras irrelevantes que está sendo alterada. *stoplist_name* pode ter no máximo 128 caracteres.  
  
 **'** *palavra irrelevante* **'**  
 É uma cadeia de caracteres que pode ser uma palavra com significado linguístico no idioma especificado ou um token sem significado linguístico. *palavra irrelevante* é limitado ao comprimento máximo do token (64 caracteres). Uma palavra irrelevante pode ser especificada como uma cadeia de caracteres de Unicode.  
  
 IDIOMA *language_term*  
 Especifica o idioma para associar o *palavra irrelevante* sendo adicionada ou removida.  
  
 *language_term* pode ser especificado como uma cadeia de caracteres, inteiro ou valor hexadecimal que corresponda ao identificador de localidade (LCID) do idioma, da seguinte maneira:  
  
|Formato|Description|  
|------------|-----------------|  
|Cadeia de caracteres|*language_term* corresponde ao **alias** no valor da coluna de [sys. syslanguages (Transact-SQL)](../../relational-databases/system-compatibility-views/sys-syslanguages-transact-sql.md) exibição de compatibilidade. A cadeia de caracteres deve ser colocada entre aspas, como em **'***language_term***'**.|  
|Integer|*language_term* é o LCID do idioma.|  
|Hexadecimal|*language_term* é 0x seguido pelo valor hexadecimal do LCID. O valor hexadecimal não deve exceder oito dígitos, inclusive zeros à esquerda. Se o valor estiver no formato DBCS (conjunto de caracteres de dois bytes), o SQL Server o converterá em Unicode.|  
  
 Adicionar **'***palavra irrelevante***'** idioma *language_term*  
 Adiciona uma palavra irrelevante à lista de palavras irrelevantes para o idioma especificado pela LINGUAGEM *language_term*.  
  
 Se a combinação especificada de palavra-chave e o valor LCID do idioma não forem exclusivos da STOPLIST, um erro será retornado.  Se o valor LCID não corresponder a um idioma registrado, um erro será gerado.  
  
 Descartar { **'***palavra irrelevante***'** idioma *language_term* | Todos os IDIOMAS *language_term* | ALL}  
 Descarta uma palavra irrelevante da lista de palavras irrelevantes.  
  
 **'** *palavra irrelevante* **'** idioma *language_term*  
 Descarta a palavra irrelevante especificada para o idioma especificado por *language_term*.  
  
 Todos os IDIOMAS *language_term*  
 Descarta todas as palavras de parada para o idioma especificado por *language_term*.  
  
 ALL  
 Descarta todas as palavras irrelevantes da lista de palavras irrelevantes.  
  
## <a name="remarks"></a>Comentários  
 Só há suporte para CREATE FULLTEXT STOPLIST no nível de compatibilidade 100 e superior. Nos níveis de compatibilidade 80 e 90, a lista de palavras irrelevantes do sistema sempre é atribuída ao banco de dados.  
  
## <a name="permissions"></a>Permissões  
 Para designar uma lista de palavras irrelevantes como a lista de palavras irrelevantes padrão do banco de dados é necessário ter a permissão ALTER DATABASE. Para alterar uma lista de palavras irrelevantes é necessário ser o proprietário da lista de palavras irrelevantes ou associação no **db_owner** ou **db_ddladmin** funções de banco de dados fixas.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir altera uma lista de palavras irrelevantes chamada `CombinedFunctionWordList`, adicionando a palavra 'en', primeiro para espanhol e depois para francês.  
  
```  
ALTER FULLTEXT STOPLIST CombinedFunctionWordList ADD 'en' LANGUAGE 'Spanish';  
ALTER FULLTEXT STOPLIST CombinedFunctionWordList ADD 'en' LANGUAGE 'French';  
```  
  
## <a name="see-also"></a>Consulte também  
 [CREATE FULLTEXT STOPLIST &#40; Transact-SQL &#41;](../../t-sql/statements/create-fulltext-stoplist-transact-sql.md)   
 [REMOVER palavras IRRELEVANTES de texto completo &#40; Transact-SQL &#41;](../../t-sql/statements/drop-fulltext-stoplist-transact-sql.md)   
 [Configurar e gerenciar palavras irrelevantes e listas de palavras irrelevantes para pesquisa de texto completo](../../relational-databases/search/configure-and-manage-stopwords-and-stoplists-for-full-text-search.md)   
 [sys.fulltext_stoplists &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql.md)   
 [sys.fulltext_stopwords &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql.md)   
 [Configurar e gerenciar palavras irrelevantes e listas de palavras irrelevantes para pesquisa de texto completo](../../relational-databases/search/configure-and-manage-stopwords-and-stoplists-for-full-text-search.md)  
  
  