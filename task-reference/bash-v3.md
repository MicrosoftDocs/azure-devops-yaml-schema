---
title: Bash@3 - Bash v3 task
description: Run a Bash script on macOS, Linux, or Windows.
ms.date: 05/06/2025
monikerRange: "<=azure-pipelines"
---

# Bash@3 - Bash v3 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to run a Bash script on macOS, Linux, or Windows.

>[!NOTE]
> On a Windows host this runs bash from the WSL default distribution. WSL must be installed and the user that the agent runs as must have a distribution setup. WSL is installed on Microsoft-hosted Windows agent images. For more information, see [Microsoft-hosted agents - Software](/azure/devops/pipelines/agents/hosted#software).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Bash v3
# Run a Bash script on macOS, Linux, or Windows.
- task: Bash@3
  inputs:
    #targetType: 'filePath' # 'filePath' | 'inline'. Type. Default: filePath.
    filePath: # string. Required when targetType = filePath. Script Path. 
    #arguments: # string. Optional. Use when targetType = filePath. Arguments. 
    #script: # string. Required when targetType = inline. Script. 
  # Advanced
    #workingDirectory: # string. Working Directory. 
    #failOnStderr: false # boolean. Fail on Standard Error. Default: false.
    #bashEnvValue: # string. Set value for BASH_ENV environment variable.
```

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

```yaml
# Bash v3
# Run a Bash script on macOS, Linux, or Windows.
- task: Bash@3
  inputs:
    #targetType: 'filePath' # 'filePath' | 'inline'. Type. Default: filePath.
    filePath: # string. Required when targetType = filePath. Script Path. 
    #arguments: # string. Optional. Use when targetType = filePath. Arguments. 
    #script: # string. Required when targetType = inline. Script. 
  # Advanced
    #workingDirectory: # string. Working Directory. 
    #failOnStderr: false # boolean. Fail on Standard Error. Default: false.
    #noProfile: true # boolean. Don't load the profile startup/initialization files. Default: true.
    #noRc: true # boolean. Don't read the `~/.bashrc' initialization file. Default: true.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="targetType"::: -->
:::moniker range="<=azure-pipelines"

**`targetType`** - **Type**<br>
`string`. Allowed values: `filePath` (File Path), `inline`. Default value: `filePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Targets script type: file path or inline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="filePath"::: -->
:::moniker range="<=azure-pipelines"

**`filePath`** - **Script Path**<br>
`string`. Required when `targetType = filePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path of the script to execute. This must be a fully qualified path or relative to `$(System.DefaultWorkingDirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **Arguments**<br>
`string`. Optional. Use when `targetType = filePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The arguments passed to the shell script. Either ordinal parameters or named parameters.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="script"::: -->
:::moniker range="<=azure-pipelines"

**`script`** - **Script**<br>
`string`. Required when `targetType = inline`. Default value: `# Write your commands here\n\necho 'Hello world'`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The contents of the script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working Directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the working directory in which you want to run the command. If you leave it empty, the working directory is [$(Build.SourcesDirectory)](/azure/devops/pipelines/build/variables).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStderr"::: -->
:::moniker range="<=azure-pipelines"

**`failOnStderr`** - **Fail on Standard Error**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, this task will fail if any errors are written to the `StandardError` stream.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="bashEnvValue"::: -->
:::moniker range=">=azure-pipelines-2022"

**`bashEnvValue`** - **Set value for BASH_ENV environment variable**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the input is specified, its value is expanded and used as the path of a startup file to execute before running the script. If the environment variable `BASH_ENV` has already been defined, the task will override this variable only for the current task. Learn more about [Bash Startup Files](https://www.gnu.org/software/bash/manual/html_node/Bash-Startup-Files.html).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="noProfile"::: -->
:::moniker range="<=azure-pipelines-2020.1"

**`noProfile`** - **Don't load the profile startup/initialization files**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Don't load the system-wide startup file `/etc/profile` or any of the personal initialization files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="noRc"::: -->
:::moniker range="<=azure-pipelines-2020.1"

**`noRc`** - **Don't read the `~/.bashrc' initialization file**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
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

The bash task has a shortcut in YAML: [steps.bash](/azure/devops/pipelines/yaml-schema/steps-bash).

```yml
steps:
- bash: string # Required as first property. An inline script. 
  ## Other task inputs
```

The Bash task will find the first Bash implementation on your system.
Running `which bash` on Linux/macOS or `where bash` on Windows will give you an idea of which one it will select.

### Info about Bash startup files

The Bash task invokes the Bash as a non-interactive, non-login shell. When Bash is started non-interactively, to run a shell script, the Bash looks for the variable `BASH_ENV` in the environment, unfolds its value if it appears there, and uses the value as the name of a file to read and execute.

There are several options for defining the `BASH_ENV` environment variable in a pipeline. Firstly, it's possible to set the `BASH_ENV` environment variable as a pipeline variable. In this case, each instance of the Bash task will try to unfold the value of the `BASH_ENV` variable and use its value.

```YAML
variables:
  BASH_ENV: "~/.profile"

steps:
- task: Bash@3
  inputs:
    targetType: 'inline'
    script: env
```

Another option is to set `BASH_ENV` for one particular instance of the Bash task, there are two ways how this can be done:

The first way is to use the `bashEnvValue` task input, see an example for reference:

```YAML
steps:
- task: Bash@3
  inputs:
    targetType: 'inline'
    script: env
    bashEnvValue: '~/.profile'
```

Another way is to set the `BASH_ENV` variable as an environment variable for the pipeline task via the `env` keyword, for example:

```YAML
- task: Bash@3
  inputs:
    targetType: 'inline'
    script: env
  env:
    BASH_ENV: '~/.profile'
```

> [!NOTE]
> Note that if the `bashEnvValue` input is defined in the Bash task, the pipeline task will override the value of the `BASH_ENV` variable with the value from the `bashEnvValue` input in a case when the `BASH_ENV` environment variable was already defined in the environment.

:::moniker range="<=azure-pipelines"

Bash scripts checked into the repo should be set executable (`chmod +x`).
Otherwise, the task will show a warning and `source` the file instead.

:::moniker-end
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

You can map in variables using the `env` parameter which is [common across all tasks](/azure/devops/pipelines/yaml-schema/steps-task#remarks), and is list of additional items to map into the process's environment.
For example, secret variables are not automatically mapped. If you have a secret variable called `Foo`, you can map it in like this:

```YAML
steps:
- task: Bash@3
  inputs:
    targetType: 'inline'
    script: echo $MYSECRET
  env:
    MYSECRET: $(Foo)
```

On macOS or Linux, the example above is equivalent to:

```YAML
steps:
- script: echo $MYSECRET
  env:
    MYSECRET: $(Foo)
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
| Agent version |  2.115.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
