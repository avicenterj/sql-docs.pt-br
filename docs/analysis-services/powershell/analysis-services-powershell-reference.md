---
title: Referência do PowerShell do Analysis Services | Microsoft Docs
ms.date: 06/25/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: powershell
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 13ea15a23bbf6de6c50b494f709f65cae2f7c48b
ms.sourcegitcommit: e77197ec6935e15e2260a7a44587e8054745d5c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2018
ms.locfileid: "37992898"
---
# <a name="analysis-services-powershell-reference"></a>Referência do Analysis Services PowerShell
[!INCLUDE[ssas-appliesto-sqlas-all-aas](../../includes/ssas-appliesto-sqlas-all-aas.md)]

  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Cmdlets do PowerShell estão incluídos na [módulo do SqlServer](https://www.powershellgallery.com/packages/SqlServer/21.0.17099). 
  
>[!NOTE] 
> Operações de banco de dados do Analysis Services do Azure usam o mesmo módulo SqlServer que o SQL Server Analysis Services. No entanto, nem todos os cmdlets têm suporte para o Azure Analysis Services. Para obter mais informações, consulte [gerenciar o Azure Analysis Services com PowerShell](https://docs.microsoft.com/azure/analysis-services/analysis-services-powershell).
  
##  <a name="bkmk_cmdlets"></a> Cmdlets do Analysis Services  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] fornece cmdlets correspondem aos métodos no **Microsoft. AnalysisServices** namespace. A tabela a seguir descreve cada cmdlet e fornece um link para o método AMO correspondente.  
  
 Se você quiser usar o PowerShell para executar uma tarefa que não esteja representada na lista a seguir (por exemplo, para criar ou sincronizar um banco de dados), escreva um script TMSL ou XMLA para essa ação e execute-o usando o cmdlet **Invoke-ASCmd** .  
  
|Cmdlet|Description|Métodos equivalentes do AMO|  
|------------|-----------------|----------------------------|  
|[Cmdlet Add-RoleMember](https://docs.microsoft.com/powershell/module/sqlserver/Add-RoleMember)|Adicionar um membro a uma função de banco de dados.|<xref:Microsoft.AnalysisServices.RoleMemberCollection.Add%2A>|  
|[Cmdlet Backup-ASDatabase](https://docs.microsoft.com/powershell/module/sqlserver/backup-asdatabase)|Fazer backup de um banco de dados do Analysis Services.|[Database.Backup](https://msdn.microsoft.com/library/microsoft.analysisservices.database.backup.aspx)|  
|[Cmdlet Invoke-ASCmd](https://docs.microsoft.com/powershell/module/sqlserver/invoke-ascmd)|Executar uma consulta ou script no formato XMLA ou TSML (JSON).|<xref:Microsoft.AnalysisServices.Core.Server.Execute%2A>|  
|[Invoke-ProcessASDatabase](https://docs.microsoft.com/powershell/module/sqlserver/invoke-processasdatabase)|Processar um banco de dados.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Cmdlet Invoke-ProcessCube](https://docs.microsoft.com/powershell/module/sqlserver/invoke-processcube)|Processar um cubo.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Cmdlet Invoke-ProcessDimension](https://docs.microsoft.com/powershell/module/sqlserver/invoke-processdimension)|Processar uma dimensão.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Cmdlet Invoke-ProcessPartition](https://docs.microsoft.com/powershell/module/sqlserver/invoke-processpartition)|Processar uma partição.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Cmdlet Invoke-ProcessTable](https://docs.microsoft.com/powershell/module/sqlserver/invoke-processtable)|Processe uma tabela em um modelo Tabular, o modelo de compatibilidade 1200 ou superior.|<xref:Microsoft.AnalysisServices.IProcessable.Process%2A>|  
|[Cmdlet Merge-Partition](https://docs.microsoft.com/powershell/module/sqlserver/merge-partition)|Mesclar uma partição.|<xref:Microsoft.AnalysisServices.Partition.Merge%2A>|  
|[Cmdlet New-RestoreFolder](https://docs.microsoft.com/powershell/module/sqlserver/new-restorefolder)|Criar uma pasta para conter um backup de banco de dados.|<xref:Microsoft.AnalysisServices.RestoreFolder>|  
|[Cmdlet New-RestoreLocation](https://docs.microsoft.com/powershell/module/sqlserver/new-restorelocation)|Especificar um ou mais servidores remotos nos quais o banco de dados deve ser restaurado.|<xref:Microsoft.AnalysisServices.RestoreLocation>|  
|[Cmdlet Remove-RoleMember](https://docs.microsoft.com/powershell/module/sqlserver/remove-rolemember)|Remover um membro de uma função de banco de dados.|<xref:Microsoft.AnalysisServices.RoleMemberCollection.Remove%2A>|  
|[Cmdlet Restore-ASDatabase](https://docs.microsoft.com/powershell/module/sqlserver/restore-asdatabase)|Restaurar um banco de dados em uma instância de servidor.|<xref:Microsoft.AnalysisServices.Core.Server.Restore%2A>|  
  

  
  
