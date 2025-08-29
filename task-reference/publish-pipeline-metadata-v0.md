---
title: PublishPipelineMetadata@0 - Publish Pipeline Metadata v0 task
description: Publish Pipeline Metadata to Evidence store.
ms.date: 08/29/2025
monikerRange: "<=azure-pipelines"
---

# PublishPipelineMetadata@0 - Publish Pipeline Metadata v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
This task is automatically injected into your pipelines when **Publish metadata from pipelines** is enabled in your project settings, and is used to support the [Evaluate artifact check](/azure/devops/pipelines/process/approvals#evaluate-artifact).

> [!IMPORTANT]
> This task is not intended for direct use in your pipelines.
>
> For more information, see [Evaluate artifact check](/azure/devops/release-notes/2019/sprint-160-update#evaluate-artifact-check) and [Collect automatic and user-specified metadata from pipeline](/azure/devops/release-notes/2019/sprint-162-update#collect-automatic-and-user-specified-metadata-from-pipeline).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Publish Pipeline Metadata v0
# Publish Pipeline Metadata to Evidence store.
- task: PublishPipelineMetadata@0
  inputs: # none
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="emptyCollectionValue"::: -->
:::moniker range="<=azure-pipelines"

None.

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

This task is automatically injected into your pipelines when **Publish metadata from pipelines** is enabled in your project settings, and is used to support the [Evaluate artifact check](/azure/devops/pipelines/process/approvals#evaluate-artifact).

> [!IMPORTANT]
> This task is not intended for direct use in your pipelines.
>
> For more information, see [Evaluate artifact check](/azure/devops/release-notes/2019/sprint-160-update#evaluate-artifact-check) and [Collect automatic and user-specified metadata from pipeline](/azure/devops/release-notes/2019/sprint-162-update#collect-automatic-and-user-specified-metadata-from-pipeline).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range="<=azure-pipelines-2022"

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
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->