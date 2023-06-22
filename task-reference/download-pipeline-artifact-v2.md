---
title: DownloadPipelineArtifact@2 - Download Pipeline Artifacts v2 task
description: Download build and pipeline artifacts.
ms.date: 06/22/2023
monikerRange: ">=azure-pipelines-2020"
---

# DownloadPipelineArtifact@2 - Download Pipeline Artifacts v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Use this task to download pipeline artifacts from earlier stages in this pipeline, or from another pipeline.

> [!NOTE]
> For more information, including Azure CLI commands, see [downloading artifacts](/azure/devops/pipelines/artifacts/pipeline-artifacts?tabs=yaml#download-artifacts).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Download Pipeline Artifacts v2
# Download build and pipeline artifacts.
- task: DownloadPipelineArtifact@2
  inputs:
    buildType: 'current' # 'current' | 'specific'. Alias: source. Required. Download artifacts produced by. Default: current.
    #project: # string. Required when source == specific. Project. 
    #definition: # string. Alias: pipeline. Required when source == specific. Build pipeline. 
    #specificBuildWithTriggering: false # boolean. Alias: preferTriggeringPipeline. Optional. Use when source == specific. When appropriate, download artifacts from the triggering build. Default: false.
    #buildVersionToDownload: 'latest' # 'latest' | 'latestFromBranch' | 'specific'. Alias: runVersion. Required when source == specific. Build version to download. Default: latest.
    #branchName: 'refs/heads/master' # string. Alias: runBranch. Required when source == specific && runVersion == latestFromBranch. Branch name. Default: refs/heads/master.
    #pipelineId: # string. Alias: runId | buildId. Required when source == specific && runVersion == specific. Build. 
    #tags: # string. Optional. Use when source == specific && runVersion != specific. Build Tags. 
    #allowPartiallySucceededBuilds: false # boolean. Optional. Use when source == specific && runVersion != specific. Download artifacts from partially succeeded builds. Default: false.
    #allowFailedBuilds: false # boolean. Optional. Use when source == specific && runVersion != specific. Download artifacts from failed builds. Default: false.
    #artifactName: # string. Alias: artifact. Artifact name. 
    #itemPattern: '**' # string. Alias: patterns. Matching patterns. Default: **.
    targetPath: '$(Pipeline.Workspace)' # string. Alias: path | downloadPath. Required. Destination directory. Default: $(Pipeline.Workspace).
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="buildType"::: -->
:::moniker range=">=azure-pipelines-2020"

**`buildType`** - **Download artifacts produced by**<br>
Input alias: `source`. `string`. Required. Allowed values: `current` (Current run), `specific` (Specific run). Default value: `current`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Downloads artifacts produced by the current pipeline run or from a specific pipeline run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="project"::: -->
:::moniker range=">=azure-pipelines-2020"

**`project`** - **Project**<br>
`string`. Required when `source == specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the project name or GUID from which to download the pipeline artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="definition"::: -->
:::moniker range=">=azure-pipelines-2020"

**`definition`** - **Build pipeline**<br>
Input alias: `pipeline`. `string`. Required when `source == specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The definition ID of the pipeline. In a running pipeline the `definitionId` can be found in the [System.DefinitionId](/azure/devops/pipelines/build/variables#system-variables-devops-services) variable. The `definitionId` can also be retrieved from the URL on the pipeline overview page in the Azure DevOps portal. In the following URL example, the `definitionId` is 78: `https://dev.azure.com/fabrikam-inc/FabrikamFiber/_build?definitionId=78&_a=summary`. To download artifacts from a specific pipeline definition, capture the `definitionId` from that pipeline, and specify it as the `pipeline` parameter.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="specificBuildWithTriggering"::: -->
:::moniker range=">=azure-pipelines-2020"

**`specificBuildWithTriggering`** - **When appropriate, download artifacts from the triggering build.**<br>
Input alias: `preferTriggeringPipeline`. `boolean`. Optional. Use when `source == specific`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If checked, the task downloads artifacts from the triggering build. If there is no triggering build from the specified pipeline, the task downloads artifacts from the build specified in the options below.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildVersionToDownload"::: -->
:::moniker range=">=azure-pipelines-2020"

**`buildVersionToDownload`** - **Build version to download**<br>
Input alias: `runVersion`. `string`. Required when `source == specific`. Allowed values: `latest`, `latestFromBranch` (Latest from specific branch and specified Build Tags), `specific` (Specific version). Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the build version to download.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="branchName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`branchName`** - **Branch name**<br>
Input alias: `runBranch`. `string`. Required when `source == specific && runVersion == latestFromBranch`. Default value: `refs/heads/master`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the filter on the branch/ref name. For example: ```refs/heads/develop```.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pipelineId"::: -->
:::moniker range=">=azure-pipelines-2020"

**`pipelineId`** - **Build**<br>
Input alias: `runId | buildId`. `string`. Required when `source == specific && runVersion == specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The identifier of the pipeline run from which to download the artifacts. In a running pipeline the `buildId` can be found in the [Build.BuildId](/azure/devops/pipelines/build/variables#build-variables-devops-services) variable. The `buildId` can also be retrieved from the URL on the pipeline run summary page in the Azure DevOps portal. In the following URL example, the `buildId` is 1088: `https://dev.azure.com/fabrikam-inc/FabrikamFiber/_build/results?buildId=1088&view=results`. To download artifacts from a specific pipeline run, capture the `buildId` from that run, and specify it as the `buildId` parameter.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
:::moniker range=">=azure-pipelines-2020"

**`tags`** - **Build Tags**<br>
`string`. Optional. Use when `source == specific && runVersion != specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The comma-delimited list of tags that the task uses to return tagged builds. Untagged builds are not returned.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowPartiallySucceededBuilds"::: -->
:::moniker range=">=azure-pipelines-2020"

**`allowPartiallySucceededBuilds`** - **Download artifacts from partially succeeded builds.**<br>
`boolean`. Optional. Use when `source == specific && runVersion != specific`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies if the build task downloads artifacts whether the build succeeds or partially succeeds.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowFailedBuilds"::: -->
:::moniker range=">=azure-pipelines-2020"

**`allowFailedBuilds`** - **Download artifacts from failed builds.**<br>
`boolean`. Optional. Use when `source == specific && runVersion != specific`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If checked, the build task downloads artifacts whether the build succeeds or fails.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`artifactName`** - **Artifact name**<br>
Input alias: `artifact`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the artifact to download. If the value is left empty, the task downloads all artifacts associated with the pipeline run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="itemPattern"::: -->
:::moniker range=">=azure-pipelines-2020"

**`itemPattern`** - **Matching patterns**<br>
Input alias: `patterns`. `string`. Default value: `**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file matching patterns that limit downloaded files. The value can be one or more file matching patterns that are new line delimited. Learn more about [file matching patterns](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targetPath"::: -->
:::moniker range=">=azure-pipelines-2020"

**`targetPath`** - **Destination directory**<br>
Input alias: `path | downloadPath`. `string`. Required. Default value: `$(Pipeline.Workspace)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies either a relative or absolute path on the agent machine where the artifacts will download. If the multi-download option is applied (by leaving an empty artifact name), a sub-directory will be created for each download. Learn more about [Artifacts in Azure Pipelines](/azure/devops/pipelines/artifacts/pipeline-artifacts).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020.1"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="BuildNumber"::: -->
**`BuildNumber`**<br><!-- :::editable-content name="Value"::: -->
Stores the build number of the pipeline artifact source.

Due to backwards compatibility, this variable returns **BuildId**.

Learn more about [build variables](/azure/devops/pipelines/build/variables#build-variables-devops-services).
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="BuildNumber"::: -->
**`BuildNumber`**<br><!-- :::editable-content name="Value"::: -->
Stores the build number of the pipeline artifact source.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to download pipeline artifacts from earlier stages in this pipeline, or from another pipeline. By default, artifacts are downloaded to `$(Pipeline.Workspace)`. If you don't specify an artifact name, a subdirectory will be created for each downloaded artifact. You can use [file matching patterns](/azure/devops/pipelines/tasks/file-matching-patterns) to limit the files you want to download.

The [publish](/azure/devops/pipelines/yaml-schema/steps-publish) and [download](/azure/devops/pipelines/yaml-schema/steps-download) keywords are tasks shortcuts to [publish](/azure/devops/pipelines/artifacts/pipeline-artifacts#publish-artifacts) and [download](/azure/devops/pipelines/artifacts/pipeline-artifacts#download-artifacts) your pipeline artifacts.

### How can I find the ID of the Pipeline I want to download an artifact from?

#### To find the definitionId for a specific pipeline definition

In a running pipeline, the `definitionId` can be found in the [System.DefinitionId](/azure/devops/pipelines/build/variables#system-variables-devops-services) variable. The `definitionId` can also be retrieved from the URL on the pipeline overview page in the Azure DevOps portal. In the following URL example, the `definitionId` is 78: `https://dev.azure.com/fabrikam-inc/FabrikamFiber/_build?definitionId=78&_a=summary`. To download artifacts from a specific pipeline definition, capture the `definitionId` from that pipeline, and specify it as the `pipeline` parameter.

#### To find the buildId for a specific pipeline run

The identifier of the pipeline run from which to download the artifacts. In a running pipeline the `buildId` can be found in the [Build.BuildId](/azure/devops/pipelines/build/variables#build-variables-devops-services) variable. The `buildId` can also be retrieved from the URL on the pipeline run summary page in the Azure DevOps portal. In the following URL example, the `buildId` is 1088: `https://dev.azure.com/fabrikam-inc/FabrikamFiber/_build/results?buildId=1088&view=results`. To download artifacts from a specific pipeline run, capture the `buildId` from that run, and specify it as the `buildId` parameter.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Download a specific artifact

```YAML
# Download an artifact named 'WebApp' to 'bin' in $(Build.SourcesDirectory)
- task: DownloadPipelineArtifact@2
  inputs:
    artifactName: 'WebApp'
    targetPath: $(Build.SourcesDirectory)/bin
```

### Download artifacts from a specific project/pipeline

```YAML
# Download artifacts from a specific pipeline.
- task: DownloadPipelineArtifact@2
  inputs:
    buildType: 'specific'
    project: 'FabrikamFiber'
    definition: 12
    buildVersionToDownload: 'latest'
```

### Download artifacts from a specific branch

```YAML
# Download artifacts from a specific branch with a tag
- task: DownloadPipelineArtifact@2
  inputs:
    buildType: 'specific'
    project: 'FabrikamFiber'
    definition: 12
    buildVersionToDownload: 'latestFromBranch'
    branchName: 'refs/heads/master'
    tags: 'testTag'
```

### Download an artifact from a specific build run

```YAML
# Download an artifact named 'WebApp' from a specific build run to 'bin' in $(Build.SourcesDirectory)
- task: DownloadPipelineArtifact@2
  inputs:
    buildType: 'specific'
    artifactName: 'WebApp'
    targetPath: $(Build.SourcesDirectory)/bin
    project: 'FabrikamFiber'
    definition: 12
    buildVersionToDownload: 'specific'
    pipelineId: 40
```
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
| Agent version |  2.164.1 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
