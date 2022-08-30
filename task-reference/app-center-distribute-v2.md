---
title: AppCenterDistribute@2 - App Center distribute v2 task
description: Distribute app builds to testers and users via Visual Studio App Center (task version 2).
ms.date: 08/10/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# AppCenterDistribute@2 - App Center distribute v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Distribute app builds to testers and users via Visual Studio App Center.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# App Center distribute v2
# Distribute app builds to testers and users via Visual Studio App Center.
- task: AppCenterDistribute@2
  inputs:
    serverEndpoint: # string. Required. App Center service connection. 
    appSlug: # string. Required. App slug. 
    appFile: # string. Required. Binary file path. 
    releaseNotesOption: 'input' # 'input' | 'file'. Required. Create release notes. Default: 'input'.
    releaseNotesInput: # string. Required when releaseNotesSelection = input. Release notes. 
    #releaseNotesFile: # string. Required when releaseNotesSelection = file. Release notes file. 
    #isMandatory: false # boolean. Require users to update to this release. Default: false.
    #distributionGroupId: # string. Destination IDs. 
  # Symbols
    #symbolsOption: 'Apple' # 'Apple'. Symbols type. Default: 'Apple'.
    #symbolsPath: # string. Optional. Use when symbolsType == AndroidNative || symbolsType = Windows. Symbols path. 
    #symbolsPdbFiles: '**/*.pdb' # string. Optional. Use when symbolsType = UWP. Symbols path (*.pdb). Default: '**/*.pdb'.
    #symbolsDsymFiles: # string. Optional. Use when symbolsType = Apple. dSYM path. 
    #symbolsMappingTxtFile: # string. Optional. Use when symbolsType = AndroidJava. Mapping file. 
    #symbolsIncludeParentDirectory: # boolean. Include all items in parent folder.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="serverEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`serverEndpoint`** - **App Center service connection**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the service connection for Visual Studio App Center. To create one, click the Manage link and create a new service connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSlug"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appSlug`** - **App slug**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The app slug is in the format of **{username}/{app_identifier}**.  To locate **{username}** and **{app_identifier}** for an app, click on its name from https://appcenter.ms/apps, and the resulting URL is in the format of [https://appcenter.ms/users/<b>{username}</b>/apps/<b>{app_identifier}</b>](https://appcenter.ms/users/{username}/apps/{app_identifier}). If you are using orgs, the app slug is of the format **{orgname}/{app_identifier}**.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appFile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appFile`** - **Binary file path**<br>
Input alias: `app`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repo root to the APK or IPA file you want to publish.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsOption"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`symbolsOption`** - **Symbols type**<br>
Input alias: `symbolsType`. Type: string. Allowed values: 'Apple'. Default value: 'Apple'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Include symbol files to receive symbolicated stack traces in App Center Diagnostics.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`symbolsPath`** - **Symbols path**<br>
Type: string. Optional. Use when symbolsType == AndroidNative || symbolsType = Windows.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repo root to the symbols folder.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsPdbFiles"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`symbolsPdbFiles`** - **Symbols path (*.pdb)**<br>
Input alias: `pdbPath`. Type: string. Optional. Use when symbolsType = UWP. Default value: '**/*.pdb'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repo root to PDB symbols files. Path may contain wildcards.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsDsymFiles"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`symbolsDsymFiles`** - **dSYM path**<br>
Input alias: `dsymPath`. Type: string. Optional. Use when symbolsType = Apple.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repo root to dSYM folder. Path may contain wildcards.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsMappingTxtFile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`symbolsMappingTxtFile`** - **Mapping file**<br>
Input alias: `mappingTxtPath`. Type: string. Optional. Use when symbolsType = AndroidJava.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repo root to Android's mapping.txt file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsIncludeParentDirectory"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`symbolsIncludeParentDirectory`** - **Include all items in parent folder**<br>
Input alias: `packParentFolder`. Type: boolean.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Upload the selected symbols file or folder and all other items inside the same parent folder. This is required for React Native apps.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotesOption"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`releaseNotesOption`** - **Create release notes**<br>
Input alias: `releaseNotesSelection`. Type: string. Required. Allowed values: 'input', 'file'. Default value: 'input'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Release notes will be attached to the release and shown to testers on the installation page.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotesInput"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`releaseNotesInput`** - **Release notes**<br>
Type: string. Required when releaseNotesSelection = input.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Release notes for this version.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotesFile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`releaseNotesFile`** - **Release notes file**<br>
Type: string. Required when releaseNotesSelection = file.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a UTF-8 encoded text file which contains the Release Notes for this version.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isMandatory"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`isMandatory`** - **Require users to update to this release**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
App Center Distribute SDK required to mandate update. Testers will automatically be prompted to update.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="distributionGroupId"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`distributionGroupId`** - **Destination IDs**<br>
Input alias: `destinationIds | destinationId`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
ID of the distribution group or store the app will deploy to. Leave it empty to use the default group.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019.1"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Added support for multiple destinations.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019.1"

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