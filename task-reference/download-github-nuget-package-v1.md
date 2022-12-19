---
title: DownloadGitHubNugetPackage@1 - Download GitHub Nuget Packages v1 task
description: Restore your nuget packages using dotnet CLI.
ms.date: 12/19/2022
monikerRange: ">=azure-pipelines-2020"
---

# DownloadGitHubNugetPackage@1 - Download GitHub Nuget Packages v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Use this task to restore your NuGet packages using dotnet CLI.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Download GitHub Nuget Packages v1
# Restore your nuget packages using dotnet CLI.
- task: DownloadGitHubNugetPackage@1
  inputs:
    packageName: # string. Required. Package Name. 
    version: # string. Required. Package Version. 
  # Feeds and authentication
    #externalFeedCredentials: # string. Alias: externalEndpoints. Required when selectOrConfig = config. Credentials for feed from GitHub. 
  # Advanced
    #restoreDirectory: # string. Alias: packagesDirectory. Destination directory.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="packageName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`packageName`** - **Package Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the package to download from GitHub.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range=">=azure-pipelines-2020"

**`version`** - **Package Version**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of the package to download from GitHub.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="externalFeedCredentials"::: -->
:::moniker range=">=azure-pipelines-2020"

**`externalFeedCredentials`** - **Credentials for feed from GitHub**<br>
Input alias: `externalEndpoints`. `string`. Required when `selectOrConfig = config`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the credentials to use for external registry from GitHub.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restoreDirectory"::: -->
:::moniker range=">=azure-pipelines-2020"

**`restoreDirectory`** - **Destination directory**<br>
Input alias: `packagesDirectory`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the folder where packages are installed. If no folder is specified, packages are restored into the default system working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020"

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

:::moniker range="=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Build |

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->