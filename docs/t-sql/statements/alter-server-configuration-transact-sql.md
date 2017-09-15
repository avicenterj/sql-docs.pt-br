---
title: "ALTERAR a configuração de servidor (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 05/01/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ALTER SERVER CONFIGURATION
- ALTER_SERVER_CONFIGURATION_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- SERVER CONFIGURATION, ALTER
- process affinity, setting
- ALTER SERVER CONFIGURATION statement
- setting process affinity
ms.assetid: f3059e42-5f6f-4a64-903c-86dca212a4b4
caps.latest.revision: 72
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a4c406824e51b79b74403623a100f2fc355d28bc
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="alter-server-configuration-transact-sql"></a>ALTER SERVER CONFIGURATION (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Modifica as definições da configuração global do servidor atual no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
ALTER SERVER CONFIGURATION  
SET <optionspec>   
[;]  
  
<optionspec> ::=  
{  
     <process_affinity>  
   | <diagnostic_log>  
   | <failover_cluster_property>  
   | <hadr_cluster_context>  
   | <buffer_pool_extension>  
   | <soft_numa>  
}  
  
<process_affinity> ::=   
   PROCESS AFFINITY   
   {  
     CPU = { AUTO | <CPU_range_spec> }   
   | NUMANODE = <NUMA_node_range_spec>   
   }  
   <CPU_range_spec> ::=   
      { CPU_ID | CPU_ID  TO CPU_ID } [ ,...n ]   
  
   <NUMA_node_range_spec> ::=   
      { NUMA_node_ID | NUMA_node_ID TO NUMA_node_ID } [ ,...n ]  
  
<diagnostic_log> ::=   
   DIAGNOSTICS LOG   
   {   
     ON    
   | OFF    
   | PATH = { 'os_file_path' | DEFAULT }    
   | MAX_SIZE = { 'log_max_size' MB | DEFAULT }    
   | MAX_FILES = { 'max_file_count' | DEFAULT }    
   }  
  
<failover_cluster_property> ::=   
   FAILOVER CLUSTER PROPERTY <resource_property>  
   <resource_property> ::=  
      {  
        VerboseLogging = { 'logging_detail' | DEFAULT }    
      | SqlDumperDumpFlags = { 'dump_file_type' | DEFAULT }  
      | SqlDumperDumpPath = { 'os_file_path'| DEFAULT }  
      | SqlDumperDumpTimeOut = { 'dump_time-out' | DEFAULT }  
      | FailureConditionLevel = { 'failure_condition_level' | DEFAULT }  
      | HealthCheckTimeout = { 'health_check_time-out' | DEFAULT }  
      }  
  
<hadr_cluster_context> ::=  
   HADR CLUSTER CONTEXT = { 'remote_windows_cluster' | LOCAL }  
  
<buffer_pool_extension>::=  
    BUFFER POOL EXTENSION   
    { ON ( FILENAME = 'os_file_path_and_name' , SIZE = <size_spec> )   
    | OFF }  
  
    <size_spec> ::=  
        { size [ KB | MB | GB ] }  
  
<soft_numa> ::=  
    SET SOFTNUMA  
    { ON | OFF }  
```  
  
## <a name="arguments"></a>Argumentos  
 **\<process_affinity >:: =**  
  
 PROCESS AFFINITY  
 Permite que threads de hardware sejam associados a CPUs.  
  
 CPU = {AUTOMÁTICA | \<CPU_range_spec >}  
 Distribui threads de trabalho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para cada CPU dentro do intervalo especificado. CPUs fora do intervalo especificado não terão threads atribuídos.  
  
 AUTO  
 Especifica que nenhum thread está atribuído a uma CPU. O sistema operacional pode mover threads livremente entre CPUs com base na carga de trabalho do servidor. Essa é a configuração padrão e recomendada.  
  
 \<CPU_range_spec >:: =  
 Especifica a CPU ou o intervalo de CPUs ao qual atribuir threads.  
  
 { CPU_ID | CPU_ID TO CPU_ID } [ ,...n ]  
 É a lista de uma ou mais CPUs. IDs de CPU começam com 0 e são **inteiro** valores.  
  
 NUMANODE = \<NUMA_node_range_spec >  
 Atribui threads a todas as CPUs que pertencem ao nó NUMA especificado ou ao intervalo de nós.  
  
 \<NUMA_node_range_spec >:: =  
 Especifica o nó NUMA ou o intervalo de nós NUMA.  
  
 { NUMA_node_ID | NUMA_node_ID TO NUMA_node_ID } [ ,...n ]  
 É a lista de um ou mais nós NUMA. IDs de nó NUMA começam com 0 e são **inteiro** valores.  
  
 **\<diagnostic_log >:: =**  
  
**Aplica-se a**: do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 DIAGNOSTICS LOG  
 Inicia ou interrompe o log de dados de diagnóstico capturados pelo procedimento sp_server_diagnostics e define os parâmetros de configuração do log SQLDIAG, como a contagem de substituições de arquivos, o tamanho do arquivo do log e o local do arquivo. Para obter mais informações, consulte [Exibir e ler o log de diagnóstico da instância do cluster de failover](../../sql-server/failover-clusters/windows/view-and-read-failover-cluster-instance-diagnostics-log.md).  
  
 ON  
 Inicia o log de dados de diagnóstico do [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] no local especificado na opção de arquivo PATH. Esse é o padrão.  
  
 OFF  
 Interrompe o log de dados diagnóstico.  
  
 PATH = { 'os_file_path' | DEFAULT }  
 Caminho que indica o local dos logs de diagnóstico. O local padrão é \<\mssql\log. > dentro da pasta de instalação da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instância de cluster de failover.  
  
 MAX_SIZE = { 'log_max_size' MB | DEFAULT }  
 Tamanho máximo em megabytes que o log de diagnóstico pode atingir. O padrão é 100 MB.  
  
 MAX_FILES = { 'max_file_count' | DEFAULT }  
 Número máximo de arquivos de log de diagnóstico que podem ser armazenados no computador antes de serem reciclados para novos logs de diagnóstico.  
  
 **\<failover_cluster_property >:: =**  
  
**Aplica-se a**: do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 FAILOVER CLUSTER PROPERTY  
 Modifica as propriedades do cluster de failover privado de recursos do SQL Server.  
  
 VERBOSE LOGGING = { 'logging_detail' | DEFAULT }  
 Define o nível do log do clustering de failover do SQL Server. Pode ser ativado para fornecer detalhes adicionais nos logs de erros para solução de problemas.  
  
-   0 – O log está desativado (padrão)  
  
-   1 – Apenas erros  
  
-   2 – Erros e avisos  
  
SQLDUMPEREDUMPFLAGS  
 Determina o tipo de arquivos de despejo gerados pelo utilitário SQLDumper do SQL Server. A configuração padrão é 0. Para obter mais informações, consulte [artigo de Conhecimento de utilitário do SQL Server Dumper](http://go.microsoft.com/fwlink/?LinkId=206173).  
  
 SQLDUMPERDUMPPATH = { 'os_file_path' | DEFAULT }  
 O local onde o utilitário SQLDumper armazena os arquivos de despejo. Para obter mais informações, consulte [artigo de Conhecimento de utilitário do SQL Server Dumper](http://go.microsoft.com/fwlink/?LinkId=206173).  
  
 SQLDUMPERDUMPTIMEOUT = { 'dump_time-out' | DEFAULT }  
 O valor do tempo limite em milissegundos para o utilitário SQLDumper gerar um despejo no caso de uma falha do SQL Server. O valor padrão é 0, o que indica que não há nenhum tempo limite para a conclusão do despejo. Para obter mais informações, consulte [artigo de Conhecimento de utilitário do SQL Server Dumper](http://go.microsoft.com/fwlink/?LinkId=206173).  
  
 FAILURECONDITIONLEVEL = { 'failure_condition_level' | DEFAULT }  
 As condições sob as quais a instância do cluster de failover do SQL Server deve apresentar uma falha ou reiniciar. O valor padrão é 3, o que indica que o recurso do SQL Server apresentará failover ou reiniciará em erros críticos do servidor. Para obter mais informações sobre este e outros níveis de condição de falha, consulte [Configure FailureConditionLevel Property Settings](../../sql-server/failover-clusters/windows/configure-failureconditionlevel-property-settings.md).  
  
 HEALTHCHECKTIMEOUT = { 'health_check_time-out' | DEFAULT }  
 O valor do tempo limite de quanto tempo a DLL de recursos do Mecanismo de Banco de Dados do SQL Server deve aguardar por informações de integridade do servidor antes de considerar a instância do SQL Server como sem resposta. O valor de tempo limite é expresso em milissegundos. O padrão é 60000 milissegundos (60 segundos).  
  
 **\<hadr_cluster_context >:: =**  
  
**Aplica-se a**: do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 CONTEXTO do CLUSTER HADR  **=**  { **'***remote_windows_cluster***'** | LOCAL}  
 Alterna o contexto do cluster HADR da instância de servidor para o cluster especificado do Windows Server Failover Clustering (WSFC). O *contexto do cluster HADR* determina qual cluster do Windows Server Failover Clustering (WSFC) gerencia os metadados de réplicas de disponibilidade hospedadas pela instância do servidor. Use a opção SET HADR CLUSTER CONTEXT somente durante uma migração entre clusters de [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] para uma instância do [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)] ou versão posterior em um novo cluster WSFC.  
  
 Só é possível alternar o contexto do cluster HADR do cluster WSFC local para um cluster remoto e, depois, do cluster remoto para o cluster local. O contexto do cluster HADR pode ser alternado para um cluster remoto somente quando a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não está hospedando réplicas de disponibilidade.  
  
 Um contexto do cluster HADR remoto pode ser alternado novamente para o cluster local a qualquer momento. Entretanto, o contexto não poderá ser alternado novamente enquanto a instância de servidor estiver hospedando réplicas de disponibilidade.  
  
 Para identificar o cluster de destino, especifique um dos seguintes valores:  
  
 *cluster_windows*  
 O CON (nome do objeto de cluster) de um cluster WSFC. Você pode especificar o nome curto ou o nome de domínio completo. Para localizar o endereço IP de destino de um nome curto, ALTER SERVER CONFIGURATION usa a resolução DNS. Em algumas situações, um nome curto pode causar confusão, e DNS pode retornar o endereço IP errado. Portanto, é recomendável especificar o nome de domínio completo.  
  
 LOCAL  
 O cluster WSFC local.  
  
 Para obter mais informações, consulte [alterar HADR Cluster contexto da instância do servidor &#40; SQL Server &#41; ](../../database-engine/availability-groups/windows/change-the-hadr-cluster-context-of-server-instance-sql-server.md).  
  
 **\<buffer_pool_extension >:: =**  
  
**Aplica-se a**: do [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 ON  
 Habilita a opção de extensão do pool de buffers. Essa opção estende o tamanho do pool de buffers usando o armazenamento não volátil como unidades de estado sólido (SSD) para manter páginas de dados de limpeza no pool. Para obter mais informações sobre esse recurso, consulte [extensão do Pool de buffers](../../database-engine/configure-windows/buffer-pool-extension.md). A extensão do pool de buffers não está disponível em todas as edições do SQL Server. Para obter mais informações, consulte [edições e os recursos com suporte para SQL Server 2016](../../sql-server/editions-and-supported-features-for-sql-server-2016.md).  
  
 FILENAME = 'os_file_path_and_name'  
 Define o caminho do diretório e o nome de arquivo do cache de extensão do pool de buffers. A extensão do arquivo deve ser especificada como .BPE. Desative BUFFER POOL EXTENSION antes que você possa alterar FILENAME.  
  
 TAMANHO = *tamanho* [ **KB** | MB | GB]  
 Define o tamanho do cache. A especificação do tamanho padrão é KB. O tamanho mínimo é o tamanho da Memória Máxima do Servidor. O limite máximo é 32 vezes o tamanho de Memória Máxima do Servidor. Para obter mais informações sobre a memória máxima do servidor, consulte [sp_configure &#40; Transact-SQL &#41; ](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md).  
  
 Desative BUFFER POOL EXTENSION antes que você possa alterar o tamanho do arquivo. Para especificar um tamanho que seja menor do que o tamanho atual, a instância do SQL Server deve ser reiniciada para recuperar a memória. Caso contrário, o tamanho especificado deve ser igual a ou maior que o tamanho atual.  
  
 OFF  
 Desabilita a opção de extensão do pool de buffers. Você deve desabilitar a opção de extensão do pool de buffers antes de modificar quaisquer parâmetros associados, como o tamanho ou o nome do arquivo. Quando esta opção estiver desabilitada, todas as informações de configuração relacionadas serão removidas do Registro.  
  
> [!WARNING]  
>  A desabilitação da extensão do pool de buffers pode ter um impacto negativo no desempenho do servidor porque o tamanho do pool de buffers é significativamente reduzido.  
  
 **\<soft_numa >**  

**Aplica-se a**: do [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 ON  
 Permite o particionamento automático dividir nós de hardware NUMA grandes em nós NUMA menores. Alterar o valor de execução requer a reinicialização do mecanismo de banco de dados.  
  
 OFF  
 Desabilita automáticas de software de particionamento de nós de hardware NUMA grandes em nós NUMA menores. Alterar o valor de execução requer a reinicialização do mecanismo de banco de dados.  

> [!WARNING]  
> Há problemas conhecidos com o comportamento da instrução ALTER SERVER CONFIGURATION com a opção de NUMA temporário e o SQL Server Agent.  Esta é a sequência recomendada de operações:  
> 1) Pare a instância do SQL Server Agent.  
> 2) Execute sua opção de ALTER SERVER configuração flexível NUMA.  
> 3) Reinicie a instância do SQL Server.  
> 4) Inicie a instância do SQL Server Agent.  
  
**Mais informações:** se uma configuração de servidor ALTER com o comando SET SOFTNUMA é executada antes que o serviço SQL Server for reiniciado, em seguida, quando o serviço SQL Server Agent for interrompido, ele será executado um comando RECONFIGURE de T-SQL que será revertido a Configurações de SOFTNUMA voltar ao que eram antes da configuração de servidor ALTER. 
  
## <a name="general-remarks"></a>Comentários gerais  
 Esta instrução não requer uma reinicialização do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a menos que explicitamente indicado em contrário. No caso de uma instância de cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], uma reinicialização do recurso de cluster do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não é necessária.  
  
## <a name="limitations-and-restrictions"></a>Limitações e restrições  
 Essa instrução não oferece suporte a gatilhos DDL.  
  
## <a name="permissions"></a>Permissões  
 Requer as permissões ALTER SETTINGS para a opção de afinidade de processo. As permissões ALTER SETTINGS e VIEW SERVER STATE para o log diagnóstico e opções de propriedades do cluster de failover, além da permissão CONTROL SERVER para a opção de contexto do cluster HADR.  
  
 Requer a permissão ALTER SERVER STATE para a opção de extensão do pool de buffers.  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] recurso DLL é executado sob a conta Sistema Local. Portanto, a conta Sistema Local deve ter acesso de leitura e gravação ao caminho especificado na opção Log de Diagnóstico.  
  
## <a name="examples"></a>Exemplos  
  
|Categoria|Elementos de sintaxe em destaque|  
|--------------|------------------------------|  
|[Configurando a afinidade do processo](#Affinity)|CPU • NUMANODE • AUTO|  
|[Definindo opções de log de diagnóstico](#Diagnostic)|ON • OFF • PATH • MAX_SIZE|  
|[Definindo propriedades de cluster de failover](#Failover)|HealthCheckTimeout|  
|[Alterar o contexto do cluster de uma réplica de disponibilidade](#ChangeClusterContextExample)|**'** *cluster_windows* **'**|  
|[Definir a extensão do pool de buffers](#BufferPoolExtension)|BUFFER POOL EXTENSION|  
  
###  <a name="Affinity"></a>Configurando a afinidade do processo  
 Os exemplos desta seção mostram como definir a afinidade do processo para CPUs e nós NUMA. Os exemplos presumem que o servidor contém 256 CPUs que são organizadas em quatro grupos de 16 nós NUMA cada um. Não são atribuídos threads a nenhum nó NUMA ou CPU.  
  
-   Grupo 0: nós NUMA 0 a 3, CPUs 0 a 63  
-   Grupo 1: nós NUMA 4 a 7, CPUs 64 a 127  
-   Grupo 2: nós NUMA 8 a 12, CPUs 128 a 191  
-   Grupo 3: nós NUMA 13 a 16, CPUs 192 a 255  
  
#### <a name="a-setting-affinity-to-all-cpus-in-groups-0-and-2"></a>A. Configurando a afinidade para todas as CPUs nos grupos 0 e 2  
 O exemplo a seguir define afinidade para todas as CPUs nos grupos 0 e 2.  
  
```  
ALTER SERVER CONFIGURATION   
SET PROCESS AFFINITY CPU=0 TO 63, 128 TO 191;  
```  
  
#### <a name="b-setting-affinity-to-all-cpus-in-numa-nodes-0-and-7"></a>B. Configurando a afinidade para todas as CPUs nos nós NUMA 0 e 7  
 O exemplo a seguir define a afinidade de CPU para nós `0` e `7`.  
  
```  
ALTER SERVER CONFIGURATION   
SET PROCESS AFFINITY NUMANODE=0, 7;  
```  
  
#### <a name="c-setting-affinity-to-cpus-60-through-200"></a>C. Definindo a afinidade para as CPUs 60 a 200  
 O exemplo a seguir define a afinidade para as CPUs 60 a 200.  
  
```  
ALTER SERVER CONFIGURATION   
SET PROCESS AFFINITY CPU=60 TO 200;  
```  
  
#### <a name="d-setting-affinity-to-cpu-0-on-a-system-that-has-two-cpus"></a>D. Definindo a afinidade para a CPU 0 em um sistema que tem duas CPUs  
 O exemplo a seguir define a afinidade para `CPU=0` em um computador que tem duas CPUs. Antes de a instrução seguinte ser executada, a máscara de bits de afinidade interna é 00.  
  
```  
ALTER SERVER CONFIGURATION SET PROCESS AFFINITY CPU=0;  
```  
  
#### <a name="e-setting-affinity-to-auto"></a>E. Definindo a afinidade como AUTO  
 O exemplo a seguir define a afinidade como `AUTO`.  
  
```  
ALTER SERVER CONFIGURATION  
SET PROCESS AFFINITY CPU=AUTO;  
```  
  
###  <a name="Diagnostic"></a> Setting diagnostic log options  
  
**Aplica-se a**: do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Os exemplos desta seção mostram como definir os valores para a opção de log de diagnóstico.  
  
#### <a name="a-starting-diagnostic-logging"></a>A. Iniciando o log de diagnóstico  
 O exemplo a seguir inicia o log de dados de diagnóstico.  
  
```  
ALTER SERVER CONFIGURATION SET DIAGNOSTICS LOG ON;  
```  
  
#### <a name="b-stopping-diagnostic-logging"></a>B. Interrompendo o log de diagnóstico  
 O exemplo a seguir interrompe o log de dados de diagnóstico.  
  
```  
ALTER SERVER CONFIGURATION SET DIAGNOSTICS LOG OFF;  
```  
  
#### <a name="c-specifying-the-location-of-the-diagnostic-logs"></a>C. Especificando o local dos logs de diagnóstico  
 O exemplo a seguir define o local dos logs de diagnóstico como o caminho do arquivo especificado.  
  
```  
ALTER SERVER CONFIGURATION  
SET DIAGNOSTICS LOG PATH = 'C:\logs';  
```  
  
#### <a name="d-specifying-the-maximum-size-of-each-diagnostic-log"></a>D. Especificando o tamanho máximo de cada log de diagnóstico  
 O exemplo a seguir define o tamanho máximo de cada log de diagnóstico como 10 megabytes.  
  
```  
ALTER SERVER CONFIGURATION   
SET DIAGNOSTICS LOG MAX_SIZE = 10 MB;  
```  
  
###  <a name="Failover"></a>Definindo propriedades de cluster de failover  
  
**Aplica-se a**: do [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 O exemplo a seguir ilustra a configuração dos valores das propriedades do recurso de cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
#### <a name="a-specifying-the-value-for-the-healthchecktimeout-property"></a>A. Especificando o valor da propriedade HealthCheckTimeout  
 O exemplo a seguir define a opção `HealthCheckTimeout` como 15.000 milissegundos (15 segundos).  
  
```  
ALTER SERVER CONFIGURATION   
SET FAILOVER CLUSTER PROPERTY HealthCheckTimeout = 15000;  
```  
  
###  <a name="ChangeClusterContextExample"></a> B. Como alterar o contexto do cluster de uma réplica de disponibilidade  
 O exemplo a seguir altera o contexto do cluster HADR da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Para especificar o cluster WSFC de destino, `clus01`, o exemplo especifica o nome de objeto completo do cluster, `clus01.xyz.com`.  
  
```  
ALTER SERVER CONFIGURATION SET HADR CLUSTER CONTEXT = 'clus01.xyz.com';  
```  
  
### <a name="setting-buffer-pool-extension-options"></a>Definindo opções de extensão do pool de buffers  
  
####  <a name="BufferPoolExtension"></a> A. Definindo a opção de extensão do pool de buffers  
  
**Aplica-se a**: do [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 O exemplo a seguir habilita a opção de extensão do pool de buffers, e especifica um nome e um tamanho de arquivo.  
  
```  
ALTER SERVER CONFIGURATION   
SET BUFFER POOL EXTENSION ON  
    (FILENAME = 'F:\SSDCACHE\Example.BPE', SIZE = 50 GB);  
```  
  
#### <a name="b-modifying-buffer-pool-extension-parameters"></a>B. Modificando parâmetros da extensão do pool de buffers  
 O exemplo a seguir modifica o tamanho de um arquivo de extensão do pool de buffers. A opção de extensão do pool de buffers deve ser desabilitada antes que qualquer parâmetro seja modificado.  
  
```  
ALTER SERVER CONFIGURATION   
SET BUFFER POOL EXTENSION OFF;  
GO  
EXEC sp_configure 'max server memory (MB)', 12000;  
GO  
RECONFIGURE;  
GO  
ALTER SERVER CONFIGURATION  
SET BUFFER POOL EXTENSION ON  
    (FILENAME = 'F:\SSDCACHE\Example.BPE', SIZE = 60 GB);  
GO  
  
```  
  
## <a name="see-also"></a>Consulte também  
 [Soft-NUMA &#40; SQL Server &#41;](../../database-engine/configure-windows/soft-numa-sql-server.md)   
 [Alterar o contexto do Cluster HADR da instância do servidor &#40; SQL Server &#41;](../../database-engine/availability-groups/windows/change-the-hadr-cluster-context-of-server-instance-sql-server.md)   
 [sys.DM os_schedulers &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-schedulers-transact-sql.md)   
 [sys.DM os_memory_nodes &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-memory-nodes-transact-sql.md)   
 [sys.DM os_buffer_pool_extension_configuration &#40; Transact-SQL &#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-buffer-pool-extension-configuration-transact-sql.md)   
 [Extensão do pool de buffers](../../database-engine/configure-windows/buffer-pool-extension.md)  
  
  
