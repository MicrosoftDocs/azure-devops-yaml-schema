---
title: NuGetCommand@2 - NuGet v2 task
description: Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Azure Artifacts and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task.
ms.date: 09/22/2025
monikerRange: "=azure-pipelines || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
author: ramiMSFT
ms.author: rabououn
---

# NuGetCommand@2 - NuGet v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to restore, pack, or push NuGet packages, or run a NuGet command. This task supports NuGet.org and authenticated feeds like Azure Artifacts and MyGet. This task also uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task.

> [!TIP]
> Use [NuGetAuthenticate@1](./nuget-authenticate-v1.md) in your pipeline before this task. For more information, see [Why is my build pipeline failing and prompting for Single Sign-On (SSO) authentication?](#why-is-my-build-pipeline-failing-and-prompting-for-single-sign-on-sso-authentication).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# NuGet v2
# Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Azure Artifacts and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task.
- task: NuGetCommand@2
  inputs:
    command: 'restore' # 'restore' | 'pack' | 'push' | 'custom'. Required. Command. Default: restore.
    restoreSolution: '**/*.sln' # string. Alias: solution. Required when command = restore. Path to solution, packages.config, or project.json. Default: **/*.sln.
    #packagesToPush: '$(Build.ArtifactStagingDirectory)/**/*.nupkg;!$(Build.ArtifactStagingDirectory)/**/*.symbols.nupkg' # string. Alias: searchPatternPush. Required when command = push. Path to NuGet package(s) to publish. Default: $(Build.ArtifactStagingDirectory)/**/*.nupkg;!$(Build.ArtifactStagingDirectory)/**/*.symbols.nupkg.
    #nuGetFeedType: 'internal' # 'internal' | 'external'. Required when command = push. Target feed location. Default: internal.
    #publishVstsFeed: # string. Alias: feedPublish. Required when command = push && nuGetFeedType = internal. Target feed. 
    #allowPackageConflicts: false # boolean. Optional. Use when command = push && nuGetFeedType = internal. Allow duplicates to be skipped. Default: false.
    #publishFeedCredentials: # string. Alias: externalEndpoint. Required when command = push && nuGetFeedType = external. NuGet server. 
    #packagesToPack: '**/*.csproj' # string. Alias: searchPatternPack. Required when command = pack. Path to csproj or nuspec file(s) to pack. Default: **/*.csproj.
    #configuration: '$(BuildConfiguration)' # string. Alias: configurationToPack. Optional. Use when command = pack. Configuration to package. Default: $(BuildConfiguration).
    #packDestination: '$(Build.ArtifactStagingDirectory)' # string. Alias: outputDir. Optional. Use when command = pack. Package folder. Default: $(Build.ArtifactStagingDirectory).
    #arguments: # string. Required when command = custom. Command and arguments. 
  # Feeds and authentication
    feedsToUse: 'select' # 'select' | 'config'. Alias: selectOrConfig. Required when command = restore. Feeds to use. Default: select.
    #vstsFeed: # string. Alias: feedRestore. Optional. Use when selectOrConfig = select && command = restore. Use packages from this Azure Artifacts/TFS feed. Select from the dropdown or enter [project name/]feed name. 
    #includeNuGetOrg: true # boolean. Optional. Use when selectOrConfig = select && command = restore. Use packages from NuGet.org. Default: true.
    #nugetConfigPath: # string. Optional. Use when selectOrConfig = config && command = restore. Path to NuGet.config. 
    #externalFeedCredentials: # string. Alias: externalEndpoints. Optional. Use when selectOrConfig = config && command = restore. Credentials for feeds outside this organization/collection. 
  # Advanced
    #noCache: false # boolean. Optional. Use when command = restore. Disable local cache. Default: false.
    #disableParallelProcessing: false # boolean. Optional. Use when command = restore. Disable parallel processing. Default: false.
    #restoreDirectory: # string. Alias: packagesDirectory. Optional. Use when command = restore. Destination directory. 
    #verbosityRestore: 'Detailed' # 'Quiet' | 'Normal' | 'Detailed'. Optional. Use when command = restore. Verbosity. Default: Detailed.
  # Advanced
    #publishPackageMetadata: true # boolean. Optional. Use when command = push && nuGetFeedType = internal. Publish pipeline metadata. Default: true.
    #verbosityPush: 'Detailed' # 'Quiet' | 'Normal' | 'Detailed'. Optional. Use when command = push. Verbosity. Default: Detailed.
  # Pack options
    #versioningScheme: 'off' # 'off' | 'byPrereleaseNumber' | 'byEnvVar' | 'byBuildNumber'. Required when command = pack. Automatic package versioning. Default: off.
    #includeReferencedProjects: false # boolean. Optional. Use when versioningScheme = off && command = pack. Include referenced projects. Default: false.
    #versionEnvVar: # string. Required when versioningScheme = byEnvVar && command = pack. Environment variable. 
    #majorVersion: '1' # string. Alias: requestedMajorVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Major. Default: 1.
    #minorVersion: '0' # string. Alias: requestedMinorVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Minor. Default: 0.
    #patchVersion: '0' # string. Alias: requestedPatchVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Patch. Default: 0.
    #packTimezone: 'utc' # 'utc' | 'local'. Optional. Use when versioningScheme = byPrereleaseNumber && command = pack. Time zone. Default: utc.
    #includeSymbols: false # boolean. Optional. Use when command = pack. Create symbols package. Default: false.
    #toolPackage: false # boolean. Optional. Use when command = pack. Tool Package. Default: false.
  # Advanced
    #buildProperties: # string. Optional. Use when command = pack. Additional build properties. 
    #basePath: # string. Optional. Use when command = pack. Base path. 
    #verbosityPack: 'Detailed' # 'Quiet' | 'Normal' | 'Detailed'. Optional. Use when command = pack. Verbosity. Default: Detailed.
```

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

```yaml
# NuGet v2
# Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Azure Artifacts and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task.
- task: NuGetCommand@2
  inputs:
    command: 'restore' # 'restore' | 'pack' | 'push' | 'custom'. Required. Command. Default: restore.
    restoreSolution: '**/*.sln' # string. Alias: solution. Required when command = restore. Path to solution, packages.config, or project.json. Default: **/*.sln.
    #packagesToPush: '$(Build.ArtifactStagingDirectory)/**/*.nupkg;!$(Build.ArtifactStagingDirectory)/**/*.symbols.nupkg' # string. Alias: searchPatternPush. Required when command = push. Path to NuGet package(s) to publish. Default: $(Build.ArtifactStagingDirectory)/**/*.nupkg;!$(Build.ArtifactStagingDirectory)/**/*.symbols.nupkg.
    #nuGetFeedType: 'internal' # 'internal' | 'external'. Required when command = push. Target feed location. Default: internal.
    #publishVstsFeed: # string. Alias: feedPublish. Required when command = push && nuGetFeedType = internal. Target feed. 
    #allowPackageConflicts: false # boolean. Optional. Use when command = push && nuGetFeedType = internal. Allow duplicates to be skipped. Default: false.
    #publishFeedCredentials: # string. Alias: externalEndpoint. Required when command = push && nuGetFeedType = external. NuGet server. 
    #packagesToPack: '**/*.csproj' # string. Alias: searchPatternPack. Required when command = pack. Path to csproj or nuspec file(s) to pack. Default: **/*.csproj.
    #configuration: '$(BuildConfiguration)' # string. Alias: configurationToPack. Optional. Use when command = pack. Configuration to package. Default: $(BuildConfiguration).
    #packDestination: '$(Build.ArtifactStagingDirectory)' # string. Alias: outputDir. Optional. Use when command = pack. Package folder. Default: $(Build.ArtifactStagingDirectory).
    #arguments: # string. Required when command = custom. Command and arguments. 
  # Feeds and authentication
    feedsToUse: 'select' # 'select' | 'config'. Alias: selectOrConfig. Required when command = restore. Feeds to use. Default: select.
    #vstsFeed: # string. Alias: feedRestore. Optional. Use when selectOrConfig = select && command = restore. Use packages from this Azure Artifacts/TFS feed. 
    #includeNuGetOrg: true # boolean. Optional. Use when selectOrConfig = select && command = restore. Use packages from NuGet.org. Default: true.
    #nugetConfigPath: # string. Optional. Use when selectOrConfig = config && command = restore. Path to NuGet.config. 
    #externalFeedCredentials: # string. Alias: externalEndpoints. Optional. Use when selectOrConfig = config && command = restore. Credentials for feeds outside this organization/collection. 
  # Advanced
    #noCache: false # boolean. Optional. Use when command = restore. Disable local cache. Default: false.
    #disableParallelProcessing: false # boolean. Optional. Use when command = restore. Disable parallel processing. Default: false.
    #restoreDirectory: # string. Alias: packagesDirectory. Optional. Use when command = restore. Destination directory. 
    #verbosityRestore: 'Detailed' # 'Quiet' | 'Normal' | 'Detailed'. Optional. Use when command = restore. Verbosity. Default: Detailed.
  # Advanced
    #publishPackageMetadata: true # boolean. Optional. Use when command = push && nuGetFeedType = internal. Publish pipeline metadata. Default: true.
    #verbosityPush: 'Detailed' # 'Quiet' | 'Normal' | 'Detailed'. Optional. Use when command = push. Verbosity. Default: Detailed.
  # Pack options
    #versioningScheme: 'off' # 'off' | 'byPrereleaseNumber' | 'byEnvVar' | 'byBuildNumber'. Required when command = pack. Automatic package versioning. Default: off.
    #includeReferencedProjects: false # boolean. Optional. Use when versioningScheme = off && command = pack. Include referenced projects. Default: false.
    #versionEnvVar: # string. Required when versioningScheme = byEnvVar && command = pack. Environment variable. 
    #majorVersion: '1' # string. Alias: requestedMajorVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Major. Default: 1.
    #minorVersion: '0' # string. Alias: requestedMinorVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Minor. Default: 0.
    #patchVersion: '0' # string. Alias: requestedPatchVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Patch. Default: 0.
    #packTimezone: 'utc' # 'utc' | 'local'. Optional. Use when versioningScheme = byPrereleaseNumber && command = pack. Time zone. Default: utc.
    #includeSymbols: false # boolean. Optional. Use when command = pack. Create symbols package. Default: false.
    #toolPackage: false # boolean. Optional. Use when command = pack. Tool Package. Default: false.
  # Advanced
    #buildProperties: # string. Optional. Use when command = pack. Additional build properties. 
    #basePath: # string. Optional. Use when command = pack. Base path. 
    #verbosityPack: 'Detailed' # 'Quiet' | 'Normal' | 'Detailed'. Optional. Use when command = pack. Verbosity. Default: Detailed.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="command"::: -->
:::moniker range="<=azure-pipelines"

**`command`** - **Command**<br>
`string`. Required. Allowed values: `restore`, `pack`, `push`, `custom`. Default value: `restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the NuGet command to run. Use the `custom` value to add arguments or to use a different command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restoreSolution"::: -->
:::moniker range="<=azure-pipelines"

**`restoreSolution`** - **Path to solution, packages.config, or project.json**<br>
[Input alias](index.md#what-are-task-input-aliases): `solution`. `string`. Required when `command = restore`. Default value: `**/*.sln`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the solution, `packages.config`, or `project.json` file that references the packages to be restored.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feedsToUse"::: -->
:::moniker range="<=azure-pipelines"

**`feedsToUse`** - **Feeds to use**<br>
[Input alias](index.md#what-are-task-input-aliases): `selectOrConfig`. `string`. Required when `command = restore`. Allowed values: `select` (Feed(s) I select here), `config` (Feeds in my NuGet.config). Default value: `select`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a feed from Azure Artifacts and/or NuGet.org for the task to use with the `select` value. Alternatively, you can commit a `NuGet.config` file to your source code repository and set its path as the value using the `config` value.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstsFeed"::: -->
:::moniker range=">azure-pipelines-2022.2"

**`vstsFeed`** - **Use packages from this Azure Artifacts/TFS feed. Select from the dropdown or enter [project name/]feed name.**<br>
[Input alias](index.md#what-are-task-input-aliases): `feedRestore`. `string`. Optional. Use when `selectOrConfig = select && command = restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the selected feed in the generated `NuGet.config`. You must have Package Management installed and licensed to specify a feed here.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

**`vstsFeed`** - **Use packages from this Azure Artifacts/TFS feed**<br>
[Input alias](index.md#what-are-task-input-aliases): `feedRestore`. `string`. Optional. Use when `selectOrConfig = select && command = restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the selected feed in the generated `NuGet.config`. You must have Package Management installed and licensed to specify a feed here.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeNuGetOrg"::: -->
:::moniker range="<=azure-pipelines"

**`includeNuGetOrg`** - **Use packages from NuGet.org**<br>
`boolean`. Optional. Use when `selectOrConfig = select && command = restore`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes NuGet.org in the generated `NuGet.config`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nugetConfigPath"::: -->
:::moniker range="<=azure-pipelines"

**`nugetConfigPath`** - **Path to NuGet.config**<br>
`string`. Optional. Use when `selectOrConfig = config && command = restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the `NuGet.config` in your repository that determines the feeds from which to restore packages.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="externalFeedCredentials"::: -->
:::moniker range="<=azure-pipelines"

**`externalFeedCredentials`** - **Credentials for feeds outside this organization/collection**<br>
[Input alias](index.md#what-are-task-input-aliases): `externalEndpoints`. `string`. Optional. Use when `selectOrConfig = config && command = restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the credentials to use for external registries located in the selected `NuGet.config`. This is the name of your NuGet service connection. For feeds in this organization or collection, leave this blank; the build's credentials are used automatically.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="noCache"::: -->
:::moniker range="<=azure-pipelines"

**`noCache`** - **Disable local cache**<br>
`boolean`. Optional. Use when `command = restore`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prevents NuGet from using packages from local machine caches when set to `true`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="disableParallelProcessing"::: -->
:::moniker range="<=azure-pipelines"

**`disableParallelProcessing`** - **Disable parallel processing**<br>
`boolean`. Optional. Use when `command = restore`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prevents NuGet from installing multiple packages in parallel processes when set to `true`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restoreDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`restoreDirectory`** - **Destination directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `packagesDirectory`. `string`. Optional. Use when `command = restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the folder in which packages are installed. If no folder is specified, packages are restored into a `packages/` folder alongside the selected solution, `packages.config`, or `project.json`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosityRestore"::: -->
:::moniker range="<=azure-pipelines"

**`verbosityRestore`** - **Verbosity**<br>
`string`. Optional. Use when `command = restore`. Allowed values: `Quiet`, `Normal`, `Detailed`. Default value: `Detailed`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the amount of detail displayed in the output.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagesToPush"::: -->
:::moniker range="<=azure-pipelines"

**`packagesToPush`** - **Path to NuGet package(s) to publish**<br>
[Input alias](index.md#what-are-task-input-aliases): `searchPatternPush`. `string`. Required when `command = push`. Default value: `$(Build.ArtifactStagingDirectory)/**/*.nupkg;!$(Build.ArtifactStagingDirectory)/**/*.symbols.nupkg`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the pattern to match or path to `nupkg` files to be uploaded. Multiple patterns can be separated by a semicolon.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetFeedType"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetFeedType`** - **Target feed location**<br>
`string`. Required when `command = push`. Allowed values: `internal` (This organization/collection), `external` (External NuGet server (including other accounts/collections)). Default value: `internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether the target feed is an internal feed/collection or an external NuGet server.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishVstsFeed"::: -->
:::moniker range="<=azure-pipelines"

**`publishVstsFeed`** - **Target feed**<br>
[Input alias](index.md#what-are-task-input-aliases): `feedPublish`. `string`. Required when `command = push && nuGetFeedType = internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a feed hosted in this account. You must have Azure Artifacts installed and licensed to select a feed here.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishPackageMetadata"::: -->
:::moniker range="<=azure-pipelines"

**`publishPackageMetadata`** - **Publish pipeline metadata**<br>
`boolean`. Optional. Use when `command = push && nuGetFeedType = internal`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Changes the version number of the subset of changed packages within a set of continually published packages.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowPackageConflicts"::: -->
:::moniker range="<=azure-pipelines"

**`allowPackageConflicts`** - **Allow duplicates to be skipped**<br>
`boolean`. Optional. Use when `command = push && nuGetFeedType = internal`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Reports task success even if some of your packages are rejected with 409 Conflict errors.

This option is currently only available on Azure Pipelines and Windows agents. If `NuGet.exe` encounters a conflict, the task will fail. This option will not work and publishing will fail if you are within a proxy environment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishFeedCredentials"::: -->
:::moniker range="<=azure-pipelines"

**`publishFeedCredentials`** - **NuGet server**<br>
[Input alias](index.md#what-are-task-input-aliases): `externalEndpoint`. `string`. Required when `command = push && nuGetFeedType = external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the NuGet service connection that contains the external NuGet server’s credentials.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosityPush"::: -->
:::moniker range="<=azure-pipelines"

**`verbosityPush`** - **Verbosity**<br>
`string`. Optional. Use when `command = push`. Allowed values: `Quiet`, `Normal`, `Detailed`. Default value: `Detailed`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the amount of detail displayed in the output.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagesToPack"::: -->
:::moniker range="<=azure-pipelines"

**`packagesToPack`** - **Path to csproj or nuspec file(s) to pack**<br>
[Input alias](index.md#what-are-task-input-aliases): `searchPatternPack`. `string`. Required when `command = pack`. Default value: `**/*.csproj`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the pattern that the task uses to search for csproj directories to pack.

You can separate multiple patterns with a semicolon, and you can make a pattern negative by prefixing it with `!`. Example: `**\*.csproj;!**\*.Tests.csproj`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration to package**<br>
[Input alias](index.md#what-are-task-input-aliases): `configurationToPack`. `string`. Optional. Use when `command = pack`. Default value: `$(BuildConfiguration)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the configuration to package when using a csproj file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packDestination"::: -->
:::moniker range="<=azure-pipelines"

**`packDestination`** - **Package folder**<br>
[Input alias](index.md#what-are-task-input-aliases): `outputDir`. `string`. Optional. Use when `command = pack`. Default value: `$(Build.ArtifactStagingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the folder where the task creates packages. If the value is empty, the task creates packages at the source root.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versioningScheme"::: -->
:::moniker range="<=azure-pipelines"

**`versioningScheme`** - **Automatic package versioning**<br>
`string`. Required when `command = pack`. Allowed values: `off`, `byPrereleaseNumber` (Use the date and time), `byEnvVar` (Use an environment variable), `byBuildNumber` (Use the build number). Default value: `off`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Applies automatic package versioning depending on the specified value. This string cannot be used with `includeReferencedProjects`. The allowed values are:

- **`byPrereleaseNumber`** - **Use the date and time**: The task will generate a [SemVer](http://semver.org/spec/v1.0.0.html)-compliant version formatted as `X.Y.Z-ci-datetime`, where you specify the values of X, Y, and Z.
- **`byEnvVar`**- **Use an environment variable**: The task will use an environment variable that you specify and contains the version number you want to use.
- **`byBuildNumber`** - **Use the build number**: The task will use the build number to version the package.

> [!NOTE]
> Under General, set the build format to be [`$(BuildDefinitionName)_$(Year:yyyy).$(Month).$(DayOfMonth)$(Rev:.r)`](/azure/devops/pipelines/tasks/package/nuget).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeReferencedProjects"::: -->
:::moniker range="<=azure-pipelines"

**`includeReferencedProjects`** - **Include referenced projects**<br>
`boolean`. Optional. Use when `versioningScheme = off && command = pack`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes referenced projects either as dependencies or as part of the package. Cannot be used with automatic package versioning. If a referenced project has a corresponding `nuspec` file that has the same name as the project, then that referenced project is added as a dependency. Otherwise, the referenced project is added as part of the package. Learn more about [using the pack command for NuGet CLI to create NuGet packages](/nuget/tools/cli-ref-pack).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionEnvVar"::: -->
:::moniker range="<=azure-pipelines"

**`versionEnvVar`** - **Environment variable**<br>
`string`. Required when `versioningScheme = byEnvVar && command = pack`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the variable name without `$`, `$env`, or `%`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="majorVersion"::: -->
:::moniker range="<=azure-pipelines"

**`majorVersion`** - **Major**<br>
[Input alias](index.md#what-are-task-input-aliases): `requestedMajorVersion`. `string`. Required when `versioningScheme = byPrereleaseNumber && command = pack`. Default value: `1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The `X` in version [X.Y.Z](http://semver.org/spec/v1.0.0.html).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="minorVersion"::: -->
:::moniker range="<=azure-pipelines"

**`minorVersion`** - **Minor**<br>
[Input alias](index.md#what-are-task-input-aliases): `requestedMinorVersion`. `string`. Required when `versioningScheme = byPrereleaseNumber && command = pack`. Default value: `0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The `Y` in version [X.Y.Z](http://semver.org/spec/v1.0.0.html).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="patchVersion"::: -->
:::moniker range="<=azure-pipelines"

**`patchVersion`** - **Patch**<br>
[Input alias](index.md#what-are-task-input-aliases): `requestedPatchVersion`. `string`. Required when `versioningScheme = byPrereleaseNumber && command = pack`. Default value: `0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The `Z` in version [X.Y.Z](http://semver.org/spec/v1.0.0.html).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packTimezone"::: -->
:::moniker range="<=azure-pipelines"

**`packTimezone`** - **Time zone**<br>
`string`. Optional. Use when `versioningScheme = byPrereleaseNumber && command = pack`. Allowed values: `utc`, `local` (Agent local time). Default value: `utc`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the desired time zone used to produce the version of the package. Selecting `utc` is recommended if you're using hosted build agents, as their date and time might differ.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeSymbols"::: -->
:::moniker range="<=azure-pipelines"

**`includeSymbols`** - **Create symbols package**<br>
`boolean`. Optional. Use when `command = pack`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies that the package contains sources and symbols. When used with a `.nuspec` file, this creates a regular NuGet package file and the corresponding symbols package.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="toolPackage"::: -->
:::moniker range="<=azure-pipelines"

**`toolPackage`** - **Tool Package**<br>
`boolean`. Optional. Use when `command = pack`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Determines if the output files of the project should be in the tool folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildProperties"::: -->
:::moniker range="<=azure-pipelines"

**`buildProperties`** - **Additional build properties**<br>
`string`. Optional. Use when `command = pack`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a list of token=value pairs, separated by semicolons, where each occurrence of `$token$` in the `.nuspec` file will be replaced with the given value. Values can be strings in quotation marks.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="basePath"::: -->
:::moniker range="<=azure-pipelines"

**`basePath`** - **Base path**<br>
`string`. Optional. Use when `command = pack`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the base path of the files defined in the `nuspec` file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosityPack"::: -->
:::moniker range="<=azure-pipelines"

**`verbosityPack`** - **Verbosity**<br>
`string`. Optional. Use when `command = pack`. Allowed values: `Quiet`, `Normal`, `Detailed`. Default value: `Detailed`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the amount of detail displayed in the output.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **Command and arguments**<br>
`string`. Required when `command = custom`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the command and arguments that will be passed to `NuGet.exe` for execution. If NuGet 3.5 or later is used, authenticated commands like `list`, `restore`, and `publish` against any feed in this organization or collection that the Project Collection Build Service has access to will be automatically authenticated.
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

> [!IMPORTANT]
> If you want to authenticate wih Azure Artifacts or other NuGet repositories you must use The [NuGet Authenticate](nuget-authenticate-v1.md) task instead of the `NuGetCommand@2` task. The `NuGetCommand@2` task is no longer being updated with new features; only critical bugs are addressed.

Use this task to restore, pack, or push NuGet packages, or run a NuGet commands. This task uses *NuGet.exe* and works with *.NET* Framework apps. If you are working with *.NET Core* or *.NET Standard*, use the [.NET Core](dotnet-core-cli-v2.md) task, which has full support for all package scenarios and is currently supported by dotnet.

If your code depends on NuGet packages and you need to restore those dependencies before building your project with the [Visual Studio Build task](vsbuild-v1.md) task, you can use the *nugetAuthenticate* and *command line* tasks to restore your packages. Place both tasks before the build step to ensure all dependencies are available before the build starts. See [Restore NuGet packages](/azure/devops/pipelines/packages/nuget-restore) for more details.

When using the [Visual Studio Build task](vsbuild-v1.md) task, make sure to leave the **restoreNugetPackages** argument blank, as the "Restore NuGet Packages" option is deprecated in the *VSBuild@1* task.

> [!TIP]
> This version of the NuGet task uses NuGet 4.1.0 by default. To select a different version of NuGet, use the [Tool Installer](nuget-tool-installer-v1.md).

### Versioning schemes

For **byPrereleaseNumber**, the version will be set to the values you choose for the major version, the minor version, and the patch, plus the date and time, in the format `yyyymmdd-hhmmss`.

For **byEnvVar**, the version will be set to the value of the environment variable that has the name specified by the **versionEnvVar** parameter, e.g. `MyVersion` (no **$**, just the environment variable name). Make sure the environment variable is set to a proper SemVer, such as `1.2.3` or `1.2.3-beta1`.

For **byBuildNumber**, the version will be set using the pipeline run's build number. This is the value specified for the pipeline's `name` property, which gets saved to the `BUILD_BUILDNUMBER` environment variable). Ensure that the build number being used contains a proper SemVer, such as `1.0.$(Rev:r)`. When using **byBuildNumber**, the task will extract the dotted version, `1.2.3.4`, from the build number string, and use only that portion.  The rest of the string will be dropped. If you want to use the build number as is, you can use **byEnvVar** as described above, and set **versionEnvVar** to `BUILD_BUILDNUMBER`.

### Migrate from NuGetInstaller@0 or NuGetRestore@1

`NuGetInstaller@0` and `NuGetRestore@1` are deprecated, and you should replace them in your pipeline with `NuGetCommand@2`.

If you were using `NuGetInstaller@0` with `restoreMode: restore`, configure the following inputs when using `NuGetCommand@2`.

| NuGetCommand@2 task input | Value |
|---------------------------|-------|
| `command`                 | `restore` |
| `restoreSolution`         | Path the .sln file |

If you were using `NuGetInstaller@0` with `restoreMode: install`, configure the following inputs when using `NuGetCommand@2`.

| NuGetCommand@2 task input | Value |
|---------------------------|-------|
| `command`                 | `custom` |
| `arguments`         | What the full install command would look like in the NuGet CLI. For example, if you want to run the equivalent of `nuget install ninject -OutputDirectory c:\proj` in your pipeline, then the `arguments` parameter would be `install ninject -OutputDirectory c:\proj`. If you were using the `NuGetInstaller@0` `nuGetRestoreArgs` parameter these also now go in `arguments`. |

If you were using `NuGetRestore@1`, configure the following inputs when using `NuGetCommand@2`.

| NuGetCommand@2 task input | Value |
|---------------------------|-------|
| `command`                 | `restore` |
| `restoreSolution`         | Path the .sln file |

Similar to using `NuGetRestore@1` or the `NuGetInstaller@0` `restore` option, `NuGetCommand@2` has inputs to set the feed, decide between `select` or `config`, specify the path to the `NuGet.config` file, and use packages from nuget.org.

For more information, see the following [examples](#examples).

### Support for Newer Ubuntu Hosted Images

Starting with Ubuntu 24.04, Microsft-hosted agents [will not ship with mono](https://github.com/actions/runner-images/issues/10636) which is required to run the underlying NuGet client that powers `NuGetCommand@2`. Users of this task on Ubuntu should migrate to the long term supported cross-platform task `NuGetAuthenticate@1` with .NET CLI.

#### Migrating to .NET CLI on Ubuntu

The [NuGet Authenticate](nuget-authenticate-v1.md) task will handle injecting credentials into the needed places for client tools to authenticate as your pipeline identity. Please see the [Examples](/azure/devops/pipelines/tasks/reference/nuget-authenticate-v1#examples) and [Remarks](/azure/devops/pipelines/tasks/reference/nuget-authenticate-v1#remarks) sections to learn more about using `NuGet Authenticate` with dotnet.

If [dotnet CLI commands](/nuget/reference/dotnet-commands) do not support your scenario, please [report this to the .NET CLI team as an issue](https://github.com/NuGet/Home/issues/). You may continue to [pin your agent image](/azure/devops/pipelines/agents/pools-queues#designate-a-pool-in-your-pipeline) to [Ubuntu 22.04 or earlier](/azure/devops/pipelines/agents/hosted#software). Ubuntu 22.04 support will continue until Ubuntu 26.04 is made generally available, no earlier than 2026.

### Why is my build pipeline failing and prompting for Single Sign-On (SSO) authentication?

Builds can fail if credentials have expired. To avoid these failures, we recommend using the [NuGet Authenticate](nuget-authenticate-v1.md) task to reinstall the credential provider and automatically refresh credentials. This ensures uninterrupted access during pipeline execution.

```yaml
steps:
# Authenticate with NuGet to ensure credentials are refreshed
- task: NuGetAuthenticate@1
# Restore NuGet packages
- task: NuGetCommand@2
  inputs:
    command: 'restore'
    restoreSolution: '**/*.sln'
    feedsToUse: 'select'
```
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Restore

Restore all your solutions with packages from a selected feed.

#### [Windows](#tab/windows/)

```YAML
# Restore from a project scoped feed in the same organization
- task: NuGetCommand@2
  inputs:
    command: 'restore'
    feedsToUse: 'select'
    vstsFeed: 'my-project/my-project-scoped-feed'
    includeNuGetOrg: false
    restoreSolution: '**/*.sln'
```

```YAML
# Restore from an organization scoped feed in the same organization
- task: NuGetCommand@2
  inputs:
    command: 'restore'
    feedsToUse: 'select'
    vstsFeed: 'my-organization-scoped-feed'
    restoreSolution: '**/*.sln'
```

```YAML
# Restore from a feed in a different organization
- task: NuGetCommand@2
  inputs:
    command: 'restore'
    feedsToUse: config
    nugetConfigPath: ./nuget.config
    restoreSolution: '**/*.sln'
    externalFeedCredentials: 'MyServiceConnectionName'
    noCache: true
  continueOnError: true
```

```YAML
# Restore from feed(s) set in nuget.config
- task: NuGetCommand@2
  inputs:
    command: 'restore'
    feedsToUse: 'config'
    nugetConfigPath: 'nuget.config'
```

#### [Linux](#tab/linux/)

```YAML
- task: UseDotNet@2
  displayName: 'Install .NET Core SDK'
  inputs:
    version: 9.x
    performMultiLevelLookup: true
    includePreviewVersions: true

- task: NuGetAuthenticate@1
  displayName: 'NuGet Authenticate'

- script: |
      dotnet restore <SOLUTION_PATH>
```

---

### Package

Create a NuGet package in the destination folder.

```YAML
# Package a project
- task: NuGetCommand@2
  inputs:
    command: 'pack'
    packagesToPack: '**/*.csproj'
    packDestination: '$(Build.ArtifactStagingDirectory)'
```

### Push

> [!NOTE]
> Pipeline artifacts are downloaded to the `Pipeline.Workspace` directory, and to the `System.ArtifactsDirectory` directory for classic release pipelines. `packagesToPush` value can be set to `$(Pipeline.Workspace)/**/*.nupkg` or `$(System.ArtifactsDirectory)/**/*.nupkg` respectively.

#### [Windows](#tab/windows/)

* Push/Publish a package to a feed defined in your NuGet.config.

    ```YAML
    # Push a project
    - task: NuGetCommand@2
      inputs:
        command: 'push'
        packagesToPush: '$(Build.ArtifactStagingDirectory)/**/*.nupkg'
        feedsToUse: 'config'
        nugetConfigPath: '$(Build.WorkingDirectory)/NuGet.config'
    ```

* Push/Publish a package to an organization scoped feed

    ```YAML
    # Push a project
    - task: NuGetCommand@2
      inputs:
        command: 'push'
        nuGetFeedType: 'internal'
        publishVstsFeed: 'my-organization-scoped-feed'
    ```
    
* Push/Publish a package to a project scoped feed

    ```YAML
    # Push a project
    - task: NuGetCommand@2
      inputs:
        command: 'push'
        nuGetFeedType: 'internal'
        publishVstsFeed: 'my-project/my-project-scoped-feed'
    ```

* Push/Publish a package to NuGet.org

    ```YAML
    # Push a project
    - task: NuGetCommand@2
      inputs:
        command: 'push'
        feedsToUse: 'config'
        includeNugetOrg: 'true'
    ```

#### [Linux](#tab/linux/)

```YAML
- task: NuGetAuthenticate@1
  displayName: 'NuGet Authenticate'

- task: UseDotNet@2 
  displayName: 'Install .NET Core SDK'
  inputs:
    version: 9.x

- script: |
      dotnet nuget push --source <SOURCE_NAME>  --api-key <ANY_STRING> <PACKAGE_PATH>     
```

---

### Custom

Run any other NuGet command besides the default ones: pack, push, and restore.

```YAML
# list local NuGet resources.
- task: NuGetCommand@2
  displayName: 'list locals'
  inputs:
    command: custom
    arguments: 'locals all -list'
```
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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Package |

:::moniker-end

:::moniker range="<=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
