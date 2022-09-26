---
title: AzureMysqlDeployment@1 - Azure Database for MySQL deployment v1 task
description: Run your scripts and make changes to your Azure Database for MySQL.
ms.date: 09/26/2022
monikerRange: ">=azure-pipelines-2019"
---

# AzureMysqlDeployment@1 - Azure Database for MySQL deployment v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Run your scripts and make changes to your Azure Database for MySQL.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Azure Database for MySQL deployment v1
# Run your scripts and make changes to your Azure Database for MySQL.
- task: AzureMysqlDeployment@1
  inputs:
    azureSubscription: # string. Required. Azure Subscription. 
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

:::moniker range="=azure-pipelines-2019"

```yaml
# Azure Database for MySQL Deployment v1
# Run your scripts and make changes to your Azure Database for MySQL.
- task: AzureMysqlDeployment@1
  inputs:
    azureSubscription: # string. Required. Azure Subscription. 
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
:::moniker range=">=azure-pipelines-2019"

**`azureSubscription`** - **Azure Subscription**<br>
Input alias: `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This is needed to connect to your Azure account.<br>To configure new service connection, select the Azure subscription from the list and click 'Authorize'.<br>If your subscription is not listed or if you want to use an existing Service Principal, you can setup an Azure service connection using 'Add' or 'Manage' button.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServerName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ServerName`** - **Host Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Server name of 'Azure Database for MySQL'.Example: fabrikam.mysql.database.azure.com. When you connect using MySQL Workbench, this is the same value that is used for 'Hostname' in 'Parameters'.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DatabaseName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`DatabaseName`** - **Database Name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of database, if you already have one, on which the below script is needed to be run, else the script itself can be used to create the database.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlUsername"::: -->
:::moniker range=">=azure-pipelines-2019"

**`SqlUsername`** - **Server Admin Login**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Database for MySQL server supports native MySQL authentication. You can connect and authenticate to a server with the server's admin login. Example:  bbo1@fabrikam. When you connect using MySQL Workbench, this is the same value that is used for 'Username' in 'Parameters'.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlPassword"::: -->
:::moniker range=">=azure-pipelines-2019"

**`SqlPassword`** - **Password**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator password for Azure Database for MySQL. In case you don’t recall the password you can change the password from [Azure portal](/azure/mysql/howto-create-manage-server-portal).<br>It can be variable defined in the pipeline. Example : $(password).<br>Also, you may mark the variable type as 'secret' to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TaskNameSelector"::: -->
:::moniker range=">=azure-pipelines-2019"

**`TaskNameSelector`** - **Type**<br>
`string`. Allowed values: `SqlTaskFile` (MySQL Script File), `InlineSqlTask` (Inline MySQL Script). Default value: `SqlTaskFile`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select one of the options between Script File & Inline Script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`SqlFile`** - **MySQL Script**<br>
`string`. Required when `TaskNameSelector = SqlTaskFile`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Full path of the script file on the automation agent or on a UNC path accessible to the automation agent like,  \\\\BudgetIT\DeployBuilds\script.sql. Also, predefined system variables like, $(agent.releaseDirectory) can also be used here. A file containing SQL statements can be used here.​.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlInline"::: -->
:::moniker range=">=azure-pipelines-2019"

**`SqlInline`** - **Inline MySQL Script**<br>
`string`. Required when `TaskNameSelector = InlineSqlTask`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the MySQL script to execute on the Database selected above.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlAdditionalArguments"::: -->
:::moniker range=">=azure-pipelines-2019"

**`SqlAdditionalArguments`** - **Additional MySQL Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional options supported by MySQL simple SQL shell.  These options will be applied when executing the given file on the Azure Database for MySQL.​<br>Example: You can change to default tab separated output format to HTML or even XML format. Or if you have problems due to insufficient memory for large result sets, use the --quick option.​.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="IpDetectionMethod"::: -->
:::moniker range=">=azure-pipelines-2019"

**`IpDetectionMethod`** - **Specify Firewall Rules Using**<br>
`string`. Required. Allowed values: `AutoDetect`, `IPAddressRange`. Default value: `AutoDetect`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
For successful execution of the task, we need to enable administrators to access the Azure Database for MySQL Server from the IP Address of the automation agent.<br>By selecting auto-detect you can automatically add firewall exception for range of possible IP Address of automation agent ​or else you can specify the range explicitly.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="StartIpAddress"::: -->
:::moniker range=">=azure-pipelines-2019"

**`StartIpAddress`** - **Start IP Address**<br>
`string`. Required when `IpDetectionMethod = IPAddressRange`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The starting IP Address of the automation agent machine pool like 196.21.30.50 .
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="EndIpAddress"::: -->
:::moniker range=">=azure-pipelines-2019"

**`EndIpAddress`** - **End IP Address**<br>
`string`. Required when `IpDetectionMethod = IPAddressRange`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The ending IP Address of the automation agent machine pool like 196.21.30.65 .
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeleteFirewallRule"::: -->
:::moniker range=">=azure-pipelines-2019"

**`DeleteFirewallRule`** - **Delete Rule After Task Ends**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If selected, the added exception for IP addresses of the automation agent will be removed for corresponding Azure Database for MySQL.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019"

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

:::moniker range=">=azure-pipelines-2019"

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