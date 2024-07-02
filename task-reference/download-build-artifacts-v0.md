---
title: DownloadBuildArtifacts@0 - Download build artifacts v0 task
description: Download files that were saved as artifacts of a completed build (task version 0).
ms.date: 07/02/2024
monikerRange: "<=azure-pipelines"
---

# DownloadBuildArtifacts@0 - Download build artifacts v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to download files that were saved as artifacts of a completed build.

If you're using Azure DevOps Services, we recommend using [Download Pipeline Artifacts](./download-pipeline-artifact-v2.md) and [Publish Pipeline Artifacts](./publish-pipeline-artifact-v1.md) for faster performance.

> [!NOTE]
> Disable IIS Basic Authentication if you are using Azure DevOps Server to allow authentication with your Personal Access Token. See [IIS Basic Authentication and PATs](/azure/devops/integrate/get-started/authentication/iis-basic-auth) for more details.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Download Build Artifacts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.2"

```yaml
# Download build artifacts v0
# Download files that were saved as artifacts of a completed build.
- task: DownloadBuildArtifacts@0
  inputs:
    buildType: 'current' # 'current' | 'specific'. Required. Download artifacts produced by. Default: current.
    #project: # string. Required when buildType == specific. Project. 
    #pipeline: # string. Alias: definition. Required when buildType == specific. Build pipeline. 
    #specificBuildWithTriggering: false # boolean. Optional. Use when buildType == specific. When appropriate, download artifacts from the triggering build. Default: false.
    #buildVersionToDownload: 'latest' # 'latest' | 'latestFromBranch' | 'specific'. Required when buildType == specific. Build version to download. Default: latest.
    #allowPartiallySucceededBuilds: false # boolean. Optional. Use when buildType == specific && buildVersionToDownload != specific. Download artifacts even from partially succeeded builds. Default: false.
    #branchName: 'refs/heads/master' # string. Required when buildType == specific && buildVersionToDownload == latestFromBranch. Branch name. Default: refs/heads/master.
    #buildId: # string. Required when buildType == specific && buildVersionToDownload == specific. Build. 
    #tags: # string. Optional. Use when buildType == specific && buildVersionToDownload != specific. Build Tags. 
    downloadType: 'single' # 'single' | 'specific'. Required. Download type. Default: single.
    artifactName: # string. Required when downloadType == single. Artifact name. 
    #itemPattern: '**' # string. Matching pattern. Default: **.
    downloadPath: '$(System.ArtifactsDirectory)' # string. Required. Destination directory. Default: $(System.ArtifactsDirectory).
    #cleanDestinationFolder: false # boolean. Clean destination folder. Default: false.
  # Advanced
    #parallelizationLimit: '8' # string. Parallelization limit. Default: 8.
    #checkDownloadedFiles: false # boolean. Check downloaded files. Default: false.
    #retryDownloadCount: '4' # string. Retry count. Default: 4.
    #retryRedirectDownloadCount: '0' # string. Retry count for redirect download. Default: 0.
    #extractTars: # boolean. Extract all files that are stored inside tar archives.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2022 <=azure-pipelines-2022.1"

```yaml
# Download build artifacts v0
# Download files that were saved as artifacts of a completed build.
- task: DownloadBuildArtifacts@0
  inputs:
    buildType: 'current' # 'current' | 'specific'. Required. Download artifacts produced by. Default: current.
    #project: # string. Required when buildType == specific. Project. 
    #pipeline: # string. Alias: definition. Required when buildType == specific. Build pipeline. 
    #specificBuildWithTriggering: false # boolean. Optional. Use when buildType == specific. When appropriate, download artifacts from the triggering build. Default: false.
    #buildVersionToDownload: 'latest' # 'latest' | 'latestFromBranch' | 'specific'. Required when buildType == specific. Build version to download. Default: latest.
    #allowPartiallySucceededBuilds: false # boolean. Optional. Use when buildType == specific && buildVersionToDownload != specific. Download artifacts even from partially succeeded builds. Default: false.
    #branchName: 'refs/heads/master' # string. Required when buildType == specific && buildVersionToDownload == latestFromBranch. Branch name. Default: refs/heads/master.
    #buildId: # string. Required when buildType == specific && buildVersionToDownload == specific. Build. 
    #tags: # string. Optional. Use when buildType == specific && buildVersionToDownload != specific. Build Tags. 
    downloadType: 'single' # 'single' | 'specific'. Required. Download type. Default: single.
    artifactName: # string. Required when downloadType == single. Artifact name. 
    #itemPattern: '**' # string. Matching pattern. Default: **.
    downloadPath: '$(System.ArtifactsDirectory)' # string. Required. Destination directory. Default: $(System.ArtifactsDirectory).
    #cleanDestinationFolder: false # boolean. Clean destination folder. Default: false.
  # Advanced
    #parallelizationLimit: '8' # string. Parallelization limit. Default: 8.
    #checkDownloadedFiles: false # boolean. Check downloaded files. Default: false.
    #retryDownloadCount: '4' # string. Retry count. Default: 4.
    #extractTars: # boolean. Extract all files that are stored inside tar archives.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

