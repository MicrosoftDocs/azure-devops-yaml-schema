---
title: NuGetCommand@2 - NuGet v2 task
description: Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Azure Artifacts and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# NuGetCommand@2 - NuGet v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Azure Artifacts and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Package Management and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# NuGet v2
# Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Azure Artifacts and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task.
- task: NuGetCommand@2
  inputs:
    command: 'restore' # 'restore' | 'pack' | 'push' | 'custom'. Required. Command. Default: 'restore'.
    restoreSolution: '**/*.sln' # string. Required when command = restore. Path to solution, packages.config, or project.json. Default: '**/*.sln'.
    #packagesToPush: '$(Build.ArtifactStagingDirectory)/**/*.nupkg;!$(Build.ArtifactStagingDirectory)/**/*.symbols.nupkg' # string. Required when command = push. Path to NuGet package(s) to publish. Default: '$(Build.ArtifactStagingDirectory)/**/*.nupkg;!$(Build.ArtifactStagingDirectory)/**/*.symbols.nupkg'.
    #nuGetFeedType: 'internal' # 'internal' | 'external'. Required when command = push. Target feed location. Default: 'internal'.
    #publishVstsFeed: # string. Required when command = push && nuGetFeedType = internal. Target feed. 
    #allowPackageConflicts: false # boolean. Optional. Use when command = push && nuGetFeedType = internal. Allow duplicates to be skipped. Default: false.
    #publishFeedCredentials: # string. Required when command = push && nuGetFeedType = external. NuGet server. 
    #packagesToPack: '**/*.csproj' # string. Required when command = pack. Path to csproj or nuspec file(s) to pack. Default: '**/*.csproj'.
    #configuration: '$(BuildConfiguration)' # string. Optional. Use when command = pack. Configuration to package. Default: '$(BuildConfiguration)'.
    #packDestination: '$(Build.ArtifactStagingDirectory)' # string. Optional. Use when command = pack. Package folder. Default: '$(Build.ArtifactStagingDirectory)'.
    #arguments: # string. Required when command = custom. Command and arguments. 
  # Feeds and authentication
    feedsToUse: 'select' # 'select' | 'config'. Required. Feeds to use. Default: 'select'.
    #vstsFeed: # string. Optional. Use when selectOrConfig = select. Use packages from this Azure Artifacts/TFS feed. 
    #includeNuGetOrg: true # boolean. Optional. Use when selectOrConfig = select. Use packages from NuGet.org. Default: true.
    #nugetConfigPath: # string. Optional. Use when selectOrConfig = config. Path to NuGet.config. 
    #externalFeedCredentials: # string. Optional. Use when selectOrConfig = config. Credentials for feeds outside this organization/collection. 
  # Advanced
    #noCache: false # boolean. Disable local cache. Default: false.
    #disableParallelProcessing: false # boolean. Disable parallel processing. Default: false.
    #restoreDirectory: # string. Destination directory. 
    #verbosityRestore: 'Detailed' # 'Quiet' | 'Normal' | 'Detailed'. Verbosity. Default: 'Detailed'.
  # Advanced
    #publishPackageMetadata: true # boolean. Optional. Use when command = push && nuGetFeedType = internal. Publish pipeline metadata. Default: true.
    #verbosityPush: 'Detailed' # 'Quiet' | 'Normal' | 'Detailed'. Verbosity. Default: 'Detailed'.
  # Pack options
    versioningScheme: 'off' # 'off' | 'byPrereleaseNumber' | 'byEnvVar' | 'byBuildNumber'. Required. Automatic package versioning. Default: 'off'.
    #includeReferencedProjects: false # boolean. Optional. Use when versioningScheme = off. Include referenced projects. Default: false.
    #versionEnvVar: # string. Required when versioningScheme = byEnvVar. Environment variable. 
    #majorVersion: '1' # string. Required when versioningScheme = byPrereleaseNumber. Major. Default: '1'.
    #minorVersion: '0' # string. Required when versioningScheme = byPrereleaseNumber. Minor. Default: '0'.
    #patchVersion: '0' # string. Required when versioningScheme = byPrereleaseNumber. Patch. Default: '0'.
    #packTimezone: 'utc' # 'utc' | 'local'. Optional. Use when versioningScheme = byPrereleaseNumber. Time zone. Default: 'utc'.
    #includeSymbols: false # boolean. Create symbols package. Default: false.
    #toolPackage: false # boolean. Tool Package. Default: false.
  # Advanced
    #buildProperties: # string. Additional build properties. 
    #basePath: # string. Base path. 
    #verbosityPack: 'Detailed' # 'Quiet' | 'Normal' | 'Detailed'. Verbosity. Default: 'Detailed'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# NuGet v2
