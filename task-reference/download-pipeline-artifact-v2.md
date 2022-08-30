---
title: DownloadPipelineArtifact@2 - Download Pipeline Artifacts v2 task
description: Download build and pipeline artifacts.
ms.date: 08/23/2022
monikerRange: ">=azure-pipelines-2020"
---

# DownloadPipelineArtifact@2 - Download Pipeline Artifacts v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Download build and pipeline artifacts.
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
    buildType: 'current' # 'current' | 'specific'. Required. Download artifacts produced by. Default: 'current'.
    #project: # string. Required when source == specific. Project. 
    #definition: # string. Required when source == specific. Build pipeline. 
    #specificBuildWithTriggering: false # boolean. Optional. Use when source == specific. When appropriate, download artifacts from the triggering build. Default: false.
    #buildVersionToDownload: 'latest' # 'latest' | 'latestFromBranch' | 'specific'. Required when source == specific. Build version to download. Default: 'latest'.
    #branchName: 'refs/heads/master' # string. Required when source == specific && runVersion == latestFromBranch. Branch name. Default: 'refs/heads/master'.
    #pipelineId: # string. Required when source == specific && runVersion == specific. Build. 
    #tags: # string. Optional. Use when source == specific && runVersion != specific. Build Tags. 
    #allowPartiallySucceededBuilds: false # boolean. Optional. Use when source == specific && runVersion != specific. Download artifacts from partially succeeded builds. Default: false.
    #allowFailedBuilds: false # boolean. Optional. Use when source == specific && runVersion != specific. Download artifacts from failed builds. Default: false.
    #artifactName: # string. Artifact name. 
    #itemPattern: '**' # string. Matching patterns. Default: '**'.
    targetPath: '$(Pipeline.Workspace)' # string. Required. Destination directory. Default: '$(Pipeline.Workspace)'.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="buildType"::: -->
:::moniker range=">=azure-pipelines-2020"

**`buildType`** - **Download artifacts produced by**<br>
Input alias: `source`. Type: string. Required. Allowed values: 'current', 'specific'. Default value: 'current'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Download artifacts produced by the current pipeline run, or from a specific pipeline run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="project"::: -->
:::moniker range=">=azure-pipelines-2020"

**`project`** - **Project**<br>
Type: string. Required when source == specific.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The project from which to download the pipeline artifacts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="definition"::: -->
:::moniker range=">=azure-pipelines-2020"

**`definition`** - **Build pipeline**<br>
Input alias: `pipeline`. Type: string. Required when source == specific.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the build pipeline name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="specificBuildWithTriggering"::: -->
:::moniker range=">=azure-pipelines-2020"

**`specificBuildWithTriggering`** - **When appropriate, download artifacts from the triggering build.**<br>
Input alias: `preferTriggeringPipeline`. Type: boolean. Optional. Use when source == specific. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If checked, this build task will try to download artifacts from the triggering build. If there is no triggering build from the specified pipeline, it will download artifacts from the build specified in the options below.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildVersionToDownload"::: -->
:::moniker range=">=azure-pipelines-2020"

**`buildVersionToDownload`** - **Build version to download**<br>
Input alias: `runVersion`. Type: string. Required when source == specific. Allowed values: 'latest', 'latestFromBranch', 'specific'. Default value: 'latest'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="branchName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`branchName`** - **Branch name**<br>
Input alias: `runBranch`. Type: string. Required when source == specific && runVersion == latestFromBranch. Default value: 'refs/heads/master'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify to filter on branch/ref name, for example: ```refs/heads/develop```.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pipelineId"::: -->
:::moniker range=">=azure-pipelines-2020"

**`pipelineId`** - **Build**<br>
Input alias: `runId | buildId`. Type: string. Required when source == specific && runVersion == specific.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The build from which to download the artifacts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
:::moniker range=">=azure-pipelines-2020"

**`tags`** - **Build Tags**<br>
Type: string. Optional. Use when source == specific && runVersion != specific.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A comma-delimited list of tags. Only builds with these tags will be returned.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowPartiallySucceededBuilds"::: -->
:::moniker range=">=azure-pipelines-2020"

