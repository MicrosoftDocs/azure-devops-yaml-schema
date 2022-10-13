---
title: DownloadPackage@1 - Download package v1 task
description: Download a package from a package management feed in Azure Artifacts.
ms.date: 09/26/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# DownloadPackage@1 - Download package v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to download a package from a package management feed in Azure Artifacts.
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
    packageType: 'nuget' # 'maven' | 'npm' | 'nuget' | 'pypi' | 'upack'. Required. Package Type. Default: nuget.
    feed: # string. Required. Feed. 
    #view: # string. View. 
    definition: # string. Required. Package. 
    version: # string. Required. Version. 
    downloadPath: '$(System.ArtifactsDirectory)' # string. Required. Destination directory. Default: $(System.ArtifactsDirectory).
  # Advanced
    #files: '**' # string. Optional. Use when packageType = maven || packageType = pypi || packageType = upack. Files. Default: **.
    #extract: true # boolean. Optional. Use when packageType = nuget || packageType = npm. Extract package contents. Default: true.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="packageType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`packageType`** - **Package Type**<br>
`string`. Required. Allowed values: `maven`, `npm`, `nuget`, `pypi` (Python), `upack` (Universal). Default value: `nuget`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feed"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`feed`** - **Feed**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
For project-scoped feeds, the format is `projectID/feedID`. See our [FAQ](/azure/devops/pipelines/tasks/utility/download-package) below to learn how to get a feed or project ID, or learn how to use a project and feed name instead.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="view"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`view`** - **View**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a view that only uses versions promoted to that specific view.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="definition"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`definition`** - **Package**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If you don't find the package in the list, you can provide the package ID, which you can find using the instructions [here](https://go.microsoft.com/fwlink/?linkid=2086778).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`version`** - **Version**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of the package. Use `latest` to download the latest version of the package at runtime.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="files"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`files`** - **Files**<br>
`string`. Optional. Use when `packageType = maven || packageType = pypi || packageType = upack`. Default value: `**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies which files to download using [file matching patterns](https://go.microsoft.com/fwlink/?linkid=2086953).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="extract"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`extract`** - **Extract package contents**<br>
`boolean`. Optional. Use when `packageType = nuget || packageType = npm`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Extracts the package contents and contains the package archive in the artifact folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="downloadPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

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

:::moniker range=">=azure-pipelines-2019.1"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to download a package from a package management feed in Azure Artifacts or TFS.

> [!NOTE]
> Requires the [Package Management extension](https://marketplace.visualstudio.com/items?itemName=ms.feed).

### How do I find the ID of the feed (or project) I want to download my artifact from

The get feed API can be used to retrieve the feed and project ID for your feed. The API is documented [here](/rest/api/azure/devops/artifacts/feed-management/get-feed).

### Can I use the project or feed name instead of IDs

Yes, you can use the project or feed name in your definition. However, if your project or feed is renamed in the future, your task will also have to be updated, or it might fail.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Download a NuGet package from an organization-scoped feed and extract to destination directory

```YAML
# Download an artifact with id 'cfe01b64-ded4-47b7-a569-2ac17cbcedbd' to $(System.ArtifactsDirectory)
- task: DownloadPackage@1
  inputs:
    packageType: 'nuget'
    feed: '6a60ef3b-e29f-41b6-9885-7874278baac7'
    definition: 'cfe01b64-ded4-47b7-a569-2ac17cbcedbd' # Can also be package name
    version: '1.0.0'
    extract: true
    downloadPath: '$(System.ArtifactsDirectory)'
```

### Download a maven package from a project-scoped feed and download only pom files

```YAML
# Download an artifact with name 'com.test:testpackage' to $(System.ArtifactsDirectory)
- task: DownloadPackage@1
  inputs:
    packageType: 'maven'
    feed: '132f5c2c-2aa0-475a-8b47-02c79617954b/c85e5de9-7b12-4cfd-9293-1b33cdff540e' # <projectId>/<feedId>
    definition: 'com.test:testpackage' 
    version: '1.0.0-snapshot' # Should be normalized version
    files: '*.pom'
    downloadPath: '$(System.ArtifactsDirectory)'
```
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