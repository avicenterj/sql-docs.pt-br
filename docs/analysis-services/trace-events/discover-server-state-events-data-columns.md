---
title: Colunas de dados de eventos de estado do servidor de identificação | Microsoft Docs
ms.date: 05/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: trace-events
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: af00bfd3d38f7014efaa04037ffdd0754165e232
ms.sourcegitcommit: c12a7416d1996a3bcce3ebf4a3c9abe61b02fb9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34045160"
---
# <a name="discover-server-state-events-data-columns"></a>Colunas de dados de eventos de identificação do estado do servidor
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  A categoria de evento Discover Server State tem as seguintes classes de evento:  
  
|**ID do evento**|**Nome do evento**|**Descrição do evento**|  
|------------------|--------------------|---------------------------|  
|33|Server State Discover Begin|Início do Server State Discover.|  
|34|Server State Discover Data|Conteúdo do Server State Discover Response.|  
|35|Server State Discover End|Final do Server State Discover.|  
  
 As tabelas a seguir listam as colunas de dados de cada uma dessas classes de evento.  
  
## <a name="server-state-discover-begin-classdata-columns"></a>Classe Server State Discover Begin - Colunas de dados  
  
|||||  
|-|-|-|-|  
|**Nome da coluna**|**Id da coluna**|**Tipo de coluna**|**Descrição da coluna**|  
|EventClass|0|1|A classe de evento é usada para categorizar eventos.|  
|EventSubclass|1|1|A Subclasse de Evento oferece informações adicionais sobre cada classe de evento:<br /><br /> 1: **DISCOVER_CONNECTIONS**<br /><br /> 2: **DISCOVER_SESSIONS**<br /><br /> 3: **DISCOVER_TRANSACTIONS**<br /><br /> 6: **DISCOVER_DB_CONNECTIONS**<br /><br /> 7: **DISCOVER_JOBS**<br /><br /> 8: **DISCOVER_LOCKS**<br /><br /> 12: **DISCOVER_PERFORMANCE_COUNTERS**<br /><br /> 13: **DISCOVER_MEMORYUSAGE**<br /><br /> 14: **DISCOVER_JOB_PROGRESS**<br /><br /> 15: **DISCOVER_MEMORYGRANT**|  
|CurrentTime|2|5|Contém a hora atual do evento de descoberta de estado do servidor, quando disponível. Para filtragem, os formatos esperados são 'AAAA-MM-DD' e 'AAAA-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Contém a hora em que o evento iniciou, quando disponível. Para filtragem, os formatos esperados são 'AAAA-MM-DD' e 'AAAA-MM-DD HH:MM:SS'.|  
|ConnectionID|25|1|Contém a ID de conexão exclusiva associada ao evento de identificação do estado do servidor.|  
|NTUserName|32|8|Contém a conta de usuário do Windows associada ao evento de identificação do estado do servidor.|  
|NTDomainName|33|8|Contém a conta de domínio do Windows associada ao evento de identificação do estado do servidor.|  
|ClientProcessID|36|1|Contém a ID de processo do aplicativo cliente que criou a conexão ao servidor.|  
|ApplicationName|37|8|Contém o nome do aplicativo cliente que criou a conexão com o servidor. Essa coluna é populada com os valores passados pelo aplicativo e não com o nome exibido do programa.|  
|SessionID|39|8|Contém a ID de sessão associada ao evento de identificação do estado do servidor.|  
|NTCanonicalUserName|40|8|Contém o nome de usuário do Windows associado ao evento de identificação do estado do servidor. O nome de usuário está na forma canônica. Por exemplo, engineering.microsoft.com/software/user.|  
|SPID|41|1|Contém a identificação do processo do servidor (SPID) que identifica de modo exclusivo a sessão de usuário associada ao evento de identificação do estado do servidor. A SPID corresponde diretamente à GUID de sessão usada pelo XMLA.|  
|TextData|42|9|Contém os dados de texto associados ao evento.|  
|ServerName|43|8|Contém o nome da instância do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] na qual o evento de identificação do estado do servidor ocorreu.|  
|RequestProperties|45|9|Contém as propriedades da solicitação XMLA atual.|  
  
## <a name="server-state-discover-data-classdata-columns"></a>Classe Server State Discover Data - Colunas de dados  
  
