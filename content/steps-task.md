---
title: steps.task definition
description: Runs a task.
ms.date: 08/14/2025
monikerRange: "<=azure-pipelines"
author: steved0x
ms.author: sdanie
---

# steps.task definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
A `task` step runs a task.

All tasks support the following set of common properties.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2022"

```yaml
steps:
- task: string # Required as first property. Name of the task to run.
  inputs: # Inputs for the task.
    string: string # Name/value pairs
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

:::moniker range="<=azure-pipelines-2020.1"

```yaml
steps:
- task: string # Required as first property. Name of the task to run.
  inputs: # Inputs for the task.
    string: string # Name/value pairs
  condition: string # Evaluate this condition expression to determine whether to run this task.
  continueOnError: boolean # Continue running even on failure?
  displayName: string # Human-readable name for the task.
  target: string | target # Environment in which to run this task.
  enabled: boolean # Run this task when the job runs?
  env: # Variables to map into the process's environment.
    string: string # Name/value pairs
  name: string # ID of the step.
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it.
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
<!-- :::item name="task"::: -->
:::moniker range="<=azure-pipelines"

**`task`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Name of the task to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="inputs"::: -->
:::moniker range="<=azure-pipelines"

**`inputs`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Inputs for the task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="condition"::: -->
:::moniker range="<=azure-pipelines"

**`condition`** string.<br><!-- :::editable-content name="propDescription"::: -->
Evaluate this condition expression to determine whether to run this task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="continueOnError"::: -->
:::moniker range="<=azure-pipelines"

**`continueOnError`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
:::moniker range="<=azure-pipelines"

**`displayName`** string.<br><!-- :::editable-content name="propDescription"::: -->
Human-readable name for the task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="target"::: -->
:::moniker range="<=azure-pipelines"

**`target`** [target](target.md).<br><!-- :::editable-content name="propDescription"::: -->
Environment in which to run this task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enabled"::: -->
:::moniker range="<=azure-pipelines"

**`enabled`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Run this task when the job runs?
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="env"::: -->
:::moniker range="<=azure-pipelines"

**`env`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Variables to map into the process's environment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
:::moniker range="<=azure-pipelines"

**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
ID of the step. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="timeoutInMinutes"::: -->
:::moniker range="<=azure-pipelines"

**`timeoutInMinutes`** string.<br><!-- :::editable-content name="propDescription"::: -->
Time to wait for this task to complete before the server kills it. For example, to configure a 10 minute timeout, use `timeoutInMinutes: 10`.

[!INCLUDE [task-timeout](./includes/task-timeout.md)]
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="retryCountOnTaskFailure"::: -->
:::moniker range=">=azure-pipelines-2022"

**`retryCountOnTaskFailure`** number.<br><!-- :::editable-content name="propDescription"::: -->
Number of retries if the task fails. On Azure DevOps Server 2022, 2022.1, and 2022.2, retries are supported only on agent jobs. For more information, see [Azure DevOps service update November 16, 2021 - Automatic retries for a task](/azure/devops/release-notes/2021/sprint-195-update#automatic-retries-for-a-task) and [Azure DevOps service update June 14, 2025 - Retries for server tasks](/azure/devops/release-notes/2024/sprint-240-update#retries-for-server-tasks).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

[Tasks](/azure/devops/pipelines/tasks/reference) are the building blocks of a pipeline.
There's a [catalog of tasks](/azure/devops/pipelines/tasks/reference) available to choose from.

If you don't specify a command mode, you can shorten the `target` structure to:

```yaml
- task:
  target: string  # container name or the word 'host'
```

### Common task properties

All tasks support a set of common properties in addition to `name` and `inputs`. For a list of common task properties, see the preceding [Properties](#properties) section. For more information on configuring these properties, see [Task control options](/azure/devops/pipelines/process/tasks#task-control-options) and [Task environment variables](/azure/devops/pipelines/process/tasks#environment-variables).

Learn more about [conditions](/azure/devops/pipelines/process/conditions),
[timeouts](/azure/devops/pipelines/process/phases#timeouts), and [step targets](/azure/devops/pipelines/process/tasks#step-target).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yaml
steps:
- task: VSBuild@1
  displayName: Build
  timeoutInMinutes: 120
  inputs:
    solution: '**\*.sln'
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Tasks](/azure/devops/pipelines/process/tasks)
- [Catalog of tasks](/azure/devops/pipelines/tasks/reference)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
