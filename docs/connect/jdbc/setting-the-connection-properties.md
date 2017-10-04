---
title: "Definindo as propriedades de Conexão | Microsoft Docs"
ms.custom: 
ms.date: 04/11/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1b62700-f046-488d-bd6b-a5cd8fc345b7
caps.latest.revision: 154
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 56dbb81f9d30ccb41a6247c4fefda9d6ecd703a6
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="setting-the-connection-properties"></a>Definindo as propriedades de conexão
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  As propriedades da cadeia de conexão podem ser especificadas de várias formas:  
  
-   Como name = value properties na URL de conexão quando você se conecta usando a classe do Gerenciador de driver.  
  
-   Como nome = value properties no *propriedades* parâmetro do método Connect da classe do Gerenciador de driver.  
  
-   Como valores no método setter apropriado da fonte de dados do driver. Por exemplo:  
  
    ```  
  
    datasource.setServerName(value)  
    datasource.setDatabaseName(value)  
  
    ```  
  
## <a name="remarks"></a>Comentários  
 Os nomes de propriedade não diferenciam maiúsculas de minúsculas, e os nomes de propriedade duplicados são resolvidos na seguinte ordem:  
  
1.  Argumentos de API (como usuário e senha)  
  
2.  Coleção de propriedades.  
  
3.  Última instância na cadeia de conexão.  
  
 Além disso, são permitidos valores desconhecidos para os nomes de propriedade, e os valores não são validados pelo driver JDBC para diferenciação de maiúsculas de minúsculas.  
  
 São permitidos sinônimos, resolvidos na ordem, assim como nomes de propriedade duplicados.  
  
 A tabela a seguir lista todas as propriedades da cadeia de conexão disponíveis no momento para o driver JDBC.  
  
