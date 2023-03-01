---
title: steps.getPackage definition
description: Downloads a package from a package management feed in Azure Artifacts or Azure DevOps Server.
ms.date: 03/01/2023
monikerRange: ">=azure-pipelines-2020"
---

# steps.getPackage definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
The `getPackage` step downloads a package from a package management feed in Azure Artifacts or Azure DevOps Server.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2022"

```yaml
steps:
- getPackage: string # Required as first property. ID for the package resource.
  path: string # Path to download the package into.
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
- getPackage: string # Required as first property. ID for the package resource.
  path: string # Path to download the package into.
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

<!-- :::item name="getPackage"::: -->
**`getPackage`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
ID for the package resource.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="path"::: -->
**`path`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Path to download the package into.
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

<!-- :::item name="getPackage"::: -->
**`getPackage`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
ID for the package resource.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="path"::: -->
**`path`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Path to download the package into.
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

The `getPackage` keyword is a shortcut for the [Download Package task](/azure/devops/pipelines/tasks/reference/download-package-v1).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Download Package task](/azure/devops/pipelines/tasks/reference/download-package-v1)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->