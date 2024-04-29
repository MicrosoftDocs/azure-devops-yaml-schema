---
title: DownloadPipelineArtifact@0 - Download pipeline artifact v0 task
description: Downloads an artifact associated with a pipeline.
ms.date: 04/29/2024
monikerRange: ">=azure-pipelines-2019"
---

# DownloadPipelineArtifact@0 - Download pipeline artifact v0 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to download pipeline artifacts from earlier stages in this pipeline, or from another pipeline.

There is a newer version of this task. For more information, see [DownloadPipelineArtifact@2](./download-pipeline-artifact-v2.md).

> [!NOTE]
> For more information, including Azure CLI commands, see [downloading artifacts](/azure/devops/pipelines/artifacts/pipeline-artifacts?tabs=yaml#download-artifacts).
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2022.1"

<!-- :::editable-content name="description"::: -->
Use this task to download pipeline artifacts from earlier stages in this pipeline, or from another pipeline.

> [!IMPORTANT]
> This task is supported on Azure DevOps Services only. If you use it on Azure DevOps Server, you'll receive an error message similar to `Pipeline Artifact Task is not supported in on-premises. Please use Build Artifact Task instead.` Use [Download Build Artifacts](download-build-artifacts-v1.md) if you're using Azure DevOps Server or TFS 2018.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to download pipeline artifacts from earlier stages in this pipeline, or from another pipeline.

> [!IMPORTANT]
> This task is supported on Azure DevOps Services only. If you use it on Azure DevOps Server, you'll receive an error message similar to `Pipeline Artifact Task is not supported in on-premises. Please use Build Artifact Task instead.` Use [Download Build Artifacts](download-build-artifacts-v1.md) if you're using Azure DevOps Server or TFS 2018.
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
    artifactName: 'drop' # string. Required. The name of artifact to download. Default: drop.
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
    artifactName: 'drop' # string. Required. The name of artifact to download. Default: drop.
    targetPath: # string. Required. Path to download to.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="pipelineId"::: -->
:::moniker range=">=azure-pipelines-2019"

**`pipelineId`** - **The specific pipeline to download from**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The build from which to download the artifacts. For example: `1764`. If missing, target the current pipeline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`artifactName`** - **The name of artifact to download.**<br>
`string`. Required. Default value: `drop`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the artifact to download. If the value is left empty, the task downloads all artifacts associated with the pipeline run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targetPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`targetPath`** - **Path to download to**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The folder path to download the artifact to. This can be a fully-qualified path or a path relative to the root of the repository. Wildcards are not supported. [Variables](https://go.microsoft.com/fwlink/?LinkID=550988) are supported. If the folder doesn't exist it will be created.
<!-- :::editable-content-end::: -->
<br>

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
## Remarks

There is a newer version of this task. For more information, see [DownloadPipelineArtifact@2](./download-pipeline-artifact-v2.md).

> [!IMPORTANT]
> This task is supported on Azure DevOps Services only. If you use it on Azure DevOps Server, you'll receive an error message similar to `Pipeline Artifact Task is not supported in on-premises. Please use Build Artifact Task instead.` Use [Download Build Artifacts](download-build-artifacts-v1.md) if you're using Azure DevOps Server or TFS 2018.

By default, artifacts are downloaded to `$(Pipeline.Workspace)`. If you don't specify an artifact name, a subdirectory will be created for each downloaded artifact. You can use [file matching patterns](/azure/devops/pipelines/tasks/file-matching-patterns) to limit the files you want to download.

### How can I find the ID of the Pipeline I want to download an artifact from?

You can find the ID of the pipeline in the 'Pipeline variables'. The pipeline ID is the [system.definitionId](/azure/devops/pipelines/build/variables#system-variables) variable. You can also find it in the URL path.
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
