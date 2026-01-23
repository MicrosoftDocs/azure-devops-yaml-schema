---
title: steps.publish definition
description: Publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume.
ms.date: 01/23/2026
monikerRange: "<=azure-pipelines"
author: ramiMSFT
ms.author: rabououn
---

# steps.publish definition

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
The `publish` keyword publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
The `publish` keyword publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume.

> [!IMPORTANT]
> The `publish` step is supported on Azure DevOps Services only. If you use it on Azure DevOps Server, you'll receive an error message similar to `Pipeline Artifact Task is not supported in on-premises. Please use Build Artifact Task instead.` Use [Publish Build Artifacts](/azure/devops/pipelines/tasks/reference/publish-build-artifacts-v1) if you're using Azure DevOps Server.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
steps:
- publish: string # Required as first property. The publish step is a shortcut for the PublishPipelineArtifact@1 task. The task publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume.
  artifact: string # Artifact name.
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
<!-- :::item name="publish"::: -->
:::moniker range="<=azure-pipelines"

**`publish`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
The publish step is a shortcut for the PublishPipelineArtifact@1 task. The task publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifact"::: -->
:::moniker range="<=azure-pipelines"

**`artifact`** string.<br><!-- :::editable-content name="propDescription"::: -->
Artifact name.
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
Time to wait for this task to complete before the server kills it.

[!INCLUDE [task-timeout](./includes/task-timeout.md)]
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
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

The `publish` keyword is a shortcut for the [Publish Pipeline Artifact task](/azure/devops/pipelines/tasks/reference/publish-pipeline-artifact-v1).

> [!IMPORTANT]
> The `publish` step is supported on Azure DevOps Services only. If you use it on Azure DevOps Server, you'll receive an error message similar to `Pipeline Artifact Task is not supported in on-premises. Please use Build Artifact Task instead.` Use [Publish Build Artifacts](/azure/devops/pipelines/tasks/reference/publish-build-artifacts-v1) if you're using Azure DevOps Server.

Learn more about [publishing artifacts](/azure/devops/pipelines/artifacts/pipeline-artifacts#publish-artifacts).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yaml
steps:
- publish: $(Build.SourcesDirectory)/build
  artifact: WebApp
  displayName: Publish artifact WebApp
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Publish Pipeline Artifact task](/azure/devops/pipelines/tasks/reference/publish-pipeline-artifact-v1)
- [Publishing artifacts](/azure/devops/pipelines/artifacts/pipeline-artifacts#publish-artifacts)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->