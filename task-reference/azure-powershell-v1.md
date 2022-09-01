---
title: AzurePowerShell@1 - Azure PowerShell v1 task
description: Run a PowerShell script within an Azure environment (task version 1).
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# AzurePowerShell@1 - Azure PowerShell v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Run a PowerShell script within an Azure environment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Azure PowerShell v1
# Run a PowerShell script within an Azure environment.
- task: AzurePowerShell@1
  inputs:
    #ConnectedServiceNameSelector: 'ConnectedServiceName' # 'ConnectedServiceName' | 'ConnectedServiceNameARM'. Azure Connection Type. Default: 'ConnectedServiceName'.
    ConnectedServiceName: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Classic Subscription. 
    #ConnectedServiceNameARM: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. Azure Subscription. 
    ScriptType: 'FilePath' # 'FilePath' | 'InlineScript'. Required. Script Type. Default: 'FilePath'.
    #ScriptPath: # string. Optional. Use when ScriptType = FilePath. Script Path. 
    #Inline: # string. Optional. Use when ScriptType = InlineScript. Inline Script. 
    #ScriptArguments: # string. Script Arguments.
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

<!-- :::item name="ConnectedServiceNameSelector"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectedServiceNameSelector`** - **Azure Connection Type**<br>
Type: string. Allowed values: 'ConnectedServiceName', 'ConnectedServiceNameARM'. Default value: 'ConnectedServiceName'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectedServiceName"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectedServiceName`** - **Azure Classic Subscription**<br>
Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceName.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Classic subscription to configure before running PowerShell.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectedServiceNameARM"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectedServiceNameARM`** - **Azure Subscription**<br>
Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Resource Manager subscription to configure before running PowerShell.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptType"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptType`** - **Script Type**<br>
Type: string. Required. Allowed values: 'FilePath', 'InlineScript'. Default value: 'FilePath'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Type of the script: File Path or Inline Script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptPath`** - **Script Path**<br>
Type: string. Optional. Use when ScriptType = FilePath.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path of the script. Should be fully qualified path or relative to the default working directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Inline"::: -->
:::moniker range="<=azure-pipelines"

**`Inline`** - **Inline Script**<br>
Type: string. Optional. Use when ScriptType = InlineScript.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the script to execute.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptArguments"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptArguments`** - **Script Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional parameters to pass to PowerShell.  Can be either ordinal or named parameters.
<!-- :::editable-content-end::: -->

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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: azureps |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.95.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->