---
title: ServiceFabricPowerShell@1 - Service Fabric PowerShell v1 task
description: Run a PowerShell script in the context of an Azure Service Fabric cluster connection.
ms.date: 07/02/2024
monikerRange: "<=azure-pipelines"
---

# ServiceFabricPowerShell@1 - Service Fabric PowerShell v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to run a PowerShell script within the context of an Azure Service Fabric cluster connection. Runs any PowerShell command or script in a PowerShell session that has a Service Fabric cluster connection initialized.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Service Fabric PowerShell v1
# Run a PowerShell script in the context of an Azure Service Fabric cluster connection.
- task: ServiceFabricPowerShell@1
  inputs:
    clusterConnection: # string. Alias: serviceConnectionName. Required. Cluster Service Connection. 
    ScriptType: 'FilePath' # 'FilePath' | 'InlineScript'. Required. Script Type. Default: FilePath.
    #ScriptPath: # string. Optional. Use when ScriptType = FilePath. Script Path. 
    #Inline: # string. Optional. Use when ScriptType = InlineScript. Inline Script. 
    #ScriptArguments: # string. Script Arguments.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Service Fabric PowerShell v1
# Run a PowerShell script within the context of an Azure Service Fabric cluster connection.
- task: ServiceFabricPowerShell@1
  inputs:
    clusterConnection: # string. Alias: serviceConnectionName. Required. Cluster Service Connection. 
    ScriptType: 'FilePath' # 'FilePath' | 'InlineScript'. Required. Script Type. Default: FilePath.
    #ScriptPath: # string. Optional. Use when ScriptType = FilePath. Script Path. 
    #Inline: # string. Optional. Use when ScriptType = InlineScript. Inline Script. 
    #ScriptArguments: # string. Script Arguments.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="clusterConnection"::: -->
:::moniker range=">=azure-pipelines-2019"

**`clusterConnection`** - **Cluster Service Connection**<br>
Input alias: `serviceConnectionName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure Service Fabric cluster which will have an established service connection when the specified PowerShell script is executed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptType"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptType`** - **Script Type**<br>
`string`. Required. Allowed values: `FilePath` (Script File Path), `InlineScript` (Inline Script). Default value: `FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether the script is provided as a file or inline in the task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptPath`** - **Script Path**<br>
`string`. Optional. Use when `ScriptType = FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the PowerShell script to run. Can include wildcards and variables. Example: `$(system.defaultworkingdirectory)/**/drop/projectartifacts/**/docker-compose.yml`.
> [!NOTE]
> Combining Compose files is not supported as part of this task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Inline"::: -->
:::moniker range="<=azure-pipelines"

**`Inline`** - **Inline Script**<br>
`string`. Optional. Use when `ScriptType = InlineScript`. Default value: `# You can write your PowerShell scripts inline here. \n# You can also pass predefined and custom variables to this script using arguments`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the PowerShell commands to run on the build agent. Learn more about [PowerShell tasks](/azure/devops/pipelines/tasks/utility/powershell).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptArguments"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptArguments`** - **Script Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the additional parameters to pass to PowerShell. Can be either ordinal or named parameters.
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

Use this task to run a PowerShell script within the context of an Azure Service Fabric cluster connection.
Runs any PowerShell command or script in a PowerShell session that has a Service Fabric cluster connection initialized.

### Service Fabric

* This task uses a Service Fabric installation to connect and deploy to a Service Fabric cluster.
* [Azure Service Fabric Core SDK](https://www.microsoft.com/web/handlers/webpi.ashx?command=getinstallerredirect&appid=MicrosoftAzure-ServiceFabric-CoreSDK) on the build agent.
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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: Cmd |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.95.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->