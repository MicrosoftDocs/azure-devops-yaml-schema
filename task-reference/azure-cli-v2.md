---
title: AzureCLI@2 - Azure CLI v2 task
description: Run Azure CLI commands against an Azure subscription in a PowerShell Core/Shell script when running on Linux agent or PowerShell/PowerShell Core/Batch script when running on Windows agent.
ms.date: 01/18/2023
monikerRange: ">=azure-pipelines-2020"
---

# AzureCLI@2 - Azure CLI v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020.1"

<!-- :::editable-content name="description"::: -->
Run Azure CLI commands against an Azure subscription in a PowerShell Core/shell script when running on Linux agent. Or, run Azure CLI commands against an Azure subscription in a PowerShell/PowerShell Core/batch script when running on Windows agent.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Run Azure CLI commands against an Azure subscription in a PowerShell Core/shell script when running on Linux agent. Or, run Azure CLI commands against an Azure subscription in a PowerShell/Powershell Core/batch script when running on Windows agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020.1"

```yaml
# Azure CLI v2
# Run Azure CLI commands against an Azure subscription in a PowerShell Core/Shell script when running on Linux agent or PowerShell/PowerShell Core/Batch script when running on Windows agent.
- task: AzureCLI@2
  inputs:
    azureSubscription: # string. Alias: connectedServiceNameARM. Required. Azure Resource Manager connection. 
    scriptType: # 'ps' | 'pscore' | 'batch' | 'bash'. Required. Script Type. 
    scriptLocation: 'scriptPath' # 'inlineScript' | 'scriptPath'. Required. Script Location. Default: scriptPath.
    scriptPath: # string. Required when scriptLocation = scriptPath. Script Path. 
    #inlineScript: # string. Required when scriptLocation = inlineScript. Inline Script. 
    #arguments: # string. Alias: scriptArguments. Script Arguments. 
    #powerShellErrorActionPreference: 'stop' # 'stop' | 'continue' | 'silentlyContinue'. Optional. Use when scriptType = ps || scriptType = pscore. ErrorActionPreference. Default: stop.
  # Advanced
    #addSpnToEnvironment: false # boolean. Access service principal details in script. Default: false.
    #useGlobalConfig: false # boolean. Use global Azure CLI configuration. Default: false.
    #workingDirectory: # string. Alias: cwd. Working Directory. 
    #failOnStandardError: false # boolean. Fail on Standard Error. Default: false.
    #powerShellIgnoreLASTEXITCODE: false # boolean. Optional. Use when scriptType = ps || scriptType = pscore. Ignore $LASTEXITCODE. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Azure CLI v2
# Run Azure CLI commands against an Azure subscription in a PowerShell Core/Shell script when running on Linux agent or PowerShell/Powershell Core/Batch script when running on Windows agent.
- task: AzureCLI@2
  inputs:
    azureSubscription: # string. Alias: connectedServiceNameARM. Required. Azure Resource Manager connection. 
    scriptType: # 'ps' | 'pscore' | 'batch' | 'bash'. Required. Script Type. 
    scriptLocation: 'scriptPath' # 'inlineScript' | 'scriptPath'. Required. Script Location. Default: scriptPath.
    scriptPath: # string. Required when scriptLocation = scriptPath. Script Path. 
    #inlineScript: # string. Required when scriptLocation = inlineScript. Inline Script. 
    #arguments: # string. Alias: scriptArguments. Script Arguments. 
    #powerShellErrorActionPreference: 'stop' # 'stop' | 'continue' | 'silentlyContinue'. Optional. Use when scriptType = ps || scriptType = pscore. ErrorActionPreference. Default: stop.
  # Advanced
    #addSpnToEnvironment: false # boolean. Access service principal details in script. Default: false.
    #useGlobalConfig: false # boolean. Use global Azure CLI configuration. Default: false.
    #workingDirectory: # string. Alias: cwd. Working Directory. 
    #failOnStandardError: false # boolean. Fail on Standard Error. Default: false.
    #powerShellIgnoreLASTEXITCODE: false # boolean. Optional. Use when scriptType = ps || scriptType = pscore. Ignore $LASTEXITCODE. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2020"

**`azureSubscription`** - **Azure Resource Manager connection**<br>
Input alias: `connectedServiceNameARM`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure Resource Manager service connection for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scriptType"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`scriptType`** - **Script Type**<br>
`string`. Required. Allowed values: `ps` (PowerShell), `pscore` (PowerShell Core), `batch`, `bash` (Shell).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Type of script. Select a `bash` or `pscore` script when running on Linux agent. Or, select a `batch`, `ps`, or `pscore` script when running on Windows agent. A `pscore` script can run on cross-platform agents (Linux, macOS, or Windows).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2020"

**`scriptType`** - **Script Type**<br>
`string`. Required. Allowed values: `ps` (Powershell), `pscore` (Powershell Core), `batch`, `bash` (Shell).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Type of script. Select a `bash` or `pscore` script when running on Linux agent. Or, select a `batch`, `ps`, or `pscore` script when running on Windows agent. A `pscore` script can run on cross-platform agents (Linux, macOS, or Windows).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scriptLocation"::: -->
:::moniker range=">=azure-pipelines-2020"

**`scriptLocation`** - **Script Location**<br>
`string`. Required. Allowed values: `inlineScript` (Inline script), `scriptPath` (Script path). Default value: `scriptPath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scriptPath"::: -->
:::moniker range=">=azure-pipelines-2020"

