---
title: UseDotNet@2 - Use dotnet v2 task
description: Acquires a specific version of the .NET Core SDK from the internet or the local cache and adds it to the PATH. Use this task to change the version of .NET Core used in subsequent tasks. Additionally provides proxy support.
ms.date: 12/19/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# UseDotNet@2 - Use dotnet v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to acquire a specific version of the .NET Core SDK from the internet or the local cache and add it to the PATH. Use this task to change the version of .NET Core that is used in subsequent tasks. This task also provides proxy support.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020.1"

```yaml
# Use .NET Core v2
# Acquires a specific version of the .NET Core SDK from the internet or the local cache and adds it to the PATH. Use this task to change the version of .NET Core used in subsequent tasks. Additionally provides proxy support.
- task: UseDotNet@2
  inputs:
    #packageType: 'sdk' # 'runtime' | 'sdk'. Package to install. Default: sdk.
    #useGlobalJson: false # boolean. Optional. Use when packageType = sdk. Use global json. Default: false.
    #workingDirectory: # string. Optional. Use when useGlobalJson = true. Working Directory. 
    #version: # string. Optional. Use when useGlobalJson = false || packageType = runtime. Version. 
    #includePreviewVersions: false # boolean. Optional. Use when useGlobalJson = false  || packageType = runtime. Include Preview Versions. Default: false.
  # Advanced
    #vsVersion: # string. Compatible Visual Studio version. 
    #installationPath: '$(Agent.ToolsDirectory)/dotnet' # string. Path To Install .Net Core. Default: $(Agent.ToolsDirectory)/dotnet.
    #performMultiLevelLookup: false # boolean. Perform Multi Level Lookup. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Use .NET Core v2
# Acquires a specific version of the .NET Core SDK from the internet or the local cache and adds it to the PATH. Use this task to change the version of .NET Core used in subsequent tasks. Additionally provides proxy support.
- task: UseDotNet@2
  inputs:
    #packageType: 'sdk' # 'runtime' | 'sdk'. Package to install. Default: sdk.
    #useGlobalJson: false # boolean. Optional. Use when packageType = sdk. Use global json. Default: false.
    #workingDirectory: # string. Optional. Use when useGlobalJson = true. Working Directory. 
    #version: # string. Optional. Use when useGlobalJson = false || packageType = runtime. Version. 
    #includePreviewVersions: false # boolean. Optional. Use when useGlobalJson = false  || packageType = runtime. Include Preview Versions. Default: false.
  # Advanced
    #installationPath: '$(Agent.ToolsDirectory)/dotnet' # string. Path To Install .Net Core. Default: $(Agent.ToolsDirectory)/dotnet.
    #performMultiLevelLookup: false # boolean. Perform Multi Level Lookup. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Use dotnet v2
# Acquires a specific version of the .NET Core SDK from the internet or the local cache and adds it to the PATH. Use this task to change the version of .NET Core used in subsequent tasks. Additionally provides proxy support.
- task: UseDotNet@2
  inputs:
    #packageType: 'sdk' # 'runtime' | 'sdk'. Package to install. Default: sdk.
    #version: # string. Version. 
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
`string`. Allowed values: `runtime`, `sdk` (SDK (contains runtime)). Default value: `sdk`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether to install only the .NET runtime or the SDK.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useGlobalJson"::: -->
:::moniker range=">=azure-pipelines-2020"

**`useGlobalJson`** - **Use global json**<br>
`boolean`. Optional. Use when `packageType = sdk`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Installs all SDKs from `global.json` files. These files are searched from `system.DefaultWorkingDirectory`. You can change the search root path by setting the working directory input.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2020"

**`workingDirectory`** - **Working Directory**<br>
`string`. Optional. Use when `useGlobalJson = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path from where `global.json` files should be searched when using `useGlobalJson`. If the value is empty, `system.DefaultWorkingDirectory` will be considered as the root path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range=">=azure-pipelines-2020"

**`version`** - **Version**<br>
`string`. Optional. Use when `useGlobalJson = false || packageType = runtime`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of the .NET Core SDK or runtime to install. The version value formats are shown with examples:

