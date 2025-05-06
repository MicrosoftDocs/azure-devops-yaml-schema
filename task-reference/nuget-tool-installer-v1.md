---
title: NuGetToolInstaller@1 - NuGet tool installer v1 task
description: Acquires a specific version of NuGet from the internet or the tools cache and adds it to the PATH. Use this task to change the version of NuGet used in the NuGet tasks.
ms.date: 05/06/2025
monikerRange: "<=azure-pipelines"
author: ramiMSFT
ms.author: rabououn
---

# NuGetToolInstaller@1 - NuGet tool installer v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Acquires a specific version of NuGet from the internet or the tools cache and adds it to the PATH. Use this task to change the version of NuGet used in the NuGet tasks.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# NuGet tool installer v1
# Acquires a specific version of NuGet from the internet or the tools cache and adds it to the PATH. Use this task to change the version of NuGet used in the NuGet tasks.
- task: NuGetToolInstaller@1
  inputs:
  # Advanced
    #versionSpec: # string. Version of NuGet.exe to install. 
    #checkLatest: false # boolean. Always check for new versions. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="versionSpec"::: -->
:::moniker range="<=azure-pipelines"

**`versionSpec`** - **Version of NuGet.exe to install**<br>
`string`.<br>
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

**`checkLatest`** - **Always check for new versions**<br>
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
## Remarks

Use this task to find, download, and cache a specified version of [NuGet](https://nuget.org/) and add it to the PATH. For information on the tools cache, see the [azure-pipelines-tool-lib](https://github.com/microsoft/azure-pipelines-tool-lib/blob/master/docs/overview.md#tool-cache) repo.
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
## See also

For an explanation of tool installers and examples, see [Tool installers](/azure/devops/pipelines/process/tasks#tool-installers).
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->