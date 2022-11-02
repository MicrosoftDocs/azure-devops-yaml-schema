---
title: DownloadBuildArtifacts@1 - Download build artifacts v1 task
description: Download files that were saved as artifacts of a completed build.
ms.date: 10/21/2022
monikerRange: "=azure-pipelines"
---

# DownloadBuildArtifacts@1 - Download build artifacts v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Download files that were saved as artifacts of a completed build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Download build artifacts v1
# Download files that were saved as artifacts of a completed build.
- task: DownloadBuildArtifacts@1
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
    #checkDownloadedFiles: false # boolean. Check downloaded files. Default: false.
    #retryDownloadCount: '4' # string. Retry count. Default: 4.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="buildType"::: -->
:::moniker range="=azure-pipelines"

**`buildType`** - **Download artifacts produced by**<br>
`string`. Required. Allowed values: `current` (Current build), `specific` (Specific build). Default value: `current`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Download artifacts produced by the current build, or from a specific build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="project"::: -->
:::moniker range="=azure-pipelines"

**`project`** - **Project**<br>
`string`. Required when `buildType == specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The project from which to download the build artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pipeline"::: -->
:::moniker range="=azure-pipelines"

**`pipeline`** - **Build pipeline**<br>
Input alias: `definition`. `string`. Required when `buildType == specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the build pipeline name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="specificBuildWithTriggering"::: -->
:::moniker range="=azure-pipelines"

**`specificBuildWithTriggering`** - **When appropriate, download artifacts from the triggering build.**<br>
`boolean`. Optional. Use when `buildType == specific`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If checked, this build task will try to download artifacts from the triggering build. If there is no triggering build from the specified pipeline, it will download artifacts from the build specified in the options below.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildVersionToDownload"::: -->
:::moniker range="=azure-pipelines"

**`buildVersionToDownload`** - **Build version to download**<br>
`string`. Required when `buildType == specific`. Allowed values: `latest`, `latestFromBranch` (Latest from specific branch and specified Build Tags), `specific` (Specific version). Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify which version of the build to download.

- Choose `latest` to download the latest available build version.
- Choose `latestFromBranch` to download the latest available build version of the branch specified by `branchName` and tags specified by `tags`.
- Choose `specific` to download the build version specified by `buildId`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowPartiallySucceededBuilds"::: -->
:::moniker range="=azure-pipelines"

**`allowPartiallySucceededBuilds`** - **Download artifacts even from partially succeeded builds.**<br>
`boolean`. Optional. Use when `buildType == specific && buildVersionToDownload != specific`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If checked, this build task will try to download artifacts whether the build is succeeded or partially succeeded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="branchName"::: -->
:::moniker range="=azure-pipelines"

**`branchName`** - **Branch name**<br>
`string`. Required when `buildType == specific && buildVersionToDownload == latestFromBranch`. Default value: `refs/heads/master`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify to filter on branch/ref name, for example: ```refs/heads/develop```.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildId"::: -->
:::moniker range="=azure-pipelines"

**`buildId`** - **Build**<br>
`string`. Required when `buildType == specific && buildVersionToDownload == specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The build from which to download the artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
:::moniker range="=azure-pipelines"

**`tags`** - **Build Tags**<br>
`string`. Optional. Use when `buildType == specific && buildVersionToDownload != specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A comma-delimited list of tags. Only builds with these tags will be returned.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="downloadType"::: -->
:::moniker range="=azure-pipelines"

**`downloadType`** - **Download type**<br>
`string`. Required. Allowed values: `single` (Specific artifact), `specific` (Specific files). Default value: `single`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Download a specific artifact or specific files from the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactName"::: -->
:::moniker range="=azure-pipelines"

**`artifactName`** - **Artifact name**<br>
`string`. Required when `downloadType == single`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the artifact to download.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="itemPattern"::: -->
:::moniker range="=azure-pipelines"

**`itemPattern`** - **Matching pattern**<br>
`string`. Default value: `**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify files to be downloaded as multi line minimatch pattern. [More Information](https://aka.ms/minimatchexamples) <p>The default pattern (\*\*) will download all files across all artifacts in the build if "Specific files" option is selected. To download all files within artifact drop use drop/**.</p>
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="downloadPath"::: -->
:::moniker range="=azure-pipelines"

**`downloadPath`** - **Destination directory**<br>
`string`. Required. Default value: `$(System.ArtifactsDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path on the agent machine where the artifacts will be downloaded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parallelizationLimit"::: -->
:::moniker range="=azure-pipelines"

**`parallelizationLimit`** - **Parallelization limit**<br>
`string`. Default value: `8`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Number of files to download simultaneously.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkDownloadedFiles"::: -->
:::moniker range="=azure-pipelines"

**`checkDownloadedFiles`** - **Check downloaded files**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If checked, this build task will check that all files are fully downloaded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="retryDownloadCount"::: -->
:::moniker range="=azure-pipelines"

**`retryDownloadCount`** - **Retry count**<br>
`string`. Default value: `4`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional number of times to retry downloading a build artifact if the download fails.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="=azure-pipelines"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="BuildNumber"::: -->
**`BuildNumber`**<br><!-- :::editable-content name="Value"::: -->
Stores the build number of the build artifact source.<br />Please note that in fact it returns <b>BuildId</b> due to backward compatibility <p>[More Information](/azure/devops/pipelines/build/variables#build-variables-devops-services)</p>
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

> [!NOTE]
> The Azure Pipelines team recommends upgrading from **build artifacts** to **[Pipeline Artifacts](/azure/devops/pipelines/artifacts/pipeline-artifacts)** for faster performance.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.188.2 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->