```yaml
# Download build artifacts v0
# Download files that were saved as artifacts of a completed build.
- task: DownloadBuildArtifacts@0
  inputs:
    buildType: 'current' # 'current' | 'specific'. Required. Download artifacts produced by. Default: current.
    #project: # string. Required when buildType == specific. Project. 
    #pipeline: # string. Alias: definition. Required when buildType == specific. Build pipeline. 
    #specificBuildWithTriggering: false # boolean. Optional. Use when buildType == specific. When appropriate, download artifacts from the triggering build. Default: false.
    #buildVersionToDownload: 'latest' # 'latest' | 'latestFromBranch' | 'specific'. Required when buildType == specific. Build version to download. Default: latest.
    #allowPartiallySucceededBuilds: false # boolean. Optional. Use when buildType == specific && buildVersionToDownload != specific. Download artifacts even from partially succeeded builds. Default: false.
    #branchName: 'refs/heads/master' # string. Required when buildType == specific && buildVersionToDownload == latestFromBranch. Branch name. Default: refs/heads/master.
    #buildId: # string. Required when buildType == specific && buildVersionToDownload == specific. Build. 
    #tags: # string. Optional. Use when buildType == specific && buildVersionToDownload != specific. Build Tags. 
    downloadType: 'single' # 'single' | 'specific'. Required. Download type. Default: single.
    artifactName: # string. Required when downloadType == single. Artifact name. 
    #itemPattern: '**' # string. Matching pattern. Default: **.
    downloadPath: '$(System.ArtifactsDirectory)' # string. Required. Destination directory. Default: $(System.ArtifactsDirectory).
  # Advanced
    #parallelizationLimit: '8' # string. Parallelization limit. Default: 8.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Download Build Artifacts v0
# Download Build Artifacts.
- task: DownloadBuildArtifacts@0
  inputs:
    buildType: 'current' # 'current' | 'specific'. Required. Download artifacts produced by. Default: current.
    #project: # string. Required when buildType == specific. Project. 
    #pipeline: # string. Alias: definition. Required when buildType == specific. Build pipeline. 
    #specificBuildWithTriggering: false # boolean. Optional. Use when buildType == specific. When appropriate, download artifacts from the triggering build. Default: false.
    #buildVersionToDownload: 'latest' # 'latest' | 'latestFromBranch' | 'specific'. Required when buildType == specific. Build version to download. Default: latest.
    #branchName: 'refs/heads/master' # string. Required when buildType == specific && buildVersionToDownload == latestFromBranch. Branch name. Default: refs/heads/master.
    #buildId: # string. Required when buildType == specific && buildVersionToDownload == specific. Build. 
    #tags: # string. Optional. Use when buildType == specific && buildVersionToDownload != specific. Build Tags. 
    downloadType: 'single' # 'single' | 'specific'. Required. Download type. Default: single.
    artifactName: # string. Required when downloadType == single. Artifact name. 
    #itemPattern: '**' # string. Matching pattern. Default: **.
    downloadPath: '$(System.ArtifactsDirectory)' # string. Required. Destination directory. Default: $(System.ArtifactsDirectory).
  # Advanced
    #parallelizationLimit: '8' # string. Parallelization limit. Default: 8.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="buildType"::: -->
:::moniker range="<=azure-pipelines"

**`buildType`** - **Download artifacts produced by**<br>
`string`. Required. Allowed values: `current` (Current build), `specific` (Specific build). Default value: `current`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Whether to download artifacts produced by the current build or from a specific build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="project"::: -->
:::moniker range="<=azure-pipelines"

**`project`** - **Project**<br>
`string`. Required when `buildType == specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The project from which you want to download the build artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pipeline"::: -->
:::moniker range=">=azure-pipelines-2019"

