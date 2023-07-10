---
title: ServiceFabricUpdateManifests@2 - Update Service Fabric manifests v2 task
description: Automatically update portions of application and service manifests in a packaged Azure Service Fabric application.
ms.date: 07/10/2023
monikerRange: "<=azure-pipelines"
---

# ServiceFabricUpdateManifests@2 - Update Service Fabric manifests v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task in a build pipeline to automatically update the versions of a packaged Service Fabric app. This task appends a version suffix to all service and app versions, specified in the manifest files, in an Azure Service Fabric app package.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Update Service Fabric manifests v2
# Automatically update portions of application and service manifests in a packaged Azure Service Fabric application.
- task: ServiceFabricUpdateManifests@2
  inputs:
    updateType: 'Manifest versions' # 'Manifest versions' | 'Docker image settings'. Required. Update Type. Default: Manifest versions.
    applicationPackagePath: # string. Required. Application Package. 
    #versionSuffix: '.$(Build.BuildNumber)' # string. Required when updateType = Manifest versions. Version Value. Default: .$(Build.BuildNumber).
    #versionBehavior: 'Append' # 'Append' | 'Replace'. Optional. Use when updateType = Manifest versions. Version Behavior. Default: Append.
    #updateOnlyChanged: false # boolean. Optional. Use when updateType = Manifest versions. Update only if changed. Default: false.
    #pkgArtifactName: # string. Optional. Use when updateType = Manifest versions && updateOnlyChanged = true. Package Artifact Name. 
    #logAllChanges: true # boolean. Optional. Use when updateType = Manifest versions && updateOnlyChanged = true. Log all changes. Default: true.
    #compareType: 'LastSuccessful' # 'LastSuccessful' | 'Specific'. Optional. Use when updateType = Manifest versions && updateOnlyChanged = true. Compare against. Default: LastSuccessful.
    #buildNumber: # string. Optional. Use when updateType = Manifest versions && compareType = Specific. Build Number. 
    #overwriteExistingPkgArtifact: true # boolean. Optional. Use when updateType = Manifest versions && updateOnlyChanged = true. Overwrite Existing Package Artifact. Default: true.
    #imageNamesPath: # string. Optional. Use when updateType = Docker image settings. Image Names Path. 
    #imageDigestsPath: # string. Required when updateType = Docker image settings. Image Digests Path.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Update Service Fabric Manifests v2
# Automatically updates portions of the application and service manifests within a packaged Service Fabric application.
- task: ServiceFabricUpdateManifests@2
  inputs:
    updateType: 'Manifest versions' # 'Manifest versions' | 'Docker image settings'. Required. Update Type. Default: Manifest versions.
    applicationPackagePath: # string. Required. Application Package. 
    #versionSuffix: '.$(Build.BuildNumber)' # string. Required when updateType = Manifest versions. Version Value. Default: .$(Build.BuildNumber).
    #versionBehavior: 'Append' # 'Append' | 'Replace'. Optional. Use when updateType = Manifest versions. Version Behavior. Default: Append.
    #updateOnlyChanged: false # boolean. Optional. Use when updateType = Manifest versions. Update only if changed. Default: false.
    #pkgArtifactName: # string. Optional. Use when updateType = Manifest versions && updateOnlyChanged = true. Package Artifact Name. 
    #logAllChanges: true # boolean. Optional. Use when updateType = Manifest versions && updateOnlyChanged = true. Log all changes. Default: true.
    #compareType: 'LastSuccessful' # 'LastSuccessful' | 'Specific'. Optional. Use when updateType = Manifest versions && updateOnlyChanged = true. Compare against. Default: LastSuccessful.
    #buildNumber: # string. Optional. Use when updateType = Manifest versions && compareType = Specific. Build Number. 
    #overwriteExistingPkgArtifact: true # boolean. Optional. Use when updateType = Manifest versions && updateOnlyChanged = true. Overwrite Existing Package Artifact. Default: true.
    #imageNamesPath: # string. Optional. Use when updateType = Docker image settings. Image Names Path. 
    #imageDigestsPath: # string. Required when updateType = Docker image settings. Image Digests Path.
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

<!-- :::item name="updateType"::: -->
:::moniker range="<=azure-pipelines"

**`updateType`** - **Update Type**<br>
`string`. Required. Allowed values: `Manifest versions`, `Docker image settings`. Default value: `Manifest versions`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the type of update that should be made to the manifest files. In order to use both update types, add an instance of this task to the build pipeline for each type of update to be executed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="applicationPackagePath"::: -->
:::moniker range="<=azure-pipelines"

**`applicationPackagePath`** - **Application Package**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the application package. [Variables](/azure/devops/pipelines/build/variables) and wildcards can be used in the path. `applicationPackagePath` must not have a trailing slash, either `\` or `/`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionSuffix"::: -->
:::moniker range="<=azure-pipelines"

**`versionSuffix`** - **Version Value**<br>
`string`. Required when `updateType = Manifest versions`. Default value: `.$(Build.BuildNumber)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version in the manifest files.

