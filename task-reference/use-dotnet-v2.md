---
title: UseDotNet@2 - Use dotnet v2 task
description: Acquires a specific version of the .NET Core SDK from the internet or the local cache and adds it to the PATH. Use this task to change the version of .NET Core used in subsequent tasks. Additionally provides proxy support.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# UseDotNet@2 - Use dotnet v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Acquires a specific version of the .NET Core SDK from the internet or the local cache and adds it to the PATH. Use this task to change the version of .NET Core used in subsequent tasks. Additionally provides proxy support.
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
    #packageType: 'sdk' # 'runtime' | 'sdk'. Package to install. Default: 'sdk'.
    #useGlobalJson: false # boolean. Optional. Use when packageType = sdk. Use global json. Default: false.
    #workingDirectory: # string. Optional. Use when useGlobalJson = true. Working Directory. 
    #version: # string. Optional. Use when useGlobalJson = false || packageType = runtime. Version. 
    #includePreviewVersions: false # boolean. Optional. Use when useGlobalJson = false  || packageType = runtime. Include Preview Versions. Default: false.
  # Advanced
    #vsVersion: # string. Compatible Visual Studio version. 
    #installationPath: '$(Agent.ToolsDirectory)/dotnet' # string. Path To Install .Net Core. Default: '$(Agent.ToolsDirectory)/dotnet'.
    #performMultiLevelLookup: false # boolean. Perform Multi Level Lookup. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Use .NET Core v2
# Acquires a specific version of the .NET Core SDK from the internet or the local cache and adds it to the PATH. Use this task to change the version of .NET Core used in subsequent tasks. Additionally provides proxy support.
- task: UseDotNet@2
  inputs:
    #packageType: 'sdk' # 'runtime' | 'sdk'. Package to install. Default: 'sdk'.
    #useGlobalJson: false # boolean. Optional. Use when packageType = sdk. Use global json. Default: false.
    #workingDirectory: # string. Optional. Use when useGlobalJson = true. Working Directory. 
    #version: # string. Optional. Use when useGlobalJson = false || packageType = runtime. Version. 
    #includePreviewVersions: false # boolean. Optional. Use when useGlobalJson = false  || packageType = runtime. Include Preview Versions. Default: false.
  # Advanced
    #installationPath: '$(Agent.ToolsDirectory)/dotnet' # string. Path To Install .Net Core. Default: '$(Agent.ToolsDirectory)/dotnet'.
    #performMultiLevelLookup: false # boolean. Perform Multi Level Lookup. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Use dotnet v2
# Acquires a specific version of the .NET Core SDK from the internet or the local cache and adds it to the PATH. Use this task to change the version of .NET Core used in subsequent tasks. Additionally provides proxy support.
- task: UseDotNet@2
  inputs:
    #packageType: 'sdk' # 'runtime' | 'sdk'. Package to install. Default: 'sdk'.
    #version: # string. Version. 
    #includePreviewVersions: false # boolean. Include Preview Versions. Default: false.
  # Advanced
    #installationPath: '$(Agent.ToolsDirectory)/dotnet' # string. Path To Install .Net Core. Default: '$(Agent.ToolsDirectory)/dotnet'.
    #performMultiLevelLookup: false # boolean. Perform Multi Level Lookup. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="packageType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`packageType`** - **Package to install**<br>
Type: string. Allowed values: 'runtime', 'sdk'. Default value: 'sdk'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Please select whether to install only runtime or SDK.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useGlobalJson"::: -->
:::moniker range=">=azure-pipelines-2020"

**`useGlobalJson`** - **Use global json**<br>
Type: boolean. Optional. Use when packageType = sdk. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to install all SDKs from global.json files. These files are searched from system.DefaultWorkingDirectory. You can change the search root path by setting working directory input.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2020"

**`workingDirectory`** - **Working Directory**<br>
Type: string. Optional. Use when useGlobalJson = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify path from where global.json files should be searched when using `Use global json`. If empty, `system.DefaultWorkingDirectory` will be considered as the root path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range=">=azure-pipelines-2020"

