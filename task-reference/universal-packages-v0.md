---
title: UniversalPackages@0 - Universal packages v0 task
description: Download or publish Universal Packages.
ms.date: 04/12/2023
monikerRange: ">=azure-pipelines-2019"
---

# UniversalPackages@0 - Universal packages v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to download, or package and publish Universal Packages.
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
    command: 'download' # 'download' | 'publish'. Required. Command. Default: download.
    downloadDirectory: '$(System.DefaultWorkingDirectory)' # string. Required when command = download. Destination directory. Default: $(System.DefaultWorkingDirectory).
    #publishDirectory: '$(Build.ArtifactStagingDirectory)' # string. Required when command = publish. Path to file(s) to publish. Default: $(Build.ArtifactStagingDirectory).
  # Feed & package details
    feedsToUse: 'internal' # 'internal' | 'external'. Alias: internalOrExternalDownload. Required. Feed location. Default: internal.
    #externalFeedCredentials: # string. Alias: externalEndpoint. Optional. Use when internalOrExternalDownload = external. organization/collection connection. 
    vstsFeed: # string. Alias: feedListDownload. Required when internalOrExternalDownload = internal. Feed. 
    vstsFeedPackage: # string. Alias: packageListDownload. Required when internalOrExternalDownload = internal. Package name. 
    vstsPackageVersion: # string. Alias: versionListDownload. Required when internalOrExternalDownload = internal. Version. 
    #feedDownloadExternal: # string. Required when internalOrExternalDownload = external. Feed (or Project/Feed if the feed was created in a project). 
    #packageDownloadExternal: # string. Required when internalOrExternalDownload = external. Package name. 
    #versionDownloadExternal: # string. Required when internalOrExternalDownload = external. Version. 
  # Feed & package details
    feedsToUsePublish: 'internal' # 'internal' | 'external'. Alias: internalOrExternalPublish. Required. Feed location. Default: internal.
    #publishFeedCredentials: # string. Alias: externalEndpoints. Required when internalOrExternalPublish = external. organization/collection connection. 
    vstsFeedPublish: # string. Alias: feedListPublish. Required when internalOrExternalPublish = internal. Destination Feed. 
    vstsFeedPackagePublish: # string. Alias: packageListPublish. Required when internalOrExternalPublish = internal. Package name. 
    #feedPublishExternal: # string. Required when internalOrExternalPublish = external. Feed (or Project/Feed if the feed was created in a project). 
    #packagePublishExternal: # string. Required when internalOrExternalPublish = external. Package name. 
    versionOption: 'patch' # 'major' | 'minor' | 'patch' | 'custom'. Alias: versionPublishSelector. Required. Version. Default: patch.
    #versionPublish: # string. Required when versionPublishSelector = custom. Custom version. 
    #packagePublishDescription: # string. Description. 
  # Advanced
    #publishPackageMetadata: true # boolean. Optional. Use when command = publish && internalOrExternalPublish = internal. Publish pipeline metadata. Default: true.
    #verbosity: 'None' # 'None' | 'Trace' | 'Debug' | 'Information' | 'Warning' | 'Error' | 'Critical'. Verbosity. Default: None.
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
    command: 'download' # 'download' | 'publish'. Required. Command. Default: download.
    downloadDirectory: '$(System.DefaultWorkingDirectory)' # string. Required when command = download. Destination directory. Default: $(System.DefaultWorkingDirectory).
    #publishDirectory: '$(Build.ArtifactStagingDirectory)' # string. Required when command = publish. Path to file(s) to publish. Default: $(Build.ArtifactStagingDirectory).
  # Feed & package details
    feedsToUse: 'internal' # 'internal' | 'external'. Alias: internalOrExternalDownload. Required. Feed location. Default: internal.
    #externalFeedCredentials: # string. Alias: externalEndpoint. Optional. Use when internalOrExternalDownload = external. organization/collection connection. 
    vstsFeed: # string. Alias: feedListDownload. Required when internalOrExternalDownload = internal. Feed. 
    vstsFeedPackage: # string. Alias: packageListDownload. Required when internalOrExternalDownload = internal. Package name. 
    vstsPackageVersion: # string. Alias: versionListDownload. Required when internalOrExternalDownload = internal. Version. 
    #feedDownloadExternal: # string. Required when internalOrExternalDownload = external. Feed. 
    #packageDownloadExternal: # string. Required when internalOrExternalDownload = external. Package name. 
    #versionDownloadExternal: # string. Required when internalOrExternalDownload = external. Version. 
  # Feed & package details
    feedsToUsePublish: 'internal' # 'internal' | 'external'. Alias: internalOrExternalPublish. Required. Feed location. Default: internal.
    #publishFeedCredentials: # string. Alias: externalEndpoints. Required when internalOrExternalPublish = external. organization/collection connection. 
    vstsFeedPublish: # string. Alias: feedListPublish. Required when internalOrExternalPublish = internal. Destination Feed. 
    vstsFeedPackagePublish: # string. Alias: packageListPublish. Required when internalOrExternalPublish = internal. Package name. 
    #feedPublishExternal: # string. Required when internalOrExternalPublish = external. Feed. 
    #packagePublishExternal: # string. Required when internalOrExternalPublish = external. Package name. 
    versionOption: 'patch' # 'major' | 'minor' | 'patch' | 'custom'. Alias: versionPublishSelector. Required. Version. Default: patch.
    #versionPublish: # string. Required when versionPublishSelector = custom. Custom version. 
    #packagePublishDescription: # string. Description. 
  # Advanced
    #publishPackageMetadata: true # boolean. Optional. Use when command = publish && internalOrExternalPublish = internal. Publish pipeline metadata. Default: true.
    #verbosity: 'None' # 'None' | 'Trace' | 'Debug' | 'Information' | 'Warning' | 'Error' | 'Critical'. Verbosity. Default: None.
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
    command: 'download' # 'download' | 'publish'. Required. Command. Default: download.
    downloadDirectory: '$(System.DefaultWorkingDirectory)' # string. Required when command = download. Destination directory. Default: $(System.DefaultWorkingDirectory).
    #publishDirectory: '$(Build.ArtifactStagingDirectory)' # string. Required when command = publish. Path to file(s) to publish. Default: $(Build.ArtifactStagingDirectory).
  # Feed & package details
    feedsToUse: 'internal' # 'internal' | 'external'. Alias: internalOrExternalDownload. Required. Feed location. Default: internal.
    #externalFeedCredentials: # string. Alias: externalEndpoint. Optional. Use when internalOrExternalDownload = external. Account/collection connection. 
    vstsFeed: # string. Alias: feedListDownload. Required when internalOrExternalDownload = internal. Feed. 
    vstsFeedPackage: # string. Alias: packageListDownload. Required when internalOrExternalDownload = internal. Package name. 
    vstsPackageVersion: # string. Alias: versionListDownload. Required when internalOrExternalDownload = internal. Version. 
    #feedDownloadExternal: # string. Required when internalOrExternalDownload = external. Feed. 
    #packageDownloadExternal: # string. Required when internalOrExternalDownload = external. Package name. 
    #versionDownloadExternal: # string. Required when internalOrExternalDownload = external. Version. 
  # Feed & package details
    feedsToUsePublish: 'internal' # 'internal' | 'external'. Alias: internalOrExternalPublish. Required. Feed location. Default: internal.
    #publishFeedCredentials: # string. Alias: externalEndpoints. Required when internalOrExternalPublish = external. Account/collection connection. 
    vstsFeedPublish: # string. Alias: feedListPublish. Required when internalOrExternalPublish = internal. Destination Feed. 
    vstsFeedPackagePublish: # string. Alias: packageListPublish. Required when internalOrExternalPublish = internal. Package name. 
    #feedPublishExternal: # string. Required when internalOrExternalPublish = external. Feed. 
    #packagePublishExternal: # string. Required when internalOrExternalPublish = external. Package name. 
    versionOption: 'patch' # 'major' | 'minor' | 'patch' | 'custom'. Alias: versionPublishSelector. Required. Version. Default: patch.
    #versionPublish: # string. Required when versionPublishSelector = custom. Custom version. 
    #packagePublishDescription: # string. Description. 
  # Advanced
    #verbosity: 'None' # 'None' | 'Trace' | 'Debug' | 'Information' | 'Warning' | 'Error' | 'Critical'. Verbosity. Default: None.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="command"::: -->
