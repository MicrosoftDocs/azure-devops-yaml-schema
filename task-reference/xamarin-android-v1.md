---
title: XamarinAndroid@1 - Xamarin.Android v1 task
description: Build an Android app with Xamarin.
ms.date: 05/14/2024
monikerRange: "<=azure-pipelines"
---

# XamarinAndroid@1 - Xamarin.Android v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to build an Android app with Xamarin.
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
    projectFile: '**/*.csproj' # string. Alias: project. Required. Project. Default: **/*.csproj.
    #target: # string. Target. 
    #outputDirectory: # string. Alias: outputDir. Output directory. 
    #configuration: # string. Configuration. 
    #createAppPackage: true # boolean. Create app package. Default: true.
    #clean: false # boolean. Clean. Default: false.
  # MSBuild Options
    #msbuildLocationOption: 'version' # 'version' | 'location'. Alias: msbuildLocationMethod. MSBuild. Default: version.
    #msbuildVersionOption: '15.0' # 'latest' | '17.0' | '16.0' | '15.0' | '14.0' | '12.0' | '4.0'. Alias: msbuildVersion. Optional. Use when msbuildLocationMethod = version. MSBuild version. Default: 15.0.
    #msbuildFile: # string. Alias: msbuildLocation. Required when msbuildLocationMethod = location. MSBuild location. 
    #msbuildArchitectureOption: 'x86' # 'x86' | 'x64'. Alias: msbuildArchitecture. Optional. Use when msbuildLocationMethod = version. MSBuild architecture. Default: x86.
    #msbuildArguments: # string. Additional arguments. 
  # JDK Options
    jdkOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: jdkSelection. Required. Select JDK to use for the build. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when jdkSelection = JDKVersion. JDK version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when jdkSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020.1"

```yaml
# Xamarin.Android v1
# Build an Android app with Xamarin.
- task: XamarinAndroid@1
  inputs:
    projectFile: '**/*.csproj' # string. Alias: project. Required. Project. Default: **/*.csproj.
    #target: # string. Target. 
    #outputDirectory: # string. Alias: outputDir. Output directory. 
    #configuration: # string. Configuration. 
    #createAppPackage: true # boolean. Create app package. Default: true.
    #clean: false # boolean. Clean. Default: false.
  # MSBuild Options
    #msbuildLocationOption: 'version' # 'version' | 'location'. Alias: msbuildLocationMethod. MSBuild. Default: version.
    #msbuildVersionOption: '15.0' # 'latest' | '15.0' | '14.0' | '12.0' | '4.0'. Alias: msbuildVersion. Optional. Use when msbuildLocationMethod = version. MSBuild version. Default: 15.0.
    #msbuildFile: # string. Alias: msbuildLocation. Required when msbuildLocationMethod = location. MSBuild location. 
    #msbuildArchitectureOption: 'x86' # 'x86' | 'x64'. Alias: msbuildArchitecture. Optional. Use when msbuildLocationMethod = version. MSBuild architecture. Default: x86.
    #msbuildArguments: # string. Additional arguments. 
  # JDK Options
    jdkOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: jdkSelection. Required. Select JDK to use for the build. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when jdkSelection = JDKVersion. JDK version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when jdkSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="projectFile"::: -->
:::moniker range="<=azure-pipelines"

**`projectFile`** - **Project**<br>
Input alias: `project`. `string`. Required. Default value: `**/*.csproj`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path from repo root of `Xamarin.Android` project(s) to build. Wildcards can be used. For more information, see the [File matching patterns reference](/azure/devops/pipelines/tasks/file-matching-patterns). For example, `**/*.csproj` for all csproj files in all subfolders. The project must have a `PackageForAndroid` target if `Create App Package` is selected.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="target"::: -->
:::moniker range="<=azure-pipelines"

**`target`** - **Target**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies which targets to build in this project. Use a semicolon to separate multiple targets.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`outputDirectory`** - **Output directory**<br>
Input alias: `outputDir`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Provides the output directory for the build. Example: **$(build.binariesDirectory)\/bin\/Release**.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the configuration you want to build. For example, `debug` or `release`.

> [!TIP]
> Declare a build variable such as `BuildConfiguration` on the variables tab (selecting `Allow` at Queue Time) and reference it here as `$(BuildConfiguration)`. You can then modify the platform when you queue the build and enable building multiple configurations.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="createAppPackage"::: -->
:::moniker range="<=azure-pipelines"

**`createAppPackage`** - **Create app package**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Passes the target, `(/t:PackageForAndroid)`, during the build to generate an APK.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="clean"::: -->
:::moniker range="<=azure-pipelines"

**`clean`** - **Clean**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Passes the clean target, `(/t:clean)`, during the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildLocationOption"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildLocationOption`** - **MSBuild**<br>
Input alias: `msbuildLocationMethod`. `string`. Allowed values: `version`, `location` (Specify Location). Default value: `version`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to MSBuild (on Windows) or xbuild (on macOS). The default behavior is to search for the latest version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildVersionOption"::: -->
:::moniker range=">=azure-pipelines-2022"

