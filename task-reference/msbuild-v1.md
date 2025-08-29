---
title: MSBuild@1 - MSBuild v1 task
description: Build with MSBuild.
ms.date: 08/29/2025
monikerRange: "<=azure-pipelines"
---

# MSBuild@1 - MSBuild v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to build with MSBuild.

> [!NOTE]
> For more information on MSBuild, see [How MSBuild builds projects](/visualstudio/msbuild/build-process-overview).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# MSBuild v1
# Build with MSBuild.
- task: MSBuild@1
  inputs:
    solution: '**/*.sln' # string. Required. Project. Default: **/*.sln.
    #msbuildLocationMethod: 'version' # 'version' | 'location'. MSBuild. Default: version.
    #msbuildVersion: 'latest' # 'latest' | '17.0' | '16.0' | '15.0' | '14.0' | '12.0' | '4.0'. Optional. Use when msbuildLocationMethod = version. MSBuild Version. Default: latest.
    #msbuildArchitecture: 'x86' # 'x86' | 'x64'. Optional. Use when msbuildLocationMethod = version. MSBuild Architecture. Default: x86.
    #msbuildLocation: # string. Optional. Use when msbuildLocationMethod = location. Path to MSBuild. 
    #platform: # string. Platform. 
    #configuration: # string. Configuration. 
    #msbuildArguments: # string. MSBuild Arguments. 
    #clean: false # boolean. Clean. Default: false.
  # Advanced
    #maximumCpuCount: false # boolean. Build in Parallel. Default: false.
    #restoreNugetPackages: false # boolean. Restore NuGet Packages. Default: false.
    #logProjectEvents: false # boolean. Record Project Details. Default: false.
    #createLogFile: false # boolean. Create Log File. Default: false.
    #logFileVerbosity: 'normal' # 'quiet' | 'minimal' | 'normal' | 'detailed' | 'diagnostic'. Optional. Use when createLogFile = true. Log File Verbosity. Default: normal.
```

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

```yaml
# MSBuild v1
# Build with MSBuild.
- task: MSBuild@1
  inputs:
    solution: '**/*.sln' # string. Required. Project. Default: **/*.sln.
    #msbuildLocationMethod: 'version' # 'version' | 'location'. MSBuild. Default: version.
    #msbuildVersion: 'latest' # 'latest' | '16.0' | '15.0' | '14.0' | '12.0' | '4.0'. Optional. Use when msbuildLocationMethod = version. MSBuild Version. Default: latest.
    #msbuildArchitecture: 'x86' # 'x86' | 'x64'. Optional. Use when msbuildLocationMethod = version. MSBuild Architecture. Default: x86.
    #msbuildLocation: # string. Optional. Use when msbuildLocationMethod = location. Path to MSBuild. 
    #platform: # string. Platform. 
    #configuration: # string. Configuration. 
    #msbuildArguments: # string. MSBuild Arguments. 
    #clean: false # boolean. Clean. Default: false.
  # Advanced
    #maximumCpuCount: false # boolean. Build in Parallel. Default: false.
    #restoreNugetPackages: false # boolean. Restore NuGet Packages. Default: false.
    #logProjectEvents: false # boolean. Record Project Details. Default: false.
    #createLogFile: false # boolean. Create Log File. Default: false.
    #logFileVerbosity: 'normal' # 'quiet' | 'minimal' | 'normal' | 'detailed' | 'diagnostic'. Optional. Use when createLogFile = true. Log File Verbosity. Default: normal.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="solution"::: -->
:::moniker range="<=azure-pipelines"

**`solution`** - **Project**<br>
`string`. Required. Default value: `**/*.sln`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If you want to build multiple projects, specify search criteria. You can use a single-folder wildcard (\*) and recursive wildcards (\*\*). For example, `**.*proj` searches for all MSBuild project (`.*proj`) files in all subdirectories.

Make sure the projects you specify are downloaded by this build pipeline. On the Repository tab:

- If you use TFVC, make sure that the project is a child of one of the mappings on the Repository tab.
- If you use Git, make sure that the project or project is in your Git repo, in a branch that you're building.