|Propriedade|Tipo|Default|Description|  
|--------------|----------|-------------|-----------------|  
|accessToken|Cadeia de caracteres|nulo|Use esta propriedade para se conectar ao banco de dados SQL usando um token de acesso. **accessToken** não pode ser definida usando a URL de conexão.|  
|applicationIntent|Cadeia de caracteres|ReadWrite|Declara o tipo de carga de trabalho de aplicativo ao conectar-se a um servidor. Os valores possíveis são **ReadOnly** e **ReadWrite**. Para obter mais informações, consulte [suporte do Driver JDBC para alta disponibilidade, recuperação de desastres](../../connect/jdbc/jdbc-driver-support-for-high-availability-disaster-recovery.md).|  
|applicationName|Cadeia de caracteres<br /><br /> [<=128 caracteres]|nulo|O nome do aplicativo ou "[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]" se nenhum nome for fornecido. Usado para identificar o aplicativo específico em várias [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] de criação de perfil e as ferramentas de log.|  
|autenticação|Cadeia de caracteres|NotSpecified|Começando com o Microsoft JDBC Driver 6.0 para SQL Server, essa propriedade opcional indica qual método de autenticação de SQL a ser usado para conexão. Os valores possíveis são **ActiveDirectoryIntegrated**, **ActiveDirectoryPassword**, **SqlPassword** e o padrão **NotSpecified**.<br /><br /> Use **ActiveDirectoryIntegrated** para se conectar ao banco de dados SQL usando a autenticação integrada do Windows.<br /><br /> Use **ActiveDirectoryPassword** para se conectar ao banco de dados SQL usando um nome principal do AD do Azure e a senha.<br /><br /> Use **SqlPassword** para se conectar a um SQL Server usando **userName**/**usuário** e **senha** propriedades.<br /><br /> Use **NotSpecified** se nenhum desses métodos de autenticação é necessária.<br /><br /> **Importante:** se a autenticação estiver definida como ActiveDirectoryIntegrated, as seguintes duas bibliotecas precisará ser instalado: **SQLJDBC_AUTH. DLL** (disponível no pacote de driver JDBC) e o Azure Active Directory Authentication Library para SQL Server (**ADALSQL. DLL**) está disponível em vários idiomas (x86 e amd64) no Centro de download em [Microsoft Active Directory Authentication Library para Microsoft SQL Server](https://www.microsoft.com/en-us/download/details.aspx?id=48742). O driver JDBC dá suporte apenas à versão **1.0.2028.318 e superior** para o ADALSQL. DLL.<br /><br /> **Observação:** quando a propriedade de autenticação é definida como qualquer valor diferente de **NotSpecified**, o driver por padrão usa criptografia Secure Sockets Layer (SSL).<br /><br /> Para obter informações sobre como configurar a autenticação do Active Directory do Azure, visite [se conectar ao SQL banco de dados, usando o Azure Active Directory Authentication](https://azure.microsoft.com/en-us/documentation/articles/sql-database-aad-authentication/).|  
|authenticationScheme|Cadeia de caracteres|"NativeAuthentication"|Indica que tipo de segurança integrada você deseja que o seu aplicativo use. Os valores possíveis são **JavaKerberos** e o padrão **NativeAuthentication**.<br /><br /> Ao usar **authenticationScheme = JavaKerberos**, você deve especificar o nome de domínio totalmente qualificado (FQDN) no **serverName** ou **serverSpn** propriedade. Senão, ocorrerá um erro (servidor não encontrado no banco de dados de Kerberos).<br /><br /> Para obter mais informações sobre como usar **authenticationScheme**, consulte [usando a autenticação integrada Kerberos para se conectar ao SQL Server](../../connect/jdbc/using-kerberos-integrated-authentication-to-connect-to-sql-server.md).|  
|columnEncryptionSetting|Cadeia de caracteres<br /><br /> ["Habilitado" &#124;" Desabilitado"]|Desabilitado|Defina como "Habilitado" para usar o início do recurso sempre criptografado (AE) com o Microsoft JDBC Driver 6.0 para SQL Server. Quando AE está habilitado, o driver JDBC criptografa e descriptografa os dados confidenciais armazenados em colunas de banco de dados criptografado no SQL Server.<br /><br /> Consulte [usar sempre criptografado com o Driver JDBC](../../connect/jdbc/using-always-encrypted-with-the-jdbc-driver.md) para obter mais detalhes.<br /><br /> **Observação:** sempre criptografado está disponível com o SQL Server 2016 ou versões posteriores.|  
|databaseName, database|Cadeia de caracteres<br /><br /> [<=128 caracteres]|nulo|O nome do banco de dados ao qual se conectar. Se não for indicada, será estabelecida uma conexão com o banco de dados padrão.|  
|disableStatementPooling|booleano<br /><br /> ["true" &#124;" False]"|true|No momento, só há suporte para o valor "true". Se estiver definida como "false", ocorrerá uma exceção.|  
|encrypt|booleano<br /><br /> ["true" &#124;" False]"|false|Defina como "true" para especificar que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] usa criptografia Secure Sockets Layer (SSL) para todos os dados enviados entre o cliente e o servidor se o servidor tem um certificado instalado. O valor padrão é false.<br /><br /> Começando com o Microsoft JDBC Driver 6.0 para SQL Server, há uma nova conexão configuração 'authentication' que usa criptografia SSL por padrão. Para obter mais informações, consulte a propriedade 'authentication'.|  
|failoverPartner|Cadeia de caracteres|nulo|O nome do servidor de failover usado em uma configuração de espelhamento de banco de dados. Essa propriedade é usada em uma falha de conexão inicial ao servidor principal; depois que você estabelecer a conexão inicial, essa propriedade será ignorada. Ele deve ser usado com a propriedade databaseName.<br /><br /> **Observação:** o driver não dá suporte para especificar o número de porta de instância de servidor para a instância de parceiro de failover como parte da propriedade failoverPartner na cadeia de conexão. No entanto, há suporte à especificação das propriedades serverName, instanceName e portNumber da instância do servidor principal e da propriedade failoverPartner da instância do parceiro de failover na mesma cadeia de conexão.<br /><br /> Se você especificar um nome de rede Virtual no **Server** propriedade de conexão, você não pode usar o espelhamento de banco de dados. Consulte [suporte do Driver JDBC para alta disponibilidade, recuperação de desastres](../../connect/jdbc/jdbc-driver-support-for-high-availability-disaster-recovery.md) para obter mais informações.|  
|hostNameInCertificate|Cadeia de caracteres|nulo|O nome do host a ser usado ao validar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] certificado SSL.<br /><br /> Se a propriedade hostNameInCertificate for especificado ou definido como null, o [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] usará o **serverName** valor da propriedade na URL de conexão como o nome do host para validar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] certificado SSL.<br /><br /> **Observação:** esta propriedade é usada em combinação com o **criptografar**/**autenticação** propriedades e o **trustServerCertificate**propriedade. Essa propriedade afetará a validação do certificado se e somente se a conexão usa criptografia Secure Sockets Layer (SSL) e o **trustServerCertificate** é definido como "false". Verifique se o valor passado para **hostNameInCertificate** corresponda exatamente ao nome DNS ou CN (nome comum) de entidade alternativo SAN (nome) no certificado do servidor para uma conexão SSL tenha êxito. Para obter mais informações, consulte [Noções básicas sobre o suporte a SSL](../../connect/jdbc/understanding-ssl-support.md).|  
|NOMEDAINSTÂNCIA|Cadeia de caracteres<br /><br /> [<=128 caracteres]|nulo|O [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] para se conectar ao nome da instância. Quando ela não for especificada, uma conexão será estabelecida com a instância padrão. Para o caso em que instanceName e a porta forem especificadas, veja as observações para a porta.<br /><br /> Se você especificar um nome de rede Virtual no **servidor** propriedade de conexão, você não pode usar **instanceName** propriedade de conexão. Consulte [suporte do Driver JDBC para alta disponibilidade, recuperação de desastres](../../connect/jdbc/jdbc-driver-support-for-high-availability-disaster-recovery.md) para obter mais informações.|  
|integratedSecurity|booleano<br /><br /> ["true" &#124;" False]"|false|Defina como "true" para indicar que as credenciais do Windows serão usadas por [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] em sistemas operacionais Windows. Se "true", o driver JDBC procurará no cache da credencial do computador local as credenciais que já foram fornecidas no computador ou no logon da rede.<br /><br /> Definido como "true" (com **authenticationscheme = JavaKerberos**), para indicar que as credenciais do Kerberos serão usadas por [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]. Para obter mais informações sobre a autenticação Kerberos, consulte [usando a autenticação integrada Kerberos para se conectar ao SQL Server](../../connect/jdbc/using-kerberos-integrated-authentication-to-connect-to-sql-server.md). <br /><br /> Se "false", o nome de usuário e a senha deverão ser fornecidos.| 
|keyStoreAuthentication|Cadeia de caracteres|nulo| Começando com o Microsoft JDBC Driver 6.0 para SQL Server, essa propriedade identifica qual repositório de chaves para configurar diretamente para a conexão com o sempre criptografado e determina um mecanismo de autenticação usado para autenticar para o repositório de chaves. Microsoft JDBC Driver 6.0 para SQL Server dá suporte à configuração backup do armazenamento de chave Java diretamente usando essa propriedade para o qual você precisa definir "**keyStoreAuthentication = JavaKeyStorePassword**". Observe que para usar essa propriedade, você também precisa definir a **keyStoreLocation** e **keyStoreSecret** propriedades para o repositório de chaves Java. <br/><br/>Para obter mais informações, visite [usar sempre criptografado com o Driver JDBC](https://msdn.microsoft.com/library/mt591987%28v=sql.110%29.aspx?f=255&MSPPError=-2147217396). 
|keyStoreLocation|Cadeia de caracteres|nulo|Quando **keyStoreAuthentication = JavaKeyStorePassword**, o **keyStoreLocation** propriedade identifica o caminho para o arquivo de armazenamento de chaves Java que armazena a chave mestra de coluna a ser usado com o sempre criptografado dados. Observe que o caminho deve incluir o nome do arquivo de armazenamento de chaves.<br/><br/>Para obter mais informações, visite [usar sempre criptografado com o Driver JDBC](https://msdn.microsoft.com/library/mt591987%28v=sql.110%29.aspx?f=255&MSPPError=-2147217396).
|keyStoreSecret|Cadeia de caracteres|nulo|Quando **keyStoreAuthentication = JavaKeyStorePassword**, o **keyStoreSecret** propriedade identifica a senha a ser usado para o armazenamento de chaves, bem como para a chave. Observe que para usar o repositório de chave Java o armazenamento de chaves e a senha da chave deve ser o mesmo.<br/><br/>Para obter mais informações, visite [usar sempre criptografado com o Driver JDBC](https://msdn.microsoft.com/library/mt591987%28v=sql.110%29.aspx?f=255&MSPPError=-2147217396).
|lastUpdateCount|booleano<br /><br /> ["true" &#124;" False]"|true|Um valor "true" só retorna a contagem de atualização mais recente de uma instrução SQL passada para o servidor, podendo ser usado em instruções SELECT, INSERT ou DELETE para ignorar contagens de atualização adicionais causadas por gatilhos de servidor. A definição dessa propriedade como "false" faz com que todas as contagens de atualização sejam retornadas, inclusive as retornadas por gatilhos de servidor.<br /><br /> **Observação:** essa propriedade se aplica somente quando ele é usado com o [executeUpdate](../../connect/jdbc/reference/executeupdate-method-sqlserverstatement.md) métodos. Todos os outros executar métodos retornam todos os resultados e contagens de atualização. Essa propriedade só afeta contagens de atualização retornadas por gatilhos de servidor. Ela não afeta conjuntos de resultados ou erros resultantes de parte da execução do gatilho.|  
|lockTimeout|int|-1|O número de milissegundos para aguardar antes do banco de dados informar um tempo limite de bloqueio. O comportamento padrão é aguardar indefinidamente. Se for especificado, esse valor será o padrão para todas as instruções na conexão. Observe que **Statement.setQueryTimeout()** pode ser usado para definir o tempo limite de instruções específicas. O valor pode ser 0, que especifica a ausência de espera.|  
|loginTimeout|int [0..65535]|15|O número de segundos que o driver deve aguardar antes que o tempo limite de uma conexão com falha seja alcançado. Um valor igual a zero indica que o tempo limite é o padrão do sistema, especificado como 15 segundos por padrão. Um valor diferente de zero é o número de segundos que o driver deve aguardar antes do tempo limite de uma conexão com falha.<br /><br /> Se você especificar um nome de rede Virtual no **Server** propriedade de conexão, você deve especificar um valor de tempo limite de três minutos ou mais para dar tempo suficiente para uma conexão de failover seja bem-sucedida. Consulte [suporte do Driver JDBC para alta disponibilidade, recuperação de desastres](../../connect/jdbc/jdbc-driver-support-for-high-availability-disaster-recovery.md) para obter mais informações.|  
|multiSubnetFailover|Booliano|false|Sempre especifique **multiSubnetFailover = true** ao se conectar ao ouvinte do grupo de disponibilidade de um [!INCLUDE[ssSQL11](../../includes/sssql11_md.md)] o grupo de disponibilidade ou uma [!INCLUDE[ssSQL11](../../includes/sssql11_md.md)] instância de Cluster de Failover. **multiSubnetFailover = true** configura [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] para fornecer detecção mais rápida e conexão ao servidor ativo (atualmente). Os valores possíveis são true e false. Consulte [suporte do Driver JDBC para alta disponibilidade, recuperação de desastres](../../connect/jdbc/jdbc-driver-support-for-high-availability-disaster-recovery.md) para obter mais informações.<br /><br /> Você pode acessar programaticamente o **multiSubnetFailover** propriedade de conexão com [getPropertyInfo](../../connect/jdbc/reference/getpropertyinfo-method-sqlserverdriver.md), [getMultiSubnetFailover](../../connect/jdbc/reference/getmultisubnetfailover-method-sqlserverdatasource.md), e [ setMultiSubnetFailover](../../connect/jdbc/reference/setmultisubnetfailover-method-sqlserverdatasource.md).<br /><br /> **Observação:** começando com o Microsoft JDBC Driver 6.0 para SQL Server não é necessário definir multiSubnetFailover como verdadeiro ao se conectar a um ouvinte de grupo de disponibilidade. Uma nova propriedade, **transparentNetworkIPResolution**, que é habilitado por padrão, fornece a detecção e a conexão ao servidor ativo (atualmente).|  
|packetSize|int [-1 &#124; 0 &#124; 512..32767]|8000|O tamanho do pacote de rede usado para se comunicar com o SQL Server, especificado em bytes. Um valor igual a -1 indica o uso do tamanho de pacote padrão do servidor. Um valor igual a 0 indica o uso do valor máximo, 32767. Se essa propriedade for definida como um valor fora do intervalo aceitável, ocorrerá uma exceção.<br /><br /> **Importante:** não é recomendável usar a propriedade packetSize quando a criptografia está habilitada (criptografar = true). Do contrário, o driver pode acionar um erro na conexão. Para obter mais informações, consulte o [setPacketSize](../../connect/jdbc/reference/setpacketsize-method-sqlserverdatasource.md) método o [SQLServerDataSource](../../connect/jdbc/reference/sqlserverdatasource-class.md) classe.|  
|password|Cadeia de caracteres<br /><br /> [<=128 caracteres]|nulo|A senha do banco de dados, no caso de conexão com o usuário do SQL e a senha.<BR/>Para a conexão de Kerberos com o nome da entidade e uma senha, essa propriedade é definida como senha Principal do Kerberos.|  
|portNumber, port|int [0..65535]|1433|A porta onde [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] está escutando. Se o número da porta for especificado na cadeia de conexão, nenhuma solicitação para sqlbrowser será feita. Quando a porta e instanceName forem especificadas, a conexão será estabelecida com a porta especificada. No entanto, o **instanceName** é validada e um erro será lançado se ela não corresponde à porta.<br /><br /> **Importante:** é recomendável que o número da porta sempre seja especificada, pois é mais segura do que o uso de sqlbrowser.|  
|responseBuffering|Cadeia de caracteres<br /><br /> ["completo" &#124;" adaptável]"|adaptive|Se essa propriedade for definida como "adaptive", o mínimo de dados possíveis será armazenado em buffer quando necessário. O modo padrão é "adaptive".<br /><br /> Quando essa propriedade for definida como "full", todo o conjunto de resultados será lido no servidor quando uma instrução for executada.<br /><br /> **Observação:** depois de atualizar o JDBC driver versão 1.2, o comportamento de buffer padrão será "adaptável". Se seu aplicativo jamais definiu a propriedade "responseBuffering" e você deseja manter o comportamento padrão da versão 1.2 no aplicativo, você deve definir a propriedade responseBufferring como "full" nas propriedades de conexão ou usando o [ setResponseBuffering](../../connect/jdbc/reference/setresponsebuffering-method-sqlserverstatement.md) método o [SQLServerStatement](../../connect/jdbc/reference/sqlserverstatement-class.md) objeto.|  
|selectMethod|Cadeia de caracteres<br /><br /> ["direto" &#124;" cursor"]|direct|Se essa propriedade for definida como "cursor", um banco de dados será criado para cada consulta criada na conexão dos cursores TYPE_FORWARD_ONLY e CONCUR_READ_ONLY. Essa propriedade só costuma ser obrigatória caso o aplicativo gere conjuntos de resultados muito grandes que não possam estar inteiramente contidos na memória do cliente. Quando essa propriedade estiver definida como "cursor", apenas um número limitado de linhas do conjunto de resultados será mantido na memória do cliente. O comportamento padrão é que todas as linhas do conjunto de resultados sejam mantidas na memória do cliente. Esse comportamento fornece o melhor desempenho quando o aplicativo processa todas as linhas.|  
|sendStringParametersAsUnicode|booleano<br /><br /> ["true" &#124;" False]"|true|Se o **sendStringParametersAsUnicode** propriedade é definida como "true", parâmetros String serão enviados para o servidor no formato Unicode.<br /><br /> Se o **sendStringParametersAsUnicode** propriedade estiver definida como "false", parâmetros String serão enviados ao servidor no formato não Unicode, como ASCII/MBCS, e Unicode.<br /><br /> O valor padrão para o **sendStringParametersAsUnicode** propriedade for "true".<br /><br /> **Observação:** o **sendStringParametersAsUnicode** propriedade é verificada apenas durante o envio de um valor de parâmetro com **CHAR**, **VARCHAR**, ou **LONGVARCHAR** tipos JDBC. Os novos métodos de caractere nacional JDBC 4.0, como os métodos setNString, setNCharacterStream e setNClob de [SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) e [SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md) classes, sempre enviam os valores de parâmetro para o servidor em Unicode, independentemente da configuração desta propriedade.<br /><br /> Para obter ótimo desempenho com o **CHAR**, **VARCHAR**, e **LONGVARCHAR** tipos de dados JDBC, um aplicativo deve definir o ** sendStringParametersAsUnicode** propriedade como "false" e usar o setString, setCharacterStream e setClob métodos de caractere não Nacional do [SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) e [ SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md) classes.<br /><br /> Quando o aplicativo define o **sendStringParametersAsUnicode** propriedade como "false" e usa tipos de um método de caractere não nacional para acessar os dados Unicode no lado do servidor (como **nchar**, **nvarchar** e **ntext**), alguns dados poderão ser perdidos se o agrupamento de banco de dados não oferece suporte os caracteres nos parâmetros de cadeia de caracteres passados pelo método de caractere não nacional.<br /><br /> Observe que um aplicativo deve usar os métodos de caractere nacional setNString, setNCharacterStream e setNClob do [SQLServerPreparedStatement](../../connect/jdbc/reference/sqlserverpreparedstatement-class.md) e [SQLServerCallableStatement](../../connect/jdbc/reference/sqlservercallablestatement-class.md) classes para o **NCHAR**, **NVARCHAR**, e **LONGNVARCHAR** tipos de dados JDBC.|  
|sendTimeAsDatetime|booleano<br /><br /> ["true" &#124;" False]"|true|Essa propriedade foi adicionada no [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] JDBC Driver 3.0.<br /><br /> Quando for verdadeiro, os valores serão enviados ao servidor como [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] **datetime** valores.<br /><br /> Quando for falso, os valores serão enviados ao servidor como [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] **tempo** valores.<br /><br /> **sendTimeAsDatetime** também pode ser modificado programaticamente com [Setsendtimeasdatetime](../../connect/jdbc/reference/setsendtimeasdatetime-method-sqlserverdatasource.md).<br /><br /> O valor padrão para esta propriedade poderá ser alterado em uma versão futura.<br /><br /> Para obter mais informações sobre como o [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] configura os valores antes de enviá-los para o servidor, consulte [configurando como os valores são enviados para o servidor](../../connect/jdbc/configuring-how-java-sql-time-values-are-sent-to-the-server.md).|  
|serverName, server|Cadeia de caracteres|nulo|O computador que esteja executando [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)].<br /><br /> Você também pode especificar o nome de rede Virtual de um [!INCLUDE[ssHADR](../../includes/sshadr_md.md)] grupo de disponibilidade. Consulte [suporte do Driver JDBC para alta disponibilidade, recuperação de desastres](../../connect/jdbc/jdbc-driver-support-for-high-availability-disaster-recovery.md) para obter mais informações.|  
|serverSpn|Cadeia de caracteres|nulo|A partir do Microsoft JDBC Driver 4.2 para SQL Server, essa propriedade opcional pode ser usada para especificar o Nome da Entidade de Serviço (SPN) para uma conexão Kerberos Java.  Ele é usado em conjunto com **authenticationScheme**.<br /><br /> Para especificar o SPN, ele pode ser na forma de: "MSSQLSvc/fqdn:port@REALM" em que fqdn é o nome de domínio totalmente qualificado, porta é o número de porta e REALM é o realm Kerberos do SQL Server em letras maiusculas.<br /><br /> Observação: o @REALM será opcional se o domínio padrão do cliente (conforme especificado na configuração do Kerberos) é o mesmo que o realm do Kerberos para o SQL Server.<br /><br /> Para obter mais informações sobre como usar **serverSpn** com Java Kerberos, consulte [usando a autenticação integrada Kerberos para se conectar ao SQL Server](../../connect/jdbc/using-kerberos-integrated-authentication-to-connect-to-sql-server.md).|  
|serverNameAsACE|booleano<br /><br /> ["true" &#124;" False]"|false|Começando com o Microsoft JDBC Driver 6.0 for SQL Server, definido como “true” para indicar que o driver deve traduzir o nome do servidor Unicode para a codificação compatível ASCII (Punycode) para a conexão. Se essa configuração for “false”, o driver se conecta usando o nome do servidor, conforme fornecido pelo usuário.<br /><br /> Consulte [recursos internacionais do JDBC Driver](../../connect/jdbc/international-features-of-the-jdbc-driver.md) para obter mais detalhes.|  
|TransparentNetworkIPResolution|booleano<br /><br /> ["true" &#124;" False]"|true|Começando com o Microsoft JDBC Driver 6.0 para SQL Server, essa propriedade, o transparentNetworkIPResolution, fornece detecção mais rápida e conexão ao servidor ativo (atualmente). Os valores possíveis são true e false verdadeiro como o valor padrão.<br /><br /> Antes do Microsoft JDBC Driver 6.0 para SQL Server, um aplicativo teve que definir a cadeia de caracteres de conexão para incluir "multiSubnetFailover = true" para indicar que ele foi conectando-se a um grupo de disponibilidade do AlwaysOn. Sem definir a palavra-chave de conexão multiSubnetFailover como true, um aplicativo pode apresentar um tempo limite ao se conectar a um grupo de disponibilidade do AlwaysOn. Começando com o Microsoft JDBC Driver 6.0 para SQL Server, um aplicativo não precisa definir multiSubnetFailover como true mais. <br /><br />**Observação:** quando transparentNetworkIPResolution = true, a primeira tentativa de conexão usa 500 MS como o tempo limite. Quaisquer tentativas subsequentes usam a mesma lógica de tempo limite como usado pela propriedade multiSubnetFailover.|  
|columnEncryptionSetting|booleano<br /><br /> ["true" &#124;" False]"|false|Definido como "true" para usar o início do recurso Sempre criptografado (AE) com o Microsoft JDBC Driver 6.0 para o SQL Server. Quando AE está habilitado, o driver JDBC criptografa e descriptografa os dados confidenciais armazenados em colunas de banco de dados criptografado no SQL Server.<br /><br /> Consulte [usar sempre criptografado com o Driver JDBC](../../connect/jdbc/using-always-encrypted-with-the-jdbc-driver.md) para obter mais detalhes.<br /><br /> **Observação:** sempre criptografado está disponível com o SQL Server 2016 ou versões mais recentes.|  
|trustServerCertificate|booleano<br /><br /> ["true" &#124;" False]"|false|Defina como "true" para especificar que o [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] não validará o [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] certificado SSL.<br /><br /> Se "true", o [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] certificado SSL será automaticamente confiável quando a camada de comunicação for criptografada com SSL.<br /><br /> Se "false", o [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] validará o certificado SSL do servidor. Se houver falha na validação do certificado, o driver acionará um erro e encerrará a conexão. O valor padrão é "falso". Verifique se o valor passado para **serverName** corresponda exatamente ao nome DNS ou CN (nome comum) no nome alternativo da entidade no certificado do servidor para uma conexão SSL tenha êxito. Para obter mais informações, consulte [Noções básicas sobre o suporte a SSL](../../connect/jdbc/understanding-ssl-support.md).<br /><br /> **Observação:** esta propriedade é usada em combinação com o **criptografar**/**autenticação** propriedades. Essa propriedade afeta apenas a validação do certificado SSL do servidor se e somente se a conexão usa criptografia SSL.|  
|trustStore|Cadeia de caracteres|nulo|O caminho (inclusive o nome de arquivo) para o arquivo trustStore do certificado. O arquivo trustStore contém a lista de certificados nos quais o cliente confia.<br /><br /> Quando essa propriedade não for especificada ou for definida como nula, o driver contará com as regras de pesquisa de fábrica do gerenciador de confiança para determinar que repositório de certificados usar.<br /><br /> **SunX509 TrustManagerFactory padrão tenta localizar o material confiável na seguinte ordem de pesquisa:**<br /><br /> Um arquivo especificado pela propriedade do sistema JVM (Máquina Virtual Java) "javax.net.ssl.trustStore".<br /><br /> "\<java-home >/lib/security/jssecacerts" arquivo.<br /><br /> "\<java-home >/lib/security/cacerts" arquivo.<br /><br /> <br /><br /> Para obter mais informações, consulte a documentação do SUNX509 TrustManager Interface no site da Sun Microsystems.<br /><br /> **Observação:** essa propriedade afeta apenas a pesquisa trustStore do certificado se e somente se a conexão usa criptografia SSL e o **trustServerCertificate** propriedade é definida como "false".|  
|trustStorePassword|String|nulo|A senha usada para verificar a integridade dos dados de trustStore.<br /><br /> Se a propriedade trustStore for definida, mas a propriedade trustStorePassword não for definida, a integridade de trustStore não será verificada.<br /><br /> Quando as propriedades trustStore e trustStorePassword não forem especificadas, o driver usará as propriedades do sistema JVM, "javax.net.ssl.trustStore" e "javax.net.ssl.trustStorePassword". Se a propriedade do sistema "javax.net.ssl.trustStorePassword" não for especificada, a integridade de trustStore não será verificada.<br /><br /> Se a propriedade trustStore não estiver definida, mas a propriedade trustStorePassword estiver, o driver JDBC usará o arquivo especificado por "javax.net.ssl.trustStore" como um repositório confiável e a integridade dele será verificada com trustStorePassword. Isso pode ser necessário quando o aplicativo cliente não quiser armazenar a senha na propriedade do sistema JVM.<br /><br /> **Observação:** a propriedade trustStorePassword só afeta a pesquisa trustStore do certificado se e somente se a conexão usa a conexão SSL e o **trustServerCertificate** propriedade é definida como "false".|  
|userName, user|Cadeia de caracteres<br /><br /> [<=128 caracteres]|nulo|O usuário de banco de dados, no caso de conexão com o usuário do SQL e a senha.<BR/>Para a conexão de Kerberos com o nome da entidade e uma senha, essa propriedade é definida como nome Principal Kerberos.|  
|workstationID|Cadeia de caracteres<br /><br /> [<=128 caracteres]|\<cadeia de caracteres vazia >|A ID da estação de trabalho. Usado para identificar a estação de trabalho específica em várias [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] de criação de perfil e as ferramentas de log. Se nenhum for especificado, o \<cadeia de caracteres vazia > é usado.|  
|xopenStates|booleano<br /><br /> ["true" &#124;" False]"|false|Defina como "true" para especificar que o driver retorna códigos de estado compatíveis com XOPEN em exceções. O padrão é retornar códigos de estado SQL 99.|  
|gsscredential|org.ietf.jgss.GSSCredential|nulo|Começando com o Microsoft JDBC Driver 6.2 para SQL Server, as credenciais do usuário a ser usada para delegação restrita de Kerberos podem ser passadas nessa propriedade. <BR/>Isso deve ser usado com **integratedSecurity** como **true** e **JavaKerberos** **authenticationscheme**.| 
|jaasConfigurationName|Cadeia de caracteres|SQLJDBCDriver|Começando com o Microsoft JDBC Driver 6.2 para SQL Server, cada conexão com o SQL Server pode ter seu próprio arquivo de configuração de logon JAAS para estabelecer a conexão do Kerberos. Nome do arquivo de configuração de logon pode ser passado a esta propriedade. <BR/> Por padrão, o driver define propriedade `useDefaultCcache = true` para IBM JVMs, e `useTicketCache = true` para outros JVMs.|
|serverPreparedStatementDiscardThreshold|Integer|10|Controla como muitas ações de descarte de instrução preparada pendentes (sp_unprepare) podem estar pendentes por conexão antes de uma chamada para limpar os identificadores pendentes no servidor é executada. Se a configuração for < = 1 un-preparar ações serão executadas imediatamente na instrução preparada fechar. Se for definido como > 1 essas chamadas serão agrupadas em conjunto para evitar a sobrecarga da chamada sp_unprepare com muita frequência.|
|enablePrepareOnFirstPreparedStatementCall|booleano<br /><br /> ["true" &#124;" False]"|false|Se essa configuração for definida como false, a primeira execução de uma instrução preparada será chamada sp_executesql e não prepara uma instrução, depois que a segunda execução acontece ele chamar sp_prepexec e instalação, na verdade, um identificador de instrução preparada.|
|statementPoolingCacheSize|Integer|10|Instruções armazenável configuráveis para reutilização em Pool| 
  
> [!NOTE]  
>  O [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] usa o servidor de valores padrão para propriedades de conexão, exceto para ANSI_DEFAULTS e IMPLICIT_TRANSACTIONS. O [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] define automaticamente ANSI_DEFAULTS como ON e IMPLICIT_TRANSACTIONS como OFF.  

> [!Note]
> Importante: Se a autenticação estiver definida como ActiveDirectoryPassword, a seguinte biblioteca precisará ser incluído no classpath: [do azure Active Directory library para java](https://github.com/AzureAD/azure-activedirectory-library-for-java). Ele pode ser encontrado em [Repositório Maven](https://mvnrepository.com/artifact/com.microsoft.azure/adal4j). A maneira mais simples para baixar a biblioteca e suas dependências é usando Maven: 
 >1. Primeiro, instale Maven em seu sistema 
 >2. Vá para o [página GitHub](https://github.com/Microsoft/mssql-jdbc) do driver
 >3. Baixe o arquivo pom.xml
 >4. Execute o seguinte comando Maven para baixar a biblioteca e suas dependências: mvn dependência: copiar-dependências
  
## <a name="see-also"></a>Consulte também  
 [Conectando ao SQL Server com o JDBC Driver](../../connect/jdbc/connecting-to-sql-server-with-the-jdbc-driver.md)  
 [Modo FIPS](../../connect/jdbc/fips-mode.md)
  
  
