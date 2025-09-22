---
title: AzurePowerShell@5 - Azure PowerShell v5 task
description: Run a PowerShell script within an Azure environment.
ms.date: 09/22/2025
monikerRange: "=azure-pipelines || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
author: juliakm
ms.author: jukullam
---

# AzurePowerShell@5 - Azure PowerShell v5 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to run a PowerShell script within an Azure environment. The Azure context is authenticated with the provided Azure Resource Manager service connection.

>[!NOTE]
> By default, Azure PowerShell v5 uses PowerShell Core for Linux agents and Windows PowerShell for Windows agents. To use the latest version of PowerShell on Windows agents, set the `pwsh` parameter to `true`. PowerShell Core will then be used instead.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.1"

```yaml
# Azure PowerShell v5
# Run a PowerShell script within an Azure environment.
- task: AzurePowerShell@5
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
    #validateScriptSignature: false # boolean. Optional. Use when ScriptType = FilePath. Validate script signature. Default: false.
    #workingDirectory: # string. Working Directory.
```

:::moniker-end

:::moniker range="<=azure-pipelines-2022"

```yaml
# Azure PowerShell v5
# Run a PowerShell script within an Azure environment.
- task: AzurePowerShell@5
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
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure Subscription**<br>
[Input alias](index.md#what-are-task-input-aliases): `ConnectedServiceNameARM`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Azure Resource Manager subscription to configure before running PowerShell.

[!INCLUDE [connection-expression](./includes/azure-subscription-variables.md)]
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptType"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptType`** - **Script Type**<br>
`string`. Allowed values: `FilePath` (Script File Path), `InlineScript` (Inline Script). Default value: `FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The type of the script: file path or inline.
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
Specifes the script to execute. The maximum supported inline script length is 5000 characters. Use a script from a file if you want to use a longer script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptArguments"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptArguments`** - **Script Arguments**<br>
`string`. Optional. Use when `ScriptType = FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The additional parameters to pass to PowerShell. These can be either ordinal or named parameters. Not applicable for an inline script option.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="errorActionPreference"::: -->
:::moniker range="<=azure-pipelines"

**`errorActionPreference`** - **ErrorActionPreference**<br>
`string`. Allowed values: `stop`, `continue`, `silentlyContinue`. Default value: `stop`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the value of the `ErrorActionPreference` variable for executing the script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="FailOnStandardError"::: -->
:::moniker range="<=azure-pipelines"

**`FailOnStandardError`** - **Fail on Standard Error**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When this is true, this task will fail if any errors are written to the error pipeline or if any data is written to the standard error stream.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azurePowerShellVersion"::: -->
:::moniker range="<=azure-pipelines"

**`azurePowerShellVersion`** - **Azure PowerShell Version**<br>
[Input alias](index.md#what-are-task-input-aliases): `TargetAzurePs`. `string`. Allowed values: `LatestVersion` (Latest installed version), `OtherVersion` (Specify other version). Default value: `OtherVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In case of hosted agents, the supported Azure PowerShell Versions are `1.0.0`, `1.6.0`, `2.3.2`, `2.6.0`, and `3.1.0` (Hosted VS2017 Queue).
To pick the latest version available on the agent, select `LatestVersion` (Latest installed version).

For private agents you can specify a preferred version of Azure PowerShell using `OtherVersion` (Specify other version).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="preferredAzurePowerShellVersion"::: -->
:::moniker range="<=azure-pipelines"

**`preferredAzurePowerShellVersion`** - **Preferred Azure PowerShell Version**<br>
[Input alias](index.md#what-are-task-input-aliases): `CustomTargetAzurePs`. `string`. Required when `TargetAzurePs = OtherVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The preferred Azure PowerShell Version needs to be a proper semantic version eg. `1.2.3`. Regex like `2.\*,2.3.\*` is not supported. The Hosted VS2017 Pool currently supports Az module versions `1.0.0`, `1.6.0`, `2.3.2`, `2.6.0`, and `3.1.0`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pwsh"::: -->
:::moniker range="<=azure-pipelines"

**`pwsh`** - **Use PowerShell Core**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, then tasks running on Windows agents will use `pwsh.exe` from your path instead of `powershell.exe`.
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
:::moniker range="<=azure-pipelines"

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

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

### Troubleshooting

#### Script worked locally, but failed in the pipeline

This typically occurs when the service connection used in the pipeline has insufficient permissions to run the script. Locally, the script runs with your credentials and would succeed as you may have the required access.

To resolve this issue, ensure the service principle/ authentication credentials have the required permissions. For more information, see [Use Role-Based Access Control to manage access to your Azure subscription resources](/azure/role-based-access-control/role-assignments-portal).

#### Error: Could not find the modules: '\<module name\>' with Version: '\<version\>'. If the module was recently installed, retry after restarting the Azure Pipelines task agent

Azure PowerShell task uses Azure/AzureRM/Az PowerShell Module to interact with Azure Subscription. This issue occurs when the PowerShell module is not available on the Hosted Agent. Hence, for a particular task version, *Preferred Azure PowerShell version* must be specified in the **Azure PowerShell version options** from the list of available versions. The installed software can be found in the [Software](/azure/devops/pipelines/agents/hosted#software) table in [Microsoft-hosted agents](/azure/devops/pipelines/agents/hosted).

#### Service Connection Issues
To troubleshoot issues related to service connections, see [Service Connection troubleshooting](/azure/devops/pipelines/release/azure-rm-endpoint).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples


The following example shows how to invoke a script from a file and pass script arguments to it.

```yml
- task: AzurePowerShell@5
  inputs:
    azureSubscription: my-arm-service-connection
    scriptType: filePath
    scriptPath: $(Build.SourcesDirectory)\myscript.ps1
    scriptArguments:
      -Arg1 val1 `
      -Arg2 val2 `
      -Arg3 val3
    azurePowerShellVersion: LatestVersion
    pwsh: true
```

The following arguments shows how to invoke an inline script.

```yml
- task: AzurePowerShell@5
  inputs:
    azureSubscription: 'Azure subscription connection placeholder'
    azurePowerShellVersion: LatestVersion
    ScriptType: 'InlineScript'
    Inline: |
      # You can write your azure powershell scripts inline here. 
      # You can also pass predefined and custom variables to this script using arguments
      Write-Host 'Hello'
      Write-Host 'World!'
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

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
