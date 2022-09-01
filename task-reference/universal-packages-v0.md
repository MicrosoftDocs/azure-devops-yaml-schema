---
title: UniversalPackages@0 - Universal packages v0 task
description: Download or publish Universal Packages.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019"
---

# UniversalPackages@0 - Universal packages v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Download or publish Universal Packages.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Universal packages v0
# Download or publish Universal Packages.
- task: UniversalPackages@0
  inputs:
    command: 'download' # 'download' | 'publish'. Required. Command. Default: 'download'.
    downloadDirectory: '$(System.DefaultWorkingDirectory)' # string. Required when command = download. Destination directory. Default: '$(System.DefaultWorkingDirectory)'.
    #publishDirectory: '$(Build.ArtifactStagingDirectory)' # string. Required when command = publish. Path to file(s) to publish. Default: '$(Build.ArtifactStagingDirectory)'.
  # Feed & package details
    feedsToUse: 'internal' # 'internal' | 'external'. Required. Feed location. Default: 'internal'.
    #externalFeedCredentials: # string. Optional. Use when internalOrExternalDownload = external. organization/collection connection. 
    vstsFeed: # string. Required when internalOrExternalDownload = internal. Feed. 
    vstsFeedPackage: # string. Required when internalOrExternalDownload = internal. Package name. 
    vstsPackageVersion: # string. Required when internalOrExternalDownload = internal. Version. 
    #feedDownloadExternal: # string. Required when internalOrExternalDownload = external. Feed (or Project/Feed if the feed was created in a project). 
    #packageDownloadExternal: # string. Required when internalOrExternalDownload = external. Package name. 
    #versionDownloadExternal: # string. Required when internalOrExternalDownload = external. Version. 
  # Feed & package details
    feedsToUsePublish: 'internal' # 'internal' | 'external'. Required. Feed location. Default: 'internal'.
    #publishFeedCredentials: # string. Required when internalOrExternalPublish = external. organization/collection connection. 
    vstsFeedPublish: # string. Required when internalOrExternalPublish = internal. Destination Feed. 
    vstsFeedPackagePublish: # string. Required when internalOrExternalPublish = internal. Package name. 
    #feedPublishExternal: # string. Required when internalOrExternalPublish = external. Feed (or Project/Feed if the feed was created in a project). 
    #packagePublishExternal: # string. Required when internalOrExternalPublish = external. Package name. 
    versionOption: 'patch' # 'major' | 'minor' | 'patch' | 'custom'. Required. Version. Default: 'patch'.
    #versionPublish: # string. Required when versionPublishSelector = custom. Custom version. 
    #packagePublishDescription: # string. Description. 
  # Advanced
    #publishPackageMetadata: true # boolean. Optional. Use when command = publish && internalOrExternalPublish = internal. Publish pipeline metadata. Default: true.
    #verbosity: 'None' # 'None' | 'Trace' | 'Debug' | 'Information' | 'Warning' | 'Error' | 'Critical'. Verbosity. Default: 'None'.
  # Output
    #publishedPackageVar: # string. Package Output Variable.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Universal packages v0
# Download or publish Universal Packages.
- task: UniversalPackages@0
  inputs:
    command: 'download' # 'download' | 'publish'. Required. Command. Default: 'download'.
    downloadDirectory: '$(System.DefaultWorkingDirectory)' # string. Required when command = download. Destination directory. Default: '$(System.DefaultWorkingDirectory)'.
    #publishDirectory: '$(Build.ArtifactStagingDirectory)' # string. Required when command = publish. Path to file(s) to publish. Default: '$(Build.ArtifactStagingDirectory)'.
  # Feed & package details
    feedsToUse: 'internal' # 'internal' | 'external'. Required. Feed location. Default: 'internal'.
    #externalFeedCredentials: # string. Optional. Use when internalOrExternalDownload = external. organization/collection connection. 
    vstsFeed: # string. Required when internalOrExternalDownload = internal. Feed. 
    vstsFeedPackage: # string. Required when internalOrExternalDownload = internal. Package name. 
    vstsPackageVersion: # string. Required when internalOrExternalDownload = internal. Version. 
    #feedDownloadExternal: # string. Required when internalOrExternalDownload = external. Feed. 
    #packageDownloadExternal: # string. Required when internalOrExternalDownload = external. Package name. 
    #versionDownloadExternal: # string. Required when internalOrExternalDownload = external. Version. 
  # Feed & package details
    feedsToUsePublish: 'internal' # 'internal' | 'external'. Required. Feed location. Default: 'internal'.
    #publishFeedCredentials: # string. Required when internalOrExternalPublish = external. organization/collection connection. 
    vstsFeedPublish: # string. Required when internalOrExternalPublish = internal. Destination Feed. 
    vstsFeedPackagePublish: # string. Required when internalOrExternalPublish = internal. Package name. 
    #feedPublishExternal: # string. Required when internalOrExternalPublish = external. Feed. 
    #packagePublishExternal: # string. Required when internalOrExternalPublish = external. Package name. 
    versionOption: 'patch' # 'major' | 'minor' | 'patch' | 'custom'. Required. Version. Default: 'patch'.
    #versionPublish: # string. Required when versionPublishSelector = custom. Custom version. 
    #packagePublishDescription: # string. Description. 
  # Advanced
    #publishPackageMetadata: true # boolean. Optional. Use when command = publish && internalOrExternalPublish = internal. Publish pipeline metadata. Default: true.
    #verbosity: 'None' # 'None' | 'Trace' | 'Debug' | 'Information' | 'Warning' | 'Error' | 'Critical'. Verbosity. Default: 'None'.
  # Output
    #publishedPackageVar: # string. Package Output Variable.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Universal Packages v0
