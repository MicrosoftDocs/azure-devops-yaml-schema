---
title: AzureCLI@3 - Azure CLI v3 task
description: Run Azure CLI commands against an Azure subscription in a PowerShell Core/Shell script when running on Linux agent or PowerShell/PowerShell Core/Batch script when running on Windows agent. (task verion 3)
ms.date: 04/27/2026
monikerRange: "=azure-pipelines"
---

# AzureCLI@3 - Azure CLI v3 task

<!-- :::description::: -->
:::moniker range=">azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Run Azure CLI commands against an Azure subscription in a PowerShell Core/Shell script when running on Linux agent or PowerShell/PowerShell Core/Batch script when running on Windows agent.

> [!NOTE]
> This task is released as part of the [Access Azure DevOps with Microsoft Entra workload identity](/azure/devops/pipelines/library/add-devops-entra-service-connection) feature, and is rolling out this week and next. If you don't see the feature yet on your Azure DevOps Services project, check back in a few days.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure CLI v3
# Run Azure CLI commands against an Azure subscription in a PowerShell Core/Shell script when running on Linux agent or PowerShell/PowerShell Core/Batch script when running on Windows agent.
- task: AzureCLI@3
  inputs:
    connectionType: 'azureRM' # 'azureRM' | 'azureDevOps'. Required. Connection Type. Default: azureRM.
    azureSubscription: # string. Alias: connectedServiceNameARM. Required when connectionType = azureRM. Azure Resource Manager connection. 
    #azureDevOpsServiceConnection: # string. Required when connectionType = azureDevOps. Azure DevOps Service Connection. 
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
    #visibleAzLogin: true # boolean. az login output visibility. Default: true.
    #allowNoSubscriptions: false # boolean. Allow no Azure subscriptions. Default: false.
    #keepAzSessionActive: false # boolean. [Experimental] Keep Azure CLI session active. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="connectionType"::: -->
:::moniker range=">azure-pipelines-server"

**`connectionType`** - **Connection Type**<br>
`string`. Required. Allowed values: `azureRM` (Azure Resource Manager), `azureDevOps` (Azure DevOps). Default value: `azureRM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Type of service connection to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range=">azure-pipelines-server"

**`azureSubscription`** - **Azure Resource Manager connection**<br>
[Input alias](index.md#what-are-task-input-aliases): `connectedServiceNameARM`. `string`. Required when `connectionType = azureRM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify an Azure Resource Manager service connection for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureDevOpsServiceConnection"::: -->
:::moniker range=">azure-pipelines-server"

**`azureDevOpsServiceConnection`** - **Azure DevOps Service Connection**<br>
`string`. Required when `connectionType = azureDevOps`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify an Azure DevOps service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scriptType"::: -->
:::moniker range=">azure-pipelines-server"

**`scriptType`** - **Script Type**<br>
`string`. Required. Allowed values: `ps` (PowerShell), `pscore` (PowerShell Core), `batch`, `bash` (Shell).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Type of script. Select a `bash` or `pscore` script when running on Linux agent. Or, select a `batch`, `ps`, or `pscore` script when running on Windows agent. A `pscore` script can run on cross-platform agents (Linux, macOS, or Windows).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scriptLocation"::: -->
:::moniker range=">azure-pipelines-server"

**`scriptLocation`** - **Script Location**<br>
`string`. Required. Allowed values: `inlineScript` (Inline script), `scriptPath` (Script path). Default value: `scriptPath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to script: File path or Inline script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scriptPath"::: -->
:::moniker range=">azure-pipelines-server"

**`scriptPath`** - **Script Path**<br>
`string`. Required when `scriptLocation = scriptPath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fully qualified path of the script. Use `.ps1`, `.bat`, or `.cmd` when using Windows-based agent. Use `.ps1` or `.sh` when using Linux-based agent or a path relative to the the default working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="inlineScript"::: -->
:::moniker range=">azure-pipelines-server"

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
:::moniker range=">azure-pipelines-server"