# Restore, pack, or push NuGet packages, or run a NuGet command. Supports NuGet.org and authenticated feeds like Package Management and MyGet. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task.
- task: NuGetCommand@2
  inputs:
    command: 'restore' # 'restore' | 'pack' | 'push' | 'custom'. Required. Command. Default: 'restore'.
    restoreSolution: '**/*.sln' # string. Required when command = restore. Path to solution, packages.config, or project.json. Default: '**/*.sln'.
    #packagesToPush: '$(Build.ArtifactStagingDirectory)/**/*.nupkg;!$(Build.ArtifactStagingDirectory)/**/*.symbols.nupkg' # string. Required when command = push. Path to NuGet package(s) to publish. Default: '$(Build.ArtifactStagingDirectory)/**/*.nupkg;!$(Build.ArtifactStagingDirectory)/**/*.symbols.nupkg'.
    #nuGetFeedType: 'internal' # 'internal' | 'external'. Required when command = push. Target feed location. Default: 'internal'.
    #publishVstsFeed: # string. Required when command = push && nuGetFeedType = internal. Target feed. 
    #allowPackageConflicts: false # boolean. Optional. Use when command = push && nuGetFeedType = internal. Allow duplicates to be skipped. Default: false.
    #publishFeedCredentials: # string. Required when command = push && nuGetFeedType = external. NuGet server. 
    #packagesToPack: '**/*.csproj' # string. Required when command = pack. Path to csproj or nuspec file(s) to pack. Default: '**/*.csproj'.
    #configuration: '$(BuildConfiguration)' # string. Optional. Use when command = pack. Configuration to package. Default: '$(BuildConfiguration)'.
    #packDestination: '$(Build.ArtifactStagingDirectory)' # string. Optional. Use when command = pack. Package folder. Default: '$(Build.ArtifactStagingDirectory)'.
    #arguments: # string. Required when command = custom. Command and arguments. 
  # Feeds and authentication
    feedsToUse: 'select' # 'select' | 'config'. Required. Feeds to use. Default: 'select'.
    #vstsFeed: # string. Optional. Use when selectOrConfig = select. Use packages from this Azure Artifacts/TFS feed. 
    #includeNuGetOrg: true # boolean. Optional. Use when selectOrConfig = select. Use packages from NuGet.org. Default: true.
    #nugetConfigPath: # string. Optional. Use when selectOrConfig = config. Path to NuGet.config. 
    #externalFeedCredentials: # string. Optional. Use when selectOrConfig = config. Credentials for feeds outside this account/collection. 
  # Advanced
    #noCache: false # boolean. Disable local cache. Default: false.
    #disableParallelProcessing: false # boolean. Disable parallel processing. Default: false.
    #restoreDirectory: # string. Destination directory. 
    #verbosityRestore: 'Detailed' # 'Quiet' | 'Normal' | 'Detailed'. Verbosity. Default: 'Detailed'.
  # Advanced
    #verbosityPush: 'Detailed' # 'Quiet' | 'Normal' | 'Detailed'. Verbosity. Default: 'Detailed'.
  # Pack options
    versioningScheme: 'off' # 'off' | 'byPrereleaseNumber' | 'byEnvVar' | 'byBuildNumber'. Required. Automatic package versioning. Default: 'off'.
    #includeReferencedProjects: false # boolean. Optional. Use when versioningScheme = off. Include referenced projects. Default: false.
    #versionEnvVar: # string. Required when versioningScheme = byEnvVar. Environment variable. 
    #majorVersion: '1' # string. Required when versioningScheme = byPrereleaseNumber. Major. Default: '1'.
    #minorVersion: '0' # string. Required when versioningScheme = byPrereleaseNumber. Minor. Default: '0'.
    #patchVersion: '0' # string. Required when versioningScheme = byPrereleaseNumber. Patch. Default: '0'.
    #packTimezone: 'utc' # 'utc' | 'local'. Optional. Use when versioningScheme = byPrereleaseNumber. Time zone. Default: 'utc'.
    #includeSymbols: false # boolean. Create symbols package. Default: false.
    #toolPackage: false # boolean. Tool Package. Default: false.
  # Advanced
    #buildProperties: # string. Additional build properties. 
    #basePath: # string. Base path. 
    #verbosityPack: 'Detailed' # 'Quiet' | 'Normal' | 'Detailed'. Verbosity. Default: 'Detailed'.
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

