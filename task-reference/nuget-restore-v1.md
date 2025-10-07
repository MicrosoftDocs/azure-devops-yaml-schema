---
title: NuGetRestore@1 - NuGet Restore v1 task
description: Restores NuGet packages in preparation for a Visual Studio Build step.
ms.date: 10/07/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
author: ramiMSFT
ms.author: rabououn
---

# NuGetRestore@1 - NuGet Restore v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Use this task to restore NuGet packages in preparation for a Visual Studio Build step.

> [!IMPORTANT]
> This task is deprecated. Builds that use it will break on 11-27-2023. Please switch to using [NuGetCommand@2](./nuget-command-v2.md)'s `restore` option as soon as possible. For more information, see [Migrate from NuGetInstaller@0 or NuGetRestore@1](./nuget-command-v2.md#migrate-from-nugetinstaller0-or-nugetrestore1).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Use this task to restore NuGet packages in preparation for a Visual Studio Build step.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.1"

<!-- :::editable-content name="description"::: -->
Use this task to restore NuGet packages in preparation for a Visual Studio Build step.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.2"

```yaml
# NuGet Restore v1
# Restores NuGet packages in preparation for a Visual Studio Build step.
- task: NuGetRestore@1
  inputs:
    solution: '**/*.sln' # string. Required. Path to solution, packages.config, or project.json. Default: **/*.sln.
    selectOrConfig: 'select' # 'select' | 'config'. Required. Feeds to use. Default: select.
    #feed: # string. Optional. Use when selectOrConfig = select. Use packages from this Azure Artifacts feed. 
    #includeNuGetOrg: true # boolean. Optional. Use when selectOrConfig = select. Use packages from NuGet.org. Default: true.
    #nugetConfigPath: # string. Optional. Use when selectOrConfig = config. Path to NuGet.config. 
  # Advanced
    #noCache: false # boolean. Disable local cache. Default: false.
    #packagesDirectory: # string. Destination directory. 
    #verbosity: 'Detailed' # '-' | 'Quiet' | 'Normal' | 'Detailed'. Verbosity. Default: Detailed.
```

:::moniker-end

:::moniker range="<=azure-pipelines-2022.1"

```yaml
# NuGet Restore v1
# Restores NuGet packages in preparation for a Visual Studio Build step.
- task: NuGetRestore@1
  inputs:
    solution: '**/*.sln' # string. Required. Path to solution, packages.config, or project.json. Default: **/*.sln.
    selectOrConfig: 'select' # 'select' | 'config'. Required. Feeds to use. Default: select.
    #feed: # string. Optional. Use when selectOrConfig = select. Use packages from this VSTS feed. 
    #includeNuGetOrg: true # boolean. Optional. Use when selectOrConfig = select. Use packages from NuGet.org. Default: true.
    #nugetConfigPath: # string. Optional. Use when selectOrConfig = config. Path to NuGet.config. 
  # Advanced
    #noCache: false # boolean. Disable local cache. Default: false.
    #packagesDirectory: # string. Destination directory. 
    #verbosity: 'Detailed' # '-' | 'Quiet' | 'Normal' | 'Detailed'. Verbosity. Default: Detailed.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="solution"::: -->
:::moniker range="<=azure-pipelines"

**`solution`** - **Path to solution, packages.config, or project.json**<br>
`string`. Required. Default value: `**/*.sln`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the solution, `packages.config`, or `project.json` file that references the packages to be restored.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="selectOrConfig"::: -->
:::moniker range="<=azure-pipelines"

**`selectOrConfig`** - **Feeds to use**<br>
`string`. Required. Allowed values: `select` (Feed(s) I select here), `config` (Feeds in my NuGet.config). Default value: `select`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the feed(s) to use. Specify one feed from VSTS and/or NuGet.org using the `select` value. Specify multiple feeds by committing a `nuget.config` file to your source code repository and setting its path with the `config` value.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feed"::: -->
:::moniker range=">=azure-pipelines-2022.2"

**`feed`** - **Use packages from this Azure Artifacts feed**<br>
`string`. Optional. Use when `selectOrConfig = select`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes the specified VSTS feed in the generated `NuGet.config` file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2022.1"

**`feed`** - **Use packages from this VSTS feed**<br>
`string`. Optional. Use when `selectOrConfig = select`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes the specified VSTS feed in the generated `NuGet.config` file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeNuGetOrg"::: -->
:::moniker range="<=azure-pipelines"

**`includeNuGetOrg`** - **Use packages from NuGet.org**<br>
`boolean`. Optional. Use when `selectOrConfig = select`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes the specified NuGet.org feed in the generated `NuGet.config`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nugetConfigPath"::: -->
:::moniker range="<=azure-pipelines"

**`nugetConfigPath`** - **Path to NuGet.config**<br>
`string`. Optional. Use when `selectOrConfig = config`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the `NuGet.config` in your repository that specifies the feeds from which to restore packages.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="noCache"::: -->
:::moniker range="<=azure-pipelines"

**`noCache`** - **Disable local cache**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prevents NuGet from using packages from local machine caches. Equivalent to the `-NoCache NuGet.exe` command line argument.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagesDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`packagesDirectory`** - **Destination directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the folder in which packages are installed. If no folder is specified, packages are restored into a `packages/` folder alongside the selected solution, `packages.config`, or `project.json`. Equivalent to the `-PackagesDirectory NuGet.exe` command line argument.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosity"::: -->
:::moniker range="<=azure-pipelines"

**`verbosity`** - **Verbosity**<br>
`string`. Allowed values: `-`, `Quiet`, `Normal`, `Detailed`. Default value: `Detailed`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the amount of detail displayed in the output.
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
## Remarks

### Why is my build pipeline failing and prompting for Single Sign-On (SSO) authentication?

Builds can fail if credentials have expired. To avoid these failures, we recommend using the [NuGet Authenticate](nuget-authenticate-v1.md) task to reinstall the credential provider and automatically refresh credentials. This ensures uninterrupted access during pipeline execution.

```yaml
steps:
# Authenticate with NuGet to ensure credentials are refreshed
- task: NuGetAuthenticate@1
# Restore NuGet packages
- task: NuGetRestore@1
  inputs:
    solution: '**/*.sln'
```
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022.2"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Package |

:::moniker-end

:::moniker range="<=azure-pipelines-2022.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
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
