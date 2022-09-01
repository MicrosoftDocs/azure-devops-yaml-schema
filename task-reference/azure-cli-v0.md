---
title: AzureCLI@0 - Azure CLI Preview v0 task
description: Run a Shell or Batch script with Azure CLI commands against an azure subscription.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# AzureCLI@0 - Azure CLI Preview v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Run a Shell or Batch script with Azure CLI commands against an azure subscription.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Azure CLI Preview v0
# Run a Shell or Batch script with Azure CLI commands against an azure subscription.
- task: AzureCLI@0
  inputs:
    connectedServiceNameSelector: 'connectedServiceNameARM' # 'connectedServiceName' | 'connectedServiceNameARM'. Required. Azure Connection Type. Default: 'connectedServiceNameARM'.
    connectedServiceNameARM: # string. Required when connectedServiceNameSelector = connectedServiceNameARM. AzureRM Subscription. 
    #connectedServiceName: # string. Required when connectedServiceNameSelector = connectedServiceName. Azure Classic Subscription. 
    scriptLocation: 'scriptPath' # 'inlineScript' | 'scriptPath'. Required. Script Location. Default: 'scriptPath'.
    scriptPath: # string. Required when scriptLocation = scriptPath. Script Path. 
    #inlineScript: # string. Required when scriptLocation = inlineScript. Inline Script. 
    #args: # string. Arguments. 
  # Advanced
    #cwd: # string. Working Directory. 
    #failOnStandardError: true # boolean. Fail on Standard Error. Default: true.
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

<!-- :::item name="connectedServiceNameSelector"::: -->
:::moniker range="<=azure-pipelines"

**`connectedServiceNameSelector`** - **Azure Connection Type**<br>
Type: string. Required. Allowed values: 'connectedServiceName', 'connectedServiceNameARM'. Default value: 'connectedServiceNameARM'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure connection type for the Deployment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="connectedServiceNameARM"::: -->
:::moniker range="<=azure-pipelines"

**`connectedServiceNameARM`** - **AzureRM Subscription**<br>
Type: string. Required when connectedServiceNameSelector = connectedServiceNameARM.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription for the deployment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="connectedServiceName"::: -->
:::moniker range="<=azure-pipelines"

**`connectedServiceName`** - **Azure Classic Subscription**<br>
Type: string. Required when connectedServiceNameSelector = connectedServiceName.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Classic subscription for the deployment.
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
You can write your scripts inline here. For batch files use the prefix "call" before every azure command. You can also pass predefined and custom variables to this script using arguments 

 example for shell: azure --version || azure account show 

 example for batch: call  azure --version || call azure account show.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="args"::: -->
:::moniker range="<=azure-pipelines"

**`args`** - **Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Arguments passed to the script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cwd"::: -->
:::moniker range="<=azure-pipelines"

**`cwd`** - **Working Directory**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Current working directory where the script is run.  Empty is the root of the repo (build) or artifacts (release), which is $(System.DefaultWorkingDirectory).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStandardError"::: -->
:::moniker range="<=azure-pipelines"

**`failOnStandardError`** - **Fail on Standard Error**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, this task will fail when any errors are written to the StandardError stream.
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
| [Demands](/azure/devops/pipelines/process/demands) | None |
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