**`arguments`** - **Script Arguments**<br>
[Input alias](index.md#what-are-task-input-aliases): `scriptArguments`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Arguments passed to the script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="powerShellErrorActionPreference"::: -->
:::moniker range=">azure-pipelines-server"

**`powerShellErrorActionPreference`** - **ErrorActionPreference**<br>
`string`. Optional. Use when `scriptType = ps || scriptType = pscore`. Allowed values: `stop`, `continue`, `silentlyContinue`. Default value: `stop`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prepends the line `$ErrorActionPreference = 'VALUE'` at the top of your powershell/powershell core script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addSpnToEnvironment"::: -->
:::moniker range=">azure-pipelines-server"

**`addSpnToEnvironment`** - **Access service principal details in script**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Adds service principal id, service principal key and tenant id of the Azure endpoint you chose to the script's execution environment. You can use variables: `servicePrincipalId`, `servicePrincipalKey` and `tenantId` in your script.

This is honored only when the Azure endpoint has Service Principal authentication scheme.

Syntax to access environment variables based on script type.

Powershell script: $env:servicePrincipalId

Batch script: %servicePrincipalId% 

Shell script: $servicePrincipalId.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useGlobalConfig"::: -->
:::moniker range=">azure-pipelines-server"

**`useGlobalConfig`** - **Use global Azure CLI configuration**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this input is false, this task will use its own separate [Azure CLI configuration directory](/cli/azure/azure-cli-configuration#cli-configuration-file). This can be used to run Azure CLI tasks in *parallel* releases.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">azure-pipelines-server"

**`workingDirectory`** - **Working Directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `cwd`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the working directory where the script is run. If left blank, the default is the root of the repo (build) or artifacts (release), which is []`$(System.DefaultWorkingDirectory)`](/azure/devops/pipelines/build/variables#system-variables).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStandardError"::: -->
:::moniker range=">azure-pipelines-server"

**`failOnStandardError`** - **Fail on Standard Error**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, this task will fail when any errors are written to the StandardError stream. Unselect the checkbox to ignore standard errors and rely on exit codes to determine the status.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="powerShellIgnoreLASTEXITCODE"::: -->
:::moniker range=">azure-pipelines-server"

**`powerShellIgnoreLASTEXITCODE`** - **Ignore $LASTEXITCODE**<br>
`boolean`. Optional. Use when `scriptType = ps || scriptType = pscore`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is false, the line `if ((Test-Path -LiteralPath variable:\LASTEXITCODE)) { exit $LASTEXITCODE }` is appended to the end of your script. This will cause the last exit code from an external command to be propagated as the exit code of powershell. Otherwise the line is not appended to the end of your script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="visibleAzLogin"::: -->
:::moniker range=">azure-pipelines-server"

**`visibleAzLogin`** - **az login output visibility**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is set to true, az login command will output to the task. Setting it to false will suppress the az login output.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowNoSubscriptions"::: -->
:::moniker range=">azure-pipelines-server"

**`allowNoSubscriptions`** - **Allow no Azure subscriptions**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If true, the task will not attempt to set a subscription context and will allow logins where the identity has access to no subscriptions. You can also supply an all-zero SubscriptionID (00000000-0000-0000-0000-000000000000) in the service connection to implicitly skip setting the subscription context.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="keepAzSessionActive"::: -->
:::moniker range=">azure-pipelines-server"

**`keepAzSessionActive`** - **[Experimental] Keep Azure CLI session active**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When enabled, this task will continuously sign into Azure to avoid AADSTS700024 errors when requesting access tokens beyond the IdToken expiry date. Note that this feature is EXPERIMENTAL, may not work in all scenarios and you are using it without any guarantees. Valid only for service connections using the Workload Identity Federation authentication scheme.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">azure-pipelines-server"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

### What's new in Version task version 3.0

- Support for dual connection types: Azure Resource Manager and Azure DevOps service connections.
- Azure DevOps CLI integration with automatic extension installation and configuration.
- Workload Identity Federation support for Azure DevOps connections.
- Added 'Allow no Azure subscriptions' option to support identities with no subscription access.

### Prerequisites

- A Microsoft Azure subscription.
- [Azure Resource Manager service connection](/azure/devops/pipelines/library/connect-to-azure) to your Azure account.
- Microsoft hosted agents have Azure CLI pre-installed. However if you are using private agents, [install Azure CLI](/cli/azure/install-azure-cli) on the computer(s) that run the build and release agent. If an agent is already running on the machine on which the Azure CLI is installed, restart the agent to ensure all the relevant stage variables are updated.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="=azure-pipelines"

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
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->