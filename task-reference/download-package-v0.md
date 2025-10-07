---
title: DownloadPackage@0 - Download package v0 task
description: Download a package from a package management feed in Azure Artifacts (task version 0).
ms.date: 10/07/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
author: ramiMSFT
ms.author: rabououn
---

# DownloadPackage@0 - Download package v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2022.1"

<!-- :::editable-content name="description"::: -->
Use this task to download a package from a package management feed in Azure Artifacts.

This task is deprecated; use [DownloadPackage@1](./download-package-v1.md).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022"

<!-- :::editable-content name="description"::: -->
Use this task to download a package from a package management feed in Azure Artifacts.
<!-- :::editable-content-end::: -->

:::moniker-end

<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Download package v0
# Download a package from a package management feed in Azure Artifacts.
- task: DownloadPackage@0
  inputs:
    feed: # string. Required. Feed. 
    definition: # string. Required. Package. 
    version: # string. Required. Version. 
    downloadPath: '$(System.ArtifactsDirectory)' # string. Required. Destination directory. Default: $(System.ArtifactsDirectory).
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="feed"::: -->
:::moniker range="<=azure-pipelines"

**`feed`** - **Feed**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the package source.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="definition"::: -->
:::moniker range="<=azure-pipelines"

**`definition`** - **Package**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the package to download. Only NuGet packages are currently supported.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range="<=azure-pipelines"

**`version`** - **Version**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of the package.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="downloadPath"::: -->
:::moniker range="<=azure-pipelines"

**`downloadPath`** - **Destination directory**<br>
`string`. Required. Default value: `$(System.ArtifactsDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path on the agent machine where the package is downloaded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
:::moniker range="<=azure-pipelines"

## Remarks

There is a newer version of this task available at [DownloadPackage@1](./download-package-v1.md).

:::moniker-end
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022.1"

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

:::moniker range="<=azure-pipelines-2022"

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