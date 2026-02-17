---
title: UniversalPackages@1 - Universal packages v1 task
description: Download or publish Universal Packages to and from Azure Artifacts feeds.
ms.date: 02/17/2026
monikerRange: "azure-pipelines"
author: ramiMSFT
ms.author: rabououn
---

# UniversalPackages@1 - Universal packages v1 task

<!-- :::description::: -->

Use this task to download or publish Universal Packages to and from Azure Artifacts feeds. This version supports Workload Identity Federation (WIF) through Azure DevOps service connections, enabling authentication without Personal Access Tokens (PATs).

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
The name of an Azure DevOps Service Connection that uses Workload Identity Federation (WIF) to authenticate. When specified, the task uses the service connection identity instead of the pipeline's build service identity. This enables scenarios such as cross-organization feed access and WIF-based authentication without PATs.

If not specified, the task authenticates using the pipeline's built-in build service identity. See [Setting up an Azure DevOps Service Connection]() for setup instructions.
<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: --> 

<!-- :::item name="organization"::: -->

**`organization`** - **Organization**<br>
`string`. Optional. Use when `adoServiceConnection` is specified.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Azure DevOps organization name where the target feed is located (for example, `myorg` from `https://dev.azure.com/myorg`). Use this input when the feed is in a different organization than the one running the pipeline.

When not specified, the task uses the current pipeline's organization.
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
The name of the Universal Package to download or publish. Package names must be lower case and can only use letters, numbers, and dashes (`-`).
<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: --> 

<!-- :::item name="packageVersion"::: -->

**`packageVersion`** - **Package version**<br>
`string`. Optional.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of the package. Required for `download`. For `publish`, specify either this input or `versionIncrement`, but not both.

For downloads, this can be a wildcard expression such as `*` to get the highest version, `1.*` to get the highest version with major version 1, or `1.2.*` to get the highest patch release with major version 1 and minor version 2. Wildcard patterns are not supported with pre-release packages.
<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: --> 

<!-- :::item name="versionIncrement"::: -->

**`versionIncrement`** - **Version increment**<br>
`string`. Optional. Use when `command = publish`. Allowed values: `major` (Major), `minor` (Minor), `patch` (Patch).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Automatically increments the package version. The task queries the feed for the highest existing version of the package and increments the specified component. Cannot be used together with `packageVersion`.

For new packages (no existing version in the feed), the starting version is:

- `major`: 1.0.0  
- `minor`: 0.1.0  
- `patch`: 0.0.1  

See the Semantic Versioning specification for more information.
<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: --> 

<!-- :::item name="directory"::: -->

**`directory`** - **Directory**<br>
`filePath`. Required. Default value: `$(System.DefaultWorkingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
For downloads, specifies the folder path where the package contents will be downloaded. For publish, specifies the path to the directory containing files to publish.
<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: --> 

<!-- :::item name="packageDescription"::: -->

**`packageDescription`** - **Description**<br>
`string`. Optional. Use when `command = publish`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Description of the package contents and/or the changes made in this version of the package.
<!-- :::editable-content-end::: -->
<br>

<!-- :::item-end::: -->

### Task control options
All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).

<!-- :::inputs-end::: -->