> [!TIP]
> If you are building a solution, we recommend you use the [Visual Studio build task](/azure/devops/pipelines/tasks/build/visual-studio-build) instead of the MSBuild task.
>
> For information on the differences between MSBuild and Visual Studio build, see [Visual Studio builds vs. MSBuild.exe builds](/visualstudio/msbuild/build-process-overview#visual-studio-builds-vs-msbuildexe-builds).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildLocationMethod"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildLocationMethod`** - **MSBuild**<br>
`string`. Allowed values: `version`, `location` (Specify Location). Default value: `version`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildVersion"::: -->
:::moniker range=">=azure-pipelines-2022"

**`msbuildVersion`** - **MSBuild Version**<br>
`string`. Optional. Use when `msbuildLocationMethod = version`. Allowed values: `latest`, `17.0` (MSBuild 17.0), `16.0` (MSBuild 16.0), `15.0` (MSBuild 15.0), `14.0` (MSBuild 14.0), `12.0` (MSBuild 12.0), `4.0` (MSBuild 4.0). Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the preferred version cannot be found, the latest version found is used instead. On an macOS agent, `xbuild` (Mono) is used if version is lower than `15.0`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

**`msbuildVersion`** - **MSBuild Version**<br>
`string`. Optional. Use when `msbuildLocationMethod = version`. Allowed values: `latest`, `16.0` (MSBuild 16.0), `15.0` (MSBuild 15.0), `14.0` (MSBuild 14.0), `12.0` (MSBuild 12.0), `4.0` (MSBuild 4.0). Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the preferred version cannot be found, the latest version found is used instead. On an macOS agent, `xbuild` (Mono) is used if version is lower than `15.0`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildArchitecture"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildArchitecture`** - **MSBuild Architecture**<br>
`string`. Optional. Use when `msbuildLocationMethod = version`. Allowed values: `x86` (MSBuild x86), `x64` (MSBuild x64). Default value: `x86`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Supplies the MSBuild architecture (x86, x64) to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildLocation"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildLocation`** - **Path to MSBuild**<br>
`string`. Optional. Use when `msbuildLocationMethod = location`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Supplies the path to MSBuild.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="platform"::: -->
:::moniker range="<=azure-pipelines"

**`platform`** - **Platform**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
> [!TIP]
> - If you are targeting an MSBuild project (.*proj) file instead of a solution, specify `AnyCPU` (no whitespace).
> - Declare a build variable such as `BuildPlatform` on the Variables tab (selecting `Allow` at Queue Time) and reference it here as `$(BuildPlatform)`. This way you can modify the platform when you queue the build and enable building multiple configurations.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
> [!TIP]
> Declare a build variable such as `BuildConfiguration` on the Variables tab (selecting `Allow` at Queue Time) and reference it here as `$(BuildConfiguration)`. This way you can modify the platform when you queue the build and enable building multiple configurations.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildArguments"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildArguments`** - **MSBuild Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional arguments passed to MSBuild (on Windows) and xbuild (on macOS).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="clean"::: -->
:::moniker range="<=azure-pipelines"

**`clean`** - **Clean**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set to `False` if you want to make this an incremental build. This setting might reduce your build time, especially if your codebase is large. This option has no practical effect unless you also set the `Clean` repository to `False`.
Set to `True` if you want to rebuild all the code in the code projects. This is equivalent to the MSBuild `/target:clean` argument.
For more information, see [repo options](/azure/devops/pipelines/repos/pipeline-options-for-git)
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="maximumCpuCount"::: -->
:::moniker range="<=azure-pipelines"

**`maximumCpuCount`** - **Build in Parallel**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If your MSBuild target configuration is compatible with building in parallel, you can  check this input to pass the `/m` switch to MSBuild (Windows only). If your target configuration is not compatible with building in parallel, checking this option may cause your build to result in `file-in-use` errors, or intermittent or inconsistent build failures.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restoreNugetPackages"::: -->
:::moniker range="<=azure-pipelines"

**`restoreNugetPackages`** - **Restore NuGet Packages**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This option is deprecated. To restore NuGet packages, add a [NuGet](/azure/devops/pipelines/tasks/package/nuget) task before the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="logProjectEvents"::: -->
:::moniker range="<=azure-pipelines"

**`logProjectEvents`** - **Record Project Details**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally records timeline details for each project (Windows only).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="createLogFile"::: -->
:::moniker range="<=azure-pipelines"

**`createLogFile`** - **Create Log File**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally creates a log file (Windows only).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="logFileVerbosity"::: -->
:::moniker range="<=azure-pipelines"

**`logFileVerbosity`** - **Log File Verbosity**<br>
`string`. Optional. Use when `createLogFile = true`. Allowed values: `quiet`, `minimal`, `normal`, `detailed`, `diagnostic`. Default value: `normal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies log file verbosity.
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

### Should I use the Visual Studio Build task or the MSBuild task?

If you are building a solution, in most cases you should use the [Visual Studio Build task](vsbuild-v1.md). This task automatically:

* Sets the `/p:VisualStudioVersion` property for you. This forces MSBuild to use a particular set of targets that increase the likelihood of a successful build.
* Specifies the MSBuild version argument.

In some cases, you might need to use the `MSBuild` task. For example, you should use it if you are building code projects apart from a solution.

### Where can I learn more about MSBuild?

[MSBuild reference](/visualstudio/msbuild/msbuild)

[MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference)

<a name="multiconfiguration"></a>

### How do I build multiple configurations for multiple platforms?

1. On the Variables tab, make sure you have variables defined for your configurations and platforms. To specify multiple values, separate them with commas. For example:
   - For a .NET app, you could specify `BuildConfiguration` with debug and release values, and you could specify `BuildPlatform` with any CPU value.
   - For a C++ app, you could specify `BuildConfiguration` with debug and release values, and you could specify `BuildPlatform` with any x86 and x64 values.

1. On the Options tab, select `MultiConfiguration` and specify the `Multipliers`, separated by commas. For example: `BuildConfiguration, BuildPlatform`
Select `Parallel` if you want to distribute the jobs (one for each combination of values) to multiple agents in parallel if they are available.
1. On the Build tab, select this step and specify the `Platform` and `Configuration` arguments. For example:
   - Platform: `$(BuildPlatform)`
   - Configuration: `$(BuildConfiguration)`

### Can I build TFSBuild.proj files?

You cannot build `TFSBuild.proj` files. These kinds of files are generated by `TFS 2005` and `TFS 2008`.  These files contain tasks, and targets are supported only using [XAML builds](/previous-versions/visualstudio/visual-studio-2013/ms181709(v=vs.120)).

### Troubleshooting

This section provides troubleshooting tips for common issues that a user might encounter when using the `MSBuild` task.

* [Build failed with the following error: An internal failure occurred while running MSBuild](#build-failed-with-the-following-error-an-internal-failure-occurred-while-running-msbuild)

#### Build failed with the following error: An internal failure occurred while running MSBuild

* [Possible causes](#possible-causes)
* [Troubleshooting suggestions](#troubleshooting-suggestions)

##### Possible causes

* Change in the MSBuild version.
* Issues with a third-party extension.
* New updates to Visual Studio that can cause missing assemblies on the build agent.
* Moved or deleted some of the necessary NuGet packages.

##### Troubleshooting suggestions

* [Run the pipeline with diagnostics to retrieve detailed logs](#run-the-pipeline-with-diagnostics-to-retrieve-detailed-logs)
* [Try to reproduce the error locally](#try-to-reproduce-the-error-locally)
* [What else can I do?](#what-else-can-i-do)

###### Run the pipeline with diagnostics to retrieve detailed logs

One of the available options to diagnose the issue is to take a look at the generated logs. You can view your pipeline logs by selecting the appropriate task and job in your pipeline run summary.

To get the logs of your pipeline execution [Get logs to diagnose problems](/azure/devops/pipelines/troubleshooting/review-logs)

You can also setup and download a customized verbose log to assist with your troubleshooting:

* [Configure verbose logs](/azure/devops/pipelines/troubleshooting/review-logs#configure-verbose-logs)
* [View and download logs](/azure/devops/pipelines/troubleshooting/review-logs#view-and-download-logs)

In addition to the pipeline diagnostic logs, you can also check these other types of logs that contain more information to help you debug and solve the problem:

* [Worker diagnostic logs](/azure/devops/pipelines/troubleshooting/review-logs#worker-diagnostic-logs)
* [Agent diagnostic logs](/azure/devops/pipelines/troubleshooting/review-logs#agent-diagnostic-logs)
* [Other logs](/azure/devops/pipelines/troubleshooting/review-logs#other-logs) (Environment and capabilities)

###### Try to reproduce the error locally

If you are using a hosted build agent, you might want to try to reproduce the error locally. This will help you to narrow down whether the failure is the result of the build agent or the build task.

Run the same `MSBuild` command on your local machine using the same arguments. Check out [MSBuild command](/visualstudio/msbuild/msbuild-command-line-reference?view=vs-2019&preserve-view=true) for reference.

> [!TIP]
> If you can reproduce the problem on your local machine, then your next step is to investigate the [MSBuild](/visualstudio/msbuild/msbuild?view=vs-2019&preserve-view=true) issue.

Learn more about [Microsoft hosted agents](/azure/devops/pipelines/agents/hosted).

To setup your own self-hosted agent and run the build jobs:

* [Self-hosted Windows agents](/azure/devops/pipelines/agents/v2-windows)
* [Self-hosted Linux agents](/azure/devops/pipelines/agents/v2-linux)
* [Self-hosted macOS agents](/azure/devops/pipelines/agents/v2-osx)

###### What else can I do?

Some of the MSBuild errors are caused by a change in Visual Studio so you can search on [Visual Studio Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) to see if this issue has been reported. We also welcome your questions, suggestions, and feedback.
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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: msbuild |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.95.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Visual Studio Build task](vsbuild-v1.md)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
