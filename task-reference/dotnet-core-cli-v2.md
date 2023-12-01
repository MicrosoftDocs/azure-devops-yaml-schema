---
title: DotNetCoreCLI@2 - .NET Core v2 task
description: Build, test, package, or publish a dotnet application, or run a custom dotnet command.
ms.date: 11/30/2023
monikerRange: "<=azure-pipelines"
---

# DotNetCoreCLI@2 - .NET Core v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Build, test, package, or publish a dotnet application, or run a custom dotnet command.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Build, test, package, or publish a dotnet application, or run a custom dotnet command. For package commands, supports NuGet.org and authenticated feeds like Package Management and MyGet.

> [!IMPORTANT]
> The [NuGet Authenticate](nuget-authenticate-v1.md) task is the new recommended way to authenticate with Azure Artifacts and other NuGet repositories. The `restore` and `push` commands of this .NET Core CLI task no longer take new features and only critical bugs are addressed. See remarks for details.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# .NET Core v2
# Build, test, package, or publish a dotnet application, or run a custom dotnet command.
- task: DotNetCoreCLI@2
  inputs:
    command: 'build' # 'build' | 'push' | 'pack' | 'publish' | 'restore' | 'run' | 'test' | 'custom'. Required. Command. Default: build.
    #publishWebProjects: true # boolean. Optional. Use when command = publish. Publish web projects. Default: true.
    #projects: # string. Optional. Use when command = build || command = restore || command = run || command = test || command = custom || publishWebProjects = false. Path to project(s). 
    #custom: # string. Required when command = custom. Custom command. 
    #arguments: # string. Optional. Use when command = build || command = publish || command = run || command = test || command = custom. Arguments. 
    #restoreArguments: # string. Optional. Use when command = restore. Arguments. 
    #publishTestResults: true # boolean. Optional. Use when command = test. Publish test results and code coverage. Default: true.
    #testRunTitle: # string. Optional. Use when command = test. Test run title. 
    #zipAfterPublish: true # boolean. Optional. Use when command = publish. Zip published projects. Default: true.
    #modifyOutputPath: true # boolean. Optional. Use when command = publish. Add project's folder name to publish path. Default: true.
    #packagesToPush: '$(Build.ArtifactStagingDirectory)/*.nupkg' # string. Alias: searchPatternPush. Required when command = push. Path to NuGet package(s) to publish. Default: $(Build.ArtifactStagingDirectory)/*.nupkg.
    #nuGetFeedType: 'internal' # 'internal' | 'external'. Required when command = push. Target feed location. Default: internal.
    #publishVstsFeed: # string. Alias: feedPublish. Required when command = push && nuGetFeedType = internal. Target feed. 
    #publishFeedCredentials: # string. Alias: externalEndpoint. Required when command = push && nuGetFeedType = external. NuGet server. 
    #packagesToPack: '**/*.csproj' # string. Alias: searchPatternPack. Required when command = pack. Path to csproj or nuspec file(s) to pack. Default: **/*.csproj.
    #configuration: '$(BuildConfiguration)' # string. Alias: configurationToPack. Optional. Use when command = pack. Configuration to Package. Default: $(BuildConfiguration).
    #packDirectory: '$(Build.ArtifactStagingDirectory)' # string. Alias: outputDir. Optional. Use when command = pack. Package Folder. Default: $(Build.ArtifactStagingDirectory).
    #nobuild: false # boolean. Optional. Use when command = pack. Do not build. Default: false.
    #includesymbols: false # boolean. Optional. Use when command = pack. Include Symbols. Default: false.
    #includesource: false # boolean. Optional. Use when command = pack. Include Source. Default: false.
  # Feeds and authentication
    #feedsToUse: 'select' # 'select' | 'config'. Alias: selectOrConfig. Required when command = restore. Feeds to use. Default: select.
    #vstsFeed: # string. Alias: feedRestore. Optional. Use when selectOrConfig = select && command = restore. Use packages from this Azure Artifacts feed. 
    #includeNuGetOrg: true # boolean. Optional. Use when selectOrConfig = select && command = restore. Use packages from NuGet.org. Default: true.
    #nugetConfigPath: # string. Optional. Use when selectOrConfig = config && command = restore. Path to NuGet.config. 
    #externalFeedCredentials: # string. Alias: externalEndpoints. Optional. Use when selectOrConfig = config && command = restore. Credentials for feeds outside this organization/collection. 
  # Advanced
    #noCache: false # boolean. Optional. Use when command = restore. Disable local cache. Default: false.
    #restoreDirectory: # string. Alias: packagesDirectory. Optional. Use when command = restore. Destination directory. 
    #verbosityRestore: 'Detailed' # '-' | 'Quiet' | 'Minimal' | 'Normal' | 'Detailed' | 'Diagnostic'. Optional. Use when command = restore. Verbosity. Default: Detailed.
  # Advanced
    #publishPackageMetadata: true # boolean. Optional. Use when command = push && nuGetFeedType = internal && command = push. Publish pipeline metadata. Default: true.
  # Pack options
    #versioningScheme: 'off' # 'off' | 'byPrereleaseNumber' | 'byEnvVar' | 'byBuildNumber'. Required when command = pack. Automatic package versioning. Default: off.
    #versionEnvVar: # string. Required when versioningScheme = byEnvVar && command = pack. Environment variable. 
    #majorVersion: '1' # string. Alias: requestedMajorVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Major. Default: 1.
    #minorVersion: '0' # string. Alias: requestedMinorVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Minor. Default: 0.
    #patchVersion: '0' # string. Alias: requestedPatchVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Patch. Default: 0.
  # Advanced
    #buildProperties: # string. Optional. Use when command = pack. Additional build properties. 
    #verbosityPack: 'Detailed' # '-' | 'Quiet' | 'Minimal' | 'Normal' | 'Detailed' | 'Diagnostic'. Optional. Use when command = pack. Verbosity. Default: Detailed.
  # Advanced
    #workingDirectory: # string. Optional. Use when command != restore && command != push && command != pack && command != pack && command != push && command != restore. Working directory.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# .NET Core v2