# Download or publish Universal Packages.
- task: UniversalPackages@0
  inputs:
    command: 'download' # 'download' | 'publish'. Required. Command. Default: 'download'.
    downloadDirectory: '$(System.DefaultWorkingDirectory)' # string. Required when command = download. Destination directory. Default: '$(System.DefaultWorkingDirectory)'.
    #publishDirectory: '$(Build.ArtifactStagingDirectory)' # string. Required when command = publish. Path to file(s) to publish. Default: '$(Build.ArtifactStagingDirectory)'.
  # Feed & package details
    feedsToUse: 'internal' # 'internal' | 'external'. Required. Feed location. Default: 'internal'.
    #externalFeedCredentials: # string. Optional. Use when internalOrExternalDownload = external. Account/collection connection. 
    vstsFeed: # string. Required when internalOrExternalDownload = internal. Feed. 
    vstsFeedPackage: # string. Required when internalOrExternalDownload = internal. Package name. 
    vstsPackageVersion: # string. Required when internalOrExternalDownload = internal. Version. 
    #feedDownloadExternal: # string. Required when internalOrExternalDownload = external. Feed. 
    #packageDownloadExternal: # string. Required when internalOrExternalDownload = external. Package name. 
    #versionDownloadExternal: # string. Required when internalOrExternalDownload = external. Version. 
  # Feed & package details
    feedsToUsePublish: 'internal' # 'internal' | 'external'. Required. Feed location. Default: 'internal'.
    #publishFeedCredentials: # string. Required when internalOrExternalPublish = external. Account/collection connection. 
    vstsFeedPublish: # string. Required when internalOrExternalPublish = internal. Destination Feed. 
    vstsFeedPackagePublish: # string. Required when internalOrExternalPublish = internal. Package name. 
    #feedPublishExternal: # string. Required when internalOrExternalPublish = external. Feed. 
    #packagePublishExternal: # string. Required when internalOrExternalPublish = external. Package name. 
    versionOption: 'patch' # 'major' | 'minor' | 'patch' | 'custom'. Required. Version. Default: 'patch'.
    #versionPublish: # string. Required when versionPublishSelector = custom. Custom version. 
    #packagePublishDescription: # string. Description. 
  # Advanced
    #verbosity: 'None' # 'None' | 'Trace' | 'Debug' | 'Information' | 'Warning' | 'Error' | 'Critical'. Verbosity. Default: 'None'.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="command"::: -->
:::moniker range=">=azure-pipelines-2019"

**`command`** - **Command**<br>
Type: string. Required. Allowed values: 'download', 'publish'. Default value: 'download'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Universal Package command to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="downloadDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`downloadDirectory`** - **Destination directory**<br>
Type: string. Required when command = download. Default value: '$(System.DefaultWorkingDirectory)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Folder path where the package's contents will be downloaded.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feedsToUse"::: -->
:::moniker range=">=azure-pipelines-2019"

**`feedsToUse`** - **Feed location**<br>
Input alias: `internalOrExternalDownload`. Type: string. Required. Allowed values: 'internal', 'external'. Default value: 'internal'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You can either select a feed from this collection or any other collection in Azure Artifacts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="externalFeedCredentials"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`externalFeedCredentials`** - **organization/collection connection**<br>
Input alias: `externalEndpoint`. Type: string. Optional. Use when internalOrExternalDownload = external.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Credentials to use for external feeds.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`externalFeedCredentials`** - **Account/collection connection**<br>
Input alias: `externalEndpoint`. Type: string. Optional. Use when internalOrExternalDownload = external.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Credentials to use for external feeds.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstsFeed"::: -->
:::moniker range=">=azure-pipelines-2019"

**`vstsFeed`** - **Feed**<br>
Input alias: `feedListDownload`. Type: string. Required when internalOrExternalDownload = internal.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstsFeedPackage"::: -->
:::moniker range=">=azure-pipelines-2019"

**`vstsFeedPackage`** - **Package name**<br>
Input alias: `packageListDownload`. Type: string. Required when internalOrExternalDownload = internal.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstsPackageVersion"::: -->
:::moniker range=">=azure-pipelines-2019"

