---
title: AzurePowerShell@2 - Azure PowerShell v2 task
description: Run a PowerShell script within an Azure environment (task version 2).
ms.date: 10/21/2022
monikerRange: "<=azure-pipelines"
---

# AzurePowerShell@2 - Azure PowerShell v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to run a PowerShell script within an Azure environment. The Azure context is authenticated with the provided Azure Resource Manager service connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Azure PowerShell v2
# Run a PowerShell script within an Azure environment.
- task: AzurePowerShell@2
  inputs:
    #azureConnectionType: 'ConnectedServiceNameARM' # 'ConnectedServiceName' | 'ConnectedServiceNameARM'. Alias: ConnectedServiceNameSelector. Azure Connection Type. Default: ConnectedServiceNameARM.
    #azureClassicSubscription: # string. Alias: ConnectedServiceName. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Classic Subscription. 
    azureSubscription: # string. Alias: ConnectedServiceNameARM. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. Azure Subscription. 
    ScriptType: 'FilePath' # 'FilePath' | 'InlineScript'. Required. Script Type. Default: FilePath.
    #ScriptPath: # string. Optional. Use when ScriptType = FilePath. Script Path. 
    #Inline: # string. Optional. Use when ScriptType = InlineScript. Inline Script. 
    #ScriptArguments: # string. Script Arguments. 
    #azurePowerShellVersion: 'OtherVersion' # 'LatestVersion' | 'OtherVersion'. Alias: TargetAzurePs. Azure PowerShell Version. Default: OtherVersion.
    preferredAzurePowerShellVersion: # string. Alias: CustomTargetAzurePs. Required when TargetAzurePs = OtherVersion. Preferred Azure PowerShell Version.
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

<!-- :::item name="azureConnectionType"::: -->
:::moniker range="<=azure-pipelines"

**`azureConnectionType`** - **Azure Connection Type**<br>
Input alias: `ConnectedServiceNameSelector`. `string`. Allowed values: `ConnectedServiceName` (Azure Classic), `ConnectedServiceNameARM` (Azure Resource Manager). Default value: `ConnectedServiceNameARM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureClassicSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureClassicSubscription`** - **Azure Classic Subscription**<br>
Input alias: `ConnectedServiceName`. `string`. Required when `ConnectedServiceNameSelector = ConnectedServiceName`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Azure Classic subscription to configure before running PowerShell.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure Subscription**<br>
Input alias: `ConnectedServiceNameARM`. `string`. Required when `ConnectedServiceNameSelector = ConnectedServiceNameARM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Azure Resource Manager subscription to configure before running PowerShell.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptType"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptType`** - **Script Type**<br>
`string`. Required. Allowed values: `FilePath` (Script File Path), `InlineScript` (Inline Script). Default value: `FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The type of script: file path or inline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptPath`** - **Script Path**<br>
`string`. Optional. Use when `ScriptType = FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path of the script. This should be a fully qualified path or one relative to the default working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Inline"::: -->
:::moniker range="<=azure-pipelines"

**`Inline`** - **Inline Script**<br>
`string`. Optional. Use when `ScriptType = InlineScript`. Default value: `# You can write your azure powershell scripts inline here. \n# You can also pass predefined and custom variables to this script using arguments`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters the script to execute.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptArguments"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptArguments`** - **Script Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The additional parameters to pass to PowerShell. These can be either ordinal or named parameters.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azurePowerShellVersion"::: -->
:::moniker range="<=azure-pipelines"

**`azurePowerShellVersion`** - **Azure PowerShell Version**<br>
Input alias: `TargetAzurePs`. `string`. Allowed values: `LatestVersion` (Latest installed version), `OtherVersion` (Specify other version). Default value: `OtherVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In case of hosted agents, the supported Azure PowerShell Versions are `2.1.0`, `3.8.0`, `4.2.1`, `5.1.1` and `6.7.0` (Hosted VS2017 Queue).
To pick the latest version available on the agent, select `LatestVersion` (Latest installed version).

For private agents you can specify a preferred version of Azure PowerShell using `OtherVersion` (Specify other version).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="preferredAzurePowerShellVersion"::: -->
:::moniker range="<=azure-pipelines"

**`preferredAzurePowerShellVersion`** - **Preferred Azure PowerShell Version**<br>
Input alias: `CustomTargetAzurePs`. `string`. Required when `TargetAzurePs = OtherVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The preferred Azure PowerShell Version needs to be a proper semantic version eg. `1.2.3.`. Regex like `2.\*,2.3.\*` is not supported. The Hosted VS2017 Pool currently supports Azure module versions `2.1.0`, `3.8.0`, `4.2.1`, `5.1.1` and AzureRM module versions `2.1.0`, `3.8.0`, `4.2.1`, `5.1.1`, `6.7.0`.
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