<!-- :::item name="command"::: -->
:::moniker range="<=azure-pipelines"

**`command`** - **Command**<br>
Type: string. Required. Allowed values: 'restore', 'pack', 'push', 'custom'. Default value: 'restore'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The NuGet command to run. Select 'Custom' to add arguments or to use a different command.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restoreSolution"::: -->
:::moniker range="<=azure-pipelines"

**`restoreSolution`** - **Path to solution, packages.config, or project.json**<br>
Input alias: `solution`. Type: string. Required when command = restore. Default value: '**/*.sln'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the solution, packages.config, or project.json file that references the packages to be restored.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feedsToUse"::: -->
:::moniker range="<=azure-pipelines"

**`feedsToUse`** - **Feeds to use**<br>
Input alias: `selectOrConfig`. Type: string. Required. Allowed values: 'select', 'config'. Default value: 'select'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You can either select a feed from Azure Artifacts and/or NuGet.org here, or commit a nuget.config file to your source code repository and set its path here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstsFeed"::: -->
:::moniker range=">=azure-pipelines-2019"

**`vstsFeed`** - **Use packages from this Azure Artifacts/TFS feed**<br>
Input alias: `feedRestore`. Type: string. Optional. Use when selectOrConfig = select.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Include the selected feed in the generated NuGet.config. You must have Package Management installed and licensed to select a feed here.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`vstsFeed`** - **Use packages from this VSTS/TFS feed**<br>
Input alias: `feedRestore`. Type: string. Optional. Use when selectOrConfig = select.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Include the selected feed in the generated NuGet.config. You must have Package Management installed and licensed to select a feed here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeNuGetOrg"::: -->
:::moniker range="<=azure-pipelines"

**`includeNuGetOrg`** - **Use packages from NuGet.org**<br>
Type: boolean. Optional. Use when selectOrConfig = select. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Include NuGet.org in the generated NuGet.config.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nugetConfigPath"::: -->
:::moniker range="<=azure-pipelines"

**`nugetConfigPath`** - **Path to NuGet.config**<br>
Type: string. Optional. Use when selectOrConfig = config.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The NuGet.config in your repository that specifies the feeds from which to restore packages.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="externalFeedCredentials"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`externalFeedCredentials`** - **Credentials for feeds outside this organization/collection**<br>
Input alias: `externalEndpoints`. Type: string. Optional. Use when selectOrConfig = config.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Credentials to use for external registries located in the selected NuGet.config. For feeds in this organization/collection, leave this blank; the build’s credentials are used automatically.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

**`externalFeedCredentials`** - **Credentials for feeds outside this account/collection**<br>
Input alias: `externalEndpoints`. Type: string. Optional. Use when selectOrConfig = config.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Credentials to use for external registries located in the selected NuGet.config. For feeds in this account/collection, leave this blank; the build’s credentials are used automatically.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="noCache"::: -->
:::moniker range="<=azure-pipelines"

**`noCache`** - **Disable local cache**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prevents NuGet from using packages from local machine caches.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="disableParallelProcessing"::: -->
:::moniker range=">=azure-pipelines-2019"

**`disableParallelProcessing`** - **Disable parallel processing**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prevents NuGet from installing multiple packages in parallel.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restoreDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`restoreDirectory`** - **Destination directory**<br>
Input alias: `packagesDirectory`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the folder in which packages are installed. If no folder is specified, packages are restored into a packages/ folder alongside the selected solution, packages.config, or project.json.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosityRestore"::: -->
:::moniker range="<=azure-pipelines"

**`verbosityRestore`** - **Verbosity**<br>
Type: string. Allowed values: 'Quiet', 'Normal', 'Detailed'. Default value: 'Detailed'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the amount of detail displayed in the output.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagesToPush"::: -->
:::moniker range="<=azure-pipelines"

**`packagesToPush`** - **Path to NuGet package(s) to publish**<br>
Input alias: `searchPatternPush`. Type: string. Required when command = push. Default value: '$(Build.ArtifactStagingDirectory)/**/*.nupkg;!$(Build.ArtifactStagingDirectory)/**/*.symbols.nupkg'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The pattern to match or path to nupkg files to be uploaded. Multiple patterns can be separated by a semicolon.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetFeedType"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetFeedType`** - **Target feed location**<br>
Type: string. Required when command = push. Allowed values: 'internal', 'external'. Default value: 'internal'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishVstsFeed"::: -->
:::moniker range="<=azure-pipelines"