**`pipeline`** - **Build pipeline**<br>
Input alias: `definition`. `string`. Required when `buildType == specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the build pipeline name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="specificBuildWithTriggering"::: -->
:::moniker range="<=azure-pipelines"

**`specificBuildWithTriggering`** - **When appropriate, download artifacts from the triggering build.**<br>
`boolean`. Optional. Use when `buildType == specific`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If `true`, this build task tries to download artifacts from the triggering build. If there is no triggering build from the specified pipeline, it downloads artifacts from the build specified in the options below.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildVersionToDownload"::: -->
:::moniker range=">=azure-pipelines-2019"

**`buildVersionToDownload`** - **Build version to download**<br>
`string`. Required when `buildType == specific`. Allowed values: `latest`, `latestFromBranch` (Latest from specific branch and specified Build Tags), `specific` (Specific version). Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowPartiallySucceededBuilds"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`allowPartiallySucceededBuilds`** - **Download artifacts even from partially succeeded builds.**<br>
`boolean`. Optional. Use when `buildType == specific && buildVersionToDownload != specific`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If `true`, this build task tries to download artifacts whether the build succeeds or partially succeeds.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="branchName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`branchName`** - **Branch name**<br>
`string`. Required when `buildType == specific && buildVersionToDownload == latestFromBranch`. Default value: `refs/heads/master`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether to filter on branch/ref name, for example: `refs/heads/develop`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildId"::: -->
:::moniker range=">=azure-pipelines-2019"

**`buildId`** - **Build**<br>
`string`. Required when `buildType == specific && buildVersionToDownload == specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The build you want to download the artifacts from.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
:::moniker range=">=azure-pipelines-2019"

**`tags`** - **Build Tags**<br>
`string`. Optional. Use when `buildType == specific && buildVersionToDownload != specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A comma-delimited list of tags. Only builds with these tags are returned.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="downloadType"::: -->
:::moniker range="<=azure-pipelines"

**`downloadType`** - **Download type**<br>
`string`. Required. Allowed values: `single` (Specific artifact), `specific` (Specific files). Default value: `single`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Downloads a specific artifact or specific files from the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`artifactName`** - **Artifact name**<br>
`string`. Required when `downloadType == single`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the artifact to download.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="itemPattern"::: -->
:::moniker range=">=azure-pipelines-2019"

**`itemPattern`** - **Matching pattern**<br>
`string`. Default value: `**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the files to download as a multi-line minimatch pattern. For more information, see [File matching patterns reference](https://aka.ms/minimatchexamples).

The default pattern `\*\*` downloads all files across all artifacts in the build if you choose the **Specific files** option. To download all the files within the artifact drop, use `drop/**`.</p>.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="downloadPath"::: -->
:::moniker range="<=azure-pipelines"

**`downloadPath`** - **Destination directory**<br>
`string`. Required. Default value: `$(System.ArtifactsDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path on the agent machine where the artifacts are downloaded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cleanDestinationFolder"::: -->
:::moniker range=">=azure-pipelines-2022"

**`cleanDestinationFolder`** - **Clean destination folder**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Deletes all the existing files in the destination folder before the artifact is downloaded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parallelizationLimit"::: -->
:::moniker range="<=azure-pipelines"

**`parallelizationLimit`** - **Parallelization limit**<br>
`string`. Default value: `8`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The number of files to download simultaneously.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkDownloadedFiles"::: -->
:::moniker range=">=azure-pipelines-2022"

**`checkDownloadedFiles`** - **Check downloaded files**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If `true`, this build task checks that all files are fully downloaded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="retryDownloadCount"::: -->
:::moniker range=">=azure-pipelines-2022"

**`retryDownloadCount`** - **Retry count**<br>
`string`. Default value: `4`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The number of times to retry downloading a build artifact if the download fails.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="retryRedirectDownloadCount"::: -->
:::moniker range=">=azure-pipelines-2022.2"

**`retryRedirectDownloadCount`** - **Retry count for redirect download**<br>
`string`. Default value: `0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional number of times to retry downloading a build artifact if the download based on redirect fails. If your network does not allow following the redirect, you can set this to -1 to always download streamed response from Azure DevOps instead.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="extractTars"::: -->
:::moniker range=">=azure-pipelines-2022"

**`extractTars`** - **Extract all files that are stored inside tar archives**<br>
`boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Extracts all downloaded files that have a `.tar` extension. This is helpful because you need to pack your artifact files into a `.tar` file if you want to preserve Unix file permissions. Enabling the `StoreAsTar` option in the PublishBuildArtifacts task stores artifacts as `.tar` files automatically.
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
Stores the build artifact source's build number.

Please note that this input returns **BuildId** due to backward compatibility. For more information, see [Variables](/azure/devops/pipelines/build/variables#build-variables-devops-services).
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="BuildNumber"::: -->
**`BuildNumber`**<br><!-- :::editable-content name="Value"::: -->
Stores the build artifact source's build number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

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

:::moniker range="<=azure-pipelines"

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