:::moniker range=">=azure-pipelines-2019"

**`command`** - **Command**<br>
`string`. Required. Allowed values: `download`, `publish`. Default value: `download`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the NuGet command to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="downloadDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`downloadDirectory`** - **Destination directory**<br>
`string`. Required when `command = download`. Default value: `$(System.DefaultWorkingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the folder path where the task downloads the package's contents.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feedsToUse"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`feedsToUse`** - **Feed location**<br>
Input alias: `internalOrExternalDownload`. `string`. Required. Allowed values: `internal` (This organization/collection), `external` (Another organization/collection). Default value: `internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a feed from this collection or another collection in Azure Artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`feedsToUse`** - **Feed location**<br>
Input alias: `internalOrExternalDownload`. `string`. Required. Allowed values: `internal` (This account/collection), `external` (Another account/collection). Default value: `internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a feed from this collection or another collection in Azure Artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="externalFeedCredentials"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`externalFeedCredentials`** - **organization/collection connection**<br>
Input alias: `externalEndpoint`. `string`. Optional. Use when `internalOrExternalDownload = external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the credentials to use for external registries located in the selected `NuGet.config`. For feeds in this organization or collection, leave this blank; the build's credentials are used automatically.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`externalFeedCredentials`** - **Account/collection connection**<br>
Input alias: `externalEndpoint`. `string`. Optional. Use when `internalOrExternalDownload = external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the credentials to use for external registries located in the selected `NuGet.config`. For feeds in this organization or collection, leave this blank; the build's credentials are used automatically.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstsFeed"::: -->
:::moniker range=">=azure-pipelines-2019"

**`vstsFeed`** - **Feed**<br>
Input alias: `feedListDownload`. `string`. Required when `internalOrExternalDownload = internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes the selected feed. You must have Azure Artifacts installed and licensed to select a feed here. Specifies the *FeedName* for an organization-scoped feed and *projectName/FeedName* or *ProjectID/FeedID* for a project-scoped feed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstsFeedPackage"::: -->
:::moniker range=">=azure-pipelines-2019"

