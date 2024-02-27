---
title: AzurePowerShell@3 - Azure PowerShell v3 task
description: Run a PowerShell script within an Azure environment (task version 3).
ms.date: 02/27/2024
monikerRange: ">=azure-pipelines-2019"
---

# AzurePowerShell@3 - Azure PowerShell v3 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to run a PowerShell script within an Azure environment. The Azure context is authenticated with the provided Azure Resource Manager service connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.1"

```yaml
# Azure PowerShell v3
# Run a PowerShell script within an Azure environment.
- task: AzurePowerShell@3
  inputs:
    #azureConnectionType: 'ConnectedServiceNameARM' # 'ConnectedServiceName' | 'ConnectedServiceNameARM'. Alias: ConnectedServiceNameSelector. Azure Connection Type. Default: ConnectedServiceNameARM.
    #azureClassicSubscription: # string. Alias: ConnectedServiceName. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Classic Subscription. 
    azureSubscription: # string. Alias: ConnectedServiceNameARM. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. Azure Subscription. 
    #ScriptType: 'FilePath' # 'FilePath' | 'InlineScript'. Script Type. Default: FilePath.
    #ScriptPath: # string. Optional. Use when ScriptType = FilePath. Script Path. 
    #Inline: # string. Optional. Use when ScriptType = InlineScript. Inline Script. 
    #ScriptArguments: # string. Optional. Use when ScriptType = FilePath. Script Arguments. 
    #errorActionPreference: 'stop' # 'stop' | 'continue' | 'silentlyContinue'. ErrorActionPreference. Default: stop.
    #FailOnStandardError: false # boolean. Fail on Standard Error. Default: false.
  # Azure PowerShell version options
    #azurePowerShellVersion: 'OtherVersion' # 'LatestVersion' | 'OtherVersion'. Alias: TargetAzurePs. Azure PowerShell Version. Default: OtherVersion.
    preferredAzurePowerShellVersion: # string. Alias: CustomTargetAzurePs. Required when TargetAzurePs = OtherVersion. Preferred Azure PowerShell Version. 
  # Advanced
    #validateScriptSignature: false # boolean. Optional. Use when ScriptType = FilePath. Validate script signature. Default: false.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022"

```yaml
# Azure PowerShell v3
# Run a PowerShell script within an Azure environment.
- task: AzurePowerShell@3
  inputs:
    #azureConnectionType: 'ConnectedServiceNameARM' # 'ConnectedServiceName' | 'ConnectedServiceNameARM'. Alias: ConnectedServiceNameSelector. Azure Connection Type. Default: ConnectedServiceNameARM.
    #azureClassicSubscription: # string. Alias: ConnectedServiceName. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Classic Subscription. 
    azureSubscription: # string. Alias: ConnectedServiceNameARM. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. Azure Subscription. 
    #ScriptType: 'FilePath' # 'FilePath' | 'InlineScript'. Script Type. Default: FilePath.
    #ScriptPath: # string. Optional. Use when ScriptType = FilePath. Script Path. 
    #Inline: # string. Optional. Use when ScriptType = InlineScript. Inline Script. 
    #ScriptArguments: # string. Optional. Use when ScriptType = FilePath. Script Arguments. 
    #errorActionPreference: 'stop' # 'stop' | 'continue' | 'silentlyContinue'. ErrorActionPreference. Default: stop.
    #FailOnStandardError: false # boolean. Fail on Standard Error. Default: false.
  # Azure PowerShell version options
    #azurePowerShellVersion: 'OtherVersion' # 'LatestVersion' | 'OtherVersion'. Alias: TargetAzurePs. Azure PowerShell Version. Default: OtherVersion.
    preferredAzurePowerShellVersion: # string. Alias: CustomTargetAzurePs. Required when TargetAzurePs = OtherVersion. Preferred Azure PowerShell Version.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureConnectionType"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureConnectionType`** - **Azure Connection Type**<br>
