---
title: "Criando e Atualizando estatísticas | Microsoft Docs"
ms.custom: 
ms.date: 08/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: smo
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: statistical information [SMO]
ms.assetid: 47a0a172-a969-4deb-bca9-dd04401a0fe1
caps.latest.revision: "40"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: e16cc6c13e46afa20af43e27d4df581f5d1df484
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="creating-and-updating-statistics"></a>Criando e atualizando estatísticas
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]No SMO, informações estatísticas sobre o processamento de consultas no banco de dados podem ser coletadas usando o <xref:Microsoft.SqlServer.Management.Smo.Statistic> objeto.  
  
 É possível criar estatísticas para qualquer coluna através dos objetos <xref:Microsoft.SqlServer.Management.Smo.Statistic> e <xref:Microsoft.SqlServer.Management.Smo.StatisticColumn>. O método <xref:Microsoft.SqlServer.Management.Smo.Statistic.Update%2A> pode ser executado para atualizar as estatísticas no objeto <xref:Microsoft.SqlServer.Management.Smo.Statistic>. Os resultados podem ser exibidos no Otimizador de Consulta.  
  
## <a name="example"></a>Exemplo  
 Para usar qualquer exemplo de código fornecido, será necessário escolher o ambiente de programação, o modelo de programação e a linguagem de programação para criar o aplicativo. Para obter mais informações, consulte [criar um Visual C &#35; Projeto SMO no Visual Studio .NET](../../../relational-databases/server-management-objects-smo/how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).  
  
## <a name="creating-and-update-statistics-in-visual-basic"></a>Criando e atualizando estatísticas no Visual Basic  
 Este exemplo de código cria uma nova tabela em um banco de dados existente para o qual os objetos <xref:Microsoft.SqlServer.Management.Smo.Statistic> e <xref:Microsoft.SqlServer.Management.Smo.StatisticColumn> são criados.  
  
```VBNET
'Connect to the local, default instance of SQL Server.
Dim srv As Server
srv = New Server
'Reference the AdventureWorks2012 database.
Dim db As Database
db = srv.Databases("AdventureWorks2012")
'Reference the CreditCard table.
Dim tb As Table
tb = db.Tables("CreditCard", "Sales")
'Define a Statistic object by supplying the parent table and name arguments in the constructor.
Dim stat As Statistic
stat = New Statistic(tb, "Test_Statistics")
'Define a StatisticColumn object variable for the CardType column and add to the Statistic object variable.
Dim statcol As StatisticColumn
statcol = New StatisticColumn(stat, "CardType")
stat.StatisticColumns.Add(statcol)
'Create the statistic counter on the instance of SQL Server.
stat.Create()
``` 
  
## <a name="creating-and-update-statistics-in-visual-c"></a>Criando e atualizando estatísticas no Visual C#  
 Este exemplo de código cria uma nova tabela em um banco de dados existente para o qual os objetos <xref:Microsoft.SqlServer.Management.Smo.Statistic> e <xref:Microsoft.SqlServer.Management.Smo.StatisticColumn> são criados.  
  
```csharp  
{  
            //Connect to the local, default instance of SQL Server.  
            Server srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Reference the CreditCard table.   
  
           Table tb = db.Tables["CreditCard", "Sales"];  
            //Define a Statistic object by supplying the parent table and name   
            //arguments in the constructor.   
            Statistic stat = default(Statistic);  
            stat = new Statistic(tb, "Test_Statistics");  
            //Define a StatisticColumn object variable for the CardType column   
            //and add to the Statistic object variable.   
            StatisticColumn statcol = default(StatisticColumn);  
            statcol = new StatisticColumn(stat, "CardType");  
            stat.StatisticColumns.Add(statcol);  
            //Create the statistic counter on the instance of SQL Server.   
            stat.Create();  
        }  
```  
  
## <a name="creating-and-update-statistics-in-powershell"></a>Criando e atualizando estatísticas no PowerShell  
 Este exemplo de código cria uma nova tabela em um banco de dados existente para o qual os objetos <xref:Microsoft.SqlServer.Management.Smo.Statistic> e <xref:Microsoft.SqlServer.Management.Smo.StatisticColumn> são criados.  
  
```powershell  
# Example of implementing a full text search on the default instance.  
# Set the path context to the local, default instance of SQL Server and database tables  
  
CD \sql\localhost\default\databases  
$db = get-item AdventureWorks2012  
  
CD AdventureWorks2012\tables  
  
#Get a reference to the table  
$tb = get-item Production.ProductCategory  
  
# Define a FullTextCatalog object variable by specifying the parent database and name arguments in the constructor.  
  
$ftc = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextCatalog -argumentlist $db, "Test_Catalog2"  
$ftc.IsDefault = $true  
  
# Create the Full Text Search catalog on the instance of SQL Server.  
$ftc.Create()  
  
# Define a FullTextIndex object variable by supplying the parent table argument in the constructor.  
$fti = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextIndex -argumentlist $tb  
  
#  Define a FullTextIndexColumn object variable by supplying the parent index   
#  and column name arguments in the constructor.  
  
$ftic = New-Object -TypeName Microsoft.SqlServer.Management.SMO.FullTextIndexColumn -argumentlist $fti, "Name"  
  
# Add the indexed column to the index.  
$fti.IndexedColumns.Add($ftic)  
  
# Set change tracking  
$fti.ChangeTracking = [Microsoft.SqlServer.Management.SMO.ChangeTracking]::Automatic  
  
# Specify the unique index on the table that is required by the Full Text Search index.  
$fti.UniqueIndexName = "AK_ProductCategory_Name"  
  
# Specify the catalog associated with the index.  
$fti.CatalogName = "Test_Catalog2"  
  
# Create the Full Text Search Index  
$fti.Create()  
```  
  
  