---
title: NuGetPublisher@0 - NuGet publisher v0 task
description: NuGetPublisher@0 is deprecated. Use the NuGet task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default.
ms.date: 08/29/2025
monikerRange: "<=azure-pipelines"
author: ramiMSFT
ms.author: rabououn
---

# NuGetPublisher@0 - NuGet publisher v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
NuGetPublisher@0 is deprecated. Use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# NuGet publisher v0
# Deprecated: use the “NuGet” task instead. It works with the new Tool Installer framework so you can easily use new versions of NuGet without waiting for a task update, provides better support for authenticated feeds outside this organization/collection, and uses NuGet 4 by default.
- task: NuGetPublisher@0
  inputs:
    searchPattern: '**/*.nupkg;-:**/packages/**/*.nupkg;-:**/*.symbols.nupkg' # string. Required. Path/Pattern to nupkg. Default: **/*.nupkg;-:**/packages/**/*.nupkg;-:**/*.symbols.nupkg.
    nuGetFeedType: 'external' # 'external' | 'internal'. Required. Feed type. Default: external.
    connectedServiceName: # string. Required when nuGetFeedType = external. NuGet Service Connection. 
    #feedName: # string. Required when nuGetFeedType = internal. Internal Feed URL. 
  # Advanced
    #nuGetAdditionalArgs: # string. NuGet Arguments. 
    #verbosity: '-' # '-' | 'Quiet' | 'Normal' | 'Detailed'. Verbosity. Default: -.
    nuGetVersion: '3.3.0' # '3.3.0' | '3.5.0.1829' | '4.0.0.2283' | 'custom'. Required. NuGet Version. Default: 3.3.0.
    #nuGetPath: # string. Path to NuGet.exe. 
    #continueOnEmptyNupkgMatch: false # boolean. Continue if no packages match the "Path/Pattern to nupkg". Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="searchPattern"::: -->
:::moniker range="<=azure-pipelines"

**`searchPattern`** - **Path/Pattern to nupkg**<br>
`string`. Required. Default value: `**/*.nupkg;-:**/packages/**/*.nupkg;-:**/*.symbols.nupkg`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The pattern that the task uses to match or path to `nupkg` files to be uploaded. Multiple patterns can be separated by a semicolon.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetFeedType"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetFeedType`** - **Feed type**<br>
`string`. Required. Allowed values: `external` (External NuGet Feed), `internal` (Internal NuGet Feed). Default value: `external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether the target feed is an internal feed/collection or an external NuGet server.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="connectedServiceName"::: -->
:::moniker range="<=azure-pipelines"

**`connectedServiceName`** - **NuGet Service Connection**<br>
`string`. Required when `nuGetFeedType = external`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the NuGet server generic service connection. Set the key `Password/Token Key` field to your NuGet API key.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="feedName"::: -->
:::moniker range="<=azure-pipelines"

**`feedName`** - **Internal Feed URL**<br>
`string`. Required when `nuGetFeedType = internal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the URL of a NuGet feed hosted in this account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetAdditionalArgs"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetAdditionalArgs`** - **NuGet Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The additional arguments passed to `NuGet.exe push`. Learn more about the [push command in the NuGet CLI](/nuget/tools/cli-ref-push).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbosity"::: -->
:::moniker range="<=azure-pipelines"

**`verbosity`** - **Verbosity**<br>
`string`. Allowed values: `-`, `Quiet`, `Normal`, `Detailed`. Default value: `-`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the amount of detail displayed in the output.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetVersion"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetVersion`** - **NuGet Version**<br>
`string`. Required. Allowed values: `3.3.0`, `3.5.0.1829` (3.5.0), `4.0.0.2283` (4.0.0), `custom`. Default value: `3.3.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of NuGet or a custom version to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nuGetPath"::: -->
:::moniker range="<=azure-pipelines"

**`nuGetPath`** - **Path to NuGet.exe**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Supplies the path to `NuGet.exe`. Will override version selection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="continueOnEmptyNupkgMatch"::: -->
:::moniker range="<=azure-pipelines"

**`continueOnEmptyNupkgMatch`** - **Continue if no packages match the "Path/Pattern to nupkg"**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Continues the task instead of failing the task if no packages match the `searchPattern` string.
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
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: Cmd |
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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: Cmd |
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