---
title: SqlServerDacpacDeployment@1 - SQL Server database deploy (Deprecated) v1 task
description: Deploy a SQL Server database using DACPAC.
ms.date: 03/21/2024
monikerRange: "<=azure-pipelines"
---

# SqlServerDacpacDeployment@1 - SQL Server database deploy (Deprecated) v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to deploy a SQL Server database using DACPAC.

> [!IMPORTANT]
> [!INCLUDE [task-deprecation](includes/task-deprecation.md)] Use [IIS Web App Deployment Using WinRM - Viual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscs-rm.iiswebapp).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.1"

<!-- :::editable-content name="description"::: -->
Use this task to deploy a SQL Server database using DACPAC.

This task is deprecated.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

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
    TargetMethod: 'server' # 'server' | 'connectionString' | 'publishProfile'. Required. Specify SQL Using. Default: server.
    ServerName: 'localhost' # string. Required when TargetMethod = server. Server Name. Default: localhost.
    DatabaseName: # string. Required when TargetMethod = server. Database Name. 
    #SqlUsername: # string. Optional. Use when TargetMethod = server. SQL Username. 
    #SqlPassword: # string. Optional. Use when TargetMethod = server. SQL Password. 
    #ConnectionString: # string. Required when TargetMethod = connectionString. Connection String. 
    #PublishProfile: # string. Publish Profile. 
    #AdditionalArguments: # string. Additional Arguments. 
  # Advanced
    #DeployInParallel: true # boolean. Deploy in Parallel. Default: true.
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Select Machines By. Default: machineNames.
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
    TargetMethod: 'server' # 'server' | 'connectionString' | 'publishProfile'. Required. Specify SQL Using. Default: server.
    ServerName: 'localhost' # string. Required when TargetMethod = server. Server Name. Default: localhost.
    DatabaseName: # string. Required when TargetMethod = server. Database Name. 
    #SqlUsername: # string. Optional. Use when TargetMethod = server. SQL Username. 
    #SqlPassword: # string. Optional. Use when TargetMethod = server. SQL Password. 
    #ConnectionString: # string. Required when TargetMethod = connectionString. Connection String. 
    #PublishProfile: # string. Publish Profile. 
    #AdditionalArguments: # string. Additional Arguments. 
  # Advanced
    #DeployInParallel: true # boolean. Deploy in Parallel. Default: true.
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Select Machines By. Default: machineNames.
    #MachineFilter: # string. Deploy to Machines.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="EnvironmentName"::: -->
:::moniker range="<=azure-pipelines"

**`EnvironmentName`** - **Machines**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a comma-separated list of machine IP addresses or FQDNs along with ports. The default port is based on the selected protocol. For example: `dbserver.fabrikam.com,dbserver_int.fabrikam.com:5986,192.168.12.34:5986` Output variables of other tasks can also be provided, for example `$(variableName)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminUserName"::: -->
:::moniker range="<=azure-pipelines"

**`AdminUserName`** - **Admin Login**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the administrator login for the target machines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminPassword"::: -->
:::moniker range="<=azure-pipelines"

**`AdminPassword`** - **Password**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the administrator password for the target machines. Variables defined in build or release definitions are accepted as `$(passwordVariable)`. You can mark the variable type as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Protocol"::: -->
:::moniker range="<=azure-pipelines"

**`Protocol`** - **Protocol**<br>
`string`. Allowed values: `Http`, `Https`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the protocol to use for the WinRM connection with the machine(s). The default value is `HTTPS`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TestCertificate"::: -->
:::moniker range="<=azure-pipelines"

**`TestCertificate`** - **Test Certificate**<br>
`boolean`. Optional. Use when `Protocol = Https`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Skips the authenticity validation of the machine's certificate by a trusted certification authority. The parameter is required for the WinRM HTTPS protocol.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DacpacFile"::: -->
:::moniker range="<=azure-pipelines"

**`DacpacFile`** - **DACPAC File**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the DACPAC file on the target machines or on a UNC path, like `\\BudgetIT\Web\Deploy\FabrikamDB.dacpac`. The UNC path should be accessible to the machine's administrator account. Environment variables are also supported, like `$env:windir`, `$env:systemroot`, and `$env:windir\FabrikamFibre\Web`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetMethod"::: -->
:::moniker range="<=azure-pipelines"

**`TargetMethod`** - **Specify SQL Using**<br>
`string`. Required. Allowed values: `server`, `connectionString` (Connection String), `publishProfile` (Publish Profile). Default value: `server`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to connect to the target SQL Server database. You can provide SQL Server database details, a SQL Server connection string, or a publish profile XML file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServerName"::: -->
:::moniker range="<=azure-pipelines"

**`ServerName`** - **Server Name**<br>
`string`. Required when `TargetMethod = server`. Default value: `localhost`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SQL Server name, like `machinename\FabriakmSQL,1433` or `localhost` or `.\SQL2012R2`. Specifying `localhost` connects to the default SQL Server instance on the machine.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DatabaseName"::: -->
:::moniker range="<=azure-pipelines"

**`DatabaseName`** - **Database Name**<br>
`string`. Required when `TargetMethod = server`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the SQL Server database.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlUsername"::: -->
:::moniker range="<=azure-pipelines"

**`SqlUsername`** - **SQL Username**<br>
`string`. Optional. Use when `TargetMethod = server`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the SQL Server login is specified, it is used to connect to the SQL Server. The default, Integrated Authentication, uses the machine administrator's credentials.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlPassword"::: -->
:::moniker range="<=azure-pipelines"

**`SqlPassword`** - **SQL Password**<br>
`string`. Optional. Use when `TargetMethod = server`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the SQL Server login user name is specified, provide the SQL Server password. The default, Integrated Authentication, uses the machine administrator's credentials.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectionString"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectionString`** - **Connection String**<br>
`string`. Required when `TargetMethod = connectionString`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SQL Server connection string, like `Server=localhost;Database=Fabrikam;User ID=AccountPlaceholder;Password=PasswordPlaceholder;`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PublishProfile"::: -->
:::moniker range="<=azure-pipelines"

**`PublishProfile`** - **Publish Profile**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides fine-grained control over SQL Server database creation or upgrades. Specifies the path to the publish profile XML file on the target machine or on a UNC share that is accessible by the machine administrator's credentials.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`AdditionalArguments`** - **Additional Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional `SqlPackage.exe` arguments that are applied when creating or updating the SQL Server database, like `/p:IgnoreAnsiNulls=True` or `/p:IgnoreComments=True`. These arguments will override the settings in the publish profile XML file (if provided).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeployInParallel"::: -->
:::moniker range="<=azure-pipelines"

**`DeployInParallel`** - **Deploy in Parallel**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When set to `true`, runs the database deployment task in parallel on the target machines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceFilteringMethod"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceFilteringMethod`** - **Select Machines By**<br>
`string`. Allowed values: `machineNames` (Machine Names), `tags`. Default value: `machineNames`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies a subset of machines by providing machine names or tags.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MachineFilter"::: -->
:::moniker range="<=azure-pipelines"

**`MachineFilter`** - **Deploy to Machines**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This input is only valid for machine groups and is not supported for a flat list of machines or output variables yet.  
Specifies a list of machines, like `dbserver.fabrikam.com, webserver.fabrikam.com, 192.168.12.34`, or tags, like `Role:DB; OS:Win8.1`. If multiple tags are provided, the task runs in all machines with the specified tags. For Azure Resource Groups, provide the virtual machine's name, like `ffweb` or `ffdb`. The default runs the task in all machines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
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