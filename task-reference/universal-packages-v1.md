---
title: UniversalPackages@1 - Universal Packages v1 task
description: Publish or download Universal Packages to and from Azure Artifacts feeds.
ms.date: 02/17/2026
monikerRange: "azure-pipelines"
author: ramiMSFT
ms.author: rabououn
---

# UniversalPackages@1 - Universal Packages v1 task

<!-- :::description::: -->

Use this task to publish or download Universal Packages to and from Azure Artifacts feeds. This version supports Workload Identity Federation (WIF) through Azure DevOps service connections, enabling authentication without Personal Access Tokens (PATs).

<!-- :::description-end::: -->

<!-- :::syntax::: -->

## Syntax

```yaml
# Universal packages v1
# Download or publish Universal Packages.
- task: UniversalPackages@1
  inputs:
    command: 'download' # 'download' | 'publish'. Required. Command. Default: download.
    #adoServiceConnection: # string. Alias: workloadIdentityServiceConnection | azureDevOpsServiceConnection. Optional. Azure DevOps Service Connection.
    #organization: # string. Optional. Use when adoServiceConnection is specified. Organization.
    feed: # string. Required. Feed name (or project/feed).
    packageName: # string. Required. Package name.
    #packageVersion: # string. Optional. Package version.
    #versionIncrement: # 'major' | 'minor' | 'patch'. Optional. Use when command = publish. Version increment.
    directory: '$(System.DefaultWorkingDirectory)' # filePath. Required. Directory. Default: $(System.DefaultWorkingDirectory).
    #packageDescription: # string. Optional. Use when command = publish. Description.

```
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="command"::: -->

**`command`** - **Command**<br>
`string`. Required. Allowed values: `download`, `publish`. Default value: `download`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Universal Package command to run: download a package from a feed, or publish a package to a feed.
<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: --> 

<!-- :::item name="adoServiceConnection"::: -->