**`vstsPackageVersion`** - **Version**<br>
Input alias: `versionListDownload`. Type: string. Required when internalOrExternalDownload = internal.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the package version or use a variable containing the version to download.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feedDownloadExternal"::: -->
:::moniker range=">=azure-pipelines-2020"

**`feedDownloadExternal`** - **Feed (or Project/Feed if the feed was created in a project)**<br>
Type: string. Required when internalOrExternalDownload = external.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Feed name.

If the feed was created in a project, this should be Project/Feed where Project is project's name or ID and Feed is the feed's name. If not created in a project, this should be only the feed name.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

**`feedDownloadExternal`** - **Feed**<br>
Type: string. Required when internalOrExternalDownload = external.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Feed name.

If the feed was created in a project, this should be Project/Feed where Project is project's name or ID and Feed is the feed's name. If not created in a project, this should be only the feed name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageDownloadExternal"::: -->
:::moniker range=">=azure-pipelines-2019"

**`packageDownloadExternal`** - **Package name**<br>
Type: string. Required when internalOrExternalDownload = external.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Package name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionDownloadExternal"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionDownloadExternal`** - **Version**<br>
Type: string. Required when internalOrExternalDownload = external.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Package version to download.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`publishDirectory`** - **Path to file(s) to publish**<br>
Type: string. Required when command = publish. Default value: '$(Build.ArtifactStagingDirectory)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to list of files to be published.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feedsToUsePublish"::: -->
:::moniker range=">=azure-pipelines-2019"

**`feedsToUsePublish`** - **Feed location**<br>
Input alias: `internalOrExternalPublish`. Type: string. Required. Allowed values: 'internal', 'external'. Default value: 'internal'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You can either select a feed from this collection or any other collection in Azure Artifacts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishFeedCredentials"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`publishFeedCredentials`** - **organization/collection connection**<br>
Input alias: `externalEndpoints`. Type: string. Required when internalOrExternalPublish = external.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Credentials to use for external feeds.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`publishFeedCredentials`** - **Account/collection connection**<br>
Input alias: `externalEndpoints`. Type: string. Required when internalOrExternalPublish = external.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Credentials to use for external feeds.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstsFeedPublish"::: -->
:::moniker range=">=azure-pipelines-2019"

**`vstsFeedPublish`** - **Destination Feed**<br>
Input alias: `feedListPublish`. Type: string. Required when internalOrExternalPublish = internal.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishPackageMetadata"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`publishPackageMetadata`** - **Publish pipeline metadata**<br>
Type: boolean. Optional. Use when command = publish && internalOrExternalPublish = internal. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Associate this build/release pipeline’s metadata (run #, source code information) with the package.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstsFeedPackagePublish"::: -->
:::moniker range=">=azure-pipelines-2019"

**`vstsFeedPackagePublish`** - **Package name**<br>
Input alias: `packageListPublish`. Type: string. Required when internalOrExternalPublish = internal.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a package ID to publish or type a new package ID if you've never published a version of this package before. Package names must be lower case and can only use letters, numbers, and dashes(-).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feedPublishExternal"::: -->
:::moniker range=">=azure-pipelines-2020"

**`feedPublishExternal`** - **Feed (or Project/Feed if the feed was created in a project)**<br>
Type: string. Required when internalOrExternalPublish = external.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Feed name.

If the feed was created in a project, this should be Project/Feed where Project is project's name or ID and Feed is the feed's name. If not created in a project, this should be only the feed name.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

**`feedPublishExternal`** - **Feed**<br>
Type: string. Required when internalOrExternalPublish = external.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Feed name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagePublishExternal"::: -->
:::moniker range=">=azure-pipelines-2019"

**`packagePublishExternal`** - **Package name**<br>
Type: string. Required when internalOrExternalPublish = external.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Package name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionOption"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionOption`** - **Version**<br>
Input alias: `versionPublishSelector`. Type: string. Required. Allowed values: 'major', 'minor', 'patch', 'custom'. Default value: 'patch'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a version increment strategy, or select Custom to input your package version manually. For new packages, the first version will be 1.0.0 if you select "Next major", 0.1.0 if you select "Next minor", or 0.0.1 if you select "Next patch". See the [Semantic Versioning spec](https://semver.org/) for more information.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionPublish"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionPublish`** - **Custom version**<br>
Type: string. Required when versionPublishSelector = custom.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the custom package version.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagePublishDescription"::: -->
:::moniker range=">=azure-pipelines-2019"

**`packagePublishDescription`** - **Description**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Description of the contents of this package and/or the changes made in this version of the package.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosity"::: -->
:::moniker range=">=azure-pipelines-2019"

**`verbosity`** - **Verbosity**<br>
Type: string. Allowed values: 'None', 'Trace', 'Debug', 'Information', 'Warning', 'Error', 'Critical'. Default value: 'None'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the amount of detail displayed in the output.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishedPackageVar"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`publishedPackageVar`** - **Package Output Variable**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the variable that will contain the published package name and version.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019"

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

:::moniker range=">=azure-pipelines-2022"

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

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020.1"

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