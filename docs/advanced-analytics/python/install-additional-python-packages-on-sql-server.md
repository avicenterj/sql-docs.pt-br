---
title: Instalar novos pacotes de Python no aprendizado de máquina do SQL Server | Microsoft Docs
description: Adicionar novos pacotes do Python para serviços do aprendizado de máquina 2017 SQL Server (no banco de dados) e o servidor de aprendizado de máquina (autônomo)
ms.prod: sql
ms.technology: machine-learning
ms.date: 05/10/2018
ms.topic: conceptual
author: HeidiSteen
ms.author: heidist
manager: cgronlun
ms.openlocfilehash: fa1ed2612fb88653a7259af0675b496fac4a6723
ms.sourcegitcommit: df382099ef1562b5f2d1cd506c1170d1db64de41
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2018
ms.locfileid: "34074230"
---
# <a name="install-new-python-packages-on-sql-server"></a>Instalar novos pacotes de Python no SQL Server
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

Este artigo descreve como instalar novos pacotes do Python em uma instância de serviços de aprendizado de máquina do SQL Server de 2017. Em geral, o processo de instalação de novos pacotes é semelhante ao que em um ambiente padrão do Python. No entanto, algumas etapas adicionais serão necessárias se o servidor não tiver uma conexão de internet.

Para obter ajuda sobre como descobrir quais pacotes estão instalados ou os pacotes que estão instalados, consulte [obter R ou Python informações do pacote](../r/determine-which-packages-are-installed-on-sql-server.md).

## <a name="prerequisites"></a>Prerequisites

+ Você deve ter instalado os serviços do aprendizado de máquina 2017 SQL Server (no banco de dados) com a opção de linguagem Python. Para obter instruções, consulte [instalar o SQL Server 2017 Machine Learning Services (no banco de dados)](../install/sql-machine-learning-services-windows-install.md).

+ Para cada instância de servidor, você deve instalar uma cópia separada do pacote. Pacotes não podem ser compartilhados entre instâncias.

+ Pacotes devem ser Python 3.5 compatível e executados no Windows. 

+ Avalie se o pacote é uma boa opção para uso no ambiente do SQL Server. Geralmente um servidor de banco de dados oferece suporte a vários serviços e aplicativos e recursos no sistema de arquivos podem ser limitado, bem como conexões para o servidor. Em muitos casos o acesso à Internet está bloqueado completamente.

    Outros problemas comuns incluem o uso da funcionalidade que está bloqueada no servidor ou pelo firewall ou pacotes com dependências que não podem ser instalados em um computador de rede. 

    Alguns pacotes Python populares (como bulbo) executam tarefas como o desenvolvimento da web que executam melhor em um ambiente autônomo. É recomendável que você use Python no banco de dados para tarefas, como o aprendizado de máquina, que exigem processamento intensivo de dados que se beneficiam da integração com o mecanismo de banco de dados, em vez de simplesmente consultar o banco de dados.

+ Acesso administrativo ao servidor é necessário para instalar pacotes.

## <a name="add-a-new-python-package"></a>Adicionar um novo pacote do Python

Neste exemplo, vamos supor que você deseja instalar um novo pacote diretamente no computador do SQL Server.