**`adoServiceConnection`** - **Azure DevOps Service Connection**<br>
[Input aliases](index.md#what-are-task-input-aliases): `workloadIdentityServiceConnection`, `azureDevOpsServiceConnection`.  
`string`. Optional.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of an Azure DevOps Service Connection that uses Workload Identity Federation (WIF) for authentication. When specified, the task uses the service connection identity instead of the pipeline's build service identity. This enables scenarios such as cross-organization feed access and WIF-based authentication without PATs.

When not specified, the task authenticates using the pipeline’s built‑in build service identity. See [Setting up an Azure DevOps Service Connection]() for setup instructions.
<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: --> 

<!-- :::item name="organization"::: -->

**`organization`** - **Organization**<br>
`string`. Optional. Use when `adoServiceConnection` is specified.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Azure DevOps organization that hosts the target feed. Use this input when the feed is in a different organization than the one running the pipeline.
If not specified, the task uses the current pipeline’s organization.

<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: --> 

<!-- :::item name="feed"::: -->

**`feed`** - **Feed name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Azure Artifacts feed. For organization-scoped feeds, specify only the feed name. For project-scoped feeds, use the format `project/feed`, where `project` is the project name and `feed` is the feed name.
<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: --> 

<!-- :::item name="packageName"::: -->

**`packageName`** - **Package name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Universal Package to download or publish. Package names must be lower case and can only use letters, numbers, and dashes `-`.
<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: --> 

<!-- :::item name="packageVersion"::: -->

**`packageVersion`** - **Package version**<br>
`string`. Optional.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of the package. Required for `download`. For `publish`, specify either this input or `versionIncrement`, but not both.

For downloads, this can be a wildcard expression such as `*` to get the latest version, `1.*` to get the latest version with major version 1, or `1.2.*` to get the latest patch release with major version 1 and minor version 2. Wildcard patterns are not supported for pre-release packages.
<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: --> 

<!-- :::item name="versionIncrement"::: -->

**`versionIncrement`** - **Version increment**<br>
`string`. Optional. Use when `command = publish`. Allowed values: `major` (Major), `minor` (Minor), `patch` (Patch).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Automatically increments the package version. The task queries the feed for the latest existing version of the package and increments the specified component. Cannot be used together with `packageVersion`.

For new packages with no existing versions in the feed, the starting version is:

- `major`: 1.0.0  
- `minor`: 0.1.0  
- `patch`: 0.0.1  

<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: --> 

<!-- :::item name="directory"::: -->

**`directory`** - **Directory**<br>
`filePath`. Required. Default value: `$(System.DefaultWorkingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
For downloads, specifies the folder path where the package contents will be downloaded. For publish, specifies the path to the directory that contains the files to publish.
<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: --> 

<!-- :::item name="packageDescription"::: -->

**`packageDescription`** - **Description**<br>
`string`. Optional. Use when `command = publish`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Description of the package contents and/or the changes included in this version of the package.
<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: -->

### Task control options
All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).

<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

None.

<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->

## Remarks

Use this task to publish or download Universal Packages to and from Azure Artifacts feeds. The task supports two authentication methods:

- *Build service identity* (default): When no service connection is specified, the task uses the pipeline's built-in build service identity. This is the simplest setup and works for feeds within the same organization.

- *Azure DevOps Service Connection (WIF)*: When *adoServiceConnection* is specified, the task uses **Workload Identity Federation** to authenticate. This enables cross-organization feed access and eliminates the need for PATs.

#### Access a feed in a different project

If the pipeline runs in a different project than the one hosting the feed, you must grant the build service or service connection identity read/write permissions in the target project. See Package permissions in Azure Pipelines for more details.

#### Access a feed in a different organization

Use the *adoServiceConnection* and *organization* inputs together to access feeds in a different Azure DevOps organization. The service connection must be configured with a Workload Identity Federation credential that has permissions on the target organization's feed. For an example, see [Download a package from a feed in a different organization](#download-a-package-from-a-feed-in-a-different-organization).

##### Version increment behavior

When you use *versionIncrement*, the task queries the feed for the latest existing version of the specified package and increments the appropriate component:

- patch: 1.2.3 -> 1.2.4
- minor: 1.2.3 -> 1.3.0
- major: 1.2.3 -> 2.0.0

If the package does not yet exist in the feed, the task starts with the initial version defined in the *versionIncrement* input table. After the task completes, the resolved version is available in the *packageVersion* output variable.

<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->

## Examples

- [Download a package from a project-scoped feed](#download-a-package-from-a-project-scoped-feed)
- [Download a package from an organization-scoped feed](#download-a-package-from-an-organization-scoped-feed)
- [Download the latest version of a package](#download-the-latest-version-of-a-package)
- [Publish a package with an explicit version](#publish-a-package-with-an-explicit-version)
- [Publish a package with automatic version increment](#publish-a-package-with-automatic-version-increment)
- [Download using a service connection (WIF)](#download-using-a-service-connection-wif)
- [Download a package from a feed in a different organization](#download-a-package-from-a-feed-in-a-different-organization)
- [Publish across organizations with auto-increment](#publish-across-organizations-with-auto-increment)

#### Download a package from a project-scoped feed

```yaml
steps:
- task: UniversalPackages@1
  displayName: 'Download from project-scoped feed'
  inputs:
    command: download
    feed: 'my-project/my-feed'
    packageName: 'my-package'
    packageVersion: '2.*'
    directory: '$(Build.SourcesDirectory)/packages'
```

#### Download a package from an organization-scoped feed

```yaml
steps:
- task: UniversalPackages@1
  displayName: 'Download universal package'
  inputs:
    command: download
    feed: 'my-feed'
    packageName: 'my-package'
    packageVersion: '1.0.0'
    directory: '$(Build.SourcesDirectory)/packages'
```

#### Download the latest version of a package

Use a wildcard expression to always download the latest available version:

```yaml
steps:
- task: UniversalPackages@1
  displayName: 'Download latest package'
  inputs:
    command: download
    feed: 'my-feed'
    packageName: 'my-package'
    packageVersion: '*'
    directory: '$(Build.SourcesDirectory)/packages'
```


#### Publish a package with an explicit version

```yaml
steps:
- task: UniversalPackages@1
  displayName: 'Publish universal package'
  inputs:
    command: publish
    feed: 'my-feed'
    packageName: 'my-app'
    packageVersion: '1.0.0'
    directory: '$(Build.ArtifactStagingDirectory)'
    packageDescription: 'Initial release of my-app'
```

#### Publish a package with automatic version increment

Use *versionIncrement* to automatically bump the version based on what's already in the feed:

```yaml
steps:
- task: UniversalPackages@1
  name: publishStep
  displayName: 'Publish with auto-increment'
  inputs:
    command: publish
    feed: 'my-project/my-feed'
    packageName: 'my-app'
    versionIncrement: patch
    directory: '$(Build.ArtifactStagingDirectory)'
    packageDescription: 'Automated build $(Build.BuildNumber)'

- script: echo "Published version $(publishStep.packageVersion)"
  displayName: 'Display published version'
```

#### Download using a service connection (WIF)

Authenticate with Workload Identity Federation instead of the build service identity:

```yaml
steps:
- task: UniversalPackages@1
  displayName: 'Download with WIF auth'
  inputs:
    command: download
    adoServiceConnection: 'my-ado-service-connection'
    feed: 'my-feed'
    packageName: 'my-package'
    packageVersion: '1.0.0'
    directory: '$(Build.SourcesDirectory)/packages'
```

#### Download a package from a feed in a different organization

Use *adoServiceConnection* with organization to download or publish across organizations:

```yaml
steps:
- task: UniversalPackages@1
  displayName: 'Download from another org'
  inputs:
    command: download
    adoServiceConnection: 'cross-org-connection'
    organization: 'other-org'
    feed: 'shared-project/shared-feed'
    packageName: 'shared-tools'
    packageVersion: '*'
    directory: '$(Build.SourcesDirectory)/tools'
```

#### Publish across organizations with auto-increment

```yaml
steps:
- task: UniversalPackages@1
  name: crossOrgPublish
  displayName: 'Publish to another org'
  inputs:
    command: publish
    adoServiceConnection: 'cross-org-connection'
    organization: 'other-org'
    feed: 'shared-feed'
    packageName: 'my-library'
    versionIncrement: minor
    directory: '$(Build.ArtifactStagingDirectory)'
    packageDescription: 'Cross-org publish from $(Build.Repository.Name)'
```

<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->

## Requirements

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  4.248.0 or greater |
| Task category | Package |

<!-- :::properties-end::: -->