**`msbuildVersionOption`** - **MSBuild version**<br>
Input alias: `msbuildVersion`. `string`. Optional. Use when `msbuildLocationMethod = version`. Allowed values: `latest`, `17.0` (MSBuild 17.0), `16.0` (MSBuild 16.0), `15.0` (MSBuild 15.0), `14.0` (MSBuild 14.0), `12.0` (MSBuild 12.0), `4.0` (MSBuild 4.0). Default value: `15.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the use of the latest version if the preferred version cannot be found. On macOS, xbuild (Mono) or MSBuild (Visual Studio for Mac) will be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

**`msbuildVersionOption`** - **MSBuild version**<br>
Input alias: `msbuildVersion`. `string`. Optional. Use when `msbuildLocationMethod = version`. Allowed values: `latest`, `15.0` (MSBuild 15.0), `14.0` (MSBuild 14.0), `12.0` (MSBuild 12.0), `4.0` (MSBuild 4.0). Default value: `15.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the use of the latest version if the preferred version cannot be found. On macOS, xbuild (Mono) or MSBuild (Visual Studio for Mac) will be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildFile"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildFile`** - **MSBuild location**<br>
Input alias: `msbuildLocation`. `string`. Required when `msbuildLocationMethod = location`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Supplies the path to MSBuild (on Windows) or xbuild (on macOS).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildArchitectureOption"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildArchitectureOption`** - **MSBuild architecture**<br>
Input alias: `msbuildArchitecture`. `string`. Optional. Use when `msbuildLocationMethod = version`. Allowed values: `x86` (MSBuild x86), `x64` (MSBuild x64). Default value: `x86`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Supplies the architecture (x86, x64) of the MSBuild you want to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msbuildArguments"::: -->
:::moniker range="<=azure-pipelines"

**`msbuildArguments`** - **Additional arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional arguments passed to MSBuild (on Windows) or xbuild (on macOS).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkOption"::: -->
:::moniker range="<=azure-pipelines"

**`jdkOption`** - **Select JDK to use for the build**<br>
Input alias: `jdkSelection`. `string`. Required. Allowed values: `JDKVersion` (JDK Version), `Path`. Default value: `JDKVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the JDK version that the task uses during the build process. The `JDKVersion` value specifies a JDK version that the task discovers during builds. The `Path` value specifies a file path for a JDK version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkVersionOption"::: -->
:::moniker range=">=azure-pipelines-2019"

**`jdkVersionOption`** - **JDK version**<br>
Input alias: `jdkVersion`. `string`. Optional. Use when `jdkSelection = JDKVersion`. Allowed values: `default`, `1.11` (JDK 11), `1.10` (JDK 10 (out of support)), `1.9` (JDK 9 (out of support)), `1.8` (JDK 8), `1.7` (JDK 7), `1.6` (JDK 6 (out of support)). Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the JDK version to use during the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`jdkDirectory`** - **JDK path**<br>
Input alias: `jdkUserInputPath`. `string`. Required when `jdkSelection = Path`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the JDK version to use during the build at the `jdkSelection` path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkArchitectureOption"::: -->
:::moniker range="<=azure-pipelines"

**`jdkArchitectureOption`** - **JDK architecture**<br>
Input alias: `jdkArchitecture`. `string`. Optional. Use when `jdkVersion != default`. Allowed values: `x86`, `x64`. Default value: `x64`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Supplies the architecture (x86, x64) of JDK.
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

Use this task to build an Android app with Xamarin.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

* [Build your Xamarin app](/azure/devops/pipelines/ecosystems/xamarin)
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