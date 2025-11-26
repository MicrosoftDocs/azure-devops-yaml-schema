---
title: VSBuild@1 - Visual Studio build v1 task
description: Build with MSBuild and set the Visual Studio version property.
ms.date: 11/11/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
author: steved0x
ms.author: sdanie
---

# VSBuild@1 - Visual Studio build v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to build with MSBuild and set the Visual Studio version property. Learn more about installing [Visual Studio images on Azure](/visualstudio/install/using-visual-studio-vm).

> [!TIP]
> Use [NuGetAuthenticate@1](./nuget-authenticate-v1.md) in your pipeline before this task. For more information, see [Why is my build pipeline failing and prompting for Single Sign-On (SSO) authentication?](#why-is-my-build-pipeline-failing-and-prompting-for-single-sign-on-sso-authentication).
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
    solution: '**\*.sln' # string. Required. Solution. Default: **\*.sln.
    #vsVersion: 'latest' # 'latest' | '18.0' | '17.0' | '16.0' | '15.0' | '14.0' | '12.0' | '11.0'. Visual Studio Version. Default: latest.
    #msbuildArgs: # string. MSBuild Arguments. 
    #platform: # string. Platform. 
    #configuration: # string. Configuration. 
    #clean: false # boolean. Clean. Default: false.
  # Advanced
    #maximumCpuCount: false # boolean. Build in Parallel. Default: false.
    #restoreNugetPackages: false # boolean. Restore NuGet Packages. Default: false.
    #msbuildArchitecture: 'x86' # 'x86' | 'x64'. MSBuild Architecture. Default: x86.
    #logProjectEvents: true # boolean. Record Project Details. Default: true.
    #createLogFile: false # boolean. Create Log File. Default: false.
    #logFileVerbosity: 'normal' # 'quiet' | 'minimal' | 'normal' | 'detailed' | 'diagnostic'. Optional. Use when createLogFile = true. Log File Verbosity. Default: normal.
    #enableDefaultLogger: true # boolean. Enable Default Logger. Default: true.
    #customVersion: # string. Custom Version.
```

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

```yaml
# Visual Studio build v1
# Build with MSBuild and set the Visual Studio version property.
- task: VSBuild@1
  inputs:
    solution: '**\*.sln' # string. Required. Solution. Default: **\*.sln.
    #vsVersion: 'latest' # 'latest' | '16.0' | '15.0' | '14.0' | '12.0' | '11.0'. Visual Studio Version. Default: latest.
    #msbuildArgs: # string. MSBuild Arguments. 
    #platform: # string. Platform. 
    #configuration: # string. Configuration. 
    #clean: false # boolean. Clean. Default: false.
  # Advanced
    #maximumCpuCount: false # boolean. Build in Parallel. Default: false.
    #restoreNugetPackages: false # boolean. Restore NuGet Packages. Default: false.
    #msbuildArchitecture: 'x86' # 'x86' | 'x64'. MSBuild Architecture. Default: x86.
    #logProjectEvents: true # boolean. Record Project Details. Default: true.
    #createLogFile: false # boolean. Create Log File. Default: false.
    #logFileVerbosity: 'normal' # 'quiet' | 'minimal' | 'normal' | 'detailed' | 'diagnostic'. Optional. Use when createLogFile = true. Log File Verbosity. Default: normal.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="solution"::: -->
:::moniker range="<=azure-pipelines"

**`solution`** - **Solution**<br>
`string`. Required. Default value: `**\*.sln`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the solution for the task to use in the build process.

If you want to build a single solution, click the **...** button and specify the solution.

If you want to build multiple solutions, specify the search criteria. You can use a single-folder wildcard (`*`) and recursive wildcards (`**`). For example, `**.sln` searches for all .sln files in all subdirectories.

Make sure the solutions you specify are downloaded by this build pipeline. On the Repository tab:

- If you use TFVC, make sure that the solution is a child of one of the mappings on the Repository tab.
- If you use Git, make sure that the project or solution is in your Git repo, and in a branch that you're building.

> [!TIP]
> - You can also build MSBuild project (.*proj) files.
> - If you are building a customized MSBuild project file, we recommend you use the MSBuild task instead of the Visual Studio Build task.
>
> For information on the differences between MSBuild and Visual Studio build, see [Visual Studio builds vs. MSBuild.exe builds](/visualstudio/msbuild/build-process-overview#visual-studio-builds-vs-msbuildexe-builds).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vsVersion"::: -->
:::moniker range=">=azure-pipelines-2022"

**`vsVersion`** - **Visual Studio Version**<br>
`string`. Allowed values: `latest`, `18.0` (Visual Studio 2026), `17.0` (Visual Studio 2022), `16.0` (Visual Studio 2019), `15.0` (Visual Studio 2017), `14.0` (Visual Studio 2015), `12.0` (Visual Studio 2013), `11.0` (Visual Studio 2012). Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The value of this input must match the version of Visual Studio used to create your solution.

Adds the `/p:VisualStudioVersion={numeric_visual_studio_version}` argument to the MSBuild command run by the build. For example, if you specify **Visual Studio 2015**, `/p:VisualStudioVersion=14.0` is added to the MSBuild command.

**Azure Pipelines**: If your team wants to use Visual Studio with the Microsoft-hosted agents, select **windows-latest** as your default build pool. See [Microsoft-hosted agents](/azure/devops/pipelines/agents/hosted).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

**`vsVersion`** - **Visual Studio Version**<br>
`string`. Allowed values: `latest`, `16.0` (Visual Studio 2019), `15.0` (Visual Studio 2017), `14.0` (Visual Studio 2015), `12.0` (Visual Studio 2013), `11.0` (Visual Studio 2012). Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The value of this input must match the version of Visual Studio used to create your solution.

Adds the `/p:VisualStudioVersion={numeric_visual_studio_version}` argument to the MSBuild command run by the build. For example, if you specify **Visual Studio 2015**, `/p:VisualStudioVersion=14.0` is added to the MSBuild command.

**Azure Pipelines**: If your team wants to use Visual Studio with the Microsoft-hosted agents, select **windows-latest** as your default build pool. See [Microsoft-hosted agents](/azure/devops/pipelines/agents/hosted).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildArgs"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildArgs`** - **MSBuild Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Passes additional arguments to MSBuild. For syntax, see [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="platform"::: -->
:::moniker range="<=azure-pipelines"

**`platform`** - **Platform**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the platform you want to build, such as `Win32`, `x86`, `x64`, or `any cpu`.

> [!TIP]
> - If you are targeting an MSBuild project (.*proj) file instead of a solution, specify `AnyCPU` (no whitespace).
> - Declare a build variable such as `BuildPlatform` on the Variables tab (selecting Allow at Queue Time) and reference it here as `$(BuildPlatform)`. This way you can modify the platform when you queue the build and enable building multiple configurations.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the configuration you want to build, such as `debug` or `release`.

> [!TIP]
> Declare a build variable such as `BuildConfiguration` on the Variables tab (selecting Allow at Queue Time) and reference it here as `$(BuildConfiguration)`. This way you can modify the platform when you queue the build and enable building multiple configurations.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="clean"::: -->
:::moniker range="<=azure-pipelines"

**`clean`** - **Clean**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `false`, the task makes an incremental build. This setting might reduce your build time, especially if your codebase is large. This option has no practical effect unless you also set the Clean repository to `false`.

If set to `true`, the task rebuilds all of the code in the code projects. This is equivalent to the MSBuild `/target:clean` argument.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="maximumCpuCount"::: -->
:::moniker range="<=azure-pipelines"

**`maximumCpuCount`** - **Build in Parallel**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. If your MSBuild target configuration is compatible with building in parallel, you can check this input to pass the `/m` switch to MSBuild (Windows only). If your target configuration is not compatible with building in parallel, checking this option may cause your build to result in file-in-use errors, or intermittent or inconsistent build failures.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restoreNugetPackages"::: -->
:::moniker range="<=azure-pipelines"

**`restoreNugetPackages`** - **Restore NuGet Packages**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This input is deprecated. To restore NuGet packages, add a [NuGet Tool Installer](nuget-installer-v0.md) task before the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildArchitecture"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildArchitecture`** - **MSBuild Architecture**<br>
`string`. Allowed values: `x86` (MSBuild x86), `x64` (MSBuild x64). Default value: `x86`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Supplies the architecture (`x86` or `x64`) of MSBuild to run.

> [!TIP]
> Because Visual Studio runs as a 32-bit application, you may experience problems when your build is processed by a build agent that is running the 64-bit version of Team Foundation Build Service. By selecting MSBuild `x86`, you may resolve these issues.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="logProjectEvents"::: -->
:::moniker range="<=azure-pipelines"

**`logProjectEvents`** - **Record Project Details**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Records timeline details for each project.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="createLogFile"::: -->
:::moniker range="<=azure-pipelines"

**`createLogFile`** - **Create Log File**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Creates a log file (Windows only).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="logFileVerbosity"::: -->
:::moniker range="<=azure-pipelines"

**`logFileVerbosity`** - **Log File Verbosity**<br>
`string`. Optional. Use when `createLogFile = true`. Allowed values: `quiet`, `minimal`, `normal`, `detailed`, `diagnostic`. Default value: `normal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the verbosity level in log files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableDefaultLogger"::: -->
:::moniker range=">=azure-pipelines-2022"

**`enableDefaultLogger`** - **Enable Default Logger**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, enables the default logger for MSBuild.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customVersion"::: -->
:::moniker range=">=azure-pipelines-2022"

**`customVersion`** - **Custom Version**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets a custom version of Visual Studio. Examples: `15.0`, `16.0`, `17.0`, `18.0`. The required version of Visual Studio must be installed in the system.

**Azure Pipelines**: If your team wants to use Visual Studio 2022 with the Microsoft-hosted agents, select `windows-2022` as your default build pool. For more info see [Microsoft-hosted agents](/azure/devops/pipelines/agents/hosted).
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
# Build the solution using VSBuild
- task: VSBuild@1
  inputs:
    solution: '**/*.sln' 
```
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