**`version`** - **Version**<br>
Type: string. Optional. Use when useGlobalJson = false || packageType = runtime.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify version of .NET Core SDK or runtime to install.<br/>Versions can be given in the following formats<li>2.x   => Install latest in major version.</li><li>2.2.x => Install latest in major and minor version</li><li>2.2.104 => Install exact version</li><li>3.1.x => Install latest in major and minor version</li><li>3.1.402 => Install exact version</li><br/>Find the value of `version` for installing SDK/Runtime, from the releases.json. The link to releases.json of that major.minor version can be found in [**releases-index file.**](https://dotnetcli.blob.core.windows.net/dotnet/release-metadata/releases-index.json). Like link to releases.json for 2.2 version is https://dotnetcli.blob.core.windows.net/dotnet/release-metadata/2.2/releases.json. Like link to releases.json for 3.1 version is https://dotnetcli.blob.core.windows.net/dotnet/release-metadata/3.1/releases.json.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`version`** - **Version**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify version of .NET Core SDK or runtime to install.<br/>Versions can be given in the following formats<li>2.x   => Install latest in major version.</li><li>2.2.x => Install latest in major and minor version</li><li>2.2.104 => Install exact version</li><br/>Find the value of `version` for installing SDK/Runtime, from the releases.json. The link to releases.json of that major.minor version can be found in [**releases-index file.**](https://github.com/dotnet/core/blob/master/release-notes/releases-index.json). Like link to releases.json for 2.2 version is https://dotnetcli.blob.core.windows.net/dotnet/release-metadata/2.2/releases.json.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vsVersion"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`vsVersion`** - **Compatible Visual Studio version**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify version of compatible visual studio for which .NET core sdk to install. Specifiy complete vs-version like 16.6.4 containing major version, minor version and patch number.Find the value of `version` for installing SDK/Runtime, from the releases.json. The link to releases.json of that major.minor version can be found in [**releases-index file.**](https://dotnetcli.blob.core.windows.net/dotnet/release-metadata/releases-index.json).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includePreviewVersions"::: -->
:::moniker range=">=azure-pipelines-2020"

**`includePreviewVersions`** - **Include Preview Versions**<br>
Type: boolean. Optional. Use when useGlobalJson = false  || packageType = runtime. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select if you want preview versions to be included while searching for latest versions, such as while searching 2.2.x or 3.1.x. This setting is ignored if you specify an exact version, such as: 3.0.100-preview3-010431.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`includePreviewVersions`** - **Include Preview Versions**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select if you want preview versions to be included while searching for latest versions, such as while searching 2.2.x. This setting is ignored if you specify an exact version, such as: 3.0.100-preview3-010431.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="installationPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`installationPath`** - **Path To Install .Net Core**<br>
Type: string. Default value: '$(Agent.ToolsDirectory)/dotnet'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify where .Net Core SDK/Runtime should be installed. Different paths can have the following impact on .Net's behavior.<li>$(Agent.ToolsDirectory): This makes the version to be cached on the agent since this directory is not cleanup up across pipelines. All pipelines running on the agent, would have access to the versions installed previously using the agent.</li><li>$(Agent.TempDirectory): This can ensure that a pipeline doesn't use any cached version of .Net core since this folder is cleaned up after each pipeline.</li><li>Any other path: You can configure any other path given the agent process has access to the path. This will change the state of the machine and impact all processes running on it.<br/>Note that you can also configure Multi-Level Lookup setting which can configure .Net host's probing for a suitable version.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="performMultiLevelLookup"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`performMultiLevelLookup`** - **Perform Multi Level Lookup**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This input is only applicable to Windows based agents. This configures the behavior of .Net host process for looking up a suitable shared framework.<li>unchecked: Only versions present in the folder specified in this task would be looked by the host process.</li><li>checked: The host will attempt to look in pre-defined global locations using multi-level lookup.<br/>The default global locations are: <br/><b>For Windows:</b><br/>C:\Program Files\dotnet (64-bit processes)<br/>C:\Program Files (x86)\dotnet (32-bit process)</li> You can read more about it [**HERE**](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).<br/>.
<!-- :::editable-content-end::: -->

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