# Build, test, package, or publish a dotnet application, or run a custom dotnet command.
- task: DotNetCoreCLI@2
  inputs:
    command: 'build' # 'build' | 'push' | 'pack' | 'publish' | 'restore' | 'run' | 'test' | 'custom'. Required. Command. Default: build.
    #publishWebProjects: true # boolean. Optional. Use when command = publish. Publish Web Projects. Default: true.
    #projects: # string. Optional. Use when command = build || command = restore || command = run || command = test || command = custom || publishWebProjects = false. Path to project(s). 
    #custom: # string. Required when command = custom. Custom command. 
    #arguments: # string. Optional. Use when command = build || command = publish || command = run || command = test || command = custom. Arguments. 
    #publishTestResults: true # boolean. Optional. Use when command = test. Publish test results and code coverage. Default: true.
    #testRunTitle: # string. Optional. Use when command = test. Test run title. 
    #zipAfterPublish: true # boolean. Optional. Use when command = publish. Zip Published Projects. Default: true.
    #modifyOutputPath: true # boolean. Optional. Use when command = publish. Add project name to publish path. Default: true.
    #packagesToPush: '$(Build.ArtifactStagingDirectory)/*.nupkg' # string. Alias: searchPatternPush. Required when command = push. Path to NuGet package(s) to publish. Default: $(Build.ArtifactStagingDirectory)/*.nupkg.
    #nuGetFeedType: 'internal' # 'internal' | 'external'. Required when command = push. Target feed location. Default: internal.
    #publishVstsFeed: # string. Alias: feedPublish. Required when command = push && nuGetFeedType = internal. Target feed. 
    #publishFeedCredentials: # string. Alias: externalEndpoint. Required when command = push && nuGetFeedType = external. NuGet server. 
    #packagesToPack: '**/*.csproj' # string. Alias: searchPatternPack. Required when command = pack. Path to csproj or nuspec file(s) to pack. Default: **/*.csproj.
    #configuration: '$(BuildConfiguration)' # string. Alias: configurationToPack. Optional. Use when command = pack. Configuration to Package. Default: $(BuildConfiguration).
    #packDirectory: '$(Build.ArtifactStagingDirectory)' # string. Alias: outputDir. Optional. Use when command = pack. Package Folder. Default: $(Build.ArtifactStagingDirectory).
    #nobuild: false # boolean. Optional. Use when command = pack. Do not build. Default: false.
    #includesymbols: false # boolean. Optional. Use when command = pack. Include Symbols. Default: false.
    #includesource: false # boolean. Optional. Use when command = pack. Include Source. Default: false.
  # Feeds and authentication
    #feedsToUse: 'select' # 'select' | 'config'. Alias: selectOrConfig. Required when command = restore. Feeds to use. Default: select.
    #vstsFeed: # string. Alias: feedRestore. Optional. Use when selectOrConfig = select && command = restore. Use packages from this Azure Artifacts feed. 
    #includeNuGetOrg: true # boolean. Optional. Use when selectOrConfig = select && command = restore. Use packages from NuGet.org. Default: true.
    #nugetConfigPath: # string. Optional. Use when selectOrConfig = config && command = restore. Path to NuGet.config. 
    #externalFeedCredentials: # string. Alias: externalEndpoints. Optional. Use when selectOrConfig = config && command = restore. Credentials for feeds outside this organization/collection. 
  # Advanced
    #noCache: false # boolean. Optional. Use when command = restore. Disable local cache. Default: false.
    #restoreDirectory: # string. Alias: packagesDirectory. Optional. Use when command = restore. Destination directory. 
    #verbosityRestore: 'Detailed' # '-' | 'Quiet' | 'Minimal' | 'Normal' | 'Detailed' | 'Diagnostic'. Optional. Use when command = restore. Verbosity. Default: Detailed.
  # Advanced
    #publishPackageMetadata: true # boolean. Optional. Use when command = push && nuGetFeedType = internal && command = push. Publish pipeline metadata. Default: true.
  # Pack options
    #versioningScheme: 'off' # 'off' | 'byPrereleaseNumber' | 'byEnvVar' | 'byBuildNumber'. Required when command = pack. Automatic package versioning. Default: off.
    #versionEnvVar: # string. Required when versioningScheme = byEnvVar && command = pack. Environment variable. 
    #majorVersion: '1' # string. Alias: requestedMajorVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Major. Default: 1.
    #minorVersion: '0' # string. Alias: requestedMinorVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Minor. Default: 0.
    #patchVersion: '0' # string. Alias: requestedPatchVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Patch. Default: 0.
  # Advanced
    #buildProperties: # string. Optional. Use when command = pack. Additional build properties. 
    #verbosityPack: 'Detailed' # '-' | 'Quiet' | 'Minimal' | 'Normal' | 'Detailed' | 'Diagnostic'. Optional. Use when command = pack. Verbosity. Default: Detailed.
  # Advanced
    #workingDirectory: # string. Optional. Use when command != pack && command != push && command != restore. Working Directory.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# .NET Core v2
