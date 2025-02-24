---
title: DownloadFileshareArtifacts@1 - Download artifacts from file share v1 task
description: Download artifacts from a file share, like \\share\drop.
ms.date: 02/24/2025
monikerRange: ">=azure-pipelines-2019"
---

# DownloadFileshareArtifacts@1 - Download artifacts from file share v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to download artifacts from a file share, like `\\share\drop`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Download artifacts from file share v1
# Download artifacts from a file share, like \\share\drop.
- task: DownloadFileshareArtifacts@1
  inputs:
    filesharePath: # string. Required. File share path. 
    artifactName: # string. Required. Artifact name. 
    #itemPattern: '**' # string. Matching pattern. Default: **.
    downloadPath: '$(System.ArtifactsDirectory)' # string. Required. Download path. Default: $(System.ArtifactsDirectory).
  # Advanced
    #parallelizationLimit: '8' # string. Parallelization limit. Default: 8.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Download Fileshare Artifacts v1
# Download artifacts from a file share e.g \\share\drop.
- task: DownloadFileshareArtifacts@1
  inputs:
    filesharePath: # string. Required. Fileshare path. 
    artifactName: # string. Required. Artifact name. 
    #itemPattern: '**' # string. Matching pattern. Default: **.
    downloadPath: '$(System.ArtifactsDirectory)' # string. Required. Download path. Default: $(System.ArtifactsDirectory).
  # Advanced
    #parallelizationLimit: '8' # string. Parallelization limit. Default: 8.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="filesharePath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`filesharePath`** - **File share path**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the file share path (for example: `\\server\folder`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`filesharePath`** - **Fileshare path**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the file share path (for example: `\\server\folder`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`artifactName`** - **Artifact name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the artifact to download (for example: `drop`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="itemPattern"::: -->
:::moniker range=">=azure-pipelines-2019"

**`itemPattern`** - **Matching pattern**<br>
`string`. Default value: `**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the files to be downloaded as a multi line minimatch pattern. Learn more about [file matching patterns](https://aka.ms/minimatchexamples).

The default pattern (`**`) downloads all files within the artifact.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="downloadPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`downloadPath`** - **Download path**<br>
`string`. Required. Default value: `$(System.ArtifactsDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path on the agent machine where the artifacts are downloaded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parallelizationLimit"::: -->
:::moniker range=">=azure-pipelines-2019"

**`parallelizationLimit`** - **Parallelization limit**<br>
`string`. Default value: `8`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the number of files to download simultaneously.
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

Use this task to download file share artifacts.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022"

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

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020.1"

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
