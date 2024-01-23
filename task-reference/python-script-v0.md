---
title: PythonScript@0 - Python script v0 task
description: Run a Python file or inline script.
ms.date: 01/22/2024
monikerRange: ">=azure-pipelines-2019"
---

# PythonScript@0 - Python script v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to run a Python file or inline script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Python script v0
# Run a Python file or inline script.
- task: PythonScript@0
  inputs:
    scriptSource: 'filePath' # 'filePath' | 'inline'. Required. Script source. Default: filePath.
    scriptPath: # string. Required when scriptSource = filePath. Script path. 
    #script: # string. Required when scriptSource = inline. Script. 
    #arguments: # string. Arguments. 
  # Advanced
    #pythonInterpreter: # string. Python interpreter. 
    #workingDirectory: # string. Working directory. 
    #failOnStderr: false # boolean. Fail on standard error. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Python Script v0
# Run a Python script.
- task: PythonScript@0
  inputs:
    scriptSource: 'filePath' # 'filePath' | 'inline'. Required. Script source. Default: filePath.
    scriptPath: # string. Required when scriptSource = filePath. Script path. 
    #script: # string. Required when scriptSource = inline. Script. 
    #arguments: # string. Arguments. 
  # Advanced
    #pythonInterpreter: # string. Python interpreter. 
    #workingDirectory: # string. Working directory. 
    #failOnStderr: false # boolean. Fail on standard error. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="scriptSource"::: -->
:::moniker range=">=azure-pipelines-2019"

**`scriptSource`** - **Script source**<br>
`string`. Required. Allowed values: `filePath` (File path), `inline`. Default value: `filePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether the script is a file in the source tree or is written inline in this task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scriptPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`scriptPath`** - **Script path**<br>
`string`. Required when `scriptSource = filePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path of the script to execute. Must be a fully qualified path or relative to `$(System.DefaultWorkingDirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="script"::: -->
:::moniker range=">=azure-pipelines-2019"

**`script`** - **Script**<br>
`string`. Required when `scriptSource = inline`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Python script to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range=">=azure-pipelines-2019"

**`arguments`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the arguments passed to the script execution available through `sys.argv`, as if you passed them on the command line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pythonInterpreter"::: -->
:::moniker range=">=azure-pipelines-2019"

**`pythonInterpreter`** - **Python interpreter**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the absolute path to the Python interpreter to use. If not specified, the task will use the interpreter in PATH.  
Run the [Use Python Version](https://go.microsoft.com/fwlink/?linkid=871498) task to add a version of Python to PATH.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`workingDirectory`** - **Working directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the working directory where the script will run. If not specified, the value of `System.DefaultWorkingDirectory` will be used. For builds, this variable defaults to the root of the repository. For releases, it defaults to the root of the artifacts directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStderr"::: -->
:::moniker range=">=azure-pipelines-2019"

**`failOnStderr`** - **Fail on standard error**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, this task will fail if any text is written to the `stderr` stream.
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

By default, this task will invoke `python` from the system path.
Run [Use Python Version](use-python-version-v0.md) to put the version you want in the system path.
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
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->