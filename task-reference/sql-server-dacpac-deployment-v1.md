---
title: SqlServerDacpacDeployment@1 - SQL Server database deploy (Deprecated) v1 task
description: Deploy a SQL Server database using DACPAC.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# SqlServerDacpacDeployment@1 - SQL Server database deploy (Deprecated) v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Deploy a SQL Server database using DACPAC.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Deploy SQL Server Database using DACPAC.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# SQL Server database deploy (Deprecated) v1
# Deploy a SQL Server database using DACPAC.
- task: SqlServerDacpacDeployment@1
  inputs:
    EnvironmentName: # string. Required. Machines. 
    #AdminUserName: # string. Admin Login. 
    #AdminPassword: # string. Password. 
    #Protocol: # 'Http' | 'Https'. Protocol. 
    #TestCertificate: true # boolean. Optional. Use when Protocol = Https. Test Certificate. Default: true.
  # Deployment
    DacpacFile: # string. Required. DACPAC File. 
  # Target
    TargetMethod: 'server' # 'server' | 'connectionString' | 'publishProfile'. Required. Specify SQL Using. Default: 'server'.
    ServerName: 'localhost' # string. Required when TargetMethod = server. Server Name. Default: 'localhost'.
    DatabaseName: # string. Required when TargetMethod = server. Database Name. 
    #SqlUsername: # string. Optional. Use when TargetMethod = server. SQL Username. 
    #SqlPassword: # string. Optional. Use when TargetMethod = server. SQL Password. 
    #ConnectionString: # string. Required when TargetMethod = connectionString. Connection String. 
    #PublishProfile: # string. Publish Profile. 
    #AdditionalArguments: # string. Additional Arguments. 
  # Advanced
    #DeployInParallel: true # boolean. Deploy in Parallel. Default: true.
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Select Machines By. Default: 'machineNames'.
    #MachineFilter: # string. Deploy to Machines.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# SQL Server database deploy (Deprecated) v1
# Deploy SQL Server Database using DACPAC.
- task: SqlServerDacpacDeployment@1
  inputs:
    EnvironmentName: # string. Required. Machines. 
    #AdminUserName: # string. Admin Login. 
    #AdminPassword: # string. Password. 
    #Protocol: # 'Http' | 'Https'. Protocol. 
    #TestCertificate: true # boolean. Optional. Use when Protocol = Https. Test Certificate. Default: true.
  # Deployment
    DacpacFile: # string. Required. DACPAC File. 
  # Target
    TargetMethod: 'server' # 'server' | 'connectionString' | 'publishProfile'. Required. Specify SQL Using. Default: 'server'.
    ServerName: 'localhost' # string. Required when TargetMethod = server. Server Name. Default: 'localhost'.
    DatabaseName: # string. Required when TargetMethod = server. Database Name. 
    #SqlUsername: # string. Optional. Use when TargetMethod = server. SQL Username. 
    #SqlPassword: # string. Optional. Use when TargetMethod = server. SQL Password. 
    #ConnectionString: # string. Required when TargetMethod = connectionString. Connection String. 
    #PublishProfile: # string. Publish Profile. 
    #AdditionalArguments: # string. Additional Arguments. 
  # Advanced
    #DeployInParallel: true # boolean. Deploy in Parallel. Default: true.
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Select Machines By. Default: 'machineNames'.
    #MachineFilter: # string. Deploy to Machines.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="EnvironmentName"::: -->
:::moniker range="<=azure-pipelines"

**`EnvironmentName`** - **Machines**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a comma separated list of machine IP addresses or FQDNs along with ports. Port is defaulted based on the selected protocol. <br>Eg: dbserver.fabrikam.com,dbserver_int.fabrikam.com:5986,192.168.12.34:5986 <br>Or provide output variable of other tasks. Eg: $(variableName).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminUserName"::: -->
:::moniker range="<=azure-pipelines"

**`AdminUserName`** - **Admin Login**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator login for the target machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminPassword"::: -->
:::moniker range="<=azure-pipelines"

**`AdminPassword`** - **Password**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator password for the target machines.<br>It can accept variable defined in Build/Release definitions as '$(passwordVariable)'. <br>You may mark variable type as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Protocol"::: -->
:::moniker range="<=azure-pipelines"