**`vstsFeedPackage`** - **Package name**<br>
Input alias: `packageListDownload`. `string`. Required when `internalOrExternalDownload = internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the package for the task to download.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstsPackageVersion"::: -->
:::moniker range=">=azure-pipelines-2019"

**`vstsPackageVersion`** - **Version**<br>
Input alias: `versionListDownload`. `string`. Required when `internalOrExternalDownload = internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the package version or uses a variable containing the version to download. This entry can also be a wildcard expression, such as `*`, to get the highest version. Examples: `1.*` gets the highest version with major version 1, and `1.2.*` gets the highest patch release with major version 1 and minor version 2.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feedDownloadExternal"::: -->
:::moniker range=">=azure-pipelines-2020"

**`feedDownloadExternal`** - **Feed (or Project/Feed if the feed was created in a project)**<br>
`string`. Required when `internalOrExternalDownload = external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a feed in another organization/collection.

For project-scoped feeds, the value should be `Project/Feed`, where `Project` is the project's name or ID, and `Feed` is the feed's name/ID. For organization-scoped feeds, the value should be only the feed name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

**`feedDownloadExternal`** - **Feed**<br>
`string`. Required when `internalOrExternalDownload = external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a feed in another organization/collection.

For project-scoped feeds, the value should be `Project/Feed`, where `Project` is the project's name or ID, and `Feed` is the feed's name/ID. For organization-scoped feeds, the value should be only the feed name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageDownloadExternal"::: -->
:::moniker range=">=azure-pipelines-2019"

