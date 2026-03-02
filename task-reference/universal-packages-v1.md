---
title: UniversalPackages@1 - Universal packages v1 task
description: Download or publish Universal Packages.
ms.date: 03/02/2026
monikerRange: "=azure-pipelines"
author: ramiMSFT
ms.author: rabououn
---

# UniversalPackages@1 - Universal packages v1 task

<!-- :::description::: -->
:::moniker range=">azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Download or publish Universal Packages.
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
The Universal Package command to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feed"::: -->
:::moniker range=">azure-pipelines-server"

**`feed`** - **Feed**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The feed name. For project-scoped feeds, use 'project/feed' format.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageName"::: -->
:::moniker range=">azure-pipelines-server"

**`packageName`** - **Package name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Universal Package. Package names must be lower case and can only use letters, numbers, and dashes (-).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageVersion"::: -->
:::moniker range=">azure-pipelines-server"

**`packageVersion`** - **Package version**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of the package. Required for download. For publish, either specify this or use 'versionIncrement' for auto-incrementing. For downloads, this can also be a wildcard expression such as * to get the highest version, 1.* to get the highest version with major version 1, or 1.2.* to get the highest patch release with major version 1 and minor version 2.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionIncrement"::: -->
:::moniker range=">azure-pipelines-server"

**`versionIncrement`** - **Version increment**<br>
`string`. Optional. Use when `command = publish`. Allowed values: `major`, `minor`, `patch`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Cannot be used with 'packageVersion'. Automatically increment the package version. Queries the feed for the highest existing version and increments the specified component. For new packages, starts at 1.0.0 (major), 0.1.0 (minor), or 0.0.1 (patch).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="directory"::: -->
:::moniker range=">azure-pipelines-server"

**`directory`** - **Directory**<br>
`string`. Required. Default value: `$(System.DefaultWorkingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
For downloads: folder path where the package's contents will be downloaded. For publish: path to the directory containing files to publish.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageDescription"::: -->
:::moniker range=">azure-pipelines-server"

**`packageDescription`** - **Description**<br>
`string`. Optional. Use when `command = publish`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Description of the contents of this package and/or the changes made in this version of the package.
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
The name of the published package. Only set when command is 'publish'.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="packageVersion"::: -->
**`packageVersion`**<br><!-- :::editable-content name="Value"::: -->
The version of the published package. Only set when command is 'publish'. Especially useful with versionIncrement, where the version is computed at runtime.
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