---
title: BatchScript@1 - Batch script v1 task
description: Run a Windows command or batch script and optionally allow it to change the environment.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# BatchScript@1 - Batch script v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Run a Windows command or batch script and optionally allow it to change the environment.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Run a windows cmd or bat script and optionally allow it to change the environment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Batch script v1
# Run a Windows command or batch script and optionally allow it to change the environment.
- task: BatchScript@1
  inputs:
    filename: # string. Required. Path. 
    #arguments: # string. Arguments. 
    #modifyEnvironment: False # boolean. Modify Environment. Default: False.
  # Advanced
    #workingFolder: # string. Working folder. 
    #failOnStandardError: false # boolean. Fail on Standard Error. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Batch Script v1
# Run a windows cmd or bat script and optionally allow it to change the environment.
- task: BatchScript@1
  inputs:
    filename: # string. Required. Path. 
    #arguments: # string. Arguments. 
    #modifyEnvironment: False # boolean. Modify Environment. Default: False.
  # Advanced
    #workingFolder: # string. Working folder. 
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

<!-- :::item name="filename"::: -->
:::moniker range="<=azure-pipelines"

**`filename`** - **Path**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path of the cmd or bat script to execute. Should be fully qualified path or relative to the default working directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Arguments passed to the cmd or bat script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="modifyEnvironment"::: -->
:::moniker range="<=azure-pipelines"

**`modifyEnvironment`** - **Modify Environment**<br>
Type: boolean. Default value: False.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Determines whether environment variable modifications will affect subsequent tasks.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingFolder"::: -->
:::moniker range="<=azure-pipelines"

**`workingFolder`** - **Working folder**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Current working directory when script is run.  Defaults to the folder where the script is located.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStandardError"::: -->
:::moniker range="<=azure-pipelines"

**`failOnStandardError`** - **Fail on Standard Error**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, this task will fail if any errors are written to the StandardError stream.
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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: Cmd |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.83.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->