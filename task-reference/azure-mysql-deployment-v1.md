---
title: AzureMysqlDeployment@1 - Azure Database for MySQL deployment v1 task
description: Run your scripts and make changes to your Azure Database for MySQL.
ms.date: 12/18/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022"
---

# AzureMysqlDeployment@1 - Azure Database for MySQL deployment v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to run your scripts and make changes to your database in Azure Database for MySQL. The Azure Database for MySQL Deployment task only works with [Azure Database for MySQL Single Server](/azure/mysql/single-server-overview).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Azure Database for MySQL deployment v1
# Run your scripts and make changes to your Azure Database for MySQL.
- task: AzureMysqlDeployment@1
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure Subscription. 
  # DB Details
    ServerName: # string. Required. Host Name. 
    #DatabaseName: # string. Database Name. 
    SqlUsername: # string. Required. Server Admin Login. 
    SqlPassword: # string. Required. Password. 
  # Deployment Package
    #TaskNameSelector: 'SqlTaskFile' # 'SqlTaskFile' | 'InlineSqlTask'. Type. Default: SqlTaskFile.
    SqlFile: # string. Required when TaskNameSelector = SqlTaskFile. MySQL Script. 
    #SqlInline: # string. Required when TaskNameSelector = InlineSqlTask. Inline MySQL Script. 
    #SqlAdditionalArguments: # string. Additional MySQL Arguments. 
  # Firewall
    IpDetectionMethod: 'AutoDetect' # 'AutoDetect' | 'IPAddressRange'. Required. Specify Firewall Rules Using. Default: AutoDetect.
    #StartIpAddress: # string. Required when IpDetectionMethod = IPAddressRange. Start IP Address. 
    #EndIpAddress: # string. Required when IpDetectionMethod = IPAddressRange. End IP Address. 
    #DeleteFirewallRule: true # boolean. Delete Rule After Task Ends. Default: true.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure Subscription**<br>
[Input alias](index.md#what-are-task-input-aliases): `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This is needed to connect to your Azure account.

To configure a new service connection, select the Azure subscription from the list and click `Authorize`.

If your subscription is not listed or if you want to use an existing Service Principal, you can setup an Azure service connection using the `Add` or `Manage` buttons.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServerName"::: -->
:::moniker range="<=azure-pipelines"

**`ServerName`** - **Host Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of your Azure Database for MySQL server.

Example: `fabrikam.mysql.database.azure.com`

The server name is provided in the Azure portal on the 'Overview' blade of your Azure Database for MySQL server resource.

When you connect using MySQL Workbench, this is the same value that is used for `Hostname` in `Parameters`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DatabaseName"::: -->
:::moniker range="<=azure-pipelines"

**`DatabaseName`** - **Database Name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. The name of the database. The script will create a database name if one does not exist.  

If not specified, ensure that the database is referenced in the supplied SQL file or inline SQL, where needed.

Note: MySQL database names are case-sensitive.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlUsername"::: -->
:::moniker range="<=azure-pipelines"

**`SqlUsername`** - **Server Admin Login**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Azure Database for MySQL server supports native MySQL authentication. You can connect and authenticate to a server with the server's admin login. Example: `bbo1@fabrikam`.

When you connect using MySQL Workbench, this is the same value that is used for `Username` in `Parameters`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlPassword"::: -->
:::moniker range="<=azure-pipelines"

**`SqlPassword`** - **Password**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The administrator password for Azure Database for MySQL. In case you don’t recall the password, you can change the password from [Azure portal](/azure/mysql/howto-create-manage-server-portal).

This string can be defined with a variable in the pipeline. Example: `$(password)`.

Also, you may mark the variable type as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TaskNameSelector"::: -->
:::moniker range="<=azure-pipelines"

**`TaskNameSelector`** - **Type**<br>
`string`. Allowed values: `SqlTaskFile` (MySQL Script File), `InlineSqlTask` (Inline MySQL Script). Default value: `SqlTaskFile`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Selects one of the options between Script File & Inline Script.

- `SqlTaskFile` (default), for use with the `SqlFile` argument
- `InlineSqlTask`, for use with the `SqlInline` argument.

**Note**: these values are case-sensitive.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlFile"::: -->
:::moniker range="<=azure-pipelines"

**`SqlFile`** - **MySQL Script**<br>
`string`. Required when `TaskNameSelector = SqlTaskFile`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The full path of the script file on the automation agent or on a UNC path accessible to the automation agent. For example: `\BudgetIT\DeployBuilds\script.sql`.

Predefined system variables, such as `$(agent.releaseDirectory)`, and files containing SQL statements can be used here.​

Note: The MySQL client prefers Unix style paths, so from version 1.183.0 on, the task will convert Windows style paths to Unix style paths.
Example: from `c:\foo\bar\myscript.sql` to `c:/foo/bar/myscript.sql`.

When the task is used on Linux platforms, paths remain unchanged. There is no need to escape special characters in paths.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlInline"::: -->
:::moniker range="<=azure-pipelines"

**`SqlInline`** - **Inline MySQL Script**<br>
`string`. Required when `TaskNameSelector = InlineSqlTask`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters the MySQL script to execute on the database selected above.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlAdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`SqlAdditionalArguments`** - **Additional MySQL Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. The additional options supported by the MySQL client. These options are applied when executing the given file on the Azure Database for MySQL.​

Example: You can change to the default tab separated output format, to HTML, or even to the XML format. Other examples include:

- `--comments` to strip comments sent from the client to the server.
- `--quick` to prevent result caching.
- `--xml` to output results as XML.

All available options are described in the MySQL client documentation.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="IpDetectionMethod"::: -->
:::moniker range="<=azure-pipelines"

**`IpDetectionMethod`** - **Specify Firewall Rules Using**<br>
`string`. Required. Allowed values: `AutoDetect`, `IPAddressRange`. Default value: `AutoDetect`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
For the successful execution of the task, we need to enable administrators to access the Azure Database for MySQL Server from the IP Address of the automation agent.

By selecting auto-detect, you can automatically add a firewall exception for the range of possible IP addresses of automation agents, ​or you can explicitly specify the range.

Accepted values:

- `AutoDetect` to auto-detect the automation agent's public IP address.
- `IPAddressRange` to explicitly specify the IP address range to configure. Set the IP address range using the `StartIpAddress` and `EndIpAddress` parameters.

**Note**: These values are case-sensitive.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="StartIpAddress"::: -->
:::moniker range="<=azure-pipelines"

**`StartIpAddress`** - **Start IP Address**<br>
`string`. Required when `IpDetectionMethod = IPAddressRange`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The starting IP Address of the automation agent machine pool. For example: `196.21.30.50`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="EndIpAddress"::: -->
:::moniker range="<=azure-pipelines"

**`EndIpAddress`** - **End IP Address**<br>
`string`. Required when `IpDetectionMethod = IPAddressRange`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The ending IP Address of the automation agent machine pool. For example: `196.21.30.65`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeleteFirewallRule"::: -->
:::moniker range="<=azure-pipelines"

**`DeleteFirewallRule`** - **Delete Rule After Task Ends**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. If selected, the added exception for the IP addresses of the automation agent will be removed for the corresponding Azure Database for MySQL.
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
## Remarks

Use this task to run your scripts and make changes to your database in Azure Database for MySQL. Note that this is a preview version. The Azure Database for MySQL Deployment task only works with [Azure Database for MySQL Single Server](/azure/mysql/single-server-overview).
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
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.100.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->