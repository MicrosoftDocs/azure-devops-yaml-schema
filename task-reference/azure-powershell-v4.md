---
title: AzurePowerShell@4 - Azure PowerShell v4 task
description: Run a PowerShell script within an Azure environment (task version 4).
ms.date: 12/21/2023
monikerRange: ">=azure-pipelines-2019.1"
---

# AzurePowerShell@4 - Azure PowerShell v4 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to run a PowerShell script within an Azure environment. The Azure context is authenticated with the provided Azure Resource Manager service connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.1"

```yaml
# Azure PowerShell v4
# Run a PowerShell script within an Azure environment.
- task: AzurePowerShell@4
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceNameARM. Required. Azure Subscription. 
    #ScriptType: 'FilePath' # 'FilePath' | 'InlineScript'. Script Type. Default: FilePath.
    #ScriptPath: # string. Optional. Use when ScriptType = FilePath. Script Path. 
    #Inline: # string. Optional. Use when ScriptType = InlineScript. Inline Script. 
    #ScriptArguments: # string. Optional. Use when ScriptType = FilePath. Script Arguments. 
    #errorActionPreference: 'stop' # 'stop' | 'continue' | 'silentlyContinue'. ErrorActionPreference. Default: stop.
    #FailOnStandardError: false # boolean. Fail on Standard Error. Default: false.
    #RestrictContextToCurrentTask: false # boolean. Restrict scope of context to current task. Default: false.
  # Azure PowerShell version options
    #azurePowerShellVersion: 'OtherVersion' # 'LatestVersion' | 'OtherVersion'. Alias: TargetAzurePs. Azure PowerShell Version. Default: OtherVersion.
    preferredAzurePowerShellVersion: # string. Alias: CustomTargetAzurePs. Required when TargetAzurePs = OtherVersion. Preferred Azure PowerShell Version. 
  # Advanced
    #pwsh: false # boolean. Use PowerShell Core. Default: false.
    #validateScriptSignature: false # boolean. Optional. Use when ScriptType = FilePath. Validate script signature. Default: false.
    #workingDirectory: # string. Working Directory.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020.1 <=azure-pipelines-2022"

```yaml
# Azure PowerShell v4
# Run a PowerShell script within an Azure environment.
- task: AzurePowerShell@4
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceNameARM. Required. Azure Subscription. 
    #ScriptType: 'FilePath' # 'FilePath' | 'InlineScript'. Script Type. Default: FilePath.
    #ScriptPath: # string. Optional. Use when ScriptType = FilePath. Script Path. 
    #Inline: # string. Optional. Use when ScriptType = InlineScript. Inline Script. 
    #ScriptArguments: # string. Optional. Use when ScriptType = FilePath. Script Arguments. 
    #errorActionPreference: 'stop' # 'stop' | 'continue' | 'silentlyContinue'. ErrorActionPreference. Default: stop.
    #FailOnStandardError: false # boolean. Fail on Standard Error. Default: false.
    #RestrictContextToCurrentTask: false # boolean. Restrict scope of context to current task. Default: false.
  # Azure PowerShell version options
    #azurePowerShellVersion: 'OtherVersion' # 'LatestVersion' | 'OtherVersion'. Alias: TargetAzurePs. Azure PowerShell Version. Default: OtherVersion.
    preferredAzurePowerShellVersion: # string. Alias: CustomTargetAzurePs. Required when TargetAzurePs = OtherVersion. Preferred Azure PowerShell Version. 
  # Advanced
    #pwsh: false # boolean. Use PowerShell Core. Default: false.
    #workingDirectory: # string. Working Directory.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Azure PowerShell v4
# Run a PowerShell script within an Azure environment.
- task: AzurePowerShell@4
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceNameARM. Required. Azure Subscription. 
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
    #pwsh: false # boolean. Use PowerShell Core. Default: false.
    #workingDirectory: # string. Working Directory.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Azure PowerShell v4
# Run a PowerShell script within an Azure environment.
- task: AzurePowerShell@4
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceNameARM. Required. Azure Subscription. 
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

<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azureSubscription`** - **Azure Subscription**<br>
Input alias: `ConnectedServiceNameARM`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Azure Resource Manager subscription to configure before running PowerShell.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ScriptType`** - **Script Type**<br>
`string`. Allowed values: `FilePath` (Script File Path), `InlineScript` (Inline Script). Default value: `FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The type of the script: file path or inline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ScriptPath`** - **Script Path**<br>
`string`. Optional. Use when `ScriptType = FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path of the script. This should be a fully qualified path or one relative to the default working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Inline"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`Inline`** - **Inline Script**<br>
`string`. Optional. Use when `ScriptType = InlineScript`. Default value: `# You can write your azure powershell scripts inline here. \n# You can also pass predefined and custom variables to this script using arguments`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifes the script to execute. The maximum supported inline script length is 5000 characters. Use a script from a file if you want to use a longer script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptArguments"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ScriptArguments`** - **Script Arguments**<br>
`string`. Optional. Use when `ScriptType = FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The additional parameters to pass to PowerShell.  Can be either ordinal or named parameters.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="errorActionPreference"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`errorActionPreference`** - **ErrorActionPreference**<br>
`string`. Allowed values: `stop`, `continue`, `silentlyContinue`. Default value: `stop`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the value of the `ErrorActionPreference` variable for executing the script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="FailOnStandardError"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`FailOnStandardError`** - **Fail on Standard Error**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When this is true, this task will fail if any errors are written to the error pipeline or if any data is written to the standard error stream.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RestrictContextToCurrentTask"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`RestrictContextToCurrentTask`** - **Restrict scope of context to current task**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When this is true, this task will restrict the scope of context to the current task only, and the context will not be available to other tasks in the pipeline when using a private agent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azurePowerShellVersion"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azurePowerShellVersion`** - **Azure PowerShell Version**<br>
Input alias: `TargetAzurePs`. `string`. Allowed values: `LatestVersion` (Latest installed version), `OtherVersion` (Specify other version). Default value: `OtherVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In case of hosted agents, the supported Azure PowerShell Version is: `1.0.0` (Hosted VS2017 Queue).
To pick the latest version available on the agent, select `LatestVersion` (Latest installed version).

For private agents you can specify a preferred version of Azure PowerShell using `OtherVersion` (Specify other version).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="preferredAzurePowerShellVersion"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`preferredAzurePowerShellVersion`** - **Preferred Azure PowerShell Version**<br>
Input alias: `CustomTargetAzurePs`. `string`. Required when `TargetAzurePs = OtherVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The preferred Azure PowerShell Version needs to be a proper semantic version eg. `1.2.3.` Regex like `2.\*,2.3.\*` is not supported. The Hosted VS2017 Pool currently supports Az module version `1.0.0.`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pwsh"::: -->
:::moniker range=">=azure-pipelines-2020"

**`pwsh`** - **Use PowerShell Core**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, then on Windows the task will use `pwsh.exe` from your path instead of `powershell.exe`.
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
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2020"

**`workingDirectory`** - **Working Directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The working directory where the script is run.
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

Added support for Az Module and cross platform agents.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
