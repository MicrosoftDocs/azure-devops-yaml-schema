---
title: steps.download definition
description: Downloads artifacts associated with the current run or from another Azure Pipeline that is associated as a pipeline resource.
ms.date: 10/19/2023
monikerRange: ">=azure-pipelines-2019"
---

# steps.download definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
The `download` step downloads artifacts associated with the current run or from another Azure Pipeline that is associated as a pipeline resource.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2022"

```yaml
steps:
- download: string # Required as first property. Specify current, pipeline resource identifier, or none to disable automatic download.
  artifact: string # Artifact name.
  patterns: string # Pattern to download files from artifact.
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
- download: string # Required as first property. Specify current, pipeline resource identifier, or none to disable automatic download.
  artifact: string # Artifact name.
  patterns: string # Pattern to download files from artifact.
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
- download: string # Required as first property. Specify current, pipeline resource identifier, or none to disable automatic download.
  artifact: string # Artifact name.
  patterns: string # Pattern to download files from artifact.
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

Definitions that reference this definition: [steps](steps.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="download"::: -->
:::moniker range=">=azure-pipelines-2019"

**`download`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Specify current, pipeline resource identifier, or none to disable automatic download.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifact"::: -->
:::moniker range=">=azure-pipelines-2019"

**`artifact`** string.<br><!-- :::editable-content name="propDescription"::: -->
Artifact name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="patterns"::: -->
:::moniker range=">=azure-pipelines-2019"

**`patterns`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pattern to download files from artifact.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="condition"::: -->
:::moniker range=">=azure-pipelines-2019"

**`condition`** string.<br><!-- :::editable-content name="propDescription"::: -->
Evaluate this condition expression to determine whether to run this task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="continueOnError"::: -->
:::moniker range=">=azure-pipelines-2019"

**`continueOnError`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`displayName`** string.<br><!-- :::editable-content name="propDescription"::: -->
Human-readable name for the task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="target"::: -->
:::moniker range=">=azure-pipelines-2020"

**`target`** [target](target.md).<br><!-- :::editable-content name="propDescription"::: -->
Environment in which to run this task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enabled"::: -->
:::moniker range=">=azure-pipelines-2019"

**`enabled`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Run this task when the job runs?
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="env"::: -->
:::moniker range=">=azure-pipelines-2019"

**`env`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Variables to map into the process's environment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
:::moniker range=">=azure-pipelines-2019"

**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
ID of the step. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="timeoutInMinutes"::: -->
:::moniker range=">=azure-pipelines-2019"

**`timeoutInMinutes`** string.<br><!-- :::editable-content name="propDescription"::: -->
Time to wait for this task to complete before the server kills it.

[!INCLUDE [task-timeout](./includes/task-timeout.md)]
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="retryCountOnTaskFailure"::: -->
:::moniker range=">=azure-pipelines-2022"

**`retryCountOnTaskFailure`** string.<br><!-- :::editable-content name="propDescription"::: -->
Number of retries if the task fails.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

The `download` keyword downloads linked artifact resources.

Depending on the type of linked artifacts, `download` calls [Download Pipeline Artifacts](/azure/devops/pipelines/tasks/reference/download-pipeline-artifact-v2) (if your pipeline is running in Azure DevOps Services), [Download Build Artifacts](/azure/devops/pipelines/tasks/reference/download-build-artifacts-v1) (if your pipeline is running in Azure DevOps Server), or [Download artifacts from file share](/azure/devops/pipelines/tasks/reference/download-fileshare-artifacts-v1).

### Artifact download location

Artifacts from the current pipeline are downloaded to `$(Pipeline.Workspace)/<artifact name>`.

Artifacts from the associated pipeline resource are downloaded to `$(Pipeline.Workspace)/<pipeline resource identifier>/<artifact name>`.

### Automatic download in deployment jobs

All available artifacts from the current pipeline and from the associated pipeline resources are automatically downloaded in deployment jobs and made available for your deployment.

To prevent downloads, specify `download: none`.

## Examples

```yaml
steps:
- download: current  # refers to artifacts published by current pipeline
  artifact: WebApp
  patterns: '**/.js'
  displayName: Download artifact WebApp
- download: MyAppA   # downloads artifacts available as part of the pipeline resource specified as MyAppA
```
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Publish and download pipeline Artifacts](/azure/devops/pipelines/artifacts/pipeline-artifacts)
- [Download Pipeline Artifacts task](/azure/devops/pipelines/tasks/reference/download-pipeline-artifact-v2)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->