---
title: Cancelar Trabalhos do Servidor de Relatório (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.component: tools
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql13.swb.reportserver.cancelreportserverjobs.f1
ms.assetid: 1c5b4975-49e9-4d0b-b298-2638e81edbfd
caps.latest.revision: 14
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 2ad15367b678ae9a304feb3d5a384d0611d6a9c9
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "33029403"
---
# <a name="cancel-report-server-jobs-management-studio"></a>Cancelar Trabalhos do Servidor de Relatório (Management Studio)
  Use a caixa de diálogo **Cancelar Trabalhos do Servidor de Relatório** para exibir ou cancelar relatórios em andamento. Essa caixa de diálogo mostra todos os trabalhos em execução atualmente no servidor de relatórios. Embora você não possa pausar ou reiniciar trabalhos atualmente em processo, pode cancelar todos os trabalhos ou trabalhos individuais se estiverem demorando muito para serem concluídos.  
  
 Você pode cancelar trabalhos de usuário e trabalhos do sistema.  
  
-   Um trabalho de usuário é qualquer trabalho iniciado por um usuário individual. Isso inclui a execução de um relatório sob demanda, a criação manual de um instantâneo de histórico de relatório ou de um instantâneo de execução de relatório. Uma assinatura padrão em andamento é também um trabalho de usuário.  
  
-   Um trabalho do sistema é um trabalho iniciado pelo servidor de relatórios. Trabalhos do sistema incluem processamento de relatório agendado.  
  
 Para abrir essa página, inicie o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se a um servidor de relatório, clique com o botão direito do mouse em **Trabalhos**e clique em **Cancelar Todos os Trabalhos**. Você pode abrir também **Trabalhos**, clicar com o botão direito do mouse em um trabalho em execução no servidor de relatório e selecionar **Cancelar Trabalho(s)**.  
  
 Antes de cancelar um trabalho, você pode exibir suas propriedades para determinar quando o trabalho foi iniciado. Para obter mais informações, consulte [Propriedades do Trabalho &#40;Management Studio&#41;](../../reporting-services/tools/job-properties-management-studio.md).  
  
> [!NOTE]  
>  Esse recurso não tem suporte no [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] com Advanced Services. A página não será exibida enquanto você estiver executando o [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].  
  
## <a name="options"></a>Opções  
 **Nome**  
 Exibe o nome do relatório. As assinaturas são identificadas por suas descrições.  
  
 **Tipo**  
 Os valores válidos são **User** e **System**.  
  
 **Start Time**  
 Exibe quando o trabalho foi iniciado.  
  
 **Nome do Usuário**  
 Para trabalhos iniciados por um usuário, essa coluna exibe o nome do usuário.  
  
 **Status**  
 Mostra o status atual do trabalho. Os valores válidos são **Novo** e **Executando**. O status é sempre **Novo** quando o trabalho começa. Depois de 60 segundos, o status é alterado para **Executando**. É necessário atualizar a página para que a alteração tenha efeito.  
  
 **OK**  
 Cancele um único trabalho ou vários trabalhos. Os trabalhos são imediatamente cancelados e não podem ser retomados. Se você cancelar um trabalho por engano, deverá solicitar o relatório ou a assinatura novamente para iniciar um novo trabalho.  
  
## <a name="see-also"></a>Consulte Também  
 [Servidor de Relatório na ajuda F1 do Management Studio](../../reporting-services/tools/report-server-in-management-studio-f1-help.md)   
 [Conectar-se a um servidor de relatório no Management Studio](../../reporting-services/tools/connect-to-a-report-server-in-management-studio.md)   
 [Gerenciar um processo em execução](../../reporting-services/subscriptions/manage-a-running-process.md)  
  
  