> [!TIP]
> You can modify the build number format directly or use a logging command to dynamically set a variable in a format. For example, you can use `$(VersionSuffix)` defined in a PowerShell task:

```
$versionSuffix = ".$([DateTimeOffset]::UtcNow.ToString('yyyyMMdd.HHmmss'))"
Write-Host "##vso[task.setvariable variable=VersionSuffix;]$versionSuffix"
```
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionBehavior"::: -->
:::moniker range="<=azure-pipelines"

**`versionBehavior`** - **Version Behavior**<br>
`string`. Optional. Use when `updateType = Manifest versions`. Allowed values: `Append`, `Replace`. Default value: `Append`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether to append the version value to existing values in the manifest files or replace them.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="updateOnlyChanged"::: -->
:::moniker range="<=azure-pipelines"

**`updateOnlyChanged`** - **Update only if changed**<br>
`boolean`. Optional. Use when `updateType = Manifest versions`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Appends the new version suffix to only the packages that have changed from a previous build. If no changes are found, the version suffix from the previous build will be appended.

> [!NOTE]
> By default, the compiler will create different outputs even if no changes were made. Use the [deterministic compiler flag](https://devblogs.microsoft.com/dotnet/whats-new-for-c-and-vb-in-visual-studio/) to ensure builds with the same inputs produce the same outputs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pkgArtifactName"::: -->
:::moniker range="<=azure-pipelines"

**`pkgArtifactName`** - **Package Artifact Name**<br>
`string`. Optional. Use when `updateType = Manifest versions && updateOnlyChanged = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the artifact containing the application package for comparison.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="logAllChanges"::: -->
:::moniker range="<=azure-pipelines"

**`logAllChanges`** - **Log all changes**<br>
`boolean`. Optional. Use when `updateType = Manifest versions && updateOnlyChanged = true`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Compares all files in every package and log if the file was added, removed, or if its content changed. Otherwise, this boolean compares files in a package only until the first change is found for faster performance.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="compareType"::: -->
:::moniker range="<=azure-pipelines"

**`compareType`** - **Compare against**<br>
`string`. Optional. Use when `updateType = Manifest versions && updateOnlyChanged = true`. Allowed values: `LastSuccessful` (Last Successful Build), `Specific` (Specific Build). Default value: `LastSuccessful`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether to compare against the last completed and successful build or against a specific build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildNumber"::: -->
:::moniker range="<=azure-pipelines"

**`buildNumber`** - **Build Number**<br>
`string`. Optional. Use when `updateType = Manifest versions && compareType = Specific`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the build number for comparison.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overwriteExistingPkgArtifact"::: -->
:::moniker range="<=azure-pipelines"

**`overwriteExistingPkgArtifact`** - **Overwrite Existing Package Artifact**<br>
`boolean`. Optional. Use when `updateType = Manifest versions && updateOnlyChanged = true`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Downloads a new copy of the artifact. Otherwise, this boolean uses an existing copy if present.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageNamesPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`imageNamesPath`** - **Image Names Path**<br>
`string`. Optional. Use when `updateType = Docker image settings`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to a text file that contains the names of the Docker images associated with the Service Fabric application that should be updated with digests. Each image name must be on its own line and must be in the same order as the digests in the Image Digests file. If the images are created by the Service Fabric project, this file is generated as part of the Package target, and its output location is controlled by the property `BuiltDockerImagesFilePath`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageDigestsPath"::: -->
:::moniker range="<=azure-pipelines"

**`imageDigestsPath`** - **Image Digests Path**<br>
`string`. Required when `updateType = Docker image settings`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to a text file that contains the digest values of the Docker images associated with the Service Fabric application. This file can be output by the [Docker task](/azure/devops/pipelines/tasks/build/docker) when using the push action. The file should contain lines of text in the format of `registry/image_name@digest_value`.
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

Use this task in a build pipeline to automatically update the versions of a packaged Service Fabric app. This task appends a version suffix to all service and app versions, specified in the manifest files, in an Azure Service Fabric app package.

> [!NOTE]
> This task requires Windows PowerShell.
>
> This task is not available in **release** pipelines.

This task can only be used in a build pipeline to automatically update the versions of a packaged Service Fabric app.

This task support two types of updates:

1. **Manifest version**: Updates Service and Application versions specified in manifest files in a Service fabric application package. If specified, `manifest version` compares current files against a previous build and updates the version only for those changed services.

1. **Docker image settings**: Updates docker container image settings specified in manifest files in a Service fabric application package. The image settings to be placed are picked from two files:

    a. **Image names file**: This file is generated by the build task.

    b. **Image digests file**: This file is generated by the docker task when it pushes images to registry.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

* *[Service Fabric Application Deployment task](service-fabric-deploy-v1.md)
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: Cmd |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.95.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->