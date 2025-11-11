---
title: ShellScript@2 - Shell script v2 task
description: Run a shell script using Bash.
ms.date: 11/11/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
---

# ShellScript@2 - Shell script v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to run a shell script using `bash`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Shell script v2
# Run a shell script using Bash.
- task: ShellScript@2
  inputs:
    scriptPath: # string. Required. Script Path. 
    #args: # string. Arguments. 
  # Advanced
    #disableAutoCwd: false # boolean. Specify Working Directory. Default: false.
    #cwd: # string. Optional. Use when disableAutoCwd = true. Working Directory. 
    #failOnStandardError: false # boolean. Fail on Standard Error. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="scriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`scriptPath`** - **Script Path**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path from the repo root to the shell script file that you want to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="args"::: -->
:::moniker range="<=azure-pipelines"

**`args`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the arguments that you want to pass to the script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="disableAutoCwd"::: -->
:::moniker range="<=azure-pipelines"

**`disableAutoCwd`** - **Specify Working Directory**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the working directory where the task runs the script. If the value is left empty, the task defaults to the folder where the script is located.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cwd"::: -->
:::moniker range="<=azure-pipelines"

**`cwd`** - **Working Directory**<br>
`string`. Optional. Use when `disableAutoCwd = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the working directory where the script is run. If the value is left empty, the task uses the root of the repo (build) or artifacts (release), which is `$(System.DefaultWorkingDirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStandardError"::: -->
:::moniker range="<=azure-pipelines"

**`failOnStandardError`** - **Fail on Standard Error**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the value is `true`, the task will fail if errors are written to the StandardError stream.
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

### Where can I learn about Bash scripts?

* [Beginners/BashScripting](https://help.ubuntu.com/community/Beginners/BashScripting) to get started.
* [Awesome Bash](https://github.com/alebcay/awesome-shell#awesome-bash) to go deeper.

### How do I set a variable so that it can be read by subsequent scripts and tasks?

To learn more about defining build variables in a script, see [Define and modify your build variables in a script](/azure/devops/pipelines/process/variables#set-a-multi-job-output-variable).

To learn more about defining release variables in a script, see [Define and modify your release variables in a script](/azure/devops/pipelines/release/variables#use-custom-variables)
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

Create `test.sh` at the root of your repo.
We recommend creating this file from a Linux environment (such as a real Linux machine or Windows Subsystem for Linux) so that line endings are correct.
Also, don't forget to `chmod +x test.sh` before you commit it.

```sh
#!/bin/bash
echo "Hello World"
echo "AGENT_WORKFOLDER is $AGENT_WORKFOLDER"
echo "AGENT_WORKFOLDER contents:"
ls -1 $AGENT_WORKFOLDER
echo "AGENT_BUILDDIRECTORY is $AGENT_BUILDDIRECTORY"
echo "AGENT_BUILDDIRECTORY contents:"
ls -1 $AGENT_BUILDDIRECTORY
echo "SYSTEM_HOSTTYPE is $SYSTEM_HOSTTYPE"
echo "Over and out."
```

Add the following task to your pipeline to run the previous script.

```yml
- task: ShellScript@2
  inputs:
    scriptPath: 'test.sh'
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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: sh |
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