# Build, test, package, or publish a dotnet application, or run a custom dotnet command. For package commands, supports NuGet.org and authenticated feeds like Package Management and MyGet.
- task: DotNetCoreCLI@2
  inputs:
    command: 'build' # 'build' | 'push' | 'pack' | 'publish' | 'restore' | 'run' | 'test' | 'custom'. Required. Command. Default: build.
    #publishWebProjects: true # boolean. Optional. Use when command = publish. Publish Web Projects. Default: true.
    #projects: # string. Optional. Use when command = build || command = restore || command = run || command = test || command = custom || publishWebProjects = false. Path to project(s). 
    #custom: # string. Required when command = custom. Custom command. 
    #arguments: # string. Optional. Use when command = build || command = publish || command = run || command = test || command = custom. Arguments. 
    #publishTestResults: true # boolean. Optional. Use when command = test. Publish test results and code coverage. Default: true.
    #zipAfterPublish: true # boolean. Optional. Use when command = publish. Zip Published Projects. Default: true.
    #modifyOutputPath: true # boolean. Optional. Use when command = publish. Add project name to publish path. Default: true.
    #packagesToPush: '$(Build.ArtifactStagingDirectory)/*.nupkg' # string. Alias: searchPatternPush. Required when command = push. Path to NuGet package(s) to publish. Default: $(Build.ArtifactStagingDirectory)/*.nupkg.
    #nuGetFeedType: 'internal' # 'internal' | 'external'. Required when command = push. Target feed location. Default: internal.
    #publishVstsFeed: # string. Alias: feedPublish. Required when command = push && nuGetFeedType = internal. Target feed. 
    #publishFeedCredentials: # string. Alias: externalEndpoint. Required when command = push && nuGetFeedType = external. NuGet server. 
    #packagesToPack: '**/*.csproj' # string. Alias: searchPatternPack. Required when command = pack. Path to csproj or nuspec file(s) to pack. Default: **/*.csproj.
    #configuration: '$(BuildConfiguration)' # string. Alias: configurationToPack. Optional. Use when command = pack. Configuration to Package. Default: $(BuildConfiguration).
    #packDirectory: '$(Build.ArtifactStagingDirectory)' # string. Alias: outputDir. Optional. Use when command = pack. Package Folder. Default: $(Build.ArtifactStagingDirectory).
    #nobuild: false # boolean. Optional. Use when command = pack. Do not build. Default: false.
  # Feeds and authentication
    #feedsToUse: 'select' # 'select' | 'config'. Alias: selectOrConfig. Required when command = restore. Feeds to use. Default: select.
    #vstsFeed: # string. Alias: feedRestore. Optional. Use when selectOrConfig = select && command = restore. Use packages from this Azure Artifacts/TFS feed. 
    #includeNuGetOrg: true # boolean. Optional. Use when selectOrConfig = select && command = restore. Use packages from NuGet.org. Default: true.
    #nugetConfigPath: # string. Optional. Use when selectOrConfig = config && command = restore. Path to NuGet.config. 
    #externalFeedCredentials: # string. Alias: externalEndpoints. Optional. Use when selectOrConfig = config && command = restore. Credentials for feeds outside this organization/collection. 
  # Advanced
    #noCache: false # boolean. Optional. Use when command = restore. Disable local cache. Default: false.
    #restoreDirectory: # string. Alias: packagesDirectory. Optional. Use when command = restore. Destination directory. 
    #verbosityRestore: 'Detailed' # '-' | 'Quiet' | 'Minimal' | 'Normal' | 'Detailed' | 'Diagnostic'. Optional. Use when command = restore. Verbosity. Default: Detailed.
  # Pack options
    #versioningScheme: 'off' # 'off' | 'byPrereleaseNumber' | 'byEnvVar' | 'byBuildNumber'. Required when command = pack. Automatic package versioning. Default: off.
    #versionEnvVar: # string. Required when versioningScheme = byEnvVar && command = pack. Environment variable. 
    #majorVersion: '1' # string. Alias: requestedMajorVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Major. Default: 1.
    #minorVersion: '0' # string. Alias: requestedMinorVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Minor. Default: 0.
    #patchVersion: '0' # string. Alias: requestedPatchVersion. Required when versioningScheme = byPrereleaseNumber && command = pack. Patch. Default: 0.
  # Advanced
    #buildProperties: # string. Optional. Use when command = pack. Additional build properties. 
    #verbosityPack: 'Detailed' # '-' | 'Quiet' | 'Minimal' | 'Normal' | 'Detailed' | 'Diagnostic'. Optional. Use when command = pack. Verbosity. Default: Detailed.
  # Advanced
    #workingDirectory: # string. Optional. Use when command != pack && command != push && command != restore. Working Directory.
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
`string`. Required. Allowed values: `build`, `push` (nuget push), `pack`, `publish`, `restore`, `run`, `test`, `custom`. Default value: `build`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The dotnet command to run. Specify `custom` to add arguments or use a command not listed here.