|||||  
|-|-|-|-|  
|**Nome da coluna**|**Id da coluna**|**Tipo de coluna**|**Descrição da coluna**|  
|EventClass|0|1|A classe de evento é usada para categorizar eventos.|  
|EventSubclass|1|1|A Subclasse de Evento oferece informações adicionais sobre cada classe de evento:<br /><br /> 1: **DISCOVER_CONNECTIONS**<br /><br /> 2: **DISCOVER_SESSIONS**<br /><br /> 3: **DISCOVER_TRANSACTIONS**<br /><br /> 6: **DISCOVER_DB_CONNECTIONS**<br /><br /> 7: **DISCOVER_JOBS**<br /><br /> 8: **DISCOVER_LOCKS**<br /><br /> 12: **DISCOVER_PERFORMANCE_COUNTERS**<br /><br /> 13: **DISCOVER_MEMORYUSAGE**<br /><br /> 14: **DISCOVER_JOB_PROGRESS**<br /><br /> 15: **DISCOVER_MEMORYGRANT**|  
|CurrentTime|2|5|Contém a hora atual do evento de descoberta de estado do servidor, quando disponível. Para filtragem, os formatos esperados são 'AAAA-MM-DD' e 'AAAA-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Contém a hora em que o evento iniciou, quando disponível. Para filtragem, os formatos esperados são 'AAAA-MM-DD' e 'AAAA-MM-DD HH:MM:SS'.|  
|ConnectionID|25|1|Contém a ID de conexão exclusiva associada ao evento de identificação do estado do servidor.|  
|SessionID|39|8|Contém a ID de sessão associada ao evento de identificação do estado do servidor.|  
|SPID|41|1|Contém a identificação do processo do servidor (SPID) que identifica de modo exclusivo a sessão de usuário associada ao evento de identificação do estado do servidor. A SPID corresponde diretamente à GUID de sessão usada pelo XMLA.|  
|TextData|42|9|Contém os dados de texto associados à resposta do servidor à solicitação de identificação.|  
|ServerName|43|8|Contém o nome da instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] na qual o evento de identificação do estado do servidor ocorreu.|  
  
## <a name="server-state-discover-end-classdata-columns"></a>Classe Server State Discover End - Colunas de dados  
  
|||||  
|-|-|-|-|  
|**Nome da coluna**|**Id da coluna**|**Tipo de coluna**|**Descrição da coluna**|  
|EventClass|0|1|A classe de evento é usada para categorizar eventos.|  
|EventSubclass|1|1|A Subclasse de Evento oferece informações adicionais sobre cada classe de evento:<br /><br /> 1: **DISCOVER_CONNECTIONS**<br /><br /> 2: **DISCOVER_SESSIONS**<br /><br /> 3: **DISCOVER_TRANSACTIONS**<br /><br /> 6: **DISCOVER_DB_CONNECTIONS**<br /><br /> 7: **DISCOVER_JOBS**<br /><br /> 8: **DISCOVER_LOCKS**<br /><br /> 12: **DISCOVER_PERFORMANCE_COUNTERS**<br /><br /> 13: **DISCOVER_MEMORYUSAGE**<br /><br /> 14: **DISCOVER_JOB_PROGRESS**<br /><br /> 15: **DISCOVER_MEMORYGRANT**|  
|CurrentTime|2|5|Contém a hora atual do evento de descoberta de estado do servidor, quando disponível. Para filtragem, os formatos esperados são 'AAAA-MM-DD' e 'AAAA-MM-DD HH:MM:SS'.|  
|StartTime|3|5|Contém a hora em que o evento iniciou, quando disponível. Para filtragem, os formatos esperados são 'AAAA-MM-DD' e 'AAAA-MM-DD HH:MM:SS'.|  
|EndTime|4|5|Contém a hora em que o evento terminou. Esta coluna não é populada para classes de eventos iniciais, como SQL:BatchStarting ou SP:Starting. Para filtragem, os formatos esperados são 'AAAA-MM-DD' e 'AAAA-MM-DD HH:MM:SS'.|  
|Duration|5|2|Contém a quantidade de tempo (em milissegundos) utilizado pelo evento.|  
|CPUTime|6|2|Contém a quantidade de tempo da CPU (em milissegundos) usada pelo evento de descoberta de estado do servidor.|  
|ConnectionID|25|1|Contém a ID de conexão exclusiva associada ao evento de identificação do estado do servidor.|  
|NTUserName|32|8|Contém a conta de usuário do Windows associada ao evento de identificação do estado do servidor.|  
|NTDomainName|33|8|Contém a conta de domínio do Windows associada ao evento de identificação do estado do servidor.|  
|ClientProcessID|36|1|Contém a ID do processo do aplicativo cliente que iniciou a solicitação de XMLA.|  
|ApplicationName|37|8|Contém o nome do aplicativo cliente que criou a conexão com o servidor. Essa coluna é populada com os valores passados pelo aplicativo e não com o nome exibido do programa.|  
|SessionID|39|8|Contém a conta de domínio do Windows associada ao evento de identificação do estado do servidor.|  
|NTCanonicalUserName|40|8|Contém o nome de usuário do Windows associado ao evento de identificação do estado do servidor. O nome de usuário está na forma canônica. Por exemplo, engineering.microsoft.com/software/user.|  
|SPID|41|1|Contém a identificação do processo do servidor (SPID) que identifica de modo exclusivo a sessão de usuário associada ao evento de identificação do estado do servidor. A SPID corresponde diretamente à GUID de sessão usada pelo XMLA.|  
|TextData|42|9|Contém os dados de texto associados à resposta do servidor à solicitação de identificação.|  
|ServerName|43|8|Contém o nome da instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] na qual o evento de identificação do estado do servidor ocorreu.|  
  
## <a name="see-also"></a>Consulte também  
 [Descobrir a categoria de evento de estado do servidor](../../analysis-services/trace-events/discover-server-state-event-category.md)  
  
  
