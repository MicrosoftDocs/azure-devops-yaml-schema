---
title: XamarinAndroid@1 - Xamarin.Android v1 task
description: Build an Android app with Xamarin.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# XamarinAndroid@1 - Xamarin.Android v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Build an Android app with Xamarin.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Xamarin.Android v1
# Build an Android app with Xamarin.
- task: XamarinAndroid@1
  inputs:
    projectFile: '**/*.csproj' # string. Required. Project. Default: '**/*.csproj'.
    #target: # string. Target. 
    #outputDirectory: # string. Output directory. 
    #configuration: # string. Configuration. 
    #createAppPackage: true # boolean. Create app package. Default: true.
    #clean: false # boolean. Clean. Default: false.
  # MSBuild Options
    #msbuildLocationOption: 'version' # 'version' | 'location'. MSBuild. Default: 'version'.
    #msbuildVersionOption: '15.0' # 'latest' | '17.0' | '16.0' | '15.0' | '14.0' | '12.0' | '4.0'. Optional. Use when msbuildLocationMethod = version. MSBuild version. Default: '15.0'.
    #msbuildFile: # string. Required when msbuildLocationMethod = location. MSBuild location. 
    #msbuildArchitectureOption: 'x86' # 'x86' | 'x64'. Optional. Use when msbuildLocationMethod = version. MSBuild architecture. Default: 'x86'.
    #msbuildArguments: # string. Additional arguments. 
  # JDK Options
    jdkOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Required. Select JDK to use for the build. Default: 'JDKVersion'.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Optional. Use when jdkSelection = JDKVersion. JDK version. Default: 'default'.
    #jdkDirectory: # string. Required when jdkSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Optional. Use when jdkVersion != default. JDK architecture. Default: 'x64'.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020.1"