**`packageDownloadExternal`** - **Package name**<br>
`string`. Required when `internalOrExternalDownload = external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the package name to download.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionDownloadExternal"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionDownloadExternal`** - **Version**<br>
`string`. Required when `internalOrExternalDownload = external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the package version or uses a variable containing the version to download. This entry can also be a wildcard expression, such as `*`, to get the highest version. Examples: `1.*` gets the highest version with major version 1, and `1.2.*` gets the highest patch release with major version 1 and minor version 2. Wildcard patterns are not supported with pre-release packages.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`publishDirectory`** - **Path to file(s) to publish**<br>
`string`. Required when `command = publish`. Default value: `$(Build.ArtifactStagingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to list of files to be published.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feedsToUsePublish"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`feedsToUsePublish`** - **Feed location**<br>
Input alias: `internalOrExternalPublish`. `string`. Required. Allowed values: `internal` (This organization/collection), `external` (Another organization/collection). Default value: `internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a feed from this collection or another collection in Azure Artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`feedsToUsePublish`** - **Feed location**<br>
Input alias: `internalOrExternalPublish`. `string`. Required. Allowed values: `internal` (This account/collection), `external` (Another account/collection). Default value: `internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a feed from this collection or another collection in Azure Artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishFeedCredentials"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`publishFeedCredentials`** - **organization/collection connection**<br>
Input alias: `externalEndpoints`. `string`. Required when `internalOrExternalPublish = external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the credentials to use for external feeds.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`publishFeedCredentials`** - **Account/collection connection**<br>
Input alias: `externalEndpoints`. `string`. Required when `internalOrExternalPublish = external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the credentials to use for external feeds.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstsFeedPublish"::: -->
:::moniker range=">=azure-pipelines-2019"

**`vstsFeedPublish`** - **Destination Feed**<br>
Input alias: `feedListPublish`. `string`. Required when `internalOrExternalPublish = internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the project and the feed's name/GUID to publish to.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishPackageMetadata"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`publishPackageMetadata`** - **Publish pipeline metadata**<br>
`boolean`. Optional. Use when `command = publish && internalOrExternalPublish = internal`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Associates this build/release pipeline's metadata (such as run # and source code information) with the package.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstsFeedPackagePublish"::: -->
:::moniker range=">=azure-pipelines-2019"

**`vstsFeedPackagePublish`** - **Package name**<br>
Input alias: `packageListPublish`. `string`. Required when `internalOrExternalPublish = internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a package ID to publish or creates a new package ID if you've never published a version of this package before. Package names must be lower case and can only use letters, numbers, and dashes (`-`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feedPublishExternal"::: -->
:::moniker range=">=azure-pipelines-2020"

**`feedPublishExternal`** - **Feed (or Project/Feed if the feed was created in a project)**<br>
`string`. Required when `internalOrExternalPublish = external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the external feed name to publish to.

If the feed was created in a project, the value should be `Project/Feed`, where `Project` is the project's name or ID, and `Feed` is the feed's name. If the feed was not created in a project, the value should be only the feed name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

**`feedPublishExternal`** - **Feed**<br>
`string`. Required when `internalOrExternalPublish = external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the external feed name to publish to.

If the feed was created in a project, the value should be `Project/Feed`, where `Project` is the project's name or ID, and `Feed` is the feed's name. If the feed was not created in a project, the value should be only the feed name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagePublishExternal"::: -->
:::moniker range=">=azure-pipelines-2019"

**`packagePublishExternal`** - **Package name**<br>
`string`. Required when `internalOrExternalPublish = external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the package name when publishing to an external feed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionOption"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionOption`** - **Version**<br>
Input alias: `versionPublishSelector`. `string`. Required. Allowed values: `major` (Next major), `minor` (Next minor), `patch` (Next patch), `custom`. Default value: `patch`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a version increment strategy. The `custom` value to input your package version manually. For new packages, the first version will be 1.0.0 if you specify `major`, 0.1.0 if you specify `minor`, or 0.0.1 if you specify `patch`. See the [Semantic Versioning spec](https://semver.org/) for more information.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionPublish"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionPublish`** - **Custom version**<br>
`string`. Required when `versionPublishSelector = custom`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a custom version schema for the package.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packagePublishDescription"::: -->
:::moniker range=">=azure-pipelines-2019"

**`packagePublishDescription`** - **Description**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the description of the package contents and/or the changes made in this version of the package.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosity"::: -->
:::moniker range=">=azure-pipelines-2020"

**`verbosity`** - **Verbosity**<br>
`string`. Allowed values: `None`, `Trace`, `Debug`, `Information`, `Warning`, `Error`, `Critical`. Default value: `None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the amount of detail displayed in the output.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

**`verbosity`** - **Verbosity**<br>
`string`. Allowed values: `None`, `Trace`, `Debug`, `Information`, `Warning`, `Error`, `Critical` (Citical). Default value: `None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the amount of detail displayed in the output.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishedPackageVar"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`publishedPackageVar`** - **Package Output Variable**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a name for the variable that will contain the published package name and version.
<!-- :::editable-content-end::: -->
<br>

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
## Remarks

Use this task to download, or package and publish Universal Packages.

### My Pipeline needs to access a feed in a different project

If the pipeline is running in a different project than the project hosting the feed, you must set up the other project to grant read/write access to the build service. See [Package permissions in Azure Pipelines](/azure/devops/artifacts/feeds/feed-permissions#pipelines-permissions) for more details.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

The simplest way to get started with the Universal Package task is to use the Pipelines task editor to generate the YAML. You can then copy the generated code into your project's `azure-pipelines.yml` file. In this example, the sample demonstrates how to quickly generate the YAML using a pipeline that builds a GatsbyJS progressive web app (PWA).  

Universal Packages are a useful way to both encapsulate and version a web app. Packaging a web app into a Universal Package enables quick rollbacks to a specific version of your site and eliminates the need to build the site in the deployment pipeline.

This example pipeline demonstrates how to fetch a tool from a feed within your project. The Universal Package task is used to download the tool, run a build, and again uses the Universal Package task to publish the entire compiled GatsbyJS PWA to a feed as a versioned Universal Package.

:::image type="content" source="media/sample-npm-project-with-universal.png" alt-text="Screenshot of sample project.":::

### Download a package with the Universal Package task

The second task in the sample project uses the Universal Package task to fetch a tool, imagemagick, from a feed that is within a different project in the same organization. The tool, imagemagick, is required by the subsequent build step to resize images.

1. Add the Universal Package task by clicking the plus icon, typing "universal" in the search box, and clicking the **Add** button to add the task to your pipeline.

    :::image type="content" source="media/add-universal-task.png" alt-text="Screenshot of adding the Universal Package task.":::

2. Click the newly added **Universal Package** task and the **Command** to `Download`.
3. Choose the **Destination directory** to use for the tool download.
4. Select a source **Feed** that contains the tool, set the **Package name**, and choose **Version** of the imagemagick tool from the source **Feed**.

    :::image type="content" source="media/universal-package-download.png" alt-text="Screenshot of configuring the Universal Package task to download.":::

5. After completing the fields, click **View YAML** to see the generated YAML.  

    :::image type="content" source="media/copy-yaml-to-clipboard.png" alt-text="Screenshot of viewing the YAML.":::

6. The **Universal Package** task builder generates simplified YAML that contains non-default values. Copy the generated YAML into your `azure-pipelines.yml` file at the [root of your project's git repo](/azure/devops/pipelines/customize-pipeline#understand-the-azure-pipelinesyml-file).

    ```YAML
    # Download Universal Package
    steps:
    - task: UniversalPackages@0
      displayName: 'Universal download'
      inputs:
        downloadDirectory: Application
        vstsFeed: '00000000-0000-0000-0000-000000000000/00000000-0000-0000-0000-000000000001'
        vstsFeedPackage: imagemagick
        vstsPackageVersion: 1.0.0
    ```

### Publish a package with the Universal Package task

The last step in this sample pipeline uses the Universal Package task to upload the production-ready Gatsby PWA that was produced by the `Run gatsby build` step to a feed as a versioned Universal Package. Once in a feed, you have a permanent copy of your complete site that can be deployed to hosting provider and started with `gatsby serve`.  

1. Add another Universal Package task to the end of the pipeline by clicking the plus icon, typing "universal" in the search box, and clicking the **Add** button to add the task to your pipeline. This task gathers all of the production-ready assets produced by the `Run gatsby build` step, produce a versioned Universal Package, and publish the package to a feed.  

    :::image type="content" source="media/universal-package-upload.png" alt-text="Screenshot of setting a Universal Package task to publish.":::

2. Set the **Command** to `Publish`.  
3. Set **Path to file(s) to publish** to the directory containing your GatsbyJS project's `package.json`.  
4. Choose a destination feed, a package name, and set your versioning strategy.

    :::image type="content" source="media/universal-package-publish.png" alt-text="Screenshot of configuring the Universal Package task to publish.":::

5. After completing the required fields, click **View YAML**.
6. Copy the resulting YAML into your `azure-pipelines.yml` file as before. The YAML for this sample project displays below.

    ```YAML
    # Publish Universal Package
    steps:
    - task: UniversalPackages@0
      displayName: 'Universal publish'
      inputs:
        command: publish
        publishDirectory: Application
        vstsFeedPublish: '00000000-0000-0000-0000-000000000000/00000000-0000-0000-0000-000000000002' # You can also use '<projectName>/<feedName>' instead of the GUIDs
        vstsFeedPackagePublish: mygatsbysite
        packagePublishDescription: 'A test package'
      ```

This example demonstrated how to use the Pipelines task builder to quickly generate the YAML for the Universal Package task, which can then be placed into your `azure-pipelines.yml` file. The Universal Package task builder supports all of the advanced configurations that can be created with **Universal Package** task's arguments.

> [!NOTE]
> Publishing a package directly to a view is not supported in Azure Artifacts. You must publish the package to your feed first, then promote it to a view.
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