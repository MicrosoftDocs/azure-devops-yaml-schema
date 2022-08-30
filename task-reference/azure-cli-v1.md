---
title: AzureCLI@1 - Azure CLI v1 task
description: Run Azure CLI commands against an Azure subscription in a Shell script when running on Linux agent or Batch script when running on Windows agent.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# AzureCLI@1 - Azure CLI v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Run Azure CLI commands against an Azure subscription in a Shell script when running on Linux agent or Batch script when running on Windows agent.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Run a Shell or Batch script with Azure CLI commands against an azure subscription.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Azure CLI v1
# Run Azure CLI commands against an Azure subscription in a Shell script when running on Linux agent or Batch script when running on Windows agent.
- task: AzureCLI@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    scriptLocation: 'scriptPath' # 'inlineScript' | 'scriptPath'. Required. Script Location. Default: 'scriptPath'.
    scriptPath: # string. Required when scriptLocation = scriptPath. Script Path. 
    #inlineScript: # string. Required when scriptLocation = inlineScript. Inline Script. 
    #arguments: # string. Arguments. 
  # Advanced
    #addSpnToEnvironment: false # boolean. Access service principal details in script. Default: false.
    #useGlobalConfig: false # boolean. Use global Azure CLI configuration. Default: false.
    #workingDirectory: # string. Working Directory. 
    #failOnStandardError: false # boolean. Fail on Standard Error. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Azure CLI v1
# Run a Shell or Batch script with Azure CLI commands against an azure subscription.
- task: AzureCLI@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    scriptLocation: 'scriptPath' # 'inlineScript' | 'scriptPath'. Required. Script Location. Default: 'scriptPath'.
    scriptPath: # string. Required when scriptLocation = scriptPath. Script Path. 
    #inlineScript: # string. Required when scriptLocation = inlineScript. Inline Script. 
    #arguments: # string. Arguments. 
  # Advanced
    #workingDirectory: # string. Working Directory. 
    #failOnStandardError: false # boolean. Fail on Standard Error. Default: false.
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

<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `connectedServiceNameARM`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure resource manager subscription for the deployment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scriptLocation"::: -->
:::moniker range="<=azure-pipelines"

**`scriptLocation`** - **Script Location**<br>
Type: string. Required. Allowed values: 'inlineScript', 'scriptPath'. Default value: 'scriptPath'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Type of script: File path or Inline script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`scriptPath`** - **Script Path**<br>
Type: string. Required when scriptLocation = scriptPath.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fully qualified path of the script or a path relative to the the default working directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="inlineScript"::: -->
:::moniker range="<=azure-pipelines"

**`inlineScript`** - **Inline Script**<br>
Type: string. Required when scriptLocation = inlineScript.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You can write your scripts inline here. When using Windows agent, use batch scripting whereas use shell scripting when using Linux based agents. For batch files use the prefix "call" before every azure command. You can also pass predefined and custom variables to this script using arguments 

 example for shell: az --version || az account show 

 example for batch: call  az --version || call az account show.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **Arguments**<br>
Input alias: `args`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Arguments passed to the script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addSpnToEnvironment"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`addSpnToEnvironment`** - **Access service principal details in script**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Adds service principal id and key of the Azure endpoint you chose to the script's execution environment. You can use these variables: `$servicePrincipalId` and `$servicePrincipalKey` in your script.

This is honored only when the Azure endpoint has Service Principal authentication scheme.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useGlobalConfig"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`useGlobalConfig`** - **Use global Azure CLI configuration**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is false, this task will use its own separate [Azure CLI configuration directory](/cli/azure/azure-cli-configuration#cli-configuration-file). This can be used to run Azure CLI tasks in *parallel* releases.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working Directory**<br>
Input alias: `cwd`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Current working directory where the script is run.  Empty is the root of the repo (build) or artifacts (release), which is $(System.DefaultWorkingDirectory).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStandardError"::: -->
:::moniker range=">=azure-pipelines-2019"

**`failOnStandardError`** - **Fail on Standard Error**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, this task will fail when any errors are written to the StandardError stream. Unselect the checkbox to ignore standard errors and rely on exit codes to determine the status.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`failOnStandardError`** - **Fail on Standard Error**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, this task will fail when any errors are written to the StandardError stream. Unselect the checkbox to ignore standard errors and rely on exit codes to determine the status.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
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