```yaml
# Xamarin.Android v1
# Build an Android app with Xamarin.
- task: XamarinAndroid@1
  inputs:
    projectFile: '**/*.csproj' # string. Required. Project. Default: '**/*.csproj'.
    #target: # string. Target. 
    #outputDirectory: # string. Output directory. 
    #configuration: # string. Configuration. 
    #createAppPackage: true # boolean. Create app package. Default: true.
    #clean: false # boolean. Clean. Default: false.
  # MSBuild Options
    #msbuildLocationOption: 'version' # 'version' | 'location'. MSBuild. Default: 'version'.
    #msbuildVersionOption: '15.0' # 'latest' | '15.0' | '14.0' | '12.0' | '4.0'. Optional. Use when msbuildLocationMethod = version. MSBuild version. Default: '15.0'.
    #msbuildFile: # string. Required when msbuildLocationMethod = location. MSBuild location. 
    #msbuildArchitectureOption: 'x86' # 'x86' | 'x64'. Optional. Use when msbuildLocationMethod = version. MSBuild architecture. Default: 'x86'.
    #msbuildArguments: # string. Additional arguments. 
  # JDK Options
    jdkOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Required. Select JDK to use for the build. Default: 'JDKVersion'.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Optional. Use when jdkSelection = JDKVersion. JDK version. Default: 'default'.
    #jdkDirectory: # string. Required when jdkSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Optional. Use when jdkVersion != default. JDK architecture. Default: 'x64'.
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

<!-- :::item name="projectFile"::: -->
:::moniker range="<=azure-pipelines"

**`projectFile`** - **Project**<br>
Input alias: `project`. Type: string. Required. Default value: '**/*.csproj'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from repo root of Xamarin.Android project(s) to build.  Wildcards can be used ([more information](https://go.microsoft.com/fwlink/?linkid=856077)).  For example, `**/*.csproj` for all csproj files in all subfolders.  The project must have a PackageForAndroid target if `Create App Package` is selected.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="target"::: -->
:::moniker range="<=azure-pipelines"

**`target`** - **Target**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Build these targets in this project. Use a semicolon to separate multiple targets.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`outputDirectory`** - **Output directory**<br>
Input alias: `outputDir`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally provide the output directory for the build. Example: $(build.binariesDirectory)/bin/Release.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="createAppPackage"::: -->
:::moniker range="<=azure-pipelines"

**`createAppPackage`** - **Create app package**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Passes the target (/t:PackageForAndroid) during build to generate an APK.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="clean"::: -->
:::moniker range="<=azure-pipelines"

**`clean`** - **Clean**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Passes the clean target (/t:clean) during build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildLocationOption"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildLocationOption`** - **MSBuild**<br>
Input alias: `msbuildLocationMethod`. Type: string. Allowed values: 'version', 'location'. Default value: 'version'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildVersionOption"::: -->
:::moniker range=">=azure-pipelines-2022"

**`msbuildVersionOption`** - **MSBuild version**<br>
Input alias: `msbuildVersion`. Type: string. Optional. Use when msbuildLocationMethod = version. Allowed values: 'latest', '17.0', '16.0', '15.0', '14.0', '12.0', '4.0'. Default value: '15.0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the preferred version cannot be found, the latest version found will be used instead. On macOS, xbuild (Mono) or MSBuild (Visual Studio for Mac) will be used.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

**`msbuildVersionOption`** - **MSBuild version**<br>
Input alias: `msbuildVersion`. Type: string. Optional. Use when msbuildLocationMethod = version. Allowed values: 'latest', '15.0', '14.0', '12.0', '4.0'. Default value: '15.0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the preferred version cannot be found, the latest version found will be used instead. On macOS, xbuild (Mono) or MSBuild (Visual Studio for Mac) will be used.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildFile"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildFile`** - **MSBuild location**<br>
Input alias: `msbuildLocation`. Type: string. Required when msbuildLocationMethod = location.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the path to MSBuild (on Windows) or xbuild (on macOS).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildArchitectureOption"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildArchitectureOption`** - **MSBuild architecture**<br>
Input alias: `msbuildArchitecture`. Type: string. Optional. Use when msbuildLocationMethod = version. Allowed values: 'x86', 'x64'. Default value: 'x86'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the architecture (x86, x64) of MSBuild to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildArguments"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildArguments`** - **Additional arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments passed to MSBuild (on Windows) or xbuild (on macOS).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkOption"::: -->
:::moniker range="<=azure-pipelines"

**`jdkOption`** - **Select JDK to use for the build**<br>
Input alias: `jdkSelection`. Type: string. Required. Allowed values: 'JDKVersion', 'Path'. Default value: 'JDKVersion'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Pick the JDK to be used during the build by selecting a JDK version that will be discovered during builds or by manually entering a JDK path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkVersionOption"::: -->
:::moniker range=">=azure-pipelines-2019"

**`jdkVersionOption`** - **JDK version**<br>
Input alias: `jdkVersion`. Type: string. Optional. Use when jdkSelection = JDKVersion. Allowed values: 'default', '1.11', '1.10', '1.9', '1.8', '1.7', '1.6'. Default value: 'default'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use the selected JDK version during build.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`jdkVersionOption`** - **JDK version**<br>
Input alias: `jdkVersion`. Type: string. Optional. Use when jdkSelection = JDKVersion. Allowed values: 'default', '1.9', '1.8', '1.7', '1.6'. Default value: 'default'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use the selected JDK version during build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`jdkDirectory`** - **JDK path**<br>
Input alias: `jdkUserInputPath`. Type: string. Required when jdkSelection = Path.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use the JDK version at specified path during build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkArchitectureOption"::: -->
:::moniker range="<=azure-pipelines"

**`jdkArchitectureOption`** - **JDK architecture**<br>
Input alias: `jdkArchitecture`. Type: string. Optional. Use when jdkVersion != default. Allowed values: 'x86', 'x64'. Default value: 'x64'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the architecture (x86, x64) of JDK.
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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: MSBuild, Xamarin.Android |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.83.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->