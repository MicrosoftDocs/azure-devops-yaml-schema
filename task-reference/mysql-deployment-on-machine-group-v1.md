---
title: MysqlDeploymentOnMachineGroup@1 - MySQL database deploy v1 task
description: Run scripts and make changes to a MySQL Database.
ms.date: 01/29/2025
monikerRange: ">=azure-pipelines-2019.1"
---

# MysqlDeploymentOnMachineGroup@1 - MySQL database deploy v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to run your scripts and make changes to your MySQL Database. There are two ways to deploy: using a script file or writing the script in our inline editor. Since this task is server based, it appears on Deployment group jobs.

This task is deprecated.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Use this task to run your scripts and make changes to your MySQL Database. There are two ways to deploy: using a script file or writing the script in our inline editor.
> [!Note]
> This is an early preview version. Since this task is server based, it appears on Deployment group jobs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# This task is supported on classic release pipelines only.
# Use the classic designer to add and configure this task in a classic release pipeline.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="TaskNameSelector"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`TaskNameSelector`** - **Deploy MySql Using**<br>
`string`. Allowed values: `SqlTaskFile` (MySQL Script File), `InlineSqlTask` (Inline MySQL Script). Default value: `SqlTaskFile`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies either Script File or Inline Script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlFile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`SqlFile`** - **MySQL Script**<br>
`string`. Required when `TaskNameSelector = SqlTaskFile`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the full path of the script file on the automation agent or on a UNC path that is accessible to the automation agent, such as `BudgetIT\DeployBuilds\script.sql`. This string can also use predefined system variables, such as `$(agent.releaseDirectory)` and a file containing SQL statements.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlInline"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`SqlInline`** - **Inline MySQL Script**<br>
`string`. Required when `TaskNameSelector = InlineSqlTask`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the MySQL script to execute on the selected database.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServerName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ServerName`** - **Host Name**<br>
`string`. Required. Default value: `localhost`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the server name of `Database for MySQL`, such as `localhost`. This string is the same value that is used for `Hostname` in `Parameters` in MySQL Workbench.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DatabaseName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`DatabaseName`** - **Database Name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the database. The script will create a database name if one does not already exist.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlUsername"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`SqlUsername`** - **MySQL User Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This string is the same value that is used for `Username` in `Parameters` in MySQL Workbench.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2022"

**`SqlUsername`** - **Mysql User Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This string is the same value that is used for `Username` in `Parameters` in MySQL Workbench.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlPassword"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`SqlPassword`** - **Password**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for MySQL Database. The password can be a variable defined in the pipeline, such as `$(password)`, and may be marked as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlAdditionalArguments"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`SqlAdditionalArguments`** - **Additional Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the additional options that are supported by MySQL simple SQL shell.  These options will be applied when executing the given file on the Database for MySQL.​

Example: You can change to the default tab separated output format, HTML format, or XML format. If you have problems due to insufficient memory for large result sets, use the `--quick` option.​
<!-- :::editable-content-end::: -->
<br>

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

Use this task to run your scripts and make changes to your MySQL Database. There are two ways to deploy, either using a script file or writing the script in our inline editor.
> [!Note]
> This is an early preview version. Since this task is server-based, it appears on deployment group jobs.

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