> [!IMPORTANT]
> The [NuGet Authenticate](nuget-authenticate-v1.md) task is the new recommended way to authenticate with Azure Artifacts and other NuGet repositories. The `restore` and `push` commands of this .NET Core CLI task no longer take new features and only critical bugs are addressed. See remarks for details.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishWebProjects"::: -->
:::moniker range=">=azure-pipelines-2020"

**`publishWebProjects`** - **Publish web projects**<br>
`boolean`. Optional. Use when `command = publish`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this input is set to `true`, the `projects` property value is skipped, and the task tries to find the web projects in the repository and run the publish command on them. Web projects are identified by the presence of either a `web.config` file or a `wwwroot` folder in the directory. In the absence of a `web.config` file or a `wwwroot` folder, projects that use a web SDK, like `Microsoft.NET.Sdk.Web`, are selected.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`publishWebProjects`** - **Publish Web Projects**<br>
`boolean`. Optional. Use when `command = publish`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this input is set to `true`, the `projects` property value is skipped, and the task tries to find the web projects in the repository and run the publish command on them. Web projects are identified by the presence of either a `web.config` file or a `wwwroot` folder in the directory. In the absence of a `web.config` file or a `wwwroot` folder, projects that use a web SDK, like `Microsoft.NET.Sdk.Web`, are selected.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="projects"::: -->
:::moniker range="<=azure-pipelines"

