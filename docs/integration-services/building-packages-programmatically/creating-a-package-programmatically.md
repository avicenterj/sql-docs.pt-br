---
title: Criando um pacote programaticamente | Microsoft Docs
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SSIS packages, creating
- Integration Services packages, creating
- packages [Integration Services], creating
- SQL Server Integration Services packages, creating
ms.assetid: e44bcc70-32d3-43e8-a84b-29aef819d5d3
caps.latest.revision: 51
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 4a8ade977c971766c8f716ae5f33cac606c8e22d
ms.openlocfilehash: 58a8201d68cb6d942bd98ca3c53b6cf98336284e
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="creating-a-package-programmatically"></a>Criando um pacote programaticamente
  O objeto <xref:Microsoft.SqlServer.Dts.Runtime.Package> é o contêiner de alto nível para todos os outros objetos em uma solução de projeto do [!INCLUDE[ssIS](../../includes/ssis-md.md)]. Como contêiner de alto nível, o pacote é o primeiro objeto criado, e os objetos subsequentes são adicionados a ele e executados dentro do contexto do pacote. O próprio pacote não move nem transforma dados. O pacote confia nas tarefas que contém para executar o trabalho. As tarefas executam a maioria do trabalho executado por um pacote e definem a funcionalidade de um pacote. Um pacote é criado e executado com apenas três linhas de código, mas várias tarefas e objetos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> são adicionados para acrescentar funcionalidades ao seu pacote. Esta seção discute como criar um pacote programaticamente. Ela não fornece informações sobre como criar as tarefas ou o <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>. Essas informações são discutidas em seções posteriores.  
  
## <a name="example"></a>Exemplo  
 Para gravar um código usando o ambiente de desenvolvimento integrado (IDE) do Visual Studio, uma referência ao Microsoft.SqlServer.ManagedDTS.DLL é necessária para criar uma instrução `using` (`Imports` no Visual Basic .NET) para o Microsoft.SqlServer.Dts.Runtime. O exemplo de código seguinte demonstra como criar um pacote vazio.  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package package;  
      package = new Package();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim package As Package  
    package = New Package  
  
  End Sub  
  
End Module  
```  
  
 Para compilar e executar o exemplo, pressione F5 no Visual Studio. Para compilar o código usando o compilador c#, **csc.exe**, no prompt de comando para compilar, use o seguinte comando e arquivo referências, substituindo o  *\<filename >* com o nome do arquivo. cs ou. vb e dando a ele um  *\<outputfilename >* de sua escolha.  
  
 **CSC /target: Library /out: \<outputfilename >. dll \<filename >. cs /r:Microsoft.SqlServer.Managed DTS.dll "/r:System.dll**  
  
 Para compilar o código usando o compilador do Visual Basic .NET, **vbc.exe**, no prompt de comando para compilar, use o seguinte comando e referências de arquivo.  
  
 **/Target Vbc /out: \<outputfilename >. dll \<filename >. vb /r:Microsoft.SqlServer.Managed DTS.dll "/r:System.dll**  
  
 Você também pode criar um pacote carregando um pacote existente que foi salvo em disco, no sistema de arquivos, ou no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. A diferença é que o <xref:Microsoft.SqlServer.Dts.Runtime.Application> objeto é criado pela primeira vez e, em seguida, o objeto de pacote é preenchido por um dos métodos sobrecarregados do aplicativo: **LoadPackage** para arquivos simples, **LoadFromSQLServer** para pacotes salvos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ou <xref:Microsoft.SqlServer.Dts.Runtime.Application.LoadFromDtsServer%2A> para pacotes salvos no sistema de arquivos. O exemplo seguinte carrega um pacote existente do disco e exibe várias propriedades no pacote.  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class ApplicationTests  
  {  
    static void Main(string[] args)  
    {  
      // The variable pkg points to the location of the  
      // ExecuteProcess package sample that was installed with  
      // the SSIS samples.  
      string pkg = @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +  
        @"\Package Samples\ExecuteProcess Sample\ExecuteProcess\UsingExecuteProcess.dtsx";  
  
      Application app = new Application();  
      Package p = app.LoadPackage(pkg, null);  
  
      // Now that the package is loaded, we can query on  
      // its properties.  
      int n = p.Configurations.Count;  
      DtsProperty p2 = p.Properties["VersionGUID"];  
      DTSProtectionLevel pl = p.ProtectionLevel;  
  
      Console.WriteLine("Number of configurations = " + n.ToString());  
      Console.WriteLine("VersionGUID = " + (string)p2.GetValue(p));  
      Console.WriteLine("ProtectionLevel = " + pl.ToString());  
      Console.Read();  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module ApplicationTests  
  
  Sub Main()  
  
    ' The variable pkg points to the location of the  
    ' ExecuteProcess package sample that was installed with  
    ' the SSIS samples.  
    Dim pkg As String = _  
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _  
      "\Package Samples\ExecuteProcess Sample\ExecuteProcess\UsingExecuteProcess.dtsx"  
  
    Dim app As Application = New Application()  
    Dim p As Package = app.LoadPackage(pkg, Nothing)  
  
    ' Now that the package is loaded, we can query on  
    ' its properties.  
    Dim n As Integer = p.Configurations.Count  
    Dim p2 As DtsProperty = p.Properties("VersionGUID")  
    Dim pl As DTSProtectionLevel = p.ProtectionLevel  
  
    Console.WriteLine("Number of configurations = " & n.ToString())  
    Console.WriteLine("VersionGUID = " & CType(p2.GetValue(p), String))  
    Console.WriteLine("ProtectionLevel = " & pl.ToString())  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
 **Saída de exemplo:**  
  
 `Number of configurations = 2`  
  
 `VersionGUID = {09016682-89B8-4406-AAC9-AF1E527FF50F}`  
  
 `ProtectionLevel = DontSaveSensitive`  
  
## <a name="external-resources"></a>Recursos externos  
  
-   Entrada de blog, [API Sample - OleDB origem e destino de OleDB](http://go.microsoft.com/fwlink/?LinkId=220824), em blogs.msdn.com.  
  
-   Entrada de blog, [EzAPI – atualizado para o SQL Server 2012](http://go.microsoft.com/fwlink/?LinkId=243223), em blogs.msdn.com.  
  
## <a name="see-also"></a>Consulte também  
 [Adicionando tarefas programaticamente](../../integration-services/building-packages-programmatically/adding-tasks-programmatically.md)  
  
  