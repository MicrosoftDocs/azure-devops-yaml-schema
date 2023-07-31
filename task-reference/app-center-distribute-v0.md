---
title: AppCenterDistribute@0 - App Center Distribute v0 task
description: Distribute app builds to testers and users via App Center (task version 1).
ms.date: 07/31/2023
monikerRange: "<=azure-pipelines"
---

# AppCenterDistribute@0 - App Center Distribute v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to distribute app builds to testers and users via App Center.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# App Center distribute v0
# Distribute app builds to testers and users via App Center.
- task: AppCenterDistribute@0
  inputs:
    serverEndpoint: # string. Required. App Center connection. 
    appSlug: # string. Required. App slug. 
    appFile: # string. Alias: app. Required. Binary file path. 
    releaseNotesOption: 'input' # 'input' | 'file'. Alias: releaseNotesSelection. Required. Create release notes. Default: input.
    releaseNotesInput: # string. Required when releaseNotesSelection = input. Release notes. 
    #releaseNotesFile: # string. Required when releaseNotesSelection = file. Release notes file. 
    #distributionGroupId: # string. Distribution group ID. 
  # Symbols
    #symbolsOption: 'Apple' # 'Apple'. Alias: symbolsType. Symbols type. Default: Apple.
    #symbolsPath: # string. Optional. Use when symbolsType == AndroidNative || symbolsType = Windows. Symbols path. 
    #symbolsPdbFiles: '**/*.pdb' # string. Alias: pdbPath. Optional. Use when symbolsType = UWP. Symbols path (*.pdb). Default: **/*.pdb.
    #symbolsDsymFiles: # string. Alias: dsymPath. Optional. Use when symbolsType = Apple. dSYM path. 
    #symbolsMappingTxtFile: # string. Alias: mappingTxtPath. Optional. Use when symbolsType = AndroidJava. Mapping file. 
    #symbolsIncludeParentDirectory: # boolean. Alias: packParentFolder. Include all items in parent folder.
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

<!-- :::item name="serverEndpoint"::: -->
:::moniker range="<=azure-pipelines"

**`serverEndpoint`** - **App Center connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the service endpoint for your Visual Studio App Center connection. To create one, click the `Manage` link and create a new service endpoint.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSlug"::: -->
:::moniker range="<=azure-pipelines"

**`appSlug`** - **App slug**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The app slug is in the format of `{username}/{app_identifier}`.  To locate `{username}` and `{app_identifier}` for an app, click on its name from [App Center](https://appcenter.ms/apps), and the resulting URL is in the format of `https://appcenter.ms/users/**{username}**/apps/**{app_identifier}**`. If you are using orgs, the app slug is of the format `{orgname}/{app_identifier}`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appFile"::: -->
:::moniker range="<=azure-pipelines"

**`appFile`** - **Binary file path**<br>
Input alias: `app`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to the APK or IPA file you want to publish.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsOption"::: -->
:::moniker range="<=azure-pipelines"

**`symbolsOption`** - **Symbols type**<br>
Input alias: `symbolsType`. `string`. Allowed values: `Apple`. Default value: `Apple`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes symbol files to receive symbolicated stack traces in App Center Diagnostics.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsPath"::: -->
:::moniker range="<=azure-pipelines"

**`symbolsPath`** - **Symbols path**<br>
`string`. Optional. Use when `symbolsType == AndroidNative || symbolsType = Windows`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to the symbols folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsPdbFiles"::: -->
:::moniker range="<=azure-pipelines"

**`symbolsPdbFiles`** - **Symbols path (*.pdb)**<br>
Input alias: `pdbPath`. `string`. Optional. Use when `symbolsType = UWP`. Default value: `**/*.pdb`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to `.pdb` symbols files. Path may contain [wildcards](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsDsymFiles"::: -->
:::moniker range="<=azure-pipelines"

**`symbolsDsymFiles`** - **dSYM path**<br>
Input alias: `dsymPath`. `string`. Optional. Use when `symbolsType = Apple`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to the dSYM folder. Path may contain [wildcards](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsMappingTxtFile"::: -->
:::moniker range="<=azure-pipelines"

**`symbolsMappingTxtFile`** - **Mapping file**<br>
Input alias: `mappingTxtPath`. `string`. Optional. Use when `symbolsType = AndroidJava`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to Android's `mapping.txt` file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsIncludeParentDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`symbolsIncludeParentDirectory`** - **Include all items in parent folder**<br>
Input alias: `packParentFolder`. `boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uploads the selected symbols file or folder and all other items inside the same parent folder. This is required for React Native apps.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotesOption"::: -->
:::moniker range="<=azure-pipelines"

**`releaseNotesOption`** - **Create release notes**<br>
Input alias: `releaseNotesSelection`. `string`. Required. Allowed values: `input` (Enter Release Notes), `file` (Select Release Notes File). Default value: `input`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The release notes will be attached to the release and shown to testers on the installation page.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotesInput"::: -->
:::moniker range="<=azure-pipelines"

**`releaseNotesInput`** - **Release notes**<br>
`string`. Required when `releaseNotesSelection = input`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The release notes for this version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotesFile"::: -->
:::moniker range="<=azure-pipelines"

**`releaseNotesFile`** - **Release notes file**<br>
`string`. Required when `releaseNotesSelection = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects a UTF-8 encoded text file which contains the release notes for this version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="distributionGroupId"::: -->
:::moniker range="<=azure-pipelines"

**`distributionGroupId`** - **Distribution group ID**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The IDs of the distribution groups who will receive the build release.. Leave it empty to use the default group.
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

This task is deprecated. Use [AppCenterDistribute@3](./app-center-distribute-v3.md).
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
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
