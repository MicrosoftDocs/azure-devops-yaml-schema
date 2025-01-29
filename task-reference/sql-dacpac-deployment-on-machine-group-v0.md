---
title: SqlDacpacDeploymentOnMachineGroup@0 - SQL Server database deploy v0 task
description: Deploy a SQL Server database using DACPAC or SQL scripts.
ms.date: 01/29/2025
monikerRange: "<=azure-pipelines"
---

# SqlDacpacDeploymentOnMachineGroup@0 - SQL Server database deploy v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to deploy a SQL Server database using DACPAC or SQL scripts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# This task is supported on classic release pipelines only.
# Use the classic designer to add and configure this task in a classic release pipeline.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="TaskType"::: -->
:::moniker range="<=azure-pipelines"

**`TaskType`** - **Deploy SQL Using**<br>
`string`. Required. Allowed values: `dacpac` (Sql Dacpac), `sqlQuery` (Sql Query File), `sqlInline` (Inline Sql). Default value: `dacpac`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the way you want to deploy the database: using Dacpac or SQL Scripts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DacpacFile"::: -->
:::moniker range="<=azure-pipelines"

**`DacpacFile`** - **DACPAC File**<br>
`string`. Required when `TaskType = dacpac`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the DACPAC file on the target machines or on a UNC path, like `\\BudgetIT\Web\Deploy\FabrikamDB.dacpac`. The UNC path should be accessible to the machine's administrator account. Environment variables are also supported, like `$env:windir`, `$env:systemroot`, or `$env:windir\FabrikamFibre\DB`. Wildcards can be used. For example, `**/*.dacpac` for the DACPAC file that's present in all sub folders.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlFile"::: -->
:::moniker range="<=azure-pipelines"

**`SqlFile`** - **Sql File**<br>
`string`. Required when `TaskType = sqlQuery`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the SQL file on the target. Provide a semi-colon separated list of SQL script files to execute multiple files. The SQL scripts are executed in the order given. The location can also be a UNC path, like `\\BudgetIT\Web\Deploy\FabrikamDB.sql`. The UNC path should be accessible to the machine's administrator account. Environment variables are also supported, like `$env:windir`, `$env:systemroot`, or `$env:windir\FabrikamFibre\DB`. Wildcards can be used. For example, `**/*.sql` for the SQL file present in all sub folders.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ExecuteInTransaction"::: -->
:::moniker range="<=azure-pipelines"

**`ExecuteInTransaction`** - **Execute within a transaction**<br>
`boolean`. Optional. Use when `TaskType = sqlQuery`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Executes the SQL script(s) within a transaction.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ExclusiveLock"::: -->
:::moniker range="<=azure-pipelines"

**`ExclusiveLock`** - **Acquire an exclusive app lock while executing script(s)**<br>
`boolean`. Optional. Use when `ExecuteInTransaction = true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Acquires an exclusive app lock while executing script(s).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppLockName"::: -->
:::moniker range="<=azure-pipelines"

**`AppLockName`** - **App lock name**<br>
`string`. Required when `ExclusiveLock = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the app lock name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="InlineSql"::: -->
:::moniker range="<=azure-pipelines"

**`InlineSql`** - **Inline Sql**<br>
`string`. Required when `TaskType = sqlInline`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SQL queries inline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetMethod"::: -->
:::moniker range="<=azure-pipelines"

**`TargetMethod`** - **Specify SQL Using**<br>
`string`. Required when `TaskType = dacpac`. Allowed values: `server`, `connectionString` (Connection String), `publishProfile` (Publish Profile). Default value: `server`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to connect to the target SQL Server database. You can provide the SQL Server database details, the SQL Server connection string, or the publish profile XML file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServerName"::: -->
:::moniker range="<=azure-pipelines"

**`ServerName`** - **Server Name**<br>
`string`. Required when `TargetMethod = server || TaskType = sqlQuery || TaskType = sqlInline`. Default value: `localhost`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SQL Server name, like `machinename\FabriakmSQL,1433`, `localhost`, or `.\SQL2012R2`. Specifying `localhost` will connect to the default SQL Server instance on the machine.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DatabaseName"::: -->
:::moniker range="<=azure-pipelines"

**`DatabaseName`** - **Database Name**<br>
`string`. Required when `TargetMethod = server || TaskType = sqlQuery || TaskType = sqlInline`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the SQL Server database.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AuthScheme"::: -->
:::moniker range="<=azure-pipelines"

**`AuthScheme`** - **Authentication**<br>
`string`. Required when `TargetMethod = server || TaskType = sqlQuery || TaskType = sqlInline`. Allowed values: `windowsAuthentication` (Windows Authentication), `sqlServerAuthentication` (SQL Server Authentication). Default value: `windowsAuthentication`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the authentication mode for connecting to the SQL Server. In Windows authentication mode, the account used to configure the deployment agent is used to connect to the SQL Server. In SQL Server authentication mode, the SQL login and password must be provided in the parameters below.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlUsername"::: -->
:::moniker range="<=azure-pipelines"

**`SqlUsername`** - **SQL User name**<br>
`string`. Required when `AuthScheme = sqlServerAuthentication`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SQL login to connect to the SQL Server. This option is only available if SQL Server authentication mode has been selected.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SqlPassword"::: -->
:::moniker range="<=azure-pipelines"

**`SqlPassword`** - **SQL Password**<br>
`string`. Required when `AuthScheme = sqlServerAuthentication`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password of the SQL login. This option is only available if SQL Server authentication mode has been selected.
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
`string`. Optional. Use when `TaskType = dacpac`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides fine-grained control over SQL Server database deployments.  
Specifies the path to the publish profile XML file on the target machine or on a UNC share that is accessible by the machine administrator's credentials.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`AdditionalArguments`** - **Additional Arguments**<br>
`string`. Optional. Use when `TaskType = dacpac`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional `SqlPackage.exe` arguments that will be applied when deploying the SQL Server database, like `/p:IgnoreAnsiNulls=True` or `/p:IgnoreComments=True`. These arguments will override the settings in the publish profile XML file (if provided).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsSql"::: -->
:::moniker range="<=azure-pipelines"

**`AdditionalArgumentsSql`** - **Additional Arguments**<br>
`string`. Optional. Use when `TaskType = sqlQuery || TaskType = sqlInline`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional `Invoke-Sqlcmd` arguments that are applied when deploying the SQL Server database.
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

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.102.0 or greater |
| Task category | Deploy |

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | Classic release |
| Runs on | DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.102.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->