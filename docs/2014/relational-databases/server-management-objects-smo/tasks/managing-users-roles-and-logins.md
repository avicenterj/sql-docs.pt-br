---
title: Gerenciar usuários, funções e logons | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- logins [SMO]
- roles [SMO]
- users [SMO]
ms.assetid: 74e411fa-74ed-49ec-ab58-68c250f2280e
caps.latest.revision: 42
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: c14e955bd2f2e0442cde266bb9bf56f4b9caed3c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37199166"
---
# <a name="managing-users-roles-and-logins"></a>Gerenciando usuários, funções e logons
  No SMO, os logons são representados pelo objeto <xref:Microsoft.SqlServer.Management.Smo.Login>. Quando o logon existir no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], ele poderá ser adicionado a uma função de servidor. A função de servidor é representada pelo <xref:Microsoft.SqlServer.Management.Smo.ServerRole> objeto. A função de banco de dados é representada pelo objeto <xref:Microsoft.SqlServer.Management.Smo.DatabaseRole> e a função de aplicativo é representada pelo objeto <xref:Microsoft.SqlServer.Management.Smo.ApplicationRole>.  
  
 Privilégios associados ao nível de servidor são listados como propriedades do <xref:Microsoft.SqlServer.Management.Smo.ServerPermission> objeto. Os privilégios em nível de servidor podem ser concedidos a, negados a ou revogados de contas de logon individuais.  
  
 Cada <xref:Microsoft.SqlServer.Management.Smo.Database> objeto tem um <xref:Microsoft.SqlServer.Management.Smo.UserCollection> objeto que especifica todos os usuários no banco de dados. Cada usuário é associado a um logon. Um logon pode ser associado a usuários em mais de um banco de dados. O <xref:Microsoft.SqlServer.Management.Smo.Login> do objeto <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> método pode ser usado para listar todos os usuários em cada banco de dados que está associado ao logon. Alternativamente, a propriedade <xref:Microsoft.SqlServer.Management.Smo.User> do objeto <xref:Microsoft.SqlServer.Management.Smo.Login> especifica o logon que é associado ao usuário.  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] bancos de dados também têm funções que especificam um conjunto de privilégios de nível de banco de dados que permitem que um usuário executar tarefas específicas. Diferente das funções de servidor, as funções de banco de dados não são fixas. Elas podem ser criadas, modificadas e removidas. Privilégios e usuários podem ser designados a uma função de banco de dados para administração em massa.  
  
