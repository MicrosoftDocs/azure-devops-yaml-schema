---
title: DownloadGitHubRelease@0 - Download GitHub Release v0 task
description: Downloads a GitHub Release from a repository.
ms.date: 10/13/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# DownloadGitHubRelease@0 - Download GitHub Release v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Downloads a GitHub Release from a repository.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Download GitHub Release v0
# Downloads a GitHub Release from a repository.
- task: DownloadGitHubRelease@0
  inputs:
    connection: # string. Required. GitHub Connection. 
    userRepository: # string. Required. Repository. 
    defaultVersionType: 'latest' # 'latest' | 'specificVersion' | 'specificTag'. Required. Default version. Default: latest.
    version: # string. Required when defaultVersionType != latest. Release. 
    #itemPattern: '**' # string. Item Pattern. Default: **.
    downloadPath: '$(System.ArtifactsDirectory)' # string. Required. Destination directory. Default: $(System.ArtifactsDirectory).
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="connection"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`connection`** - **GitHub Connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the service connection name for your GitHub service connection. Learn more about [service connections](/azure/devops/pipelines/library/service-endpoints).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="userRepository"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`userRepository`** - **Repository**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the GitHub repository that GitHub releases will be downloaded from.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="defaultVersionType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`defaultVersionType`** - **Default version**<br>
`string`. Required. Allowed values: `latest` (Latest Release), `specificVersion` (Specific Version), `specificTag` (Specific Tag). Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Downloads assets from the latest GitHub release or a specific GitHub release version/tag.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`version`** - **Release**<br>
`string`. Required when `defaultVersionType != latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Defines the GitHub release version/tag to download. This option appears if `specificVersion` or `specificTag` is selected as the value for `defaultVersionType`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="itemPattern"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`itemPattern`** - **Item Pattern**<br>
`string`. Default value: `**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Minimatch pattern to filter files to be downloaded. To download all files within a release, use `**`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="downloadPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`downloadPath`** - **Destination directory**<br>
`string`. Required. Default value: `$(System.ArtifactsDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path on the agent machine where the release assets will be downloaded.
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

Use this task in your pipeline to download assets from your [GitHub release](https://help.github.com/categories/releases/) as part of your CI/CD pipeline.

### GitHub service connection
This task requires a [GitHub service connection](/azure/devops/pipelines/library/service-endpoints#github-service-connection) with **Read** permission to the GitHub repository. You can create a GitHub service connection in your Azure Pipelines project. Once created, use the name of the service connection in this task's settings.
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
| Agent version |  2.144.0 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.99.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->