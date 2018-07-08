---
title: Considerações sobre a instalação do SQL Server usando o SysPrep | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1792eeb-2874-4653-b20e-3063f4eb4e5d
caps.latest.revision: 21
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 09ada3ef426e365ec6ff734cb35da7bb2e394b14
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36118402"
---
# <a name="considerations-for-installing-sql-server-using-sysprep"></a>Considerações para instalação do SQL Server usando SysPrep
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] O SysPrep permite preparar uma instância autônoma do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um computador e concluir a configuração posteriormente. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] O SysPrep envolve um processo de duas etapas para obter uma instância autônoma configurada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. As etapas incluem o seguinte:  
  
-   [Preparar imagem](#BKMK_PrepareImage)  
  
     Essa etapa interrompe o processo de instalação após os binários do produto serem instalados, sem configurar o computador, a rede ou as informações específicas da conta para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo preparada.  
  
-   [Concluir Imagem](#BKMK_CompleteImage)  
  
     Essa etapa permite que você conclua a configuração de uma instância preparada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Durante essa etapa, você pode fornecer as informações específicas de computador, rede e conta.  
  
 Para obter mais informações sobre como instalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o SysPrep, consulte [instalar o SQL Server 2014 usando SysPrep](install-sql-server-using-sysprep.md).  
  
## <a name="common-uses-for-includessnoversionincludesssnoversion-mdmd-sysprep"></a>Usos comuns do SysPrep do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]  
 Você pode usar o recurso SysPrep do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] das seguintes maneiras:  
  
-   Na etapa Preparar Imagem, você pode preparar uma ou mais instâncias não configuradas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no mesmo computador. Você pode configurar essas instâncias preparadas usando a etapa Concluir Imagem no mesmo computador.  
  
-   Você pode capturar o arquivo de configuração de Instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da instância preparada e usá-lo para preparar outras instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não configuradas em vários computadores para configuração posterior.  
  
-   Em combinação com a ferramenta Windows System Preparation (também conhecida como also SysPrep), você pode criar uma imagem do sistema operacional incluindo as instâncias preparadas não configuradas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no computador de origem. Então, você poderá instalar a imagem do sistema operacional em vários computadores. Depois de concluir a configuração do sistema operacional, as instâncias preparadas podem ser configuradas usando a etapa Concluir Imagem da instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
     A ferramenta Windows SysPrep é usada para preparar imagens do sistema operacional Windows. Ela é usada para capturar uma imagem personalizada do sistema operacional para implantação em toda a organização. Para obter mais informações sobre o SysPrep e suas utilizações, consulte [O que é SysPrep?](http://go.microsoft.com/fwlink/?LinkId=143546).  
  
## <a name="installation-media-considerations"></a>Considerações sobre mídia de instalação  
 Se você estiver usando uma versão completa do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], considere o seguinte:  
  
-   Edições que não sejam Express do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:  
  
    -   A etapa Preparar Imagem usa a edição de Avaliação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para instalar os binários do produto. Quando a instância é concluída, a edição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] depende da ID do produto fornecida durante a etapa de concluir imagem.  
  
    -   Se você fornecer uma ID de produto da edição de Avaliação, o período de avaliação será definido para expirar 180 dias depois que a instância preparada for concluída.  
  
-   Edições Express do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:  
  
    -   Para preparar uma instância de edições Express do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , use a mídia de instalação do Express.  
  
    -   Você não pode especificar IDs de produto de uma instância preparada de edições Express do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
## <a name="supported-includessnoversionincludesssnoversion-mdmd-installations"></a>Instalações do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com suporte  
 SysPrep no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] dá suporte a todos os recursos, incluindo ferramentas, do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 É possível preparar várias instâncias para instalações lado a lado do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ou versões anteriores. Os recursos destas instâncias devem oferecer suporte a SysPrep.  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client é instalado automaticamente e concluído ao término da etapa de preparação de imagem.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e o Gravador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são automaticamente preparados quando você prepara uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Eles são concluídos quando você conclui a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizando a etapa Concluir Imagem.  
  
 Para obter informações sobre edições com suporte do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [recursos compatíveis com as edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).  
  
 É possível executar uma atualização de edição durante a configuração de uma instância preparada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Essa opção não tem suporte em edições Express do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 A partir do [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], o SysPrep do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dá suporte a instalações de cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da linha de comando.  
  
## <a name="includessnoversionincludesssnoversion-mdmd-sysprep-limitations"></a>[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Limitações do SysPrep  
 Não há suporte para a reparação de uma instância preparada. Se a instalação falhar durante a etapa Preparar Imagem ou Concluir Imagem, você deverá executar a desinstalação.  
  
##  <a name="BKMK_PrepareImage"></a> Preparar imagem  
 A etapa Preparar Imagem instala o produto e os recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , mas não configura a instalação.  
  
 Os recursos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a serem instalados e o local de instalação dos arquivos de instalação do produto [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem ser especificados durante essa etapa. Você pode preparar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] por meio da **preparação de imagem de uma instância autônoma para implantação do SysPrep** na página **Avançado** da **Central de Instalação** ou do prompt de comando.  
  
-   Você pode preparar várias instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no mesmo computador que podem ser concluídas mais tarde.  
  
-   Você pode adicionar ou remover recursos que têm suporte para instalações do SysPrep a partir das instâncias preparadas existentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 Depois que a instância estiver preparada, um atalho no menu **Iniciar** ficará disponível para concluir a configuração da instância preparada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
##  <a name="BKMK_CompleteImage"></a> Concluir Imagem  
 Você pode concluir as instâncias preparadas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando qualquer um dos seguintes métodos:  
  
-   Usar o atalho no menu Iniciar.  
  
-   Acessar a etapa **Conclusão de imagem de uma instância autônoma preparada** na página **Avançado** da **Central de Instalação**.  
  
## <a name="see-also"></a>Consulte também  
 [Planejando uma instalação do SQL Server](../../sql-server/install/planning-a-sql-server-installation.md)  
  
  