O pacote instalado neste exemplo é [CNTK](https://docs.microsoft.com/cognitive-toolkit/), uma estrutura de aprendizado da Microsoft que oferece suporte à personalização, treinamento e de compartilhamento de tipos diferentes de redes neurais.

> [!TIP]
> Precisa de ajuda para configurar as ferramentas Python? Consulte esses blogs:
> 
> [Introdução ao Python Web Services usando o servidor de aprendizado de máquina](https://blogs.msdn.microsoft.com/mlserver/2017/12/13/getting-started-with-python-web-services-using-machine-learning-server/)
> 
> [David escroque: Microsoft cognitivas Toolkit + código VS](http://dacrook.com/cntk-vs-code-awesome/)

### <a name="step-1-download-the-windows-version-of-the-python-package"></a>Etapa 1. Baixe a versão do Windows do pacote do Python

+ Se você estiver instalando os pacotes do Python em um servidor sem acesso à internet, você deve baixar o arquivo WHL para um computador diferente e, em seguida, copie-o para o servidor.

    Por exemplo, em um computador separado, você pode baixar o arquivo WHL deste site [ https://cntk.ai/PythonWheel/CPU-Only ](https://cntk.ai/PythonWheel/CPU-Only/cntk-2.1-cp35-cp35m-win_amd64.whl)e, em seguida, copie o arquivo `cntk-2.1-cp35-cp35m-win_amd64.whl` para uma pasta local no computador do SQL Server.

+ SQL Server 2017 usa Python 3.5. 

> [!IMPORTANT]
> Certifique-se de que você obtenha a versão do pacote do Windows. Se o arquivo termina em .gz, provavelmente não é a versão correta.

Esta página contém os downloads de várias plataformas e de várias versões de Python: [configurar CNTK](https://docs.microsoft.com/cognitive-toolkit/Setup-CNTK-on-your-machine)

### <a name="step-2-open-a-python-command-prompt"></a>Etapa 2. Abra um prompt de comando do Python

Localize o local de biblioteca do Python padrão usado pelo SQL Server. Se você tiver instalado várias instâncias, localize a pasta PYTHON_SERVICE para a instância onde você deseja adicionar o pacote.

Por exemplo, se os serviços de aprendizado de máquina foi instalado usando os padrões e aprendizado de máquina está habilitado na instância padrão, o caminho seria da seguinte maneira:

    `C:\Program Files\Microsoft SQL Server\MSSQL14.MSSQLSERVER\PYTHON_SERVICES`

Abra o prompt de comando do Python associado à instância.

> [!TIP]
> Para depurar e testar futuras, convém configurar um ambiente de Python específicas para a biblioteca de instância.

### <a name="step-3-install-the-package-using-pip"></a>Etapa 3. Instale o pacote usando o pip

+ Se você estiver acostumado a usar a linha de comando do Python, use PIP.exe para instalar novos pacotes. Você pode encontrar o **pip** instalador no `Scripts` subpasta. 

  Instalação do SQL Server não adicionar Scripts para o caminho do sistema. Se você receber um erro que `pip` não é reconhecido como um comando interno ou externo, você pode adicionar a pasta de Scripts para a variável de caminho no Windows.

  O caminho completo do **Scripts** pasta em uma instalação padrão é o seguinte:

    C:\Program Files\Microsoft SQL Server\MSSQL14. MSSQLSERVER\PYTHON_SERVICES\Scripts

+ Se você estiver usando o Visual Studio de 2017 ou Visual Studio 2015 com as extensões de Python, você pode executar `pip install` do **Python ambientes** janela. Clique em **pacotes**e na caixa de texto, forneça o nome ou local do pacote para instalar. Você não precisa digitar `pip install`; ele é preenchido para você automaticamente. 

    - Se o computador tiver acesso à Internet, forneça o nome do pacote ou a URL de um pacote específico e a versão. 
    
    Por exemplo, para instalar a versão do CNTK que tem suporte para Windows e 3.5 do Python, especifique a URL de download: `https://cntk.ai/PythonWheel/CPU-Only/cntk-2.1-cp35-cp35m-win_amd64.whl`

    - Se o computador não tiver acesso à internet, você deve baixar o arquivo WHL antes de iniciar a instalação. Em seguida, especifique o nome e caminho do arquivo local. Por exemplo, cole o seguinte caminho e arquivo para instalar o arquivo WHL baixado do site: `"C:\Downloads\CNTK\cntk-2.1-cp35-cp35m-win_amd64.whl"`

Você pode ser solicitado a elevar as permissões para concluir a instalação.

Enquanto a instalação prossegue, você pode ver as mensagens de status na janela do prompt de comando:

```python
pip install https://cntk.ai/PythonWheel/CPU-Only/cntk-2.1-cp35-cp35m-win_amd64.whl
Collecting cntk==2.1 from https://cntk.ai/PythonWheel/CPU-Only/cntk-2.1-cp35-cp35m-win_amd64.whl
  Downloading https://cntk.ai/PythonWheel/CPU-Only/cntk-2.1-cp35-cp35m-win_amd64.whl (34.1MB)
    100% |################################| 34.1MB 13kB/s
...
Installing collected packages: cntk
Successfully installed cntk-2.1
```


### <a name="step-4-load-the-package-or-its-functions-as-part-of-your-script"></a>Etapa 4. Carregar o pacote ou suas funções como parte do script

Quando a instalação for concluída, você pode começar imediatamente usando o pacote conforme descrito na próxima etapa.

Para obter exemplos de aprendizado usando CNTK, consulte estes tutoriais: [API do Python para CNTK](https://cntk.ai/pythondocs/tutorials.html)

Para usar funções do pacote em seu script, insira o padrão `import <package_name>` instrução nas linhas de inicial do script:

```python
import numpy as np
import cntk as cntk
cntk._version_
```

## <a name="list-installed-packages-using-conda"></a>Listar os pacotes instalados usando conda

Há diferentes maneiras como você pode obter uma lista de pacotes instalados. Por exemplo, você pode exibir os pacotes instalados no **Python ambientes** windows do Visual Studio.

Se você estiver usando a linha de comando do Python, você pode usar **Pip** ou **conda** Gerenciador de pacotes, incluído com o ambiente Anaconda Python adicionado pela instalação do SQL Server.

Supondo que você adicionou a pasta de Scripts para a variável de ambiente PATH, execute este comando no prompt de comando do administrador para listar os pacotes em seu ambiente de Python. Caso contrário, consulte [informações de pacote de R obtenha e Python](../r/determine-which-packages-are-installed-on-sql-server.md#pip-conda) ponteiros sobre como executar as ferramentas Python no SQL Server.

```python
conda list
```

Para obter mais informações sobre **conda** e como usá-lo para criar e gerenciar vários ambientes de Python, consulte [gerenciamento de ambientes com conda](https://conda.io/docs/user-guide/tasks/manage-environments.html).