Input alias: `ConnectedServiceNameSelector`. `string`. Allowed values: `ConnectedServiceName` (Azure Classic), `ConnectedServiceNameARM` (Azure Resource Manager). Default value: `ConnectedServiceNameARM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureClassicSubscription"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureClassicSubscription`** - **Azure Classic Subscription**<br>
Input alias: `ConnectedServiceName`. `string`. Required when `ConnectedServiceNameSelector = ConnectedServiceName`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Azure Classic subscription to configure before running PowerShell.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureSubscription`** - **Azure Subscription**<br>
Input alias: `ConnectedServiceNameARM`. `string`. Required when `ConnectedServiceNameSelector = ConnectedServiceNameARM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Azure Resource Manager subscription to configure before running PowerShell.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptType"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ScriptType`** - **Script Type**<br>
`string`. Allowed values: `FilePath` (Script File Path), `InlineScript` (Inline Script). Default value: `FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The type of the script: file path or inline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ScriptPath`** - **Script Path**<br>
`string`. Optional. Use when `ScriptType = FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path of the script. This should be a fully qualified path or one relative to the default working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Inline"::: -->
:::moniker range=">=azure-pipelines-2019"

**`Inline`** - **Inline Script**<br>
`string`. Optional. Use when `ScriptType = InlineScript`. Default value: `# You can write your azure powershell scripts inline here. \n# You can also pass predefined and custom variables to this script using arguments`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifes the script to execute. The maximum supported inline script length is 5000 characters. Use a script from a file if you want to use a longer script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptArguments"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ScriptArguments`** - **Script Arguments**<br>
`string`. Optional. Use when `ScriptType = FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The additional parameters to pass to PowerShell. These can be either ordinal or named parameters.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="errorActionPreference"::: -->
:::moniker range=">=azure-pipelines-2019"

**`errorActionPreference`** - **ErrorActionPreference**<br>
`string`. Allowed values: `stop`, `continue`, `silentlyContinue`. Default value: `stop`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the value of the `ErrorActionPreference` variable for executing the script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="FailOnStandardError"::: -->
:::moniker range=">=azure-pipelines-2019"

**`FailOnStandardError`** - **Fail on Standard Error**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When this is true, this task will fail if any errors are written to the error pipeline or if any data is written to the standard error stream.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azurePowerShellVersion"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azurePowerShellVersion`** - **Azure PowerShell Version**<br>
Input alias: `TargetAzurePs`. `string`. Allowed values: `LatestVersion` (Latest installed version), `OtherVersion` (Specify other version). Default value: `OtherVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In case of hosted agents, the supported Azure PowerShell Versions are `2.1.0`, `3.8.0`, `4.2.1`, `5.1.1` and `6.7.0`.
To pick the latest version available on the agent, select `LatestVersion` (Latest installed version).

For private agents, you can specify a preferred version of Azure PowerShell using `OtherVersion` (Specify other version).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="preferredAzurePowerShellVersion"::: -->
:::moniker range=">=azure-pipelines-2019"

**`preferredAzurePowerShellVersion`** - **Preferred Azure PowerShell Version**<br>
Input alias: `CustomTargetAzurePs`. `string`. Required when `TargetAzurePs = OtherVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The preferred Azure PowerShell Version needs to be a proper semantic version eg. `1.2.3.`. Regex like `2.\*,2.3.\*` is not supported. Hosted agents currently supports Azure module versions `2.1.0`, `3.8.0`, `4.2.1`, `5.1.1` and AzureRM module versions `2.1.0`, `3.8.0`, `4.2.1`, `5.1.1`, `6.7.0`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="validateScriptSignature"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`validateScriptSignature`** - **Validate script signature**<br>
`boolean`. Optional. Use when `ScriptType = FilePath`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, then the task will first check to make sure specified script is signed and valid before executing it.
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

Added support for Fail on standard error and ErrorActionPreference.
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
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: azureps |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.0.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
