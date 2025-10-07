---
title: AzureCLI@1 - Azure CLI v1 task
description: Run Azure CLI commands against an Azure subscription in a Shell script when running on Linux agent or Batch script when running on Windows agent.
ms.date: 10/07/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
---

# AzureCLI@1 - Azure CLI v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Run Azure CLI commands against an Azure subscription in a shell script when running on Linux agent or batch script when running on Windows agent.
<!-- :::editable-content-end::: -->

:::moniker-end

<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Azure CLI v1
# Run Azure CLI commands against an Azure subscription in a Shell script when running on Linux agent or Batch script when running on Windows agent.
- task: AzureCLI@1
  inputs:
    azureSubscription: # string. Alias: connectedServiceNameARM. Required. Azure subscription. 
    scriptLocation: 'scriptPath' # 'inlineScript' | 'scriptPath'. Required. Script Location. Default: scriptPath.
    scriptPath: # string. Required when scriptLocation = scriptPath. Script Path. 
    #inlineScript: # string. Required when scriptLocation = inlineScript. Inline Script. 
    #arguments: # string. Alias: args. Arguments. 
  # Advanced
    #addSpnToEnvironment: false # boolean. Access service principal details in script. Default: false.
    #useGlobalConfig: false # boolean. Use global Azure CLI configuration. Default: false.
    #workingDirectory: # string. Alias: cwd. Working Directory. 
    #failOnStandardError: false # boolean. Fail on Standard Error. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
[Input alias](index.md#what-are-task-input-aliases): `connectedServiceNameARM`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects an Azure Resource Manager subscription for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scriptLocation"::: -->
:::moniker range="<=azure-pipelines"

**`scriptLocation`** - **Script Location**<br>
`string`. Required. Allowed values: `inlineScript` (Inline script), `scriptPath` (Script path). Default value: `scriptPath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the script location.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`scriptPath`** - **Script Path**<br>
`string`. Required when `scriptLocation = scriptPath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fully qualified path of the script or a path relative to the the default working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="inlineScript"::: -->
:::moniker range="<=azure-pipelines"

**`inlineScript`** - **Inline Script**<br>
`string`. Required when `scriptLocation = inlineScript`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You can write your scripts inline here. When using Windows agent, use batch scripting. Use shell scripting when using Linux-based agents. For batch files, use the prefix `call` before every Azure command. You can also pass predefined and custom variables to this script using arguments 

See the following examples. The first is a shell example and the second is a batch example:

```
azure --version || azure account show 
```
```
call  azure --version || call azure account show
```
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **Arguments**<br>
[Input alias](index.md#what-are-task-input-aliases): `args`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Arguments passed to the script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addSpnToEnvironment"::: -->
:::moniker range="<=azure-pipelines"

**`addSpnToEnvironment`** - **Access service principal details in script**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Adds the service principal ID and key of the Azure endpoint that you chose to the script's execution environment. You can use the `$servicePrincipalId` and `$servicePrincipalKey` variables in your script.

This is honored only when the Azure endpoint has Service Principal authentication scheme.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useGlobalConfig"::: -->
:::moniker range="<=azure-pipelines"

**`useGlobalConfig`** - **Use global Azure CLI configuration**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is false, this task will use its own separate [Azure CLI configuration directory](/cli/azure/azure-cli-configuration#cli-configuration-file). This can be used to run Azure CLI tasks in *parallel* releases.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working Directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `cwd`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Current working directory where the script is run. If left blank, this input is the root of the repo (build) or artifacts (release), which is `$(System.DefaultWorkingDirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStandardError"::: -->
:::moniker range="<=azure-pipelines"

**`failOnStandardError`** - **Fail on Standard Error**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this input is true, this task will fail when any errors are written to the StandardError stream. Clear the checkbox to ignore standard errors and instead rely on exit codes to determine the status.
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

What's new in Version 1.0:
   - Supports the new Azure CLI 2.0 which is Python based
   - Works with cross-platform agents (Linux, macOS, or Windows)
   - For working with Azure CLI 1.0 (node.js-based), switch to task version 0.0
   - Limitations:
    - No support for Azure Classic subscriptions. Azure CLI 2.0 supports only Azure Resource Manager (ARM) subscriptions.
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