- `2.x`: Installs the latest SDK or runtime with the specified major version, `2`.
- `3.1.x`: Installs the latest SDK or runtime with the specified major and minor versions, `3` and `1`.
- `3.1.402`: Installs the specified SDK or runtime version, `3.1.402`.

The version values for SDK or runtime installations are in the `releases.json` file. The link to the `releases.json` of a major/minor version is in the [releases-index](https://github.com/dotnet/core/blob/master/release-notes/releases-index.json) file. For example, the link to the [releases.json file for version 3.1](https://dotnetcli.blob.core.windows.net/dotnet/release-metadata/3.1/releases.json).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`version`** - **Version**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of the .NET Core SDK or runtime to install. The version value formats are shown with examples:

- `2.x`: Installs the latest SDK or runtime with the specified major version, `2`.
- `3.1.x`: Installs the latest SDK or runtime with the specified major and minor versions, `3` and `1`.
- `3.1.402`: Installs the specified SDK or runtime version, `3.1.402`.

The version values for SDK or runtime installations are in the `releases.json` file. The link to the `releases.json` of a major/minor version is in the [releases-index](https://github.com/dotnet/core/blob/master/release-notes/releases-index.json) file. For example, the link to the [releases.json file for version 3.1](https://dotnetcli.blob.core.windows.net/dotnet/release-metadata/3.1/releases.json).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vsVersion"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`vsVersion`** - **Compatible Visual Studio version**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a compatible Visual Studio version for a corresponding .NET Core SDK installation. The value must be a complete version number, such as `16.6.4`, which contains a major version, a minor version, and a patch number.

The version values for SDK or runtime installations, which are used for the `version` string, are in the `releases.json` file. The link to the `releases.json` of a major/minor version is in the [releases-index](https://github.com/dotnet/core/blob/master/release-notes/releases-index.json) file. For example, the link to the [releases.json file for version 3.1](https://dotnetcli.blob.core.windows.net/dotnet/release-metadata/3.1/releases.json).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includePreviewVersions"::: -->
:::moniker range=">=azure-pipelines-2020"

**`includePreviewVersions`** - **Include Preview Versions**<br>
`boolean`. Optional. Use when `useGlobalJson = false  || packageType = runtime`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, includes preview versions when the task searches for latest runtime/SDK versions, such as searching for `2.2.x` or `3.1.x`. This setting is ignored if you specify an exact version, such as `3.0.100-preview3-010431`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`includePreviewVersions`** - **Include Preview Versions**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, includes preview versions when the task searches for latest runtime/SDK versions, such as searching for `2.2.x` or `3.1.x`. This setting is ignored if you specify an exact version, such as `3.0.100-preview3-010431`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="installationPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`installationPath`** - **Path To Install .Net Core**<br>
`string`. Default value: `$(Agent.ToolsDirectory)/dotnet`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies where the .NET Core SDK/Runtime should be installed. Different paths can have the following impact on .NET's behavior.

- **`$(Agent.ToolsDirectory)`**: Using this path caches the installation on the agent, as this directory is not cleaned across pipelines. All pipelines running on the agent have access to the previously installed versions.
- **`$(Agent.TempDirectory)`**: Using this path ensures that a pipeline doesn't use a cached version of .NET Core, as this folder is cleaned after each pipeline.
- **Another path**: You can use any path if the agent process has access to the path. This will change the state of the machine and impact all processes running on it.

> [!NOTE]
> You can use the **Multi-Level Lookup** setting, `performMultiLevelLookup`, to configure how the .NET host searches for versions.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="performMultiLevelLookup"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`performMultiLevelLookup`** - **Perform Multi Level Lookup**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Configures the behavior of the .NET host process when it searches for a suitable shared framework. The values are:

- **`false`**: The host process searches only for versions that are present in the folder that is specified by the task.
- **`true`**: The host process will search in predefined global locations using multi-level lookup. The default global locations are:
    - `C:\Program Files\dotnet` (64-bit processes)
    - `C:\Program Files (x86)\dotnet` (32-bit processes)

Learn more about [multi-level SharedFX lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).
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
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: DotNetCore |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Tool |

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

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