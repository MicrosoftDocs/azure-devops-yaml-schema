---
title: PowerShell@1 - PowerShell v1 task
description: Run a PowerShell script.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# PowerShell@1 - PowerShell v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Run a PowerShell script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# PowerShell v1
# Run a PowerShell script.
- task: PowerShell@1
  inputs:
    scriptType: 'filePath' # 'inlineScript' | 'filePath'. Required. Type. Default: 'filePath'.
    scriptName: # string. Required when scriptType = filePath. Script Path. 
    #arguments: # string. Arguments. 
    #inlineScript: # string. Required when scriptType = inlineScript. Inline Script. 
  # Advanced
    #workingFolder: # string. Working folder. 
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

<!-- :::item name="scriptType"::: -->
:::moniker range="<=azure-pipelines"

**`scriptType`** - **Type**<br>
Type: string. Required. Allowed values: 'inlineScript', 'filePath'. Default value: 'filePath'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Type of the script: File Path or Inline Script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scriptName"::: -->
:::moniker range="<=azure-pipelines"

**`scriptName`** - **Script Path**<br>
Type: string. Required when scriptType = filePath.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path of the script to execute. Should be fully qualified path or relative to the default working directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Arguments passed to the PowerShell script. Either ordinal parameters or named parameters. For example, `-Name someName -Path -Value "Some long string value"`.

`arguments` is not used when `targetType` is `inline`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingFolder"::: -->
:::moniker range="<=azure-pipelines"

**`workingFolder`** - **Working folder**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Current working directory when script is run. Defaults to the folder where the script is located.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="inlineScript"::: -->
:::moniker range="<=azure-pipelines"

**`inlineScript`** - **Inline Script**<br>
Type: string. Required when scriptType = inlineScript.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Contents of the script. The maximum supported inline script length is 32766 characters. If you need more than that limit allows, use a script from file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStandardError"::: -->
:::moniker range="<=azure-pipelines"

**`failOnStandardError`** - **Fail on Standard Error**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, this task will fail if any errors are written to the error pipeline, or if any data is written to the Standard Error stream. Otherwise the task will rely solely on $LASTEXITCODE and the exit code to determine failure.
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

`PowerShell@1` runs only on Windows agents. To run PowerShell on other agent types, use [PowerShell@2](powershell-v2.md).

Each PowerShell session lasts only for the duration of the job in which it runs. Tasks that depend on what has been bootstrapped must be in the same job as the bootstrap.

### Set a variable so it can be read by subsequent scripts and tasks

To learn more about defining build variables in a script, see [Define and modify your build variables in a script](/azure/devops/pipelines/process/variables#set-a-multi-job-output-variable).

To learn more about defining release variables in a script, see [Define and modify your release variables in a script](/azure/devops/pipelines/release/variables#use-custom-variables).

### Passing pipeline secrets in script, but secret is not masked in pipeline logs

Be aware that PowerShell cuts off error message, so if you use some secrets in the script - they could be trimmed as well, and won't be masked in this case. For example, for the inline script below:

```powershell
./script.ps1 --arg1 value1 --arg2 <some_secret_which_will_be_masked_here>
```

There could be an exception like: `At <path_to_temp_script_file>:4 char:3`:

```powershell
+   ./script.ps1 --arg1 value1 --arg2 <unmasked_part_of_original_secret> ...
+   ~~~~~~~~~~
    + <Additional exception details>
```

To avoid this issue you can handle such exceptions on a script level, or avoid cases when secrets could appear in the source code line in the error message.
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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: DotNetFramework |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.102 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Use a PowerShell script to customize your pipeline - ApplyVersionToAssemblies.ps1](/azure/devops/pipelines/scripts/powershell)
* Learn more about PowerShell scripts
  * [Scripting with Windows PowerShell](/powershell/scripting/overview)
  * [Microsoft Script Center (the Scripting Guys)](https://technet.microsoft.com/scriptcenter/bb410849.aspx)
  * [Windows PowerShell Tutorial](http://www.computerperformance.co.uk/powershell/index.htm)
  * [PowerShell.org](https://powershell.org/)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->