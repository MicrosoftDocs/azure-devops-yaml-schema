---
title: DownloadPackage@1 - Download package v1 task
description: Download a package from a package management feed in Azure Artifacts.
ms.date: 08/10/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# DownloadPackage@1 - Download package v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Download a package from a package management feed in Azure Artifacts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Download package v1
# Download a package from a package management feed in Azure Artifacts.
- task: DownloadPackage@1
  inputs:
    packageType: 'nuget' # 'maven' | 'npm' | 'nuget' | 'pypi' | 'upack'. Required. Package Type. Default: 'nuget'.
    feed: # string. Required. Feed. 
    #view: # string. View. 
    definition: # string. Required. Package. 
    version: # string. Required. Version. 
    downloadPath: '$(System.ArtifactsDirectory)' # string. Required. Destination directory. Default: '$(System.ArtifactsDirectory)'.
  # Advanced
    #files: '**' # string. Optional. Use when packageType = maven || packageType = pypi || packageType = upack. Files. Default: '**'.
    #extract: true # boolean. Optional. Use when packageType = nuget || packageType = npm. Extract package contents. Default: true.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="packageType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`packageType`** - **Package Type**<br>
Type: string. Required. Allowed values: 'maven', 'npm', 'nuget', 'pypi', 'upack'. Default value: 'nuget'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feed"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`feed`** - **Feed**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the package source.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="view"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`view`** - **View**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a view to use only versions promoted to that view.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="definition"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`definition`** - **Package**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If you don't find the package in the list, you can provide the package ID, which you can find using the instructions [here](https://go.microsoft.com/fwlink/?linkid=2086778).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`version`** - **Version**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Version of the package. Use `latest` to download the latest version of the package at runtime.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="files"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`files`** - **Files**<br>
Type: string. Optional. Use when packageType = maven || packageType = pypi || packageType = upack. Default value: '**'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify which files to download using [file matching patterns](https://go.microsoft.com/fwlink/?linkid=2086953).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="extract"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`extract`** - **Extract package contents**<br>
Type: boolean. Optional. Use when packageType = nuget || packageType = npm. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Instead of extracting the package contents and removing the archive, the artifact folder will contain the package archive.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="downloadPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`downloadPath`** - **Destination directory**<br>
Type: string. Required. Default value: '$(System.ArtifactsDirectory)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path on the agent machine where the package will be downloaded.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
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

Adds support to download Maven, Python, Universal and Npm packages.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->