## <a name="example"></a>Exemplo  
 Para o exemplo de código a seguir, selecione o ambiente de programação, o modelo de programação e a linguagem de programação para criar seu aplicativo. Para obter mais informações, consulte [criar um projeto do Visual Basic SMO no Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e [criar um Visual C&#35; projeto de SMO no Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).  
  
## <a name="enumerating-logins-and-associated-users-in-visual-basic"></a>Enumerando logons e usuários associados no Visual Basic  
 Cada usuário em um banco de dados é associado a um logon. O logon pode ser associado a usuários em mais de um banco de dados. O exemplo de código mostra como chamar o método <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Login> para listar todos os usuários de banco de dados associados ao logon. O exemplo cria um logon e usuário do [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] banco de dados para verificar se há informações de mapeamento para enumerar.  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBLogins1](SMO How to#SMO_VBLogins1)]  -->  
  
## <a name="enumerating-logins-and-associated-users-in-visual-c"></a>Enumerando logons e usuários associados no Visual C#  
 Cada usuário em um banco de dados é associado a um logon. O logon pode ser associado a usuários em mais de um banco de dados. O exemplo de código mostra como chamar o método <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Login> para listar todos os usuários de banco de dados associados ao logon. O exemplo cria um logon e usuário do [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] banco de dados para verificar se há informações de mapeamento para enumerar.  
  
```  
{   
Server srv = new Server();   
//Iterate through each database and display.   
  
foreach ( Database db in srv.Databases) {   
   Console.WriteLine("========");   
   Console.WriteLine("Login Mappings for the database: " + db.Name);   
   Console.WriteLine(" ");   
   //Run the EnumLoginMappings method and return details of database user-login mappings to a DataTable object variable.   
   DataTable d;  
   d = db.EnumLoginMappings();   
   //Display the mapping information.   
   foreach (DataRow r in d.Rows) {   
      foreach (DataColumn c in r.Table.Columns) {   
         Console.WriteLine(c.ColumnName + " = " + r[c]);   
      }   
      Console.WriteLine(" ");   
   }   
}   
}  
```  
  
## <a name="enumerating-logins-and-associated-users-in-powershell"></a>Enumerando logons e usuários associados no PowerShell  
 Cada usuário em um banco de dados é associado a um logon. O logon pode ser associado a usuários em mais de um banco de dados. O exemplo de código mostra como chamar o método <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> do objeto <xref:Microsoft.SqlServer.Management.Smo.Login> para listar todos os usuários de banco de dados associados ao logon. O exemplo cria um logon e usuário do [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] banco de dados para verificar se há informações de mapeamento para enumerar.  
  
```  
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\Default\Databases  
  
#Iterate through all databases  
 foreach ($db in Get-ChildItem)  
 {  
 "====="  
 "Login Mappings for the database: "+ $db.Name  
  
 #get the datatable containing the mapping from the smo database oject  
 $dt = $db.EnumLoginMappings()  
  
 #display the results  
 foreach($row in $dt.Rows)  
     {  
        foreach($col in $row.Table.Columns)  
      {  
        $col.ColumnName + "=" + $row[$col]  
       }  
  
     }  
 }  
```  
  
## <a name="managing-roles-and-users"></a>Gerenciando funções e usuários  
 Este exemplo demonstra como gerenciar funções e usuários. O primeiro exemplo usa C# e o segundo usa o Visual Basic. Estes exemplos precisam referenciar os seguintes assemblies:  
  
-   Microsoft.SqlServer.Smo.dll  
  
-   Microsoft.SqlServer.Management.Sdk.Sfc.dll  
  
-   Microsoft.SqlServer.ConnectionInfo.dll  
  
-   Microsoft.SqlServer.SqlEnum.dll  
  
```  
using Microsoft.SqlServer.Management.Smo;  
using System;  
  
public class A {  
   public static void Main() {  
      Server svr = new Server();  
      Database db = new Database(svr, "TESTDB");  
      db.Create();  
  
      // Creating Logins  
      Login login = new Login(svr, "Login1");  
      login.LoginType = LoginType.SqlLogin;  
      login.Create("password@1");  
  
      Login login2 = new Login(svr, "Login2");  
      login2.LoginType = LoginType.SqlLogin;  
      login2.Create("password@1");  
  
      // Creating Users in the database for the logins created  
      User user1 = new User(db, "User1");  
      user1.Login = "Login1";  
      user1.Create();  
  
      User user2 = new User(db, "User2");  
      user2.Login = "Login2";  
      user2.Create();  
  
      // Creating database permission Sets  
      DatabasePermissionSet dbPermSet = new DatabasePermissionSet(DatabasePermission.AlterAnySchema);  
      dbPermSet.Add(DatabasePermission.AlterAnyUser);  
  
      DatabasePermissionSet dbPermSet2 = new DatabasePermissionSet(DatabasePermission.CreateType);  
      dbPermSet2.Add(DatabasePermission.CreateSchema);  
      dbPermSet2.Add(DatabasePermission.CreateTable);  
  
      // Creating Database roles  
      DatabaseRole role1 = new DatabaseRole(db, "Role1");  
      role1.Create();  
  
      DatabaseRole role2 = new DatabaseRole(db, "Role2");  
      role2.Create();  
  
      // Granting Database Permission Sets to Roles  
      db.Grant(dbPermSet, role1.Name);  
      db.Grant(dbPermSet2, role2.Name);  
  
      // Adding members (Users / Roles) to Role  
      role1.AddMember("User1");  
  
      role2.AddMember("User2");  
  
      // Role1 becomes a member of Role2  
      role2.AddMember("Role1");  
  
      // Enumerating through explicit permissions granted to Role1  
      // enumerates all database permissions for the Grantee  
      DatabasePermissionInfo[] dbPermsRole1 = db.EnumDatabasePermissions("Role1");     
      foreach (DatabasePermissionInfo dbp in dbPermsRole1) {  
         Console.WriteLine(dbp.Grantee + " has " + dbp.PermissionType.ToString() + " permission.");  
      }  
      Console.WriteLine(" ");  
   }  
}  
```  
  
 Esta é a versão do Visual Basic:  
  
```  
Imports Microsoft.SqlServer.Management.Smo  
  
Public Class A  
   Public Shared Sub Main()  
      Dim svr As New Server()  
      Dim db As New Database(svr, "TESTDB")  
      db.Create()  
  
      ' Creating Logins  
      Dim login As New Login(svr, "Login1")  
      login.LoginType = LoginType.SqlLogin  
      login.Create("password@1")  
  
      Dim login2 As New Login(svr, "Login2")  
      login2.LoginType = LoginType.SqlLogin  
      login2.Create("password@1")  
  
      ' Creating Users in the database for the logins created  
      Dim user1 As New User(db, "User1")  
      user1.Login = "Login1"  
      user1.Create()  
  
      Dim user2 As New User(db, "User2")  
      user2.Login = "Login2"  
      user2.Create()  
  
      ' Creating database permission Sets  
      Dim dbPermSet As New DatabasePermissionSet(DatabasePermission.AlterAnySchema)  
      dbPermSet.Add(DatabasePermission.AlterAnyUser)  
  
      Dim dbPermSet2 As New DatabasePermissionSet(DatabasePermission.CreateType)  
      dbPermSet2.Add(DatabasePermission.CreateSchema)  
      dbPermSet2.Add(DatabasePermission.CreateTable)  
  
      ' Creating Database roles  
      Dim role1 As New DatabaseRole(db, "Role1")  
      role1.Create()  
  
      Dim role2 As New DatabaseRole(db, "Role2")  
      role2.Create()  
  
      ' Granting Database Permission Sets to Roles  
      db.Grant(dbPermSet, role1.Name)  
      db.Grant(dbPermSet2, role2.Name)  
  
      ' Adding members (Users / Roles) to Role  
      role1.AddMember("User1")  
  
      role2.AddMember("User2")  
  
      ' Role1 becomes a member of Role2  
      role2.AddMember("Role1")  
  
      ' Enumerating through explicit permissions granted to Role1  
      ' enumerates all database permissions for the Grantee  
      Dim dbPermsRole1 As DatabasePermissionInfo() = db.EnumDatabasePermissions("Role1")  
      For Each dbp As DatabasePermissionInfo In dbPermsRole1  
         Console.WriteLine(dbp.Grantee + " has " & dbp.PermissionType.ToString() & " permission.")  
      Next  
      Console.WriteLine(" ")  
   End Sub  
End Class  
```  
  
  
