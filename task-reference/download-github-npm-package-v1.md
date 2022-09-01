---
title: DownloadGithubNpmPackage@1 - Download Github Npm Package v1 task
description: Install npm packages from GitHub.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2020"
---

# DownloadGithubNpmPackage@1 - Download Github Npm Package v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Install npm packages from GitHub.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Download Github Npm Package v1
# Install npm packages from GitHub.
- task: DownloadGithubNpmPackage@1
  inputs:
    packageName: # string. Required. Package Name. 
    version: # string. Required. Package Version. 
    externalRegistryCredentials: # string. Required. Credentials for registry from GitHub. 
    #installDirectory: # string. Destination directory.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="packageName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`packageName`** - **Package Name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the package to download from github.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range=">=azure-pipelines-2020"

**`version`** - **Package Version**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Version of the package to download from github.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="externalRegistryCredentials"::: -->
:::moniker range=">=azure-pipelines-2020"

**`externalRegistryCredentials`** - **Credentials for registry from GitHub**<br>
Input alias: `externalEndpoints`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Credentials to use for external registry from GitHub.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="installDirectory"::: -->
:::moniker range=">=azure-pipelines-2020"

**`installDirectory`** - **Destination directory**<br>
Input alias: `packagesDirectory`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the folder in which packages are installed. If no folder is specified, packages are restored into the default system working directory.
<!-- :::editable-content-end::: -->

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

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: npm |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->