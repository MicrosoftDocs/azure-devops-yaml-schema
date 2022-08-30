---
title: VSBuild@1 - Visual Studio build v1 task
description: Build with MSBuild and set the Visual Studio version property.
ms.date: 08/23/2022
monikerRange: "<=azure-pipelines"
---

# VSBuild@1 - Visual Studio build v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Build with MSBuild and set the Visual Studio version property.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Visual Studio build v1
# Build with MSBuild and set the Visual Studio version property.
- task: VSBuild@1
  inputs:
    solution: '**\*.sln' # string. Required. Solution. Default: '**\*.sln'.
    #vsVersion: 'latest' # 'latest' | '17.0' | '16.0' | '15.0' | '14.0' | '12.0' | '11.0'. Visual Studio Version. Default: 'latest'.
    #msbuildArgs: # string. MSBuild Arguments. 
    #platform: # string. Platform. 
    #configuration: # string. Configuration. 
    #clean: false # boolean. Clean. Default: false.
  # Advanced
    #maximumCpuCount: false # boolean. Build in Parallel. Default: false.
    #restoreNugetPackages: false # boolean. Restore NuGet Packages. Default: false.
    #msbuildArchitecture: 'x86' # 'x86' | 'x64'. MSBuild Architecture. Default: 'x86'.
    #logProjectEvents: true # boolean. Record Project Details. Default: true.
    #createLogFile: false # boolean. Create Log File. Default: false.
    #logFileVerbosity: 'normal' # 'quiet' | 'minimal' | 'normal' | 'detailed' | 'diagnostic'. Optional. Use when createLogFile = true. Log File Verbosity. Default: 'normal'.
    #enableDefaultLogger: true # boolean. Enable Default Logger. Default: true.
    #customVersion: # string. Custom Version.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

```yaml
# Visual Studio build v1
# Build with MSBuild and set the Visual Studio version property.
- task: VSBuild@1
  inputs:
    solution: '**\*.sln' # string. Required. Solution. Default: '**\*.sln'.
    #vsVersion: 'latest' # 'latest' | '16.0' | '15.0' | '14.0' | '12.0' | '11.0'. Visual Studio Version. Default: 'latest'.
    #msbuildArgs: # string. MSBuild Arguments. 
    #platform: # string. Platform. 
    #configuration: # string. Configuration. 
    #clean: false # boolean. Clean. Default: false.
  # Advanced
    #maximumCpuCount: false # boolean. Build in Parallel. Default: false.
    #restoreNugetPackages: false # boolean. Restore NuGet Packages. Default: false.
    #msbuildArchitecture: 'x86' # 'x86' | 'x64'. MSBuild Architecture. Default: 'x86'.
    #logProjectEvents: true # boolean. Record Project Details. Default: true.
    #createLogFile: false # boolean. Create Log File. Default: false.
    #logFileVerbosity: 'normal' # 'quiet' | 'minimal' | 'normal' | 'detailed' | 'diagnostic'. Optional. Use when createLogFile = true. Log File Verbosity. Default: 'normal'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Visual Studio Build v1
# Build with MSBuild and set the Visual Studio version property.
- task: VSBuild@1
  inputs:
    solution: '**\*.sln' # string. Required. Solution. Default: '**\*.sln'.
    #vsVersion: 'latest' # 'latest' | '16.0' | '15.0' | '14.0' | '12.0' | '11.0'. Visual Studio Version. Default: 'latest'.
    #msbuildArgs: # string. MSBuild Arguments. 
    #platform: # string. Platform. 
    #configuration: # string. Configuration. 
    #clean: false # boolean. Clean. Default: false.
  # Advanced
    #maximumCpuCount: false # boolean. Build in Parallel. Default: false.
    #restoreNugetPackages: false # boolean. Restore NuGet Packages. Default: false.
    #msbuildArchitecture: 'x86' # 'x86' | 'x64'. MSBuild Architecture. Default: 'x86'.
    #logProjectEvents: true # boolean. Record Project Details. Default: true.
    #createLogFile: false # boolean. Create Log File. Default: false.
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

<!-- :::item name="solution"::: -->
:::moniker range="<=azure-pipelines"

**`solution`** - **Solution**<br>
Type: string. Required. Default value: '**\*.sln'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from repo root of the solution(s) or MSBuild project to run.  Wildcards can be used.  For example, `**\*.sln` for all sln files in all sub folders.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vsVersion"::: -->
:::moniker range=">=azure-pipelines-2022"

**`vsVersion`** - **Visual Studio Version**<br>
Type: string. Allowed values: 'latest', '17.0', '16.0', '15.0', '14.0', '12.0', '11.0'. Default value: 'latest'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the preferred version cannot be found, the latest version found will be used instead.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020.1"

**`vsVersion`** - **Visual Studio Version**<br>
Type: string. Allowed values: 'latest', '16.0', '15.0', '14.0', '12.0', '11.0'. Default value: 'latest'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the preferred version cannot be found, the latest version found will be used instead.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`vsVersion`** - **Visual Studio Version**<br>
Type: string. Allowed values: 'latest', '15.0', '14.0', '12.0', '11.0'. Default value: 'latest'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the preferred version cannot be found, the latest version found will be used instead.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildArgs"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildArgs`** - **MSBuild Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments passed to MSBuild.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="platform"::: -->
:::moniker range="<=azure-pipelines"