**`allowPartiallySucceededBuilds`** - **Download artifacts from partially succeeded builds.**<br>
Type: boolean. Optional. Use when source == specific && runVersion != specific. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If checked, this build task will try to download artifacts whether the build is succeeded or partially succeeded.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowFailedBuilds"::: -->
:::moniker range=">=azure-pipelines-2020"

**`allowFailedBuilds`** - **Download artifacts from failed builds.**<br>
Type: boolean. Optional. Use when source == specific && runVersion != specific. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If checked, this build task will try to download artifacts whether the build is succeeded or failed.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`artifactName`** - **Artifact name**<br>
Input alias: `artifact`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the artifact to download. If left empty, it will download all artifacts associated to the pipeline run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="itemPattern"::: -->
:::moniker range=">=azure-pipelines-2020"

**`itemPattern`** - **Matching patterns**<br>
Input alias: `patterns`. Type: string. Default value: '**'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
One or more file matching patterns (new line delimited) that limit which files get downloaded.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targetPath"::: -->
:::moniker range=">=azure-pipelines-2020"

**`targetPath`** - **Destination directory**<br>
Input alias: `path | downloadPath`. Type: string. Required. Default value: '$(Pipeline.Workspace)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path on the agent machine where the artifacts will be downloaded. Can be relative to the pipeline workspace directory or absolute. If multi-download option is applied (by leaving an empty artifact name), a sub-directory will be created for each.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020.1"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="BuildNumber"::: -->
**`BuildNumber`**<br><!-- :::editable-content name="Value"::: -->
Stores the build number of the pipeline artifact source.<br />Please note that in fact it returns <b>BuildId</b> due to backward compatibility <p>[More Information](/azure/devops/pipelines/build/variables#build-variables-devops-services)</p>
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="BuildNumber"::: -->
**`BuildNumber`**<br><!-- :::editable-content name="Value"::: -->
Stores the build number of the pipeline artifact source
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to download pipeline artifacts from earlier stages in this pipeline, or from another pipeline.

> [!NOTE]
> For more information, including Azure CLI commands, see [downloading artifacts](/azure/devops/pipelines/artifacts/pipeline-artifacts#download-artifacts).

The [publish](/azure/devops/pipelines/yaml-schema/steps-publish) and [download](/azure/devops/pipelines/yaml-schema/steps-download) keywords are shortcuts for the **Publish Pipeline Artifact** task. You can use them in your pipeline to publish and download artifacts. For more information, see [Publish](/azure/devops/pipelines/yaml-schema/steps-publish) and [Download](/azure/devops/pipelines/yaml-schema/steps-download) in the YAML schema.

### How can I find the ID of the Pipeline I want to download an artifact from? 

You can find the ID of the pipeline in the 'Pipeline variables'. The pipeline ID is the [system.definitionId](/azure/devops/pipelines/build/variables#system-variables) variable. You can also find it in the URL path.
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
    artifact: 'WebApp'
    path: $(Build.SourcesDirectory)/bin
```

### Download artifacts from a specific project/pipeline

```YAML
# Download artifacts from a specific pipeline.
- task: DownloadPipelineArtifact@2
  inputs:
    source: 'specific'
    project: 'FabrikamFiber'
    pipeline: 12
    runVersion: 'latest'
```

### Download artifacts from a specific branch

```YAML
# Download artifacts from a specific branch with a tag
- task: DownloadPipelineArtifact@2
  inputs:
    source: 'specific'
    project: 'FabrikamFiber'
    pipeline: 12
    runVersion: 'latestFromBranch'
    runBranch: 'refs/heads/master'
    tags: 'testTag'
```

### Download an artifact from a specific build run

```YAML
# Download an artifact named 'WebApp' from a specific build run to 'bin' in $(Build.SourcesDirectory)
- task: DownloadPipelineArtifact@2
  inputs:
    source: 'specific'
    artifact: 'WebApp'
    path: $(Build.SourcesDirectory)/bin
    project: 'FabrikamFiber'
    pipeline: 12
    runVersion: 'specific'
    runId: 40
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