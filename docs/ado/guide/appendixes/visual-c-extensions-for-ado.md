---
title: "Extensões do Visual C++ para ADO | Microsoft Docs"
ms.prod: sql-non-specified
ms.technology:
- drivers
ms.custom: H1Hack27Feb2017
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ADO, Visual C++
- Visual C++ [ADO], VC++ extensions for ADO
ms.assetid: 2952ece0-7217-4448-bb09-f6b64f43b7e2
caps.latest.revision: 10
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: fbc17b15d552f9b7afeeb4841febdd7d08e54808
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="visual-c-extensions"></a>Extensões do Visual C++
O método preferido de programação ADO com o Visual C++ está usando o **#import** diretiva, conforme discutido em [programação do Microsoft Visual C++ ADO](../../../ado/guide/appendixes/visual-c-ado-programming.md). No entanto, versões anteriores do ADO fornecido com um método alternativo de programação usando o Visual C++: as extensões do Visual C++. Esta seção documenta esse recurso para aqueles que deve manter o código de extensões do Visual C++, mas o novo código ADO deve ser escrito usando #**importar**.

 Um dos mais entediante trabalhos Visual C++ programadores face ao recuperar dados com ADO é converter os dados retornados como um tipo de dados VARIANT em um tipo de dados do C++ e armazenando os dados convertidos em uma classe ou estrutura. Além de ser um incômodo, recuperando dados de C++ por meio de um tipo de dados VARIANT afeta o desempenho.

 ADO fornece uma interface que oferece suporte à recuperação de dados em tipos de dados C/C++ nativo sem passar por uma VARIANTE e também fornece macros de pré-processador que simplificam o uso da interface. O resultado é uma ferramenta flexível que é mais fácil de usar e exibe um ótimo desempenho.

 É um cenário comum de cliente do C/C++ vincular um registro em uma [registros](../../../ado/reference/ado-api/recordset-object-ado.md) para uma classe que contém os tipos do C/C++ nativo ou a estrutura C/C++. Ao passar por variantes, isso envolve a escrever código de conversão de VARIANT para tipos de C/C++ nativo. As extensões do Visual C++ para o ADO são direcionadas a fazer neste cenário muito mais fácil para o programador do Visual C++.

 Consulte os tópicos a seguir para saber mais sobre as extensões do Visual C++ para ADO.

-   [Usando as extensões do Visual C++ para ADO](../../../ado/guide/appendixes/using-visual-c-extensions.md)

-   [Cabeçalho de extensões do Visual C++](../../../ado/guide/appendixes/visual-c-extensions-header.md)

-   [ADO com exemplo de extensões do Visual C++](../../../ado/guide/appendixes/visual-c-extensions-example.md)

## <a name="see-also"></a>Consulte também
 [ADO para o índice da sintaxe do Visual C++ COM](../../../ado/reference/ado-api/ado-for-visual-c-syntax-index-for-com.md) [exemplo de extensões do Visual C++](../../../ado/guide/appendixes/visual-c-extensions-example.md) [usando as extensões do Visual C++](../../../ado/guide/appendixes/using-visual-c-extensions.md) [cabeçalho de extensões do Visual C++](../../../ado/guide/appendixes/visual-c-extensions-header.md)
