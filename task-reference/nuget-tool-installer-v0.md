---
title: NuGetToolInstaller@0 - NuGet tool installer v0 task
description: Acquires a specific version of NuGet from the internet or the tools cache and adds it to the PATH. Use this task to change the version of NuGet used in the NuGet tasks (task version 0).
ms.date: 07/10/2023
monikerRange: "<=azure-pipelines"
---

# NuGetToolInstaller@0 - NuGet tool installer v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to find, download, and cache a specified version of [NuGet](https://nuget.org/) and add it to the PATH. For information on the tools cache, see the [azure-pipelines-tool-lib](https://github.com/microsoft/azure-pipelines-tool-lib/blob/master/docs/overview.md#tool-cache) repo.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# NuGet tool installer v0
# Acquires a specific version of NuGet from the internet or the tools cache and adds it to the PATH. Use this task to change the version of NuGet used in the NuGet tasks.
- task: NuGetToolInstaller@0
  inputs:
    #versionSpec: # string. Version of NuGet.exe to install. 
    #checkLatest: false # boolean. Always download the latest matching version. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# NuGet tool installer v0
# Acquires a specific version of NuGet from the internet or the tools cache and adds it to the PATH. Use this task to change the version of NuGet used in the NuGet tasks.
- task: NuGetToolInstaller@0
  inputs:
    versionSpec: '4.3.0' # string. Required. Version of NuGet.exe to install. Default: 4.3.0.
    #checkLatest: false # boolean. Always download the latest matching version. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# NuGet Tool Installer v0
# Acquires a specific version of NuGet from the internet or the tools cache and adds it to the PATH. Use this task to change the version of NuGet used in the NuGet tasks.
- task: NuGetToolInstaller@0
  inputs:
    versionSpec: '4.3.0' # string. Required. Version of NuGet.exe to install. Default: 4.3.0.
    #checkLatest: false # boolean. Always download the latest matching version. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="versionSpec"::: -->
:::moniker range=">=azure-pipelines-2020"

**`versionSpec`** - **Version of NuGet.exe to install**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A version or version range that specifies the NuGet version to make available on the path. Use x as a wildcard. See the [list of available NuGet versions](https://dist.nuget.org/tools.json).

If you want to match a pre-release version, the specification must contain a major, minor, patch, and pre-release version from the list above. If a version isn't specified, then one will be chosen automatically.

Examples: `4.x`, `3.3.x`, `2.8.6`, `>=4.0.0-0`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`versionSpec`** - **Version of NuGet.exe to install**<br>
`string`. Required. Default value: `4.3.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A version or version range that specifies the NuGet version to make available on the path. Use x as a wildcard. See the [list of available NuGet versions](https://dist.nuget.org/tools.json).

If you want to match a pre-release version, the specification must contain a major, minor, patch, and pre-release version from the list above. If a version isn't specified, then one will be chosen automatically.

Examples: `4.x`, `3.3.x`, `2.8.6`, `>=4.0.0-0`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkLatest"::: -->
:::moniker range="<=azure-pipelines"

**`checkLatest`** - **Always download the latest matching version**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When this boolean is set to `true`, the task always checks for and downloads the latest available version of `NuGet.exe` that satisfies the version spec. This option will also always incur download time, even if the selected version of NuGet is already cached.

Enabling this option could cause unexpected build breaks when a new version of NuGet is released.

> [!TIP]
> If you're using [the Microsoft-hosted agents](/azure/devops/pipelines/agents/hosted), you should leave this set to false. Microsoft updates the Microsoft-hosted agents on a regular basis, but they're often slightly behind the latest version. Enabling this parameter could result in your build spending a lot of time updating to a newer minor version.
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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: NuGet |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Tool |

:::moniker-end

:::moniker range="<=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: NuGet |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Tool |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->