---
title: Erros e avisos de colunas de dados de eventos | Microsoft Docs
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: trace-events
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 84a1f21e5556efcf64e1ff1b7c6d5ab2208d1038
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34043090"
---
# <a name="errors-and-warnings-events-data-columns"></a>Colunas de dados de eventos de erros e de avisos
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  A categoria de evento de segurança de auditoria tem a seguinte classe de evento:  
  
-   Classe de erro  
  
 A tabela a seguir lista as colunas de dados dessa classe de evento.  
  
## <a name="error-event-classdata-columns"></a>Classe Error Event - Colunas de dados  
  
|**Nome da coluna**|**Id da coluna**|**Tipo de coluna**|**Descrição da coluna**|  
|---------------------|-------------------|---------------------|----------------------------|  
|EventClass|0|1|A classe de evento é usada para categorizar eventos.|  
|StartTime|3|5|Contém a hora em que o evento iniciou, quando disponível. Para filtragem, os formatos esperados são 'AAAA-MM-DD' e 'AAAA-MM-DD HH:MM:SS'.|  
|SessionType|8|8|Contém o tipo de entidade que causou o erro.|  
|Severity|22|1|Contém o nível de severidade de uma exceção associada ao evento de erro. Os valores são:<br /><br /> 0 = Êxito<br /><br /> 1 = Informativo<br /><br /> 2 = Aviso<br /><br /> 3 = Erro|  
|Success|23|1|Contém o êxito ou a falha do evento de erro. Os valores são:<br /><br /> 0 = Falha<br /><br /> 1 = Êxito|  
|Erro|24|1|Contém o número de qualquer erro associado ao evento de erro.|  
|ConnectionID|25|1|Contém a ID de conexão exclusiva associada ao evento de erro.|  
|DatabaseName|28|8|Contém o nome da instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] na qual o evento de erro ocorreu.|  
|NTUserName|32|8|Contém o nome de usuário do Windows associado ao evento de erro.|  
|NTDomainName|33|8|Contém a conta de domínio do Windows associada ao evento de logon.|  
|ClientHostName|35|8|Contém o nome do computador no qual o cliente está sendo executado. Essa coluna de dados será populada se o nome do host for fornecido pelo cliente.|  
|ClientProcessID|36|1|Contém a ID de processo do aplicativo cliente.|  
|ApplicationName|37|8|Contém o nome do aplicativo cliente que criou a conexão com o servidor. Essa coluna é populada com os valores passados pelo aplicativo e não com o nome exibido do programa.|  
|SessionID|39|8|Contém a identificação do processo do servidor (SPID) que identifica de modo exclusivo a sessão de usuário associada ao evento de erro. A SPID corresponde diretamente à GUID de sessão usada pelo XML for Analysis (XMLA).|  
|SPID|41|1|Contém a identificação do processo do servidor (SPID) que identifica de modo exclusivo a sessão de usuário associada ao evento de erro. A SPID corresponde diretamente à GUID de sessão usada pelo XML for Analysis (XMLA).|  
|TextData|42|9|Contém os dados de texto associados ao evento de erro.|  
|ServerName|43|8|Contém o nome do servidor que executa a instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] na qual o evento de erro ocorreu.|  
  
## <a name="see-also"></a>Consulte também  
 [Categoria de evento de auditoria de segurança](../../analysis-services/trace-events/security-audit-event-category.md)  
  
  
