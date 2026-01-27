---
title: steps.pwsh definition
description: Runs a script in PowerShell Core on Windows, macOS, and Linux.
ms.date: 01/27/2026
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# steps.pwsh definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
The `pwsh` step runs a script in PowerShell Core on Windows, macOS, and Linux.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
steps:
- pwsh: string # Required as first property. Inline PowerShell script.
  errorActionPreference: string # Unless otherwise specified, the error action preference defaults to the value stop. See the following section for more information.
  failOnStderr: string # Fail the task if output is sent to Stderr?
  ignoreLASTEXITCODE: string # Check the final exit code of the script to determine whether the step succeeded?
  workingDirectory: string # Start the script with this working directory.
  condition: string # Evaluate this condition expression to determine whether to run this task.
  continueOnError: boolean # Continue running even on failure?
  displayName: string # Human-readable name for the task.
  target: string | target # Environment in which to run this task.
  enabled: boolean # Run this task when the job runs?
  env: # Variables to map into the process's environment.
    string: string # Name/value pairs
  name: string # ID of the step.
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it.
  retryCountOnTaskFailure: string # Number of retries if the task fails.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [steps](steps.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<a name="pwsh-property"></a>
<!-- :::item name="pwsh"::: -->
:::moniker range="<=azure-pipelines"

**`pwsh`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Inline PowerShell script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="errorActionPreference-property"></a>
<!-- :::item name="errorActionPreference"::: -->
:::moniker range="<=azure-pipelines"

**`errorActionPreference`** string.<br><!-- :::editable-content name="propDescription"::: -->
Unless otherwise specified, the error action preference defaults to the value stop. See the following section for more information.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="failOnStderr-property"></a>
<!-- :::item name="failOnStderr"::: -->
:::moniker range="<=azure-pipelines"

**`failOnStderr`** string.<br><!-- :::editable-content name="propDescription"::: -->
Fail the task if output is sent to Stderr?
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="ignoreLASTEXITCODE-property"></a>
<!-- :::item name="ignoreLASTEXITCODE"::: -->
:::moniker range="<=azure-pipelines"

**`ignoreLASTEXITCODE`** string.<br><!-- :::editable-content name="propDescription"::: -->
Check the final exit code of the script to determine whether the step succeeded?
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="workingDirectory-property"></a>
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** string.<br><!-- :::editable-content name="propDescription"::: -->
Start the script with this working directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="condition-property"></a>
<!-- :::item name="condition"::: -->
:::moniker range="<=azure-pipelines"

**`condition`** string.<br><!-- :::editable-content name="propDescription"::: -->
Evaluate this condition expression to determine whether to run this task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="continueOnError-property"></a>
<!-- :::item name="continueOnError"::: -->
:::moniker range="<=azure-pipelines"

**`continueOnError`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="displayName-property"></a>
<!-- :::item name="displayName"::: -->
:::moniker range="<=azure-pipelines"

**`displayName`** string.<br><!-- :::editable-content name="propDescription"::: -->
Human-readable name for the task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="target-property"></a>
<!-- :::item name="target"::: -->
:::moniker range="<=azure-pipelines"

**`target`** [target](target.md).<br><!-- :::editable-content name="propDescription"::: -->
Environment in which to run this task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="enabled-property"></a>
<!-- :::item name="enabled"::: -->
:::moniker range="<=azure-pipelines"

**`enabled`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Run this task when the job runs?
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="env-property"></a>
<!-- :::item name="env"::: -->
:::moniker range="<=azure-pipelines"

**`env`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Variables to map into the process's environment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="name-property"></a>
<!-- :::item name="name"::: -->
:::moniker range="<=azure-pipelines"

**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
ID of the step. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="timeoutInMinutes-property"></a>
<!-- :::item name="timeoutInMinutes"::: -->
:::moniker range="<=azure-pipelines"

**`timeoutInMinutes`** string.<br><!-- :::editable-content name="propDescription"::: -->
Time to wait for this task to complete before the server kills it.

[!INCLUDE [task-timeout](./includes/task-timeout.md)]
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="retryCountOnTaskFailure-property"></a>
<!-- :::item name="retryCountOnTaskFailure"::: -->
:::moniker range="<=azure-pipelines"

**`retryCountOnTaskFailure`** string.<br><!-- :::editable-content name="propDescription"::: -->
Number of retries if the task fails.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

The `pwsh` keyword is a shortcut for the [PowerShell task](/azure/devops/pipelines/tasks/reference/powershell-v2) when that task's **pwsh** value is set to **true**.
The task runs a script in PowerShell Core on Windows, macOS, and Linux.

Learn more about [conditions](/azure/devops/pipelines/process/conditions) and [timeouts](/azure/devops/pipelines/process/phases#timeouts).

Each PowerShell session lasts only for the duration of the job in which it runs. Tasks that depend on what has been bootstrapped must be in the same job as the bootstrap.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yaml
steps:
- pwsh: Write-Host Hello $($env:name)
  displayName: Say hello
  name: firstStep
  workingDirectory: $(build.sourcesDirectory)
  failOnStderr: true
  env:
    name: Microsoft
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [PowerShell task](/azure/devops/pipelines/tasks/reference/powershell-v2)
- Learn more about [conditions](/azure/devops/pipelines/process/conditions) and [timeouts](/azure/devops/pipelines/process/phases#timeouts)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