**`platform`** - **Platform**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the platform you want to build such as Win32, x86, x64 or any cpu.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the configuration you want to build such as debug or release.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="clean"::: -->
:::moniker range="<=azure-pipelines"

**`clean`** - **Clean**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set to False if you want to make this an incremental build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="maximumCpuCount"::: -->
:::moniker range="<=azure-pipelines"

**`maximumCpuCount`** - **Build in Parallel**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If your MSBuild target configuration is compatible with building in parallel, you can optionally check this input to pass the /m switch to MSBuild (Windows only). If your target configuration is not compatible with building in parallel, checking this option may cause your build to result in file-in-use errors, or intermittent or inconsistent build failures.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restoreNugetPackages"::: -->
:::moniker range="<=azure-pipelines"

**`restoreNugetPackages`** - **Restore NuGet Packages**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This option is deprecated. To restore NuGet packages, add a [NuGet Tool Installer](nuget-installer-v0.md) task before the build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildArchitecture"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildArchitecture`** - **MSBuild Architecture**<br>
Type: string. Allowed values: 'x86', 'x64'. Default value: 'x86'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the architecture (x86, x64) of MSBuild to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="logProjectEvents"::: -->
:::moniker range="<=azure-pipelines"

**`logProjectEvents`** - **Record Project Details**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally record timeline details for each project.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="createLogFile"::: -->
:::moniker range="<=azure-pipelines"

**`createLogFile`** - **Create Log File**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally create a log file (Windows only).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="logFileVerbosity"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`logFileVerbosity`** - **Log File Verbosity**<br>
Type: string. Optional. Use when createLogFile = true. Allowed values: 'quiet', 'minimal', 'normal', 'detailed', 'diagnostic'. Default value: 'normal'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional log file verbosity.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableDefaultLogger"::: -->
:::moniker range=">=azure-pipelines-2022"

**`enableDefaultLogger`** - **Enable Default Logger**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If true - enables default logger for msbuild.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customVersion"::: -->
:::moniker range=">=azure-pipelines-2022"

**`customVersion`** - **Custom Version**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Allows setting custom version of Visual Studio. Examples: 15.0, 16.0, 17.0. Make sure that the required version of Visual Studio is installed in the system.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
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

 Learn more about installing [Visual Studio images on Azure](/visualstudio/install/using-visual-studio-vm).

> [!IMPORTANT]
> This task is only supported on agents running Windows.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: msbuild, visualstudio |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.95.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->