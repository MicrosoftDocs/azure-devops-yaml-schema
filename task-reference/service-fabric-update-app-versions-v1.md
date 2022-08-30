---
title: ServiceFabricUpdateAppVersions@1 - Update Service Fabric App Versions v1 task
description: Automatically updates the versions of a packaged Service Fabric application.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# ServiceFabricUpdateAppVersions@1 - Update Service Fabric App Versions v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Automatically updates the versions of a packaged Service Fabric application.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Update Service Fabric App Versions v1
# Automatically updates the versions of a packaged Service Fabric application.
- task: ServiceFabricUpdateAppVersions@1
  inputs:
    applicationPackagePath: # string. Required. Application Package. 
    versionSuffix: '.$(Build.BuildNumber)' # string. Required. Version Value. Default: '.$(Build.BuildNumber)'.
    #versionBehavior: 'Append' # 'Append' | 'Replace'. Version Behavior. Default: 'Append'.
    updateOnlyChanged: false # boolean. Required. Update only if changed. Default: false.
    #pkgArtifactName: # string. Optional. Use when updateOnlyChanged = true. Package Artifact Name. 
    #logAllChanges: true # boolean. Optional. Use when updateOnlyChanged = true. Log all changes. Default: true.
    #compareType: 'LastSuccessful' # 'LastSuccessful' | 'Specific'. Optional. Use when updateOnlyChanged = true. Compare against. Default: 'LastSuccessful'.
    #buildNumber: # string. Optional. Use when compareType = Specific. Build Number.
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

<!-- :::item name="applicationPackagePath"::: -->
:::moniker range="<=azure-pipelines"

**`applicationPackagePath`** - **Application Package**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the application package. [Variables](https://go.microsoft.com/fwlink/?LinkID=550988) and wildcards can be used in the path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionSuffix"::: -->
:::moniker range="<=azure-pipelines"

**`versionSuffix`** - **Version Value**<br>
Type: string. Required. Default value: '.$(Build.BuildNumber)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The value used to specify the version in the manifest files. Default is .$(Build.BuildNumber).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionBehavior"::: -->
:::moniker range="<=azure-pipelines"

**`versionBehavior`** - **Version Behavior**<br>
Type: string. Allowed values: 'Append', 'Replace'. Default value: 'Append'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify whether to append the version value to existing values in the manifest files or replace them.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="updateOnlyChanged"::: -->
:::moniker range="<=azure-pipelines"

**`updateOnlyChanged`** - **Update only if changed**<br>
Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Incrementally update only the packages that have changed. Use the [deterministic compiler flag](https://go.microsoft.com/fwlink/?LinkId=808668) to ensure builds with the same inputs produce the same outputs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pkgArtifactName"::: -->
:::moniker range="<=azure-pipelines"

**`pkgArtifactName`** - **Package Artifact Name**<br>
Type: string. Optional. Use when updateOnlyChanged = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the artifact containing the application package for comparison.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="logAllChanges"::: -->
:::moniker range="<=azure-pipelines"

**`logAllChanges`** - **Log all changes**<br>
Type: boolean. Optional. Use when updateOnlyChanged = true. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Compare all files in every package and log if the file was added, removed, or if its content changed. Otherwise, compare files in a package only until the first change is found for faster performance.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="compareType"::: -->
:::moniker range="<=azure-pipelines"

**`compareType`** - **Compare against**<br>
Type: string. Optional. Use when updateOnlyChanged = true. Allowed values: 'LastSuccessful', 'Specific'. Default value: 'LastSuccessful'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The build for comparison.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildNumber"::: -->
:::moniker range="<=azure-pipelines"

**`buildNumber`** - **Build Number**<br>
Type: string. Optional. Use when compareType = Specific.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The build number for comparison.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
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
| Pipeline types | YAML, Classic build |
| Runs on | Agent |
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