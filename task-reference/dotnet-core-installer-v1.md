---
title: DotNetCoreInstaller@1 - .NET Core SDK/runtime installer v1 task
description: Acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH.
ms.date: 07/02/2024
monikerRange: ">=azure-pipelines-2019.1"
---

# DotNetCoreInstaller@1 - .NET Core SDK/runtime installer v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH.

> [!IMPORTANT]
> [!INCLUDE [task-deprecation](includes/task-deprecation.md)] Use [UseDotNet@2](use-dotnet-v2.md).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Use this task to acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH.

> [!IMPORTANT]
> TThis task is deprecated. Use [@UseDotNet2](use-dotnet-v2.md).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Acquires a specific version of the .NET Core SDK from the internet or local cache and adds it to the PATH.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# .NET Core SDK/runtime installer v1
# Acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH.
- task: DotNetCoreInstaller@1
  inputs:
    packageType: 'sdk' # 'runtime' | 'sdk'. Required. Package to install. Default: sdk.
    version: '2.2.x' # string. Required. Version. Default: 2.2.x.
    #includePreviewVersions: false # boolean. Include Preview Versions. Default: false.
  # Advanced
    #installationPath: '$(Agent.ToolsDirectory)/dotnet' # string. Path To Install .Net Core. Default: $(Agent.ToolsDirectory)/dotnet.
    #performMultiLevelLookup: false # boolean. Perform Multi Level Lookup. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="packageType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`packageType`** - **Package to install**<br>
`string`. Required. Allowed values: `runtime` (Only Runtime), `sdk` (SDK (contains runtime)). Default value: `sdk`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether to install only Runtime or the full SDK.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`version`** - **Version**<br>
`string`. Required. Default value: `2.2.x`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of .NET Core SDK or Runtime to install.

Use the following format to specify the version:

* 2.x: Installs the latest in major version.
* 2.2.x: Installs the latest in major and minor version.
* 2.2.104: Installs the exact version.

Find the value of `version` for installing SDK/Runtime in the [releases-index file](https://github.com/dotnet/core/blob/master/release-notes/releases-index.json).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includePreviewVersions"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`includePreviewVersions`** - **Include Preview Versions**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies if you want preview versions to be included while searching for latest versions. This setting is ignored if you specify an exact version, such as `3.0.100-preview3-010431`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="installationPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`installationPath`** - **Path To Install .Net Core**<br>
`string`. Default value: `$(Agent.ToolsDirectory)/dotnet`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies where .NET Core SDK/Runtime should be installed. Different paths can have the following impact on .NET's behavior:

* **$(Agent.ToolsDirectory)**: This determines the version to be cached on the agent since this directory isn't cleaned up across pipelines. All pipelines running on the agent, would have access to the versions installed previously using the agent.
* **$(Agent.TempDirectory)**: This can ensure that a pipeline doesn't use any cached version of .NET core since this folder is cleaned up after each pipeline.
* **Any other path**: You can configure any other path, given the agent process has access to the path. This will change the state of the machine and impact all processes running on it.

You can also configure the Multi-Level Lookup setting. This setting can configure .NET host to probe for a suitable version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="performMultiLevelLookup"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`performMultiLevelLookup`** - **Perform Multi Level Lookup**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This input is only applicable to Windows-based agents. This input configures the behavior of .NET host processes for looking up a suitable shared framework. `False` means that only versions present in the folder specified in this task would be looked by the host process. `True` means that the host will attempt to look in pre-defined global locations using Multi-level Lookup.

For Windows, the default global locations are: 
* `C:\Program Files\dotnet` (64-bit processes)
* `C:\Program Files (x86)\dotnet` (32-bit process)

For more information, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).
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

This task is deprecated. Use [@UseDotNet2](use-dotnet-v2.md).

What's new in this task version.
* Support for installing multiple versions side by side.
* Support for patterns in version to fetch latest in minor/major version.
* Restrict Multi-level lookup.
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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: DotNetCore |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Tool |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
