---
title: 'Lição 5: Formatando um relatório (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 05/23/2016
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.component: reporting-services
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- SQL Server 2016
ms.assetid: ae46efa9-6e04-48ec-afb4-5a2314dcb05a
caps.latest.revision: 20
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 22524a7fb35104934661f0dead998319cf9a99f2
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
ms.locfileid: "33016373"
---
# <a name="lesson-5-formatting-a-report-reporting-services"></a>Lesson 5: Formatting a Report (Reporting Services)
Agora que já adicionou uma região de dados e alguns campos ao relatório de ordens de venda, você pode formatar os campos de data e moeda, além dos cabeçalhos da coluna.  
  
## <a name="bkmk_format_date"></a>Formatar a data  
Por padrão, o campo Data exibe informações de data e hora. É possível formatá-lo para exibir apenas a data.  
  
#### <a name="to-format-a-date-field"></a>Para formatar um campo de data  
  
1.  Clique na guia **Design** .  
  
2.  Clique com o botão direito do mouse na célula com a expressão de campo `[Date]` e clique em **Propriedades da Caixa de Texto**.  
  
3.  Clique em **Número**e, no campo **Categoria** , clique em **Data**.  
  
4.  Na caixa **Tipo** , selecione **31 de janeiro de 2000**.  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  Visualize o relatório para ver a alteração no campo `[Date]` e, em seguida, altere de volta para a exibição de design.  
  
## <a name="bkmk_format_currency"></a>Formatar a moeda  
O campo **LineTotal** exibe um número geral. Formate-o para exibir o número como moeda.  
  
#### <a name="to-format-a-currency-field"></a>Para formatar um campo de conversor de moedas  
  
1.  Clique com o botão direito do mouse na célula com a expressão de campo `[LineTotal]` e clique em **Propriedades da Caixa de Texto**.  
  
2.  Clique em **Número**e, no campo **Categoria** , clique em **Moeda**.  
  
3.  Caso a configuração regional seja inglês (Estados Unidos), os padrões devem ser:  
  
    -   **Casas decimais: 2**  
  
    -   **Números negativos: (R$ 1.2345,00)**  
  
    -   **Símbolo: R$ português (Brasil)**  
  
4.  Selecione **Usar separador de milhar (.)**.  
  
    Caso o texto de exemplo seja **$12.345,00**, as configurações estão corretas.  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  Visualize o relatório para ver a alteração no campo `[LineTotal]` e, em seguida, altere de volta para a exibição de design.  
  
## <a name="bkmk_change_textstyle"></a>Alterar estilo do texto e larguras da coluna  
Também é possível alterar a formatação da linha do cabeçalho para diferenciá-la das linhas de dados no relatório. Por fim, você ajustará as larguras das colunas.  
  
#### <a name="to-format-header-rows-and-table-columns"></a>Para formatar as linhas do cabeçalho e as colunas da tabela  
  
1.  Clique na tabela de forma que os identificadores de coluna e linha sejam exibidos acima e ao lado da tabela. As barras em cinza ao longo da parte superior e ao lado da tabela são os identificadores de coluna e de linha.  
       
  
2.  Aponte para a linha entre os identificadores de coluna para que o cursor seja alterado para uma seta dupla. Arraste as colunas de acordo com o tamanho desejado.
 ![rs_BasicTableDetailsDesign](../reporting-services/media/rs-basictabledetailsdesign.png)   
  
3.  Selecione a linha que contém rótulos de cabeçalho de coluna e, no menu **Formatar** , aponte para **Fonte** e clique em **Negrito**.  
  
4.  Para visualizar o relatório, clique na guia **Visualizar** . O resultado deve ser algo como:  
  
    ![Visualização de tabela com cabeçalhos de coluna em negrito](../reporting-services/media/rs-basictabledetailsformattedpreview.png "Visualização de tabela com cabeçalhos de coluna em negrito")  
  
5.  No menu **Arquivo** , clique em **Salvar Tudo** para salvar o relatório.  
  
## <a name="next-steps"></a>Next Steps  
Você formatou cabeçalhos de coluna e valores de data e moeda com êxito. Agora você adicionará agrupamento e totais ao relatório. Consulte a [Lição 6: Adicionando agrupamentos e totais &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).  
  
## <a name="see-also"></a>Consulte Também  
[Formatando números e datas &#40;Construtor de Relatórios e SSRS&#41;](../reporting-services/report-design/formatting-numbers-and-dates-report-builder-and-ssrs.md)  
[Comportamentos de renderização &#40;Construtor de Relatórios e SSRS&#41;](../reporting-services/report-design/rendering-behaviors-report-builder-and-ssrs.md)  
  
  
  