**`publishVstsFeed`** - **Target feed**<br>
Input alias: `feedPublish`. Type: string. Required when command = push && nuGetFeedType = internal.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a feed hosted in this account. You must have Package Management installed and licensed to select a feed here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishPackageMetadata"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`publishPackageMetadata`** - **Publish pipeline metadata**<br>
Type: boolean. Optional. Use when command = push && nuGetFeedType = internal. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Associate this build/release pipeline’s metadata (run #, source code information) with the package.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowPackageConflicts"::: -->
:::moniker range="<=azure-pipelines"

**`allowPackageConflicts`** - **Allow duplicates to be skipped**<br>
Type: boolean. Optional. Use when command = push && nuGetFeedType = internal. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If you continually publish a set of packages and only change the version number of the subset of packages that changed, use this option. It allows the task to report success even if some of your packages are rejected with 409 Conflict errors.

This option is currently only available on Azure Pipelines and using Windows agents. If NuGet.exe encounters a conflict, the task will fail.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishFeedCredentials"::: -->
:::moniker range="<=azure-pipelines"

**`publishFeedCredentials`** - **NuGet server**<br>
Input alias: `externalEndpoint`. Type: string. Required when command = push && nuGetFeedType = external.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The NuGet service connection that contains the external NuGet server’s credentials.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosityPush"::: -->
:::moniker range="<=azure-pipelines"

**`verbosityPush`** - **Verbosity**<br>
Type: string. Allowed values: 'Quiet', 'Normal', 'Detailed'. Default value: 'Detailed'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the amount of detail displayed in the output.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagesToPack"::: -->
:::moniker range="<=azure-pipelines"

**`packagesToPack`** - **Path to csproj or nuspec file(s) to pack**<br>
Input alias: `searchPatternPack`. Type: string. Required when command = pack. Default value: '**/*.csproj'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Pattern to search for csproj directories to pack.

You can separate multiple patterns with a semicolon, and you can make a pattern negative by prefixing it with '!'. Example: `**\*.csproj;!**\*.Tests.csproj`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration to package**<br>
Input alias: `configurationToPack`. Type: string. Optional. Use when command = pack. Default value: '$(BuildConfiguration)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When using a csproj file this specifies the configuration to package.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packDestination"::: -->
:::moniker range="<=azure-pipelines"

**`packDestination`** - **Package folder**<br>
Input alias: `outputDir`. Type: string. Optional. Use when command = pack. Default value: '$(Build.ArtifactStagingDirectory)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Folder where packages will be created. If empty, packages will be created at the source root.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versioningScheme"::: -->
:::moniker range="<=azure-pipelines"

**`versioningScheme`** - **Automatic package versioning**<br>
Type: string. Required. Allowed values: 'off', 'byPrereleaseNumber', 'byEnvVar', 'byBuildNumber'. Default value: 'off'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Cannot be used with include referenced projects. If you choose 'Use the date and time', this will generate a [SemVer](http://semver.org/spec/v1.0.0.html)-compliant version formatted as `X.Y.Z-ci-datetime` where you choose X, Y, and Z.

If you choose 'Use an environment variable', you must select an environment variable and ensure it contains the version number you want to use.

If you choose 'Use the build number', this will use the build number to version your package. **Note:** Under Options set the build number format to be '[$(BuildDefinitionName)_$(Year:yyyy).$(Month).$(DayOfMonth)$(Rev:.r)](https://go.microsoft.com/fwlink/?LinkID=627416)'.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeReferencedProjects"::: -->
:::moniker range="<=azure-pipelines"

**`includeReferencedProjects`** - **Include referenced projects**<br>
Type: boolean. Optional. Use when versioningScheme = off. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Include referenced projects either as dependencies or as part of the package. Cannot be used with automatic package versioning. If a referenced project has a corresponding nuspec file that has the same name as the project, then that referenced project is added as a dependency. Otherwise, the referenced project is added as part of the package. [Learn more](/nuget/tools/cli-ref-pack).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionEnvVar"::: -->
:::moniker range="<=azure-pipelines"

**`versionEnvVar`** - **Environment variable**<br>
Type: string. Required when versioningScheme = byEnvVar.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the variable name without $, $env, or %.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="majorVersion"::: -->
:::moniker range="<=azure-pipelines"

**`majorVersion`** - **Major**<br>
Input alias: `requestedMajorVersion`. Type: string. Required when versioningScheme = byPrereleaseNumber. Default value: '1'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The 'X' in version [X.Y.Z](http://semver.org/spec/v1.0.0.html).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="minorVersion"::: -->
:::moniker range="<=azure-pipelines"

**`minorVersion`** - **Minor**<br>
Input alias: `requestedMinorVersion`. Type: string. Required when versioningScheme = byPrereleaseNumber. Default value: '0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The 'Y' in version [X.Y.Z](http://semver.org/spec/v1.0.0.html).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="patchVersion"::: -->
:::moniker range="<=azure-pipelines"

**`patchVersion`** - **Patch**<br>
Input alias: `requestedPatchVersion`. Type: string. Required when versioningScheme = byPrereleaseNumber. Default value: '0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The 'Z' in version [X.Y.Z](http://semver.org/spec/v1.0.0.html).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packTimezone"::: -->
:::moniker range="<=azure-pipelines"

**`packTimezone`** - **Time zone**<br>
Type: string. Optional. Use when versioningScheme = byPrereleaseNumber. Allowed values: 'utc', 'local'. Default value: 'utc'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the desired time zone used to produce the version of the package. Selecting UTC is recommended if you're using hosted build agents as their date and time might differ.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeSymbols"::: -->
:::moniker range="<=azure-pipelines"

**`includeSymbols`** - **Create symbols package**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies that the package contains sources and symbols. When used with a .nuspec file, this creates a regular NuGet package file and the corresponding symbols package.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="toolPackage"::: -->
:::moniker range="<=azure-pipelines"

**`toolPackage`** - **Tool Package**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Determines if the output files of the project should be in the tool folder.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildProperties"::: -->
:::moniker range="<=azure-pipelines"

**`buildProperties`** - **Additional build properties**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a list of token=value pairs, separated by semicolons, where each occurrence of $token$ in the .nuspec file will be replaced with the given value. Values can be strings in quotation marks.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="basePath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`basePath`** - **Base path**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The base path of the files defined in the nuspec file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosityPack"::: -->
:::moniker range="<=azure-pipelines"

**`verbosityPack`** - **Verbosity**<br>
Type: string. Allowed values: 'Quiet', 'Normal', 'Detailed'. Default value: 'Detailed'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the amount of detail displayed in the output.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **Command and arguments**<br>
Type: string. Required when command = custom.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The command and arguments which will be passed to NuGet.exe for execution. If NuGet 3.5 or later is used, authenticated commands like list, restore, and publish against any feed in this account/collection that the Project Collection Build Service has access to will be automatically authenticated.
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
## Remarks

> [!IMPORTANT]
> The [NuGet Authenticate](nuget-authenticate-v1.md) task is the new recommended way to authenticate with Azure Artifacts and other NuGet repositories. This task no longer takes new features and only critical bugs are addressed.

Use this task to install and update NuGet package dependencies, or package and publish NuGet packages. Uses NuGet.exe and works with .NET Framework apps. For .NET Core and .NET Standard apps, use the .NET Core task.

If your code depends on NuGet packages, make sure to add this step before your [Visual Studio Build task](vsbuild-v1.md). Also make sure to clear the deprecated **Restore NuGet Packages** checkbox in that task.

If you are working with .NET Core or .NET Standard, use the [.NET Core](dotnet-core-cli-v2.md) task, which has full support for all package scenarios and it's currently supported by dotnet.

> [!TIP]
> This version of the NuGet task uses NuGet 4.1.0 by default. To select a different version of NuGet, use the [Tool Installer](nuget-installer-v0.md).

### Versioning schemes

For **byPrereleaseNumber**, the version will be set to whatever you choose for major, minor, and patch, plus the date and time in the format `yyyymmdd-hhmmss`.

For **byEnvVar**, the version will be set to the value of the environment variable that has the name specified by the **versionEnvVar** parameter, e.g. `MyVersion` (no **$**, just the environment variable name). Make sure the environment variable is set to a proper SemVer e.g. `1.2.3` or `1.2.3-beta1`.

For **byBuildNumber**, the version will be set using the pipeline run's build number.  This is the value specified for the pipeline's `name` property, which gets saved to the `BUILD_BUILDNUMBER` environment variable).  Ensure that the build number being used contains a proper SemVer e.g. `1.0.$(Rev:r)`. When using **byBuildNumber**, the task will extract the dotted version, `1.2.3.4` from the build number string, and use only that portion.  The rest of the string will be dropped.  If you want to use the build number as is, you can use **byEnvVar** as described above, and set **versionEnvVar** to `BUILD_BUILDNUMBER`.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Restore

Restore all your solutions with packages from a selected feed.

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

:::moniker range="<=azure-pipelines"

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