---
title: Consultando o Active Directory com a tarefa Script | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
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
helpviewer_keywords:
- Script task [Integration Services], Active Directory access
- SSIS Script task, Active Directory access
- Script task [Integration Services], examples
- Active Directory [Integration Services]
ms.assetid: a88fefbb-9ea2-4a86-b836-e71315bac68e
caps.latest.revision: 51
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: ee5a82829785e78554b105e1f3bf3bd24f05b778
ms.contentlocale: pt-br
ms.lasthandoff: 09/26/2017

---
# <a name="querying-the-active-directory-with-the-script-task"></a>Consultando o Active Directory com a tarefa Script
  Aplicativos de processamento de dados corporativos, como pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], em geral, precisam processar dados de forma diferente com base na classificação, no nome do cargo ou em outras características dos funcionários armazenadas no Active Directory. O Active Directory é um [!INCLUDE[msCoName](../../includes/msconame-md.md)] serviço de diretório do Windows que fornece um repositório centralizado de metadados, não apenas sobre usuários, mas também sobre outros ativos organizacionais, como computadores e impressoras. O **System. DirectoryServices** namespace no Microsoft .NET Framework fornece classes para trabalhar com o Active Directory, para ajudá-lo direto de processamento de dados de fluxo de trabalho com base nas informações que ele armazena.  
  
> [!NOTE]  
>  Se desejar criar uma tarefa mais fácil de ser reutilizada em vários pacotes, procure utilizar o código desse exemplo de tarefa Script como o ponto inicial de uma tarefa personalizada. Para obter mais informações, consulte [Desenvolvendo uma tarefa personalizada](../../integration-services/extending-packages-custom-objects/task/developing-a-custom-task.md).  
  
## <a name="description"></a>Description  
 O exemplo a seguir recupera nome, cargo e número de telefone de um funcionário no Active Directory, com base no valor da variável `email`, que contém o endereço de email desse funcionário. As restrições de precedência no pacote podem usar as informações recuperadas para determinar, por exemplo, se ele deve enviar uma mensagem de email de baixa prioridade ou uma página de alta prioridade, baseando-se no nome do cargo do funcionário.  
  
#### <a name="to-configure-this-script-task-example"></a>Para configurar esse exemplo de tarefa Script  
  
1.  Crie as três variáveis de cadeia de caracteres `email`, `name` e `title`. Digite um endereço de email corporativo válido como o valor da variável `email`.  
  
2.  No **Script** página do **Editor da tarefa Script**, adicionar o `email` variável para o **ReadOnlyVariables** propriedade.  
  
3.  Adicionar o `name` e `title` variáveis para o **ReadWriteVariables** propriedade.  
  
4.  No projeto de script, adicione uma referência para o **System. DirectoryServices** namespace.  
  
5.  . No seu código, use um **Imports** instrução para importar o **DirectoryServices** namespace.  
  
> [!NOTE]  
>  Para executar esse script com sucesso, sua empresa deve usar o Active Directory em sua rede e armazenar as informações do funcionário que este exemplo usa.  
  
### <a name="code"></a>Código  
  
```vb  
Public Sub Main()  
  
    Dim directory As DirectoryServices.DirectorySearcher  
    Dim result As DirectoryServices.SearchResult  
    Dim email As String  
  
    email = Dts.Variables("email").Value.ToString  
  
    Try  
        directory = New _  
            DirectoryServices.DirectorySearcher("(mail=" & email & ")")  
        result = directory.FindOne  
        Dts.Variables("name").Value = _  
            result.Properties("displayname").ToString  
        Dts.Variables("title").Value = _  
            result.Properties("title").ToString  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, _  
            "Script Task Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
public void Main()  
{  
    //  
    DirectorySearcher directory;  
    SearchResult result;  
    string email;  
  
    email = (string)Dts.Variables["email"].Value;  
  
    try  
    {  
        directory = new DirectorySearcher("(mail=" + email + ")");  
        result = directory.FindOne();  
        Dts.Variables["name"].Value = result.Properties["displayname"].ToString();  
        Dts.Variables["title"].Value = result.Properties["title"].ToString();  
        Dts.TaskResult = (int)ScriptResults.Success;  
    }  
    catch (Exception ex)  
    {  
        Dts.Events.FireError(0, "Script Task Example", ex.Message + "\n" + ex.StackTrace, String.Empty, 0);  
        Dts.TaskResult = (int)ScriptResults.Failure;  
    }  
  
}  
```  
  
## <a name="external-resources"></a>Recursos externos  
  
-   Artigo técnico, [processamento de informações do Active Directory no SSIS](http://go.microsoft.com/fwlink/?LinkId=199588), em social.technet.microsoft.com  
  
  