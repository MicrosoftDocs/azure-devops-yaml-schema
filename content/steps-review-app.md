---
title: steps.reviewApp definition
description: Downloads creates a resource dynamically under a deploy phase provider.
ms.date: 03/01/2023
monikerRange: ">=azure-pipelines-2020"
---

# steps.reviewApp definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
The `reviewApp` step creates a resource dynamically under a deploy phase provider.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2022"

```yaml
steps:
- reviewApp: string # Required as first property. Use this task under deploy phase provider to create a resource dynamically.
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

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

```yaml
steps:
- reviewApp: string # Required as first property. Use this task under deploy phase provider to create a resource dynamically.
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
:::moniker range=">=azure-pipelines-2020"

Definitions that that reference this definition: [steps](steps.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::item name="reviewApp"::: -->
**`reviewApp`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
Use this task under deploy phase provider to create a resource dynamically.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="condition"::: -->
**`condition`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Evaluate this condition expression to determine whether to run this task.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="continueOnError"::: -->
**`continueOnError`** [boolean](boolean.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
**`displayName`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Human-readable name for the task.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="target"::: -->
**`target`** [target](target.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Environment in which to run this task.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="enabled"::: -->
**`enabled`** [boolean](boolean.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Run this task when the job runs?
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="env"::: -->
**`env`** string dictionary.<br>
<!-- :::editable-content name="propDescription"::: -->
Variables to map into the process's environment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
ID of the step. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="timeoutInMinutes"::: -->
**`timeoutInMinutes`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Time to wait for this task to complete before the server kills it.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="retryCountOnTaskFailure"::: -->
**`retryCountOnTaskFailure`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Number of retries if the task fails.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

<!-- :::item name="reviewApp"::: -->
**`reviewApp`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
Use this task under deploy phase provider to create a resource dynamically.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="condition"::: -->
**`condition`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Evaluate this condition expression to determine whether to run this task.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="continueOnError"::: -->
**`continueOnError`** [boolean](boolean.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
**`displayName`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Human-readable name for the task.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="target"::: -->
**`target`** [target](target.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Environment in which to run this task.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="enabled"::: -->
**`enabled`** [boolean](boolean.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Run this task when the job runs?
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="env"::: -->
**`env`** string dictionary.<br>
<!-- :::editable-content name="propDescription"::: -->
Variables to map into the process's environment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
ID of the step. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="timeoutInMinutes"::: -->
**`timeoutInMinutes`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Time to wait for this task to complete before the server kills it.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

The `reviewApp` keyword is a shortcut for the [Review App task](/azure/devops/pipelines/tasks/reference/review-app-v0).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Review App task](/azure/devops/pipelines/tasks/reference/review-app-v0)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->