**`scriptPath`** - **Script Path**<br>
`string`. Required when `scriptLocation = scriptPath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fully qualified path of the script. Use `.ps1`, `.bat`, or `.cmd` when using Windows-based agent. Use `.ps1` or `.sh` when using Linux-based agent or a path relative to the the default working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="inlineScript"::: -->
:::moniker range=">=azure-pipelines-2020"

**`inlineScript`** - **Inline Script**<br>
`string`. Required when `scriptLocation = inlineScript`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You can write your scripts inline here. When using Windows agent, use PowerShell,  PowerShell Core, or batch scripting. Use PowerShell Core or shell scripting when using Linux-based agents. For batch files, use the prefix `call` before every Azure command. You can also pass predefined and custom variables to this script by using arguments. 

The following is an example for PowerShell/PowerShellCore/shell. 

```
az --version 
az account show 
```

The following is an example for batch.

```
call  az --version 
call az account show
```
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range=">=azure-pipelines-2020"

**`arguments`** - **Script Arguments**<br>
Input alias: `scriptArguments`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Arguments passed to the script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="powerShellErrorActionPreference"::: -->
:::moniker range=">=azure-pipelines-2020"

**`powerShellErrorActionPreference`** - **ErrorActionPreference**<br>
`string`. Optional. Use when `scriptType = ps || scriptType = pscore`. Allowed values: `stop`, `continue`, `silentlyContinue`. Default value: `stop`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prepends the line `$ErrorActionPreference = 'VALUE'` at the top of your PowerShell/PowerShell Core script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addSpnToEnvironment"::: -->
:::moniker range=">=azure-pipelines-2020"

**`addSpnToEnvironment`** - **Access service principal details in script**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Adds the service principal ID, service principal key, and tenant ID of the Azure endpoint you chose to the script's execution environment. You can use the `servicePrincipalId`, `servicePrincipalKey` and `tenantId` variables in your script.

This is honored only when the Azure endpoint has service principal authentication scheme.

The following list shows the syntax to access environment variables based on the script type.

* PowerShell script syntax: `$env:servicePrincipalId`

* Batch script syntax: `%servicePrincipalId%`

* Shell script syntax: `$servicePrincipalId`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useGlobalConfig"::: -->
:::moniker range=">=azure-pipelines-2020"

**`useGlobalConfig`** - **Use global Azure CLI configuration**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this input is false, this task will use its own [Azure CLI configuration directory](/cli/azure/azure-cli-configuration#cli-configuration-file). Use this task to run Azure CLI tasks in *parallel* releases.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2020"

**`workingDirectory`** - **Working Directory**<br>
Input alias: `cwd`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Current working directory where the script is run. If left blank, this input is the root of the repo (build) or artifacts (release), which is `$(System.DefaultWorkingDirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStandardError"::: -->
:::moniker range=">=azure-pipelines-2020"

**`failOnStandardError`** - **Fail on Standard Error**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this input is true, this task will fail when any errors are written to the StandardError stream. Clear the checkbox to ignore standard errors and instead rely on exit codes to determine the status.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="powerShellIgnoreLASTEXITCODE"::: -->
:::moniker range=">=azure-pipelines-2020"

**`powerShellIgnoreLASTEXITCODE`** - **Ignore $LASTEXITCODE**<br>
`boolean`. Optional. Use when `scriptType = ps || scriptType = pscore`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this input is false, the line `if ((Test-Path -LiteralPath variable:\LASTEXITCODE)) { exit $LASTEXITCODE }` is appended to the end of your script. This will propagate the last exit code from an external command as the exit code of PowerShell. Otherwise, the line is not appended to the end of your script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

### What's new in Version task version 2.0

* Support for PowerShell and PowerShell Core script.
* PowerShell Core works with cross-platform agents (Linux, macOS, or Windows), make sure the agent has PowerShell version 6 or more.
* Powershell script works with only Windows agent, make sure the agent has PowerShell version 5 or below.

### Prerequisites

* A Microsoft Azure subscription.
* [Azure Resource Manager service connection](/azure/devops/pipelines/library/connect-to-azure) to your Azure account.
* Microsoft hosted agents have Azure CLI pre-installed. However if you are using private agents, [install Azure CLI](/cli/azure/install-azure-cli) on the computer(s) that run the build and release agent. If an agent is already running on the machine on which the Azure CLI is installed, restart the agent to ensure all the relevant stage variables are updated.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

The following example lists the version of Azure CLI and gets the details of the subscription.

```yaml
- task: AzureCLI@2
  displayName: Azure CLI
  inputs:
    azureSubscription: <Name of the Azure Resource Manager service connection>
    scriptType: ps
    scriptLocation: inlineScript
    inlineScript: |
      az --version
      az account show
```

The following example illustrates how to pass arguments to your script.

* Passing arguments to inline scripts:

    ```yaml
    - task: AzureCLI@2
      inputs:
        azureSubscription: <Azure_Resource_Manager_Service_Connection>
        scriptType: 'ps'
        scriptLocation: 'inlineScript'
        arguments: '$(AZURE_STORAGE_ACCOUNT) $(AZURE_STORAGE_KEY)'
        inlineScript: './scripts/publish.ps1 $1 $2'
    ```

* Passing arguments with script path:

    ```yaml
    - task: AzureCLI@2
      inputs:
        azureSubscription: <Azure_Resource_Manager_Service_Connection>
        scriptType: 'ps'
        scriptLocation: 'scriptPath'
        arguments: '$(AZURE_STORAGE_ACCOUNT) $(AZURE_STORAGE_KEY)'
        scriptPath: './scripts/publish.ps1'
    ```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.0.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
### See also

* [Azure Resource Group Deployment](azure-resource-group-deployment-v2.md)
* [Azure Cloud Service Deployment](azure-cloud-powershell-deployment-v1.md)
* [Azure Web App Deployment](azure-web-app-v1.md)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->