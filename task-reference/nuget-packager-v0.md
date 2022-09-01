---
title: NuGetPackager@0 - NuGet packager v0 task
description: NuGetPackager@0 is deprecated. Use the NuGet task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# NuGetPackager@0 - NuGet packager v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
NuGetPackager@0 is deprecated. Use the NuGet task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this account/collection, and uses NuGet 4 by default.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# NuGet packager v0
# Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default.
- task: NuGetPackager@0
  inputs:
    searchPattern: '**\*.csproj' # string. Required. Path to csproj or nuspec file(s) to pack. Default: '**\*.csproj'.
    #outputdir: # string. Package Folder. 
  # Pack options
    #includeReferencedProjects: false # boolean. Include referenced projects. Default: false.
    versionByBuild: 'false' # 'false' | 'byPrereleaseNumber' | 'byEnvVar' | 'true'. Required. Automatic package versioning. Default: 'false'.
    #versionEnvVar: # string. Required when versionByBuild = byEnvVar. Environment variable. 
    #requestedMajorVersion: '1' # string. Required when versionByBuild = byPrereleaseNumber. Major. Default: '1'.
    #requestedMinorVersion: '0' # string. Required when versionByBuild = byPrereleaseNumber. Minor. Default: '0'.
    #requestedPatchVersion: '0' # string. Required when versionByBuild = byPrereleaseNumber. Patch. Default: '0'.
  # Advanced
    #configurationToPack: '$(BuildConfiguration)' # string. Configuration to Package. Default: '$(BuildConfiguration)'.
    #buildProperties: # string. Additional build properties. 
    #nuGetAdditionalArgs: # string. NuGet Arguments. 
    #nuGetPath: # string. Path to NuGet.exe.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# NuGet Packager v0
# Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this account/collection, and uses NuGet 4 by default.
- task: NuGetPackager@0
  inputs:
    searchPattern: '**\*.csproj' # string. Required. Path to csproj or nuspec file(s) to pack. Default: '**\*.csproj'.
    #outputdir: # string. Package Folder. 
  # Pack options
    #includeReferencedProjects: false # boolean. Include referenced projects. Default: false.
    versionByBuild: 'false' # 'false' | 'byPrereleaseNumber' | 'byEnvVar' | 'true'. Required. Automatic package versioning. Default: 'false'.
    #versionEnvVar: # string. Required when versionByBuild = byEnvVar. Environment variable. 
    #requestedMajorVersion: '1' # string. Required when versionByBuild = byPrereleaseNumber. Major. Default: '1'.
    #requestedMinorVersion: '0' # string. Required when versionByBuild = byPrereleaseNumber. Minor. Default: '0'.
    #requestedPatchVersion: '0' # string. Required when versionByBuild = byPrereleaseNumber. Patch. Default: '0'.
  # Advanced
    #configurationToPack: '$(BuildConfiguration)' # string. Configuration to Package. Default: '$(BuildConfiguration)'.
    #buildProperties: # string. Additional build properties. 
    #nuGetAdditionalArgs: # string. NuGet Arguments. 
    #nuGetPath: # string. Path to NuGet.exe.
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

<!-- :::item name="searchPattern"::: -->
:::moniker range="<=azure-pipelines"

**`searchPattern`** - **Path to csproj or nuspec file(s) to pack**<br>
Type: string. Required. Default value: '**\*.csproj'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Pattern to search for csproj or nuspec files to pack.

You can separate multiple patterns with a semicolon, and you can make a pattern negative by prefixing it with '-:'. Example: `**\*.csproj;-:**\*.Tests.csproj`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputdir"::: -->
:::moniker range="<=azure-pipelines"

**`outputdir`** - **Package Folder**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Folder where packages will be created. If empty, packages will be created alongside the csproj or nuspec file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeReferencedProjects"::: -->
:::moniker range="<=azure-pipelines"

**`includeReferencedProjects`** - **Include referenced projects**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Include referenced projects either as dependencies or as part of the package. Cannot be used with automatic package versioning. If a referenced project has a corresponding nuspec file that has the same name as the project, then that referenced project is added as a dependency. Otherwise, the referenced project is added as part of the package. [Learn more](/nuget/tools/cli-ref-pack).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionByBuild"::: -->
:::moniker range="<=azure-pipelines"

**`versionByBuild`** - **Automatic package versioning**<br>
Type: string. Required. Allowed values: 'false', 'byPrereleaseNumber', 'byEnvVar', 'true'. Default value: 'false'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Cannot be used with include referenced projects. If you choose 'Use the date and time', this will generate a [SemVer](http://semver.org/spec/v1.0.0.html)-compliant version formatted as `X.Y.Z-ci-datetime` where you choose X, Y, and Z.

If you choose 'Use an environment variable', you must select an environment variable and ensure it contains the version number you want to use.

If you choose 'Use the build number', this will use the build number to version you package. **Note:** Under General set the build format to be '[$(BuildDefinitionName)_$(Year:yyyy).$(Month).$(DayOfMonth)$(Rev:.r)](https://go.microsoft.com/fwlink/?LinkID=627416)'.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionEnvVar"::: -->
:::moniker range="<=azure-pipelines"

**`versionEnvVar`** - **Environment variable**<br>
Type: string. Required when versionByBuild = byEnvVar.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the variable name without $, $env, or %.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="requestedMajorVersion"::: -->
:::moniker range="<=azure-pipelines"

**`requestedMajorVersion`** - **Major**<br>
Type: string. Required when versionByBuild = byPrereleaseNumber. Default value: '1'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The 'X' in version [X.Y.Z](http://semver.org/spec/v1.0.0.html).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="requestedMinorVersion"::: -->
:::moniker range="<=azure-pipelines"

**`requestedMinorVersion`** - **Minor**<br>
Type: string. Required when versionByBuild = byPrereleaseNumber. Default value: '0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The 'Y' in version [X.Y.Z](http://semver.org/spec/v1.0.0.html).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="requestedPatchVersion"::: -->
:::moniker range="<=azure-pipelines"

**`requestedPatchVersion`** - **Patch**<br>
Type: string. Required when versionByBuild = byPrereleaseNumber. Default value: '0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The 'Z' in version [X.Y.Z](http://semver.org/spec/v1.0.0.html).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configurationToPack"::: -->
:::moniker range="<=azure-pipelines"

**`configurationToPack`** - **Configuration to Package**<br>
Type: string. Default value: '$(BuildConfiguration)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When using a csproj file this specifies the configuration to package.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildProperties"::: -->
:::moniker range="<=azure-pipelines"

**`buildProperties`** - **Additional build properties**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Semicolon delimited list of properties used to build the package.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetAdditionalArgs"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetAdditionalArgs`** - **NuGet Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments passed to NuGet.exe pack. [More Information](/nuget/tools/cli-ref-pack).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetPath"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetPath`** - **Path to NuGet.exe**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the path to NuGet.exe.
<!-- :::editable-content-end::: -->

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

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: Cmd |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.83.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->