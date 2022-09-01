---
title: DownloadPipelineArtifact@0 - Download pipeline artifact v0 task
description: Downloads an artifact associated with a pipeline.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019"
---

# DownloadPipelineArtifact@0 - Download pipeline artifact v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Downloads an artifact associated with a pipeline.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Download Pipeline Artifact.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Download Pipeline Artifacts v0
# Downloads an artifact associated with a pipeline.
- task: DownloadPipelineArtifact@0
  inputs:
    #pipelineId: # string. The specific pipeline to download from. 
    artifactName: 'drop' # string. Required. The name of artifact to download. Default: 'drop'.
    targetPath: # string. Required. Path to download to.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
# Download Pipeline Artifacts v0
# Download Pipeline Artifact.
- task: DownloadPipelineArtifact@0
  inputs:
    #pipelineId: # string. The specific pipeline to download from. 
    artifactName: 'drop' # string. Required. The name of artifact to download. Default: 'drop'.
    targetPath: # string. Required. Path to download to.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="pipelineId"::: -->
:::moniker range=">=azure-pipelines-2019"

**`pipelineId`** - **The specific pipeline to download from**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The pipeline to download from. Target the current pipeline if left blank.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`artifactName`** - **The name of artifact to download.**<br>
Type: string. Required. Default value: 'drop'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of artifact to download. The artifact must be a pipeline artifact.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targetPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`targetPath`** - **Path to download to**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The folder path to download the artifact to. This can be a fully-qualified path or a path relative to the root of the repository. Wildcards are not supported. [Variables](https://go.microsoft.com/fwlink/?LinkID=550988) are supported. If the folder doesn't exist it will be created.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.155.1 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.140.1 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->