**`Protocol`** - **Protocol**<br>
Type: string. Allowed values: 'Http', 'Https'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the protocol to use for the WinRM connection with the machine(s). Default is HTTPS.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TestCertificate"::: -->
:::moniker range="<=azure-pipelines"

**`TestCertificate`** - **Test Certificate**<br>
Type: boolean. Optional. Use when Protocol = Https. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to skip validating the authenticity of the machine's certificate by a trusted certification authority. The parameter is required for the WinRM HTTPS protocol.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DacpacFile"::: -->
:::moniker range="<=azure-pipelines"

**`DacpacFile`** - **DACPAC File**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Location of the DACPAC file on the target machines or on a UNC path like, \\\\BudgetIT\Web\Deploy\FabrikamDB.dacpac. The UNC path should be accessible to the machine's administrator account. Environment variables are also supported like $env:windir, $env:systemroot, like, $env:windir\FabrikamFibre\Web.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetMethod"::: -->
:::moniker range="<=azure-pipelines"

**`TargetMethod`** - **Specify SQL Using**<br>
Type: string. Required. Allowed values: 'server', 'connectionString', 'publishProfile'. Default value: 'server'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to connect to the target SQL Server Database. The options are to provide SQL Server Database details, or a SQL Server connection string, or a Publish profile XML file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServerName"::: -->
:::moniker range="<=azure-pipelines"

**`ServerName`** - **Server Name**<br>
Type: string. Required when TargetMethod = server. Default value: 'localhost'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the SQL Server name like, machinename\FabriakmSQL,1433 or localhost or .\SQL2012R2. Specifying localhost will connect to the Default SQL Server instance on the machine.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DatabaseName"::: -->
:::moniker range="<=azure-pipelines"

**`DatabaseName`** - **Database Name**<br>
Type: string. Required when TargetMethod = server.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of the SQL Server database.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlUsername"::: -->
:::moniker range="<=azure-pipelines"

**`SqlUsername`** - **SQL Username**<br>
Type: string. Optional. Use when TargetMethod = server.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the SQL Server login is specified, it will be used to connect to the SQL Server. The default is Integrated Authentication and uses the machine administrator's credentials.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlPassword"::: -->
:::moniker range="<=azure-pipelines"

**`SqlPassword`** - **SQL Password**<br>
Type: string. Optional. Use when TargetMethod = server.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If SQL Server login user name is specified, then provide the SQL Server password. The default is Integrated Authentication and uses the machine administrator's credentials.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectionString"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectionString`** - **Connection String**<br>
Type: string. Required when TargetMethod = connectionString.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the SQL Server connection string like "Server=localhost;Database=Fabrikam;User ID=AccountPlaceholder;Password=PasswordPlaceholder;".
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PublishProfile"::: -->
:::moniker range="<=azure-pipelines"

**`PublishProfile`** - **Publish Profile**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Publish profile provide fine-grained control over SQL Server database creation or upgrades. Specify the path to the Publish profile XML file on the target machine or on a UNC share that is accessible by the machine administrator's credentials.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`AdditionalArguments`** - **Additional Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional SqlPackage.exe arguments that will be applied when creating or updating the SQL Server database like, /p:IgnoreAnsiNulls=True /p:IgnoreComments=True. These arguments will override the settings in the Publish profile XML file (if provided).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeployInParallel"::: -->
:::moniker range="<=azure-pipelines"

**`DeployInParallel`** - **Deploy in Parallel**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Setting it to true will run the database deployment task in-parallel on the target machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceFilteringMethod"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceFilteringMethod`** - **Select Machines By**<br>
Type: string. Allowed values: 'machineNames', 'tags'. Default value: 'machineNames'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally, select a subset of machines either by providing machine names or tags.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MachineFilter"::: -->
:::moniker range="<=azure-pipelines"

**`MachineFilter`** - **Deploy to Machines**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This input is valid only for machine groups and is not supported for flat list of machines or output variables yet. Provide a list of machines like, dbserver.fabrikam.com, webserver.fabrikam.com, 192.168.12.34, or tags like, Role:DB; OS:Win8.1. If multiple tags are provided, then the task will run in all the machines with the specified tags. For Azure Resource Groups, provide the virtual machine's name like, ffweb, ffdb. The default is to run the task in all machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.96.2 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->