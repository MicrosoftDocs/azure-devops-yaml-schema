---
title: steps.downloadBuild definition
description: Downloads build artifacts.
ms.date: 03/01/2023
monikerRange: ">=azure-pipelines-2019"
---

# steps.downloadBuild definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
The `downloadBuild` step downloads build artifacts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2022"

```yaml
steps:
- downloadBuild: string # Required as first property. ID for the build resource.
  artifact: string # Artifact name.
  path: string # Path to download the artifact into.
  patterns: string # Downloads the files which matches the patterns.
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
- downloadBuild: string # Required as first property. ID for the build resource.
  artifact: string # Artifact name.
  path: string # Path to download the artifact into.
  patterns: string # Downloads the files which matches the patterns.
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

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
steps:
- downloadBuild: string # Required as first property. ID for the build resource.
  artifact: string # Artifact name.
  path: string # Path to download the artifact into.
  patterns: string # Downloads the files which matches the patterns.
  condition: string # Evaluate this condition expression to determine whether to run this task.
  continueOnError: boolean # Continue running even on failure?
  displayName: string # Human-readable name for the task.
  enabled: boolean # Run this task when the job runs?
  env: # Variables to map into the process's environment.
    string: string # Name/value pairs
  name: string # ID of the step.
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2019"

Definitions that that reference this definition: [steps](steps.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::item name="downloadBuild"::: -->
**`downloadBuild`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
ID for the build resource.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="artifact"::: -->
**`artifact`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Artifact name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="path"::: -->
**`path`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Path to download the artifact into.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="patterns"::: -->
**`patterns`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Downloads the files which matches the patterns.
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

<!-- :::item name="downloadBuild"::: -->
**`downloadBuild`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
ID for the build resource.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="artifact"::: -->
**`artifact`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Artifact name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="path"::: -->
**`path`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Path to download the artifact into.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="patterns"::: -->
**`patterns`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Downloads the files which matches the patterns.
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

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

<!-- :::item name="downloadBuild"::: -->
**`downloadBuild`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
ID for the build resource.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="artifact"::: -->
**`artifact`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Artifact name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="path"::: -->
**`path`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Path to download the artifact into.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="patterns"::: -->
**`patterns`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Downloads the files which matches the patterns.
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

The `downloadBuild` keyword is a shortcut for the [Download Build Artifacts task](/azure/devops/pipelines/tasks/reference/download-build-artifacts-v1).

> [!NOTE]
> The pipelines team recommends upgrading from `downloadBuild` (download build artifacts task) to [download](steps-download.md) (download pipeline artifacts task) for faster performance.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [download](steps-download.md)
- [Publish and download pipeline Artifacts](/azure/devops/pipelines/artifacts/pipeline-artifacts)
- [Download Build Artifacts task](/azure/devops/pipelines/tasks/reference/download-build-artifacts-v1)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->