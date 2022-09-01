---
title: DownloadPipelineArtifact@1 - Download pipeline artifact v1 task
description: Download a named artifact from a pipeline to a local path.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# DownloadPipelineArtifact@1 - Download pipeline artifact v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Download a named artifact from a pipeline to a local path.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Download Pipeline Artifact.
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
    buildType: 'current' # 'current' | 'specific'. Required. Download artifacts produced by. Default: 'current'.
    #project: # string. Required when buildType == specific. Project. 
    #pipeline: # string. Required when buildType == specific. Build pipeline. 
    #specificBuildWithTriggering: false # boolean. Optional. Use when buildType == specific. When appropriate, download artifacts from the triggering build. Default: false.
    #buildVersionToDownload: 'latest' # 'latest' | 'latestFromBranch' | 'specific'. Required when buildType == specific. Build version to download. Default: 'latest'.
    #branchName: 'refs/heads/master' # string. Required when buildType == specific && buildVersionToDownload == latestFromBranch. Branch name. Default: 'refs/heads/master'.
    #pipelineId: # string. Required when buildType == specific && buildVersionToDownload == specific. Build. 
    #tags: # string. Optional. Use when buildType == specific && buildVersionToDownload != specific. Build Tags. 
    #artifactName: # string. Artifact name. 
    #itemPattern: '**' # string. Matching pattern. Default: '**'.
    targetPath: '$(System.ArtifactsDirectory)' # string. Required. Destination directory. Default: '$(System.ArtifactsDirectory)'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Download Pipeline Artifacts v1
# Download Pipeline Artifact.
- task: DownloadPipelineArtifact@1
  inputs:
    buildType: 'current' # 'current' | 'specific'. Required. Download artifacts produced by. Default: 'current'.
    #project: # string. Required when buildType == specific. Project. 
    #pipeline: # string. Required when buildType == specific. Build pipeline. 
    #specificBuildWithTriggering: false # boolean. Optional. Use when buildType == specific. When appropriate, download artifacts from the triggering build. Default: false.
    #buildVersionToDownload: 'latest' # 'latest' | 'latestFromBranch' | 'specific'. Required when buildType == specific. Build version to download. Default: 'latest'.
    #branchName: 'refs/heads/master' # string. Required when buildType == specific && buildVersionToDownload == latestFromBranch. Branch name. Default: 'refs/heads/master'.
    #pipelineId: # string. Required when buildType == specific && buildVersionToDownload == specific. Build. 
    #tags: # string. Optional. Use when buildType == specific && buildVersionToDownload != specific. Build Tags. 
    #artifactName: # string. Artifact name. 
    #itemPattern: '**' # string. Matching pattern. Default: '**'.
    targetPath: '$(System.ArtifactsDirectory)' # string. Required. Destination directory. Default: '$(System.ArtifactsDirectory)'.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="buildType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`buildType`** - **Download artifacts produced by**<br>
Type: string. Required. Allowed values: 'current', 'specific'. Default value: 'current'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Download artifacts produced by the current build, or from a specific build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="project"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`project`** - **Project**<br>
Type: string. Required when buildType == specific.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The project from which to download the pipeline artifacts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pipeline"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`pipeline`** - **Build pipeline**<br>
Input alias: `definition`. Type: string. Required when buildType == specific.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the build pipeline name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="specificBuildWithTriggering"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`specificBuildWithTriggering`** - **When appropriate, download artifacts from the triggering build.**<br>
Type: boolean. Optional. Use when buildType == specific. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If checked, this build task will try to download artifacts from the triggering build. If there is no triggering build from the specified pipeline, it will download artifacts from the build specified in the options below.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildVersionToDownload"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`buildVersionToDownload`** - **Build version to download**<br>
Type: string. Required when buildType == specific. Allowed values: 'latest', 'latestFromBranch', 'specific'. Default value: 'latest'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="branchName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`branchName`** - **Branch name**<br>
Type: string. Required when buildType == specific && buildVersionToDownload == latestFromBranch. Default value: 'refs/heads/master'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify to filter on branch/ref name, for example: ```refs/heads/develop```.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pipelineId"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`pipelineId`** - **Build**<br>
Input alias: `buildId`. Type: string. Required when buildType == specific && buildVersionToDownload == specific.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The build from which to download the artifacts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`tags`** - **Build Tags**<br>
Type: string. Optional. Use when buildType == specific && buildVersionToDownload != specific.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A comma-delimited list of tags. Only builds with these tags will be returned.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`artifactName`** - **Artifact name**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the artifact to download.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="itemPattern"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`itemPattern`** - **Matching pattern**<br>
Type: string. Default value: '**'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify files to be downloaded as multi line minimatch pattern. [More Information](https://aka.ms/minimatchexamples).</p>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targetPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`targetPath`** - **Destination directory**<br>
Input alias: `downloadPath`. Type: string. Required. Default value: '$(System.ArtifactsDirectory)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path on the agent machine where the artifacts will be downloaded.
<!-- :::editable-content-end::: -->

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