**`projects`** - **Path to project(s)**<br>
`string`. Optional. Use when `command = build || command = restore || command = run || command = test || command = custom || publishWebProjects = false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the `.csproj` file(s) to use. You can use wildcards (e.g. `**/*.csproj` for all `.csproj` files in all subfolders). For more information, see the [file matching patterns reference](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="custom"::: -->
:::moniker range="<=azure-pipelines"

**`custom`** - **Custom command**<br>
`string`. Required when `command = custom`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The command to pass to `dotnet.exe` for execution. For a full list of available commands, see the [dotnet CLI documentation](/dotnet/core/tools/#cli-commands).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **Arguments**<br>
`string`. Optional. Use when `command = build || command = publish || command = run || command = test || command = custom`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the arguments for the selected command. For example, build configuration, output folder, and runtime. The arguments depend on the command selected.

This input currently only accepts arguments for `build`, `publish`, `run`, `test`, and `custom`. If you would like to add arguments for a command not listed, use `custom`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restoreArguments"::: -->
:::moniker range=">=azure-pipelines-2020"

**`restoreArguments`** - **Arguments**<br>
`string`. Optional. Use when `command = restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Writes the additional arguments to be passed to the `restore` command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishTestResults"::: -->
:::moniker range=">=azure-pipelines-2019"

**`publishTestResults`** - **Publish test results and code coverage**<br>
`boolean`. Optional. Use when `command = test`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enabling this option will generate a `test results` TRX file in `$(Agent.TempDirectory)`, and the results will be published to the server.

This option appends `--logger trx --results-directory $(Agent.TempDirectory)` to the command line arguments.


Code coverage can be collected by adding the `--collect "Code coverage"` option to the command line arguments.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`publishTestResults`** - **Publish test results**<br>
`boolean`. Optional. Use when `command = test`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enabling this option will generate a `test results` TRX file in `$(Agent.TempDirectory)`, and the results will be published to the server. 

This option appends the `--logger trx --results-directory $(Agent.TempDirectory)` to the command line arguments.


Code coverage can be collected by adding the `--collect "Code coverage"` option to the command line arguments.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`testRunTitle`** - **Test run title**<br>
`string`. Optional. Use when `command = test`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a name for the test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="zipAfterPublish"::: -->
:::moniker range=">=azure-pipelines-2020"

**`zipAfterPublish`** - **Zip published projects**<br>
`boolean`. Optional. Use when `command = publish`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this input is set to `true`, folders created by the publish command will be zipped and deleted.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`zipAfterPublish`** - **Zip Published Projects**<br>
`boolean`. Optional. Use when `command = publish`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this input is set to `true`, the folder created by the publish command will be zipped and deleted.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="modifyOutputPath"::: -->
:::moniker range=">=azure-pipelines-2020"

**`modifyOutputPath`** - **Add project's folder name to publish path**<br>
`boolean`. Optional. Use when `command = publish`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this input is set to `true`, folders created by the publish command will have the project file name prefixed to their folder names when the output path is specified explicitly in arguments. This is useful if you want to publish multiple projects to the same folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`modifyOutputPath`** - **Add project name to publish path**<br>
`boolean`. Optional. Use when `command = publish`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this input is set to `true`, folders created by the publish command will have the project file name prefixed to their folder names when the output path is specified explicitly in arguments. This is useful if you want to publish multiple projects to the same folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feedsToUse"::: -->
:::moniker range="<=azure-pipelines"

**`feedsToUse`** - **Feeds to use**<br>
Input alias: `selectOrConfig`. `string`. Required when `command = restore`. Allowed values: `select` (Feed(s) I select here), `config` (Feeds in my NuGet.config). Default value: `select`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You can either select a feed from Azure Artifacts and/or `NuGet.org` here, or you can commit a `nuget.config` file to your source code repository and set its path using the `nugetConfigPath` input.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstsFeed"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`vstsFeed`** - **Use packages from this Azure Artifacts feed**<br>
Input alias: `feedRestore`. `string`. Optional. Use when `selectOrConfig = select && command = restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes the selected feed in the generated `NuGet.config`. You must have Package Management installed and licensed to select a feed here. `projectName`/`feedName` are used for project-scoped feeds. Only `FeedName` is used for organization-scoped feeds. Note: This is not supported for the test command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`vstsFeed`** - **Use packages from this Azure Artifacts/TFS feed**<br>
Input alias: `feedRestore`. `string`. Optional. Use when `selectOrConfig = select && command = restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes the selected feed in the generated `NuGet.config`. You must have Package Management installed and licensed to select a feed here. `projectName`/`feedName` are used for for project-scoped feeds. Only `FeedName` is used for organization-scoped feeds. Note: This is not supported for the test command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`vstsFeed`** - **Use packages from this VSTS/TFS feed**<br>
Input alias: `feedRestore`. `string`. Optional. Use when `selectOrConfig = select && command = restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes the selected feed in the generated `NuGet.config`. You must have Package Management installed and licensed to select a feed here.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeNuGetOrg"::: -->
:::moniker range="<=azure-pipelines"

**`includeNuGetOrg`** - **Use packages from NuGet.org**<br>
`boolean`. Optional. Use when `selectOrConfig = select && command = restore`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes `NuGet.org` in the generated `NuGet.config`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nugetConfigPath"::: -->
:::moniker range="<=azure-pipelines"

**`nugetConfigPath`** - **Path to NuGet.config**<br>
`string`. Optional. Use when `selectOrConfig = config && command = restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The `NuGet.config` in your repository that specifies the feeds from which to restore packages.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="externalFeedCredentials"::: -->
:::moniker range=">=azure-pipelines-2019"

**`externalFeedCredentials`** - **Credentials for feeds outside this organization/collection**<br>
Input alias: `externalEndpoints`. `string`. Optional. Use when `selectOrConfig = config && command = restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The credentials to use for external registries located in the selected `NuGet.config`. For feeds in this organization/collection, leave this input blank; the build's credentials are used automatically.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`externalFeedCredentials`** - **Credentials for feeds outside this account/collection**<br>
Input alias: `externalEndpoints`. `string`. Optional. Use when `selectOrConfig = config && command = restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The credentials to use for external registries located in the selected `NuGet.config`. For feeds in this organization/collection, leave this input blank; the build's credentials are used automatically.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="noCache"::: -->
:::moniker range="<=azure-pipelines"

**`noCache`** - **Disable local cache**<br>
`boolean`. Optional. Use when `command = restore`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prevents NuGet from using packages from local machine caches.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restoreDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`restoreDirectory`** - **Destination directory**<br>
Input alias: `packagesDirectory`. `string`. Optional. Use when `command = restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the folder in which packages are installed. If no folder is specified, packages are restored into the default NuGet package cache.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosityRestore"::: -->
:::moniker range="<=azure-pipelines"

**`verbosityRestore`** - **Verbosity**<br>
`string`. Optional. Use when `command = restore`. Allowed values: `-`, `Quiet`, `Minimal`, `Normal`, `Detailed`, `Diagnostic`. Default value: `Detailed`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the amount of detail displayed in the output for the `restore` command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagesToPush"::: -->
:::moniker range="<=azure-pipelines"

**`packagesToPush`** - **Path to NuGet package(s) to publish**<br>
Input alias: `searchPatternPush`. `string`. Required when `command = push`. Default value: `$(Build.ArtifactStagingDirectory)/*.nupkg`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The pattern to match or path to `nupkg` files to be uploaded. Multiple patterns can be separated by a semicolon, and you can make a pattern negative by prefixing it with `!`. Example: `**/*.nupkg;!**/*.Tests.nupkg`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetFeedType"::: -->
:::moniker range=">=azure-pipelines-2019"

**`nuGetFeedType`** - **Target feed location**<br>
`string`. Required when `command = push`. Allowed values: `internal` (This organization/collection), `external` (External NuGet server (including other organizations/collections)). Default value: `internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether the target feed is internal or external.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`nuGetFeedType`** - **Target feed location**<br>
`string`. Required when `command = push`. Allowed values: `internal` (This account/collection), `external` (External NuGet server (including other accounts/collections)). Default value: `internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether the target feed is internal or external.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishVstsFeed"::: -->
:::moniker range="<=azure-pipelines"

**`publishVstsFeed`** - **Target feed**<br>
Input alias: `feedPublish`. `string`. Required when `command = push && nuGetFeedType = internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a feed hosted in this organization. You must have Package Management installed and licensed to select a feed here.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishPackageMetadata"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`publishPackageMetadata`** - **Publish pipeline metadata**<br>
`boolean`. Optional. Use when `command = push && nuGetFeedType = internal && command = push`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Associates this build/release pipeline's metadata (run #, source code information) with the package.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishFeedCredentials"::: -->
:::moniker range="<=azure-pipelines"

**`publishFeedCredentials`** - **NuGet server**<br>
Input alias: `externalEndpoint`. `string`. Required when `command = push && nuGetFeedType = external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The NuGet [service connection](/azure/devops/pipelines/library/service-endpoints) that contains the external NuGet server's credentials.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagesToPack"::: -->
:::moniker range="<=azure-pipelines"

**`packagesToPack`** - **Path to csproj or nuspec file(s) to pack**<br>
Input alias: `searchPatternPack`. `string`. Required when `command = pack`. Default value: `**/*.csproj`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The pattern to search for `.csproj` or `.nuspec` files to pack.

You can separate multiple patterns with a semicolon, and you can make a pattern negative by prefixing it with `!`. Example: `**/*.csproj;!**/*.Tests.csproj`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration to Package**<br>
Input alias: `configurationToPack`. `string`. Optional. Use when `command = pack`. Default value: `$(BuildConfiguration)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When using a `.csproj` file, this input specifies the configuration to package.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`packDirectory`** - **Package Folder**<br>
Input alias: `outputDir`. `string`. Optional. Use when `command = pack`. Default value: `$(Build.ArtifactStagingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The folder where packages will be created. If this folder is empty, packages will be created alongside the `csproj` file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nobuild"::: -->
:::moniker range="<=azure-pipelines"

**`nobuild`** - **Do not build**<br>
`boolean`. Optional. Use when `command = pack`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies that the task will not build the project before packing. This task corresponds to the `--no-build` parameter of the `build` command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includesymbols"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`includesymbols`** - **Include Symbols**<br>
`boolean`. Optional. Use when `command = pack`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Creates symbol NuGet packages. This task corresponds to the `--include-symbols` command line parameter.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includesource"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`includesource`** - **Include Source**<br>
`boolean`. Optional. Use when `command = pack`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes source code in the package. This task corresponds to the `--include-source` command line parameter.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versioningScheme"::: -->
:::moniker range="<=azure-pipelines"

**`versioningScheme`** - **Automatic package versioning**<br>
`string`. Required when `command = pack`. Allowed values: `off`, `byPrereleaseNumber` (Use the date and time), `byEnvVar` (Use an environment variable), `byBuildNumber` (Use the build number). Default value: `off`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This task cannot be used with included referenced projects. If you choose `Use the date and time`, this will generate a [SemVer](http://semver.org/spec/v1.0.0.html)-compliant version formatted as `X.Y.Z-ci-datetime` where you choose `X`, `Y`, and `Z`.

If you choose `Use an environment variable`, you must select an environment variable and ensure it contains the version number you want to use.

If you choose `Use the build number`, this will use the build number to version your package. **Note:** Under `Options`, set the build number format to [`$(BuildDefinitionName)_$(Year:yyyy).$(Month).$(DayOfMonth)$(Rev:.r)`](https://go.microsoft.com/fwlink/?LinkID=627416).
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
Input alias: `requestedMajorVersion`. `string`. Required when `versioningScheme = byPrereleaseNumber && command = pack`. Default value: `1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The `X` in version [X.Y.Z](http://semver.org/spec/v1.0.0.html).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="minorVersion"::: -->
:::moniker range="<=azure-pipelines"

**`minorVersion`** - **Minor**<br>
Input alias: `requestedMinorVersion`. `string`. Required when `versioningScheme = byPrereleaseNumber && command = pack`. Default value: `0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The `Y` in version [X.Y.Z](http://semver.org/spec/v1.0.0.html).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="patchVersion"::: -->
:::moniker range="<=azure-pipelines"

**`patchVersion`** - **Patch**<br>
Input alias: `requestedPatchVersion`. `string`. Required when `versioningScheme = byPrereleaseNumber && command = pack`. Default value: `0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The `Z` in version [X.Y.Z](http://semver.org/spec/v1.0.0.html).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildProperties"::: -->
:::moniker range="<=azure-pipelines"

**`buildProperties`** - **Additional build properties**<br>
`string`. Optional. Use when `command = pack`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a list of `token = value` pairs, separated by semicolons, where each occurrence of `$token$` in the `.nuspec` file will be replaced with the given value. Values can be strings in quotation marks.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosityPack"::: -->
:::moniker range="<=azure-pipelines"

**`verbosityPack`** - **Verbosity**<br>
`string`. Optional. Use when `command = pack`. Allowed values: `-`, `Quiet`, `Minimal`, `Normal`, `Detailed`, `Diagnostic`. Default value: `Detailed`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the amount of detail displayed in the output for the `pack` command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2020"

**`workingDirectory`** - **Working directory**<br>
`string`. Optional. Use when `command != restore && command != push && command != pack && command != pack && command != push && command != restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The current working directory where the script is run. `Empty` is the root of the repo (build) or artifacts (release), which is `$(System.DefaultWorkingDirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`workingDirectory`** - **Working Directory**<br>
`string`. Optional. Use when `command != pack && command != push && command != restore`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The current working directory where the script is run. `Empty` is the root of the repo (build) or artifacts (release), which is `$(System.DefaultWorkingDirectory)`.
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
> The [NuGet Authenticate](nuget-authenticate-v1.md) task is the new recommended way to authenticate with Azure Artifacts and other NuGet repositories. The `restore` and `push` commands of this .NET Core CLI task no longer take new features and only critical bugs are addressed.

### Why is my build, publish, or test step failing to restore packages?

Most `dotnet` commands, including `build`, `publish`, and `test` include an implicit `restore` step. This will fail against authenticated feeds, even if you ran a successful `dotnet restore` in an earlier step, because the earlier step will have cleaned up the credentials it used.

To fix this issue, add the `--no-restore` flag to the `Arguments` textbox.

In addition, the `test` command does not recognize the `feedRestore` or `vstsFeed` arguments, and feeds specified in this manner will not be included in the generated `NuGet.config` file when the implicit `restore` step runs.  It's recommended that an explicit `dotnet restore` step be used to restore packages.  The `restore` command respects the `feedRestore` and `vstsFeed` arguments.

### Why am I getting NU1507 warnings with [Package Source Mapping](/nuget/consume-packages/package-source-mapping) although when building on my machine it has no warnings?

The the various commands that do a NuGet restore or access a NuGet feed build a special temporary `NuGet.config` file that add NuGet authentication for azure artifacts NuGet feeds. The way this is done is in conflict with the schema that Package Source Mapping uses to map the packages to the sources and breaks the Package Source Mappin configuration in the `NuGet.config` file in your repository.
To work around this conflict you can use the [NuGet Authenticate](nuget-authenticate-v1.md) task to authenticate and afterwards the custom command to invoke the desired dotnet command without the `NuGet.config` modification.

```YAML
# Authenticate Azure DevOps NuGet feed
- task: NuGetAuthenticate@1
  displayName: 'Authenticate Azure DevOps NuGet feed'

# Restore project
- task: DotNetCoreCLI@2
  inputs:
    command: 'custom'
    custom: 'restore'

# Build project
- task: DotNetCoreCLI@2
  inputs:
    command: 'custom'
    custom: 'build'
    arguments: '--no-restore'
```

### Why should I check in a NuGet.config?

Checking a `NuGet.config` into source control ensures that a key piece of information needed to build your project&mdash;the location of its packages&mdash;is available to every developer that checks out your code.

However, for situations where a team of developers works on a large range of projects, it's also possible to add an Azure Artifacts feed to the global `NuGet.config` on each developer's machine. In these situations, using the `Feeds I select here` option in the NuGet task replicates this configuration.

### Troubleshooting

#### Project using Entity Framework has stopped working on Hosted Agents

.NET Core does not have Entity Framework(EF) built-in. You will have to either install EF before beginning execution or add `global.json` to the project with required .NET Core SDK version. This will ensure that correct SDK is used to build EF project. If the required version is not present on the machine, add the `UseDotNetV2` task to your pipeline to install the required version. For more information, see [Get the Entity Framework Core runtime](/ef/core/get-started/overview/install#get-the-entity-framework-core-runtime).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

* [Build examples](#build-examples)
* [Push examples](#push-examples)
* [Push examples](#push-examples)
* [Pack examples](#pack-examples)
* [Publish examples](#publish-examples)
* [Restore examples](#restore-examples)
* [Test examples](#test-examples)


### Build examples

#### Build a project

```YAML
# Build project
- task: DotNetCoreCLI@2
  inputs:
    command: 'build'
```

#### Build Multiple Projects

```YAML
# Build multiple projects
- task: DotNetCoreCLI@2
  inputs:
    command: 'build'
    projects: |
      src/proj1/proj1.csproj 
      src/proj2/proj2.csproj 
      src/other/other.sln    # Pass a solution instead of a csproj.
```

### Push examples

#### Push NuGet packages to internal feed

```YAML
# Push non test NuGet packages from a build to internal organization Feed
- task: DotNetCoreCLI@2
  inputs:
    command: 'push'
    searchPatternPush: '$(Build.ArtifactStagingDirectory)/*.nupkg;!$(Build.ArtifactStagingDirectory)/*.Tests.nupkg'
    feedPublish: 'FabrikamFeed'
```

#### Push NuGet packages to external feed

```YAML
# Push all NuGet packages from a build to external Feed
- task: DotNetCoreCLI@2
  inputs:
    command: 'push'
    nugetFeedType: 'external'
    externalEndPoint: 'MyNuGetServiceConnection'
```

### Pack examples

#### Pack a NuGetPackage to a specific output directory

```YAML
# Pack a NuGet package to a test directory
- task: DotNetCoreCLI@2
  inputs: 
    command: 'pack'
    outputDir: '$(Build.ArtifactStagingDirectory)/TestDir'
```

#### Pack a Symbol Package

```YAML
# Pack a symbol package along with NuGet package
- task: DotNetCoreCLI@2
  inputs: 
    command: 'pack'
    includesymbols: true
```

### Publish examples

#### Publish projects to specified folder

```YAML
# Publish projects to specified folder.
- task: DotNetCoreCLI@2
  displayName: 'dotnet publish'
  inputs:
    command: 'publish'
    publishWebProjects: false
    projects: '**/*.csproj'
    arguments: '-o $(Build.ArtifactStagingDirectory)/Output'
    zipAfterPublish: true
    modifyOutputPath: true
```
### Restore examples

```YAML
#Restore packages with the .NET Core CLI task
- task: DotNetCoreCLI@2
  displayName: 'dotnet restore'
  inputs:
    command: 'restore'
    feedsToUse: 'select'
    feedRestore: 'projectName/feedName'
    projects: '**/*.csproj'
    includeNuGetOrg: true
```

### Test examples

#### Run tests in your repository

```YAML
# Run tests and auto publish test results.
- task: DotNetCoreCLI@2
  inputs:
    command: 'test'
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Build |

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Build |

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.0.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
