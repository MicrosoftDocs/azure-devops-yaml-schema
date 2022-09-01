---
title: CmdLine@2 - Command line v2 task
description: Run a command line script using Bash on Linux and macOS and cmd.exe on Windows.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# CmdLine@2 - Command line v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Run a command line script using Bash on Linux and macOS and cmd.exe on Windows.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Command Line v2
# Run a command line script using Bash on Linux and macOS and cmd.exe on Windows.
- task: CmdLine@2
  inputs:
    script: # string. Required. Script. 
  # Advanced
    #workingDirectory: # string. Working Directory. 
    #failOnStderr: false # boolean. Fail on Standard Error. Default: false.
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

<!-- :::item name="script"::: -->
:::moniker range=">=azure-pipelines-2019"

**`script`** - **Script**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Contents of the script you want to run.
Default value: `echo Write your commands here\n\necho Hello world\n"`.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`script`** - **Script**<br>
Type: string. Required. Default value: 'echo Write your commands here'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Contents of the script you want to run.
Default value: `echo Write your commands here\n\necho Hello world\n"`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working Directory**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the working directory in which you want to run the command. If you leave it empty, the working directory is [$(Build.SourcesDirectory)](/azure/devops/pipelines/build/variables).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStderr"::: -->
:::moniker range="<=azure-pipelines"

**`failOnStderr`** - **Fail on Standard Error**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, this task will fail if any errors are written to the stderr.
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
## Remarks

Command line has a shortcut in YAML: [steps.script](/azure/devops/pipelines/yaml-schema/steps-script).

```yml
- script: # script path or inline
  workingDirectory: #
  displayName: #
  failOnStderr: #
  env: { string: string } # mapping of environment variables to add
```

### Running batch and .CMD files

Azure Pipelines puts your inline script contents into a temporary batch file (.cmd) in order to run it.
When you want to run a batch file from another batch file in Windows CMD, you must use the `call` command, otherwise the first batch file is terminated.
This will result in Azure Pipelines running your intended script up until the first batch file, then running the batch file, then ending the step.
Additional lines in the first script wouldn't be run.
You should always prepend `call` before executing a batch file in an Azure Pipelines script step.

> [!IMPORTANT]
> You may not realize you're running a batch file.
> For example, `npm` on Windows, along with any tools that you install using `npm install -g`, are actually batch files.
> Always use `call npm <command>` to run NPM commands in a Command Line task on Windows.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yaml
steps:
- script: date /t
  displayName: Get the date
- script: dir
  workingDirectory: $(Agent.BuildDirectory)
  displayName: List contents of a folder
- script: |
    set MYVAR=foo
    set
  displayName: Set a variable and then display all
  env:
    aVarFromYaml: someValue
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
| Agent version | All supported agent versions. |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* Learn how to use [verbose logs](/azure/devops/pipelines/troubleshooting/review-logs#configure-verbose-logs) for [troubleshooting](/azure/devops/pipelines/troubleshooting/troubleshooting).
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->