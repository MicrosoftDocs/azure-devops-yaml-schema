---
title: DownloadPipelineArtifact@1 - Download pipeline artifact v1 task
description: Download a named artifact from a pipeline to a local path.
ms.date: 11/30/2023
monikerRange: ">=azure-pipelines-2019.1"
---

# DownloadPipelineArtifact@1 - Download pipeline artifact v1 task

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

:::moniker range="=azure-pipelines-2019.1"

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
# Download Pipeline Artifacts v1
# Download a named artifact from a pipeline to a local path.
- task: DownloadPipelineArtifact@1
  inputs:
    buildType: 'current' # 'current' | 'specific'. Required. Download artifacts produced by. Default: current.
    #project: # string. Required when buildType == specific. Project. 
    #pipeline: # string. Alias: definition. Required when buildType == specific. Build pipeline. 
    #specificBuildWithTriggering: false # boolean. Optional. Use when buildType == specific. When appropriate, download artifacts from the triggering build. Default: false.
    #buildVersionToDownload: 'latest' # 'latest' | 'latestFromBranch' | 'specific'. Required when buildType == specific. Build version to download. Default: latest.
    #branchName: 'refs/heads/master' # string. Required when buildType == specific && buildVersionToDownload == latestFromBranch. Branch name. Default: refs/heads/master.
    #pipelineId: # string. Alias: buildId. Required when buildType == specific && buildVersionToDownload == specific. Build. 
    #tags: # string. Optional. Use when buildType == specific && buildVersionToDownload != specific. Build Tags. 
    #artifactName: # string. Artifact name. 
    #itemPattern: '**' # string. Matching pattern. Default: **.
    targetPath: '$(System.ArtifactsDirectory)' # string. Alias: downloadPath. Required. Destination directory. Default: $(System.ArtifactsDirectory).
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Download Pipeline Artifacts v1
# Download Pipeline Artifact.
- task: DownloadPipelineArtifact@1
  inputs:
    buildType: 'current' # 'current' | 'specific'. Required. Download artifacts produced by. Default: current.
    #project: # string. Required when buildType == specific. Project. 
    #pipeline: # string. Alias: definition. Required when buildType == specific. Build pipeline. 
    #specificBuildWithTriggering: false # boolean. Optional. Use when buildType == specific. When appropriate, download artifacts from the triggering build. Default: false.
    #buildVersionToDownload: 'latest' # 'latest' | 'latestFromBranch' | 'specific'. Required when buildType == specific. Build version to download. Default: latest.
    #branchName: 'refs/heads/master' # string. Required when buildType == specific && buildVersionToDownload == latestFromBranch. Branch name. Default: refs/heads/master.
    #pipelineId: # string. Alias: buildId. Required when buildType == specific && buildVersionToDownload == specific. Build. 
    #tags: # string. Optional. Use when buildType == specific && buildVersionToDownload != specific. Build Tags. 
    #artifactName: # string. Artifact name. 
    #itemPattern: '**' # string. Matching pattern. Default: **.
    targetPath: '$(System.ArtifactsDirectory)' # string. Alias: downloadPath. Required. Destination directory. Default: $(System.ArtifactsDirectory).
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="buildType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`buildType`** - **Download artifacts produced by**<br>
`string`. Required. Allowed values: `current` (Current build), `specific` (Specific build). Default value: `current`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Downloads artifacts produced by the current pipeline run or from a specific pipeline run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="project"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`project`** - **Project**<br>
`string`. Required when `buildType == specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the project name or GUID from which to download the pipeline artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pipeline"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`pipeline`** - **Build pipeline**<br>
Input alias: `definition`. `string`. Required when `buildType == specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The definition ID of the pipeline. In a running pipeline the `definitionId` can be found in the [System.DefinitionId](/azure/devops/pipelines/build/variables#system-variables-devops-services) variable. The `definitionId` can also be retrieved from the URL on the pipeline overview page in the Azure DevOps portal. In the following URL example, the `definitionId` is 78: `https://dev.azure.com/fabrikam-inc/FabrikamFiber/_build?definitionId=78&_a=summary`. To download artifacts from a specific pipeline definition, capture the `definitionId` from that pipeline, and specify it as the `pipeline` parameter.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="specificBuildWithTriggering"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`specificBuildWithTriggering`** - **When appropriate, download artifacts from the triggering build.**<br>
`boolean`. Optional. Use when `buildType == specific`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If checked, the task downloads artifacts from the triggering build. If there is no triggering build from the specified pipeline, the task downloads artifacts from the build specified in the options below.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildVersionToDownload"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`buildVersionToDownload`** - **Build version to download**<br>
`string`. Required when `buildType == specific`. Allowed values: `latest`, `latestFromBranch` (Latest from specific branch and specified Build Tags), `specific` (Specific version). Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the build version to download.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="branchName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`branchName`** - **Branch name**<br>
`string`. Required when `buildType == specific && buildVersionToDownload == latestFromBranch`. Default value: `refs/heads/master`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the filter on the branch/ref name. For example: ```refs/heads/develop```.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pipelineId"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`pipelineId`** - **Build**<br>
Input alias: `buildId`. `string`. Required when `buildType == specific && buildVersionToDownload == specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The identifier of the pipeline run from which to download the artifacts. In a running pipeline the `buildId` can be found in the [Build.BuildId](/azure/devops/pipelines/build/variables#build-variables-devops-services) variable. The `buildId` can also be retrieved from the URL on the pipeline run summary page in the Azure DevOps portal. In the following URL example, the `buildId` is 1088: `https://dev.azure.com/fabrikam-inc/FabrikamFiber/_build/results?buildId=1088&view=results`. To download artifacts from a specific pipeline run, capture the `buildId` from that run, and specify it as the `buildId` parameter.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`tags`** - **Build Tags**<br>
`string`. Optional. Use when `buildType == specific && buildVersionToDownload != specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The comma-delimited list of tags that the task uses to return tagged builds. Untagged builds are not returned.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`artifactName`** - **Artifact name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the artifact to download. If the value is left empty, the task downloads all artifacts associated with the pipeline run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="itemPattern"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`itemPattern`** - **Matching pattern**<br>
`string`. Default value: `**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file matching patterns that limit downloaded files. The value can be one or more file matching patterns that are new line delimited. Learn more about [file matching patterns](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targetPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`targetPath`** - **Destination directory**<br>
Input alias: `downloadPath`. `string`. Required. Default value: `$(System.ArtifactsDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path on the agent machine where the artifacts will be downloaded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019.1"

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

#### To find the definitionId for a specific pipeline definition

In a running pipeline, the `definitionId` can be found in the [System.DefinitionId](/azure/devops/pipelines/build/variables#system-variables-devops-services) variable. The `definitionId` can also be retrieved from the URL on the pipeline overview page in the Azure DevOps portal. In the following URL example, the `definitionId` is 78: `https://dev.azure.com/fabrikam-inc/FabrikamFiber/_build?definitionId=78&_a=summary`. To download artifacts from a specific pipeline definition, capture the `definitionId` from that pipeline, and specify it as the `pipeline` parameter.

#### To find the buildId for a specific pipeline run

The identifier of the pipeline run from which to download the artifacts. In a running pipeline the `buildId` can be found in the [Build.BuildId](/azure/devops/pipelines/build/variables#build-variables-devops-services) variable. The `buildId` can also be retrieved from the URL on the pipeline run summary page in the Azure DevOps portal. In the following URL example, the `buildId` is 1088: `https://dev.azure.com/fabrikam-inc/FabrikamFiber/_build/results?buildId=1088&view=results`. To download artifacts from a specific pipeline run, capture the `buildId` from that run, and specify it as the `buildId` parameter.
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

:::moniker range="=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.150.3 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->