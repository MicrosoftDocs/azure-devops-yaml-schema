---
title: UniversalPackages@1 - Universal Packages v1 task
description: Publish or download Universal Packages using the Universal Packages v1 task.
ms.date: 06/29/2026
monikerRange: "=azure-pipelines"
---

# UniversalPackages@1 - Universal Packages v1 task

<!-- :::description::: -->
:::moniker range=">azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Use this task to publish or download Universal Packages to and from Azure Artifacts feeds. This version supports Workload Identity Federation (WIF) through Azure DevOps service connections, enabling authentication without Personal Access Tokens (PATs).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Universal packages v1
# Download or publish Universal Packages.
- task: UniversalPackages@1
  inputs:
    command: 'download' # 'download' | 'publish'. Required. Command. Default: download.
    #workloadIdentityServiceConnection: # string. Alias: adoServiceConnection | azureDevOpsServiceConnection. Azure DevOps Service Connection. 
    #organization: # string. Optional. Use when adoServiceConnection != ''. Organization. 
    feed: # string. Required. Feed. 
    packageName: # string. Required. Package name. 
    #packageVersion: # string. Package version. 
    #versionIncrement: # 'major' | 'minor' | 'patch'. Optional. Use when command = publish. Version increment. 
    directory: '$(System.DefaultWorkingDirectory)' # string. Required. Directory. Default: $(System.DefaultWorkingDirectory).
    #packageDescription: # string. Optional. Use when command = publish. Description.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="command"::: -->
:::moniker range=">azure-pipelines-server"

**`command`** - **Command**<br>
`string`. Required. Allowed values: `download`, `publish`. Default value: `download`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Universal Package command to run: download a package from a feed, or publish a package to a feed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workloadIdentityServiceConnection"::: -->
:::moniker range=">azure-pipelines-server"

**`workloadIdentityServiceConnection`** - **Azure DevOps Service Connection**<br>
[Input alias](index.md#what-are-task-input-aliases): `adoServiceConnection | azureDevOpsServiceConnection`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of an Azure DevOps Service Connection that uses Workload Identity Federation (WIF) for authentication. When specified, the task uses the service connection identity instead of the pipeline's build service identity. This enables scenarios such as cross-organization feed access and WIF-based authentication without PATs.

When not specified, the task authenticates using the pipeline’s built‑in build service identity. See [Setting up an Azure DevOps Service Connection](/azure/devops/pipelines/library/service-endpoints) for setup instructions.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="organization"::: -->
:::moniker range=">azure-pipelines-server"

**`organization`** - **Organization**<br>
`string`. Optional. Use when `adoServiceConnection != ''`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Azure DevOps organization that hosts the target feed. Use this input when the feed is in a different organization than the one running the pipeline.

If not specified, the task uses the current pipeline’s organization.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feed"::: -->
:::moniker range=">azure-pipelines-server"

**`feed`** - **Feed**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Azure Artifacts feed. For organization-scoped feeds, specify only the feed name. For project-scoped feeds, use the format `project/feed`, where `project` is the project name and `feed` is the feed name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageName"::: -->
:::moniker range=">azure-pipelines-server"

**`packageName`** - **Package name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Universal Package to download or publish. Package names must be lower case and can only use letters, numbers, and dashes `-`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageVersion"::: -->
:::moniker range=">azure-pipelines-server"

**`packageVersion`** - **Package version**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of the package. Required for `download`. For `publish`, specify either this input or `versionIncrement`, but not both.

For downloads, this can be a wildcard expression such as `*` to get the latest version, `1.*` to get the latest version with major version 1, or `1.2.*` to get the latest patch release with major version 1 and minor version 2. Wildcard patterns are not supported for pre-release packages.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionIncrement"::: -->
:::moniker range=">azure-pipelines-server"

**`versionIncrement`** - **Version increment**<br>
`string`. Optional. Use when `command = publish`. Allowed values: `major`, `minor`, `patch`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Automatically increments the package version. The task queries the feed for the latest existing version of the package and increments the specified component. Cannot be used together with `packageVersion`.

For new packages with no existing versions in the feed, the starting version is:

- `major`: 1.0.0  
- `minor`: 0.1.0  
- `patch`: 0.0.1
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="directory"::: -->
:::moniker range=">azure-pipelines-server"

**`directory`** - **Directory**<br>
`string`. Required. Default value: `$(System.DefaultWorkingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
For downloads, specifies the folder path where the package contents will be downloaded. For publish, specifies the path to the directory that contains the files to publish.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageDescription"::: -->
:::moniker range=">azure-pipelines-server"

**`packageDescription`** - **Description**<br>
`string`. Optional. Use when `command = publish`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Description of the package contents and/or the changes included in this version of the package.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">azure-pipelines-server"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="packageName"::: -->
**`packageName`**<br><!-- :::editable-content name="Value"::: -->
The name of the published package. Only set when command is `publish`.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="packageVersion"::: -->
**`packageVersion`**<br><!-- :::editable-content name="Value"::: -->
The version of the published package. Only set when command is `publish`. Especially useful with `versionIncrement`, where the version is computed at runtime.
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

:::moniker range="=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  4.248.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
