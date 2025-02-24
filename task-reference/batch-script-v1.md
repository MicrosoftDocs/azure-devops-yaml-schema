---
title: BatchScript@1 - Batch script v1 task
description: Run a Windows command or batch script and optionally allow it to change the environment.
ms.date: 01/29/2025
monikerRange: "<=azure-pipelines"
---

# BatchScript@1 - Batch script v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to run a Windows `.bat` or `.cmd` script. Optionally, the `.bat` or `.cmd` script can permanently modify environment variables.
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


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="filename"::: -->
:::moniker range="<=azure-pipelines"

**`filename`** - **Path**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path of the `.cmd` or `.bat` script to execute. This should be a fully qualified path or one relative to the default working directory. (Please note that the working directory could differ from `workingFolder`, which could be specified for this task.)
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The arguments passed to the `.cmd` or `.bat` script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="modifyEnvironment"::: -->
:::moniker range="<=azure-pipelines"

**`modifyEnvironment`** - **Modify Environment**<br>
`boolean`. Default value: `False`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Determines whether environment variable modifications will affect subsequent tasks.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingFolder"::: -->
:::moniker range="<=azure-pipelines"

**`workingFolder`** - **Working folder**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The current working directory when a script is run.  This defaults to the folder where the script is located.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStandardError"::: -->
:::moniker range="<=azure-pipelines"

**`failOnStandardError`** - **Fail on Standard Error**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, this task will fail if any errors are written to the `StandardError` stream.
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

Use this task to run a Windows .bat or .cmd script.
Optionally, allow it to permanently modify environment variables.

> [!NOTE]
> This task is not compatible with Windows containers. If you need to run a batch script on a Windows container, use the [command line task](cmd-line-v2.md) instead.
> 
> For information on supporting multiple platforms, see [cross platform scripting](/azure/devops/pipelines/scripts/cross-platform-scripting).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

Create `test.bat` at the root of your repo:

```bat
@echo off
echo Hello World from %AGENT_NAME%.
echo My ID is %AGENT_ID%.
echo AGENT_WORKFOLDER contents:
@dir %AGENT_WORKFOLDER%
echo AGENT_BUILDDIRECTORY contents:
@dir %AGENT_BUILDDIRECTORY%
echo BUILD_SOURCESDIRECTORY contents:
@dir %BUILD_SOURCESDIRECTORY%
echo Over and out.
```

To run this script, add the following task to your pipeline.

```yml
- task: BatchScript@1
  inputs:
    filename: 'test.bat'
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
