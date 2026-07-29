---
title: AppCenterDistribute@2 - App Center distribute v2 task
description: Distribute app builds to testers and users via Visual Studio App Center (task version 2).
ms.date: 07/28/2026
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022"
author: ramiMSFT
ms.author: rabououn
---

# AppCenterDistribute@2 - App Center distribute v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Use this task to distribute app builds to testers and users via Visual Studio App Center.

> [!IMPORTANT]
> [!INCLUDE [task-deprecation](includes/task-deprecation.md)] Use [AppCenterDistribute@3](./app-center-distribute-v3.md).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range=">=azure-pipelines-2022.1 <=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Use this task to distribute app builds to testers and users via Visual Studio App Center.

This task is deprecated; use [AppCenterDistribute@3](./app-center-distribute-v3.md).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="=azure-pipelines-2022"

<!-- :::editable-content name="description"::: -->
Use this task to distribute app builds to testers and users via Visual Studio App Center.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# App Center distribute v2
# Distribute app builds to testers and users via Visual Studio App Center.
- task: AppCenterDistribute@2
  inputs:
    serverEndpoint: # string. Required. App Center service connection. 
    appSlug: # string. Required. App slug. 
    appFile: # string. Alias: app. Required. Binary file path. 
    releaseNotesOption: 'input' # 'input' | 'file'. Alias: releaseNotesSelection. Required. Create release notes. Default: input.
    releaseNotesInput: # string. Required when releaseNotesOption = input. Release notes. 
    #releaseNotesFile: # string. Required when releaseNotesOption = file. Release notes file. 
    #isMandatory: false # boolean. Require users to update to this release. Default: false.
    #distributionGroupId: # string. Alias: destinationIds | destinationId. Destination IDs. 
  # Symbols
    #symbolsOption: 'Apple' # 'Apple'. Alias: symbolsType. Symbols type. Default: Apple.
    #symbolsPath: # string. Optional. Use when symbolsOption == AndroidNative || symbolsOption = Windows. Symbols path. 
    #symbolsPdbFiles: '**/*.pdb' # string. Alias: pdbPath. Optional. Use when symbolsOption = UWP. Symbols path (*.pdb). Default: **/*.pdb.
    #symbolsDsymFiles: # string. Alias: dsymPath. Optional. Use when symbolsOption = Apple. dSYM path. 
    #symbolsMappingTxtFile: # string. Alias: mappingTxtPath. Optional. Use when symbolsOption = AndroidJava. Mapping file. 
    #symbolsIncludeParentDirectory: # boolean. Alias: packParentFolder. Include all items in parent folder.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<a name="serverendpoint-property"></a>
<!-- :::item name="serverEndpoint"::: -->
:::moniker range="<=azure-pipelines"

**`serverEndpoint`** - **App Center service connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the service connection for Visual Studio App Center. To create one, click the `Manage` link and create a new service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="appslug-property"></a>
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
<a name="appfile-property"></a>
<!-- :::item name="appFile"::: -->
:::moniker range="<=azure-pipelines"

**`appFile`** - **Binary file path**<br>
[Input alias](index.md#what-are-task-input-aliases): `app`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to the APK or IPA file you want to publish.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="symbolsoption-property"></a>
<!-- :::item name="symbolsOption"::: -->
:::moniker range="<=azure-pipelines"

**`symbolsOption`** - **Symbols type**<br>
[Input alias](index.md#what-are-task-input-aliases): `symbolsType`. `string`. Allowed values: `Apple`. Default value: `Apple`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes symbol files to receive symbolicated stack traces in App Center Diagnostics.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="symbolspath-property"></a>
<!-- :::item name="symbolsPath"::: -->
:::moniker range="<=azure-pipelines"

**`symbolsPath`** - **Symbols path**<br>
`string`. Optional. Use when `symbolsOption == AndroidNative || symbolsOption = Windows`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to the symbols folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="symbolspdbfiles-property"></a>
<!-- :::item name="symbolsPdbFiles"::: -->
:::moniker range="<=azure-pipelines"

**`symbolsPdbFiles`** - **Symbols path (*.pdb)**<br>
[Input alias](index.md#what-are-task-input-aliases): `pdbPath`. `string`. Optional. Use when `symbolsOption = UWP`. Default value: `**/*.pdb`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to PDB symbols files. Path may contain [wildcards](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="symbolsdsymfiles-property"></a>
<!-- :::item name="symbolsDsymFiles"::: -->
:::moniker range="<=azure-pipelines"

**`symbolsDsymFiles`** - **dSYM path**<br>
[Input alias](index.md#what-are-task-input-aliases): `dsymPath`. `string`. Optional. Use when `symbolsOption = Apple`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to dSYM folder. Path may contain [wildcards](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="symbolsmappingtxtfile-property"></a>
<!-- :::item name="symbolsMappingTxtFile"::: -->
:::moniker range="<=azure-pipelines"

**`symbolsMappingTxtFile`** - **Mapping file**<br>
[Input alias](index.md#what-are-task-input-aliases): `mappingTxtPath`. `string`. Optional. Use when `symbolsOption = AndroidJava`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to Android's `mapping.txt` file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="symbolsincludeparentdirectory-property"></a>
<!-- :::item name="symbolsIncludeParentDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`symbolsIncludeParentDirectory`** - **Include all items in parent folder**<br>
[Input alias](index.md#what-are-task-input-aliases): `packParentFolder`. `boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uploads the selected symbols file or folder and all other items inside the same parent folder. This is required for React Native apps.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="releasenotesoption-property"></a>
<!-- :::item name="releaseNotesOption"::: -->
:::moniker range="<=azure-pipelines"

**`releaseNotesOption`** - **Create release notes**<br>
[Input alias](index.md#what-are-task-input-aliases): `releaseNotesSelection`. `string`. Required. Allowed values: `input` (Enter Release Notes), `file` (Select Release Notes File). Default value: `input`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Release notes are attached to the release and shown to testers on the installation page.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="releasenotesinput-property"></a>
<!-- :::item name="releaseNotesInput"::: -->
:::moniker range="<=azure-pipelines"

**`releaseNotesInput`** - **Release notes**<br>
`string`. Required when `releaseNotesOption = input`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The release notes for this version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="releasenotesfile-property"></a>
<!-- :::item name="releaseNotesFile"::: -->
:::moniker range="<=azure-pipelines"

**`releaseNotesFile`** - **Release notes file**<br>
`string`. Required when `releaseNotesOption = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects a UTF-8 encoded text file which contains the release notes for this version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="ismandatory-property"></a>
<!-- :::item name="isMandatory"::: -->
:::moniker range="<=azure-pipelines"

**`isMandatory`** - **Require users to update to this release**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The App Center Distribute SDK required to mandate update. Testers are automatically prompted to update.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<a name="distributiongroupid-property"></a>
<!-- :::item name="distributionGroupId"::: -->
:::moniker range="<=azure-pipelines"

**`distributionGroupId`** - **Destination IDs**<br>
[Input alias](index.md#what-are-task-input-aliases): `destinationIds | destinationId`. `string`.<br>
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

:::moniker range=">=azure-pipelines-2022.1"

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

:::moniker range="=azure-pipelines-2022"

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
