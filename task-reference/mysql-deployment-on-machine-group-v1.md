---
title: MysqlDeploymentOnMachineGroup@1 - MySQL database deploy v1 task
description: Run scripts and make changes to a MySQL Database.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# MysqlDeploymentOnMachineGroup@1 - MySQL database deploy v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Run scripts and make changes to a MySQL Database.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# MySQL database deploy v1
# Run scripts and make changes to a MySQL Database.
- task: MysqlDeploymentOnMachineGroup@1
  inputs:
    #TaskNameSelector: 'SqlTaskFile' # 'SqlTaskFile' | 'InlineSqlTask'. Deploy MySql Using. Default: 'SqlTaskFile'.
    SqlFile: # string. Required when TaskNameSelector = SqlTaskFile. MySQL Script. 
    #SqlInline: # string. Required when TaskNameSelector = InlineSqlTask. Inline MySQL Script. 
    ServerName: 'localhost' # string. Required. Host Name. Default: 'localhost'.
    #DatabaseName: # string. Database Name. 
    SqlUsername: # string. Required. Mysql User Name. 
    SqlPassword: # string. Required. Password. 
    #SqlAdditionalArguments: # string. Additional Arguments.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="TaskNameSelector"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`TaskNameSelector`** - **Deploy MySql Using**<br>
Type: string. Allowed values: 'SqlTaskFile', 'InlineSqlTask'. Default value: 'SqlTaskFile'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select one of the options between Script File & Inline Script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlFile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`SqlFile`** - **MySQL Script**<br>
Type: string. Required when TaskNameSelector = SqlTaskFile.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Full path of the script file on the automation agent or on a UNC path accessible to the automation agent like,  \\\\BudgetIT\DeployBuilds\script.sql. Also, predefined system variables like, $(agent.releaseDirectory) can also be used here. A file containing SQL statements can be used here.​.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlInline"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`SqlInline`** - **Inline MySQL Script**<br>
Type: string. Required when TaskNameSelector = InlineSqlTask.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the MySQL script to execute on the Database selected above.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServerName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ServerName`** - **Host Name**<br>
Type: string. Required. Default value: 'localhost'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Server name of 'Database for MySQL'.Example: localhost. When you connect using MySQL Workbench, this is the same value that is used for 'Hostname' in 'Parameters'.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DatabaseName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`DatabaseName`** - **Database Name**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of database, if you already have one, on which the below script is needed to be run, else the script itself can be used to create the database.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlUsername"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`SqlUsername`** - **Mysql User Name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When you connect using MySQL Workbench, this is the same value that is used for 'Username' in 'Parameters'.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlPassword"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`SqlPassword`** - **Password**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password for MySQL Database.<br>It can be variable defined in the pipeline. Example : $(password).<br>Also, you may mark the variable type as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlAdditionalArguments"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`SqlAdditionalArguments`** - **Additional Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional options supported by MySQL simple SQL shell.  These options will be applied when executing the given file on the Database for MySQL.​<br>Example: You can change to default tab separated output format to HTML or even XML format. Or if you have problems due to insufficient memory for large result sets, use the --quick option.​.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019.1"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to run your scripts and make changes to your MySQL Database. There are two ways to deploy, either using a script file or writing the script in our inline editor. Note that this is an early preview version. Since this task is server based, it appears on Deployment group jobs.

### Prerequisites

- MySQL Client in agent box

The task expects MySQL client must be in agent box.

- **Windows Agent**: Use this [script file](https://aka.ms/window-mysqlcli-installer) to install MySQL client
- **Linux Agent**: Run command 'apt-get install mysql-client' to install MySQL client
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

This example creates a sample db in MySQL.

```YAML
steps:
- task: MysqlDeploymentOnMachineGroup@1
  displayName: 'Deploy Using : InlineSqlTask'
  inputs:
    TaskNameSelector: InlineSqlTask
    SqlInline: |
      CREATE DATABASE IF NOT EXISTS alm;
      use alm;
    ServerName: localhost
    SqlUsername: root
    SqlPassword: P2ssw0rd
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.100.0 or greater |
| Task category | Deploy |

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | Preview, Classic release |
| Runs on | DeploymentGroup |
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