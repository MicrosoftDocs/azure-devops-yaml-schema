---
title: AppCenterDistribute@1 - App Center distribute v1 task
description: Distribute app builds to testers and users via Visual Studio App Center (task version 1).
ms.date: 10/21/2022
monikerRange: ">=azure-pipelines-2019"
---

# AppCenterDistribute@1 - App Center distribute v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to distribute app builds to testers and users via App Center and Visual Studio App Center.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Distribute app builds to testers and users via App Center.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# App Center distribute v1
# Distribute app builds to testers and users via Visual Studio App Center.
- task: AppCenterDistribute@1
  inputs:
    serverEndpoint: # string. Required. App Center service connection. 
    appSlug: # string. Required. App slug. 
    appFile: # string. Alias: app. Required. Binary file path. 
    releaseNotesOption: 'input' # 'input' | 'file'. Alias: releaseNotesSelection. Required. Create release notes. Default: input.
    releaseNotesInput: # string. Required when releaseNotesSelection = input. Release notes. 
    #releaseNotesFile: # string. Required when releaseNotesSelection = file. Release notes file. 
    #isMandatory: false # boolean. Require users to update to this release. Default: false.
    #distributionGroupId: # string. Alias: destinationId. Destination ID. 
  # Symbols
    #symbolsOption: 'Apple' # 'Apple'. Alias: symbolsType. Symbols type. Default: Apple.
    #symbolsPath: # string. Optional. Use when symbolsType == AndroidNative || symbolsType = Windows. Symbols path. 
    #symbolsPdbFiles: '**/*.pdb' # string. Alias: pdbPath. Optional. Use when symbolsType = UWP. Symbols path (*.pdb). Default: **/*.pdb.
    #symbolsDsymFiles: # string. Alias: dsymPath. Optional. Use when symbolsType = Apple. dSYM path. 
    #symbolsMappingTxtFile: # string. Alias: mappingTxtPath. Optional. Use when symbolsType = AndroidJava. Mapping file. 
    #symbolsIncludeParentDirectory: # boolean. Alias: packParentFolder. Include all items in parent folder.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# App Center Distribute v1
# Distribute app builds to testers and users via App Center.
- task: AppCenterDistribute@1
  inputs:
    serverEndpoint: # string. Required. App Center service connection. 
    appSlug: # string. Required. App slug. 
    appFile: # string. Alias: app. Required. Binary file path. 
    releaseNotesOption: 'input' # 'input' | 'file'. Alias: releaseNotesSelection. Required. Create release notes. Default: input.
    releaseNotesInput: # string. Required when releaseNotesSelection = input. Release notes. 
    #releaseNotesFile: # string. Required when releaseNotesSelection = file. Release notes file. 
    #distributionGroupId: # string. Alias: destinationId. Destination ID. 
  # Symbols
    #symbolsOption: 'Apple' # 'Apple'. Alias: symbolsType. Symbols type. Default: Apple.
    #symbolsPath: # string. Optional. Use when symbolsType == AndroidNative || symbolsType = Windows. Symbols path. 
    #symbolsPdbFiles: '**/*.pdb' # string. Alias: pdbPath. Optional. Use when symbolsType = UWP. Symbols path (*.pdb). Default: **/*.pdb.
    #symbolsDsymFiles: # string. Alias: dsymPath. Optional. Use when symbolsType = Apple. dSYM path. 
    #symbolsMappingTxtFile: # string. Alias: mappingTxtPath. Optional. Use when symbolsType = AndroidJava. Mapping file. 
    #symbolsIncludeParentDirectory: # boolean. Alias: packParentFolder. Include all items in parent folder.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="serverEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`serverEndpoint`** - **App Center service connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the service connection for Visual Studio App Center. To create one, click the `Manage` link and create a new service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSlug"::: -->
:::moniker range=">=azure-pipelines-2019"

**`appSlug`** - **App slug**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The app slug is in the format of `{username}/{app_identifier}`.  To locate `{username}` and `{app_identifier}` for an app, click on its name from [App Center](https://appcenter.ms/apps). The resulting URL is in the format of `https://appcenter.ms/users/**{username}**/apps/**{app_identifier}**`. If you are using orgs, the app slug is of the format `{orgname}/{app_identifier}`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`appFile`** - **Binary file path**<br>
Input alias: `app`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to the APK or IPA file you want to publish.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsOption"::: -->
:::moniker range=">=azure-pipelines-2019"

**`symbolsOption`** - **Symbols type**<br>
Input alias: `symbolsType`. `string`. Allowed values: `Apple`. Default value: `Apple`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes symbol files to receive symbolicated stack traces in App Center Diagnostics.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`symbolsPath`** - **Symbols path**<br>
`string`. Optional. Use when `symbolsType == AndroidNative || symbolsType = Windows`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to the symbols folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsPdbFiles"::: -->
:::moniker range=">=azure-pipelines-2019"

**`symbolsPdbFiles`** - **Symbols path (*.pdb)**<br>
Input alias: `pdbPath`. `string`. Optional. Use when `symbolsType = UWP`. Default value: `**/*.pdb`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to `.pdb` symbols files. Path may contain [wildcards](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsDsymFiles"::: -->
:::moniker range=">=azure-pipelines-2019"

**`symbolsDsymFiles`** - **dSYM path**<br>
Input alias: `dsymPath`. `string`. Optional. Use when `symbolsType = Apple`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to the dSYM folder. Path may contain [wildcards](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsMappingTxtFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`symbolsMappingTxtFile`** - **Mapping file**<br>
Input alias: `mappingTxtPath`. `string`. Optional. Use when `symbolsType = AndroidJava`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to Android's `mapping.txt` file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsIncludeParentDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`symbolsIncludeParentDirectory`** - **Include all items in parent folder**<br>
Input alias: `packParentFolder`. `boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uploads the selected symbols file or folder and all other items inside the same parent folder. This is required for React Native apps.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotesOption"::: -->
:::moniker range=">=azure-pipelines-2019"

**`releaseNotesOption`** - **Create release notes**<br>
Input alias: `releaseNotesSelection`. `string`. Required. Allowed values: `input` (Enter Release Notes), `file` (Select Release Notes File). Default value: `input`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The release notes are attached to the release and shown to testers on the installation page.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotesInput"::: -->
:::moniker range=">=azure-pipelines-2019"

**`releaseNotesInput`** - **Release notes**<br>
`string`. Required when `releaseNotesSelection = input`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The release notes for this version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotesFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`releaseNotesFile`** - **Release notes file**<br>
`string`. Required when `releaseNotesSelection = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects a UTF-8 encoded text file which contains the release notes for this version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isMandatory"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`isMandatory`** - **Require users to update to this release**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The App Center Distribute SDK required to mandate an update. Testers are automatically prompted to update.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="distributionGroupId"::: -->
:::moniker range=">=azure-pipelines-2019"

**`distributionGroupId`** - **Destination ID**<br>
Input alias: `destinationId`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The IDs of the distribution stores or groups who will receive the build release. Leave it empty to use the default group.
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

Add support for distribution to stores.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Deploy |

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022"

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
