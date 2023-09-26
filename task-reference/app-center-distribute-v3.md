---
title: AppCenterDistribute@3 - App Center distribute v3 task
description: Distribute app builds to testers and users via Visual Studio App Center.
ms.date: 09/26/2023
monikerRange: ">=azure-pipelines-2019.1"
---

# AppCenterDistribute@3 - App Center distribute v3 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to distribute app builds to testers and users via Visual Studio App Center.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# App Center distribute v3
# Distribute app builds to testers and users via Visual Studio App Center.
- task: AppCenterDistribute@3
  inputs:
    serverEndpoint: # string. Required. App Center service connection. 
    appSlug: # string. Required. App slug. 
    appFile: # string. Alias: app. Required. Binary file path. 
    #buildVersion: # string. Build version. 
    releaseNotesOption: 'input' # 'input' | 'file'. Alias: releaseNotesSelection. Required. Create release notes. Default: input.
    releaseNotesInput: # string. Required when releaseNotesSelection = input. Release notes. 
    #releaseNotesFile: # string. Required when releaseNotesSelection = file. Release notes file. 
    #isMandatory: false # boolean. Require users to update to this release. Default: false.
    destinationType: 'groups' # 'groups' | 'store'. Required. Release destination. Default: groups.
    #distributionGroupId: # string. Alias: destinationGroupIds. Optional. Use when destinationType = groups. Destination IDs. 
    #destinationStoreId: # string. Required when destinationType = store. Destination ID. 
    #isSilent: # boolean. Optional. Use when destinationType = groups. Do not notify testers. Release will still be available to install. 
  # Symbols
    #symbolsOption: 'Apple' # 'Apple' | 'Android' | 'UWP'. Alias: symbolsType. Symbols type. Default: Apple.
    #symbolsPath: # string. Optional. Use when symbolsType == AndroidNative || symbolsType = Windows. Symbols path. 
    #appxsymPath: # string. Optional. Use when symbolsType = UWP. Symbols path (*.appxsym). 
    #symbolsDsymFiles: # string. Alias: dsymPath. Optional. Use when symbolsType = Apple. dSYM path. 
    #symbolsMappingTxtFile: # string. Alias: mappingTxtPath. Optional. Use when symbolsType = Android. Mapping file. 
    #nativeLibrariesPath: # string. Optional. Use when symbolsType == Android. Native Library File Path. 
    #symbolsIncludeParentDirectory: # boolean. Alias: packParentFolder. Optional. Use when symbolsType = Apple. Include all items in parent folder.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# App Center distribute v3
# Distribute app builds to testers and users via Visual Studio App Center.
- task: AppCenterDistribute@3
  inputs:
    serverEndpoint: # string. Required. App Center service connection. 
    appSlug: # string. Required. App slug. 
    appFile: # string. Alias: app. Required. Binary file path. 
    releaseNotesOption: 'input' # 'input' | 'file'. Alias: releaseNotesSelection. Required. Create release notes. Default: input.
    releaseNotesInput: # string. Required when releaseNotesSelection = input. Release notes. 
    #releaseNotesFile: # string. Required when releaseNotesSelection = file. Release notes file. 
    #isMandatory: false # boolean. Require users to update to this release. Default: false.
    destinationType: 'groups' # 'groups' | 'store'. Required. Release destination. Default: groups.
    #distributionGroupId: # string. Alias: destinationGroupIds. Optional. Use when destinationType = groups. Destination IDs. 
    #destinationStoreId: # string. Required when destinationType = store. Destination ID. 
    #isSilent: # boolean. Optional. Use when destinationType = groups. Do not notify testers. Release will still be available to install. 
  # Symbols
    #symbolsOption: 'Apple' # 'Apple' | 'Android'. Alias: symbolsType. Symbols type. Default: Apple.
    #symbolsPath: # string. Optional. Use when symbolsType == AndroidNative || symbolsType = Windows. Symbols path. 
    #symbolsPdbFiles: '**/*.pdb' # string. Alias: pdbPath. Optional. Use when symbolsType = UWP. Symbols path (*.pdb). Default: **/*.pdb.
    #symbolsDsymFiles: # string. Alias: dsymPath. Optional. Use when symbolsType = Apple. dSYM path. 
    #symbolsMappingTxtFile: # string. Alias: mappingTxtPath. Optional. Use when symbolsType = Android. Mapping file. 
    #symbolsIncludeParentDirectory: # boolean. Alias: packParentFolder. Optional. Use when symbolsType = Apple. Include all items in parent folder.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="serverEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`serverEndpoint`** - **App Center service connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the service connection for Visual Studio App Center. To create one, click the `Manage` link and create a new service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSlug"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appSlug`** - **App slug**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The app slug is in the format of `{username}/{app_identifier}`.  To locate `{username}` and `{app_identifier}` for an app, click on its name from [App Center](https://appcenter.ms/apps), and the resulting URL is in the format of `https://appcenter.ms/users/**{username}**/apps/**{app_identifier}**`. If you are using orgs, the app slug is of the format `{orgname}/{app_identifier}`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appFile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appFile`** - **Binary file path**<br>
Input alias: `app`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to the APK/AAB or IPA file you want to publish.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildVersion"::: -->
:::moniker range=">=azure-pipelines-2020"

**`buildVersion`** - **Build version**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The build version of the uploading binary which needs to be specified for `.zip` and `.msi`. This value will be ignored unless the platform is WPF or WinForms.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsOption"::: -->
:::moniker range=">=azure-pipelines-2020"

**`symbolsOption`** - **Symbols type**<br>
Input alias: `symbolsType`. `string`. Allowed values: `Apple`, `Android`, `UWP`. Default value: `Apple`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes symbol files to receive symbolicated stack traces in App Center Diagnostics.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`symbolsOption`** - **Symbols type**<br>
Input alias: `symbolsType`. `string`. Allowed values: `Apple`, `Android`. Default value: `Apple`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Includes symbol files to receive symbolicated stack traces in App Center Diagnostics.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`symbolsPath`** - **Symbols path**<br>
`string`. Optional. Use when `symbolsType == AndroidNative || symbolsType = Windows`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to the symbols folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appxsymPath"::: -->
:::moniker range=">=azure-pipelines-2020"

**`appxsymPath`** - **Symbols path (*.appxsym)**<br>
`string`. Optional. Use when `symbolsType = UWP`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path to the APPXSYM symbols file. Path may contain [wildcards](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsDsymFiles"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`symbolsDsymFiles`** - **dSYM path**<br>
Input alias: `dsymPath`. `string`. Optional. Use when `symbolsType = Apple`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to dSYM folder. Path may contain [wildcards](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsMappingTxtFile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`symbolsMappingTxtFile`** - **Mapping file**<br>
Input alias: `mappingTxtPath`. `string`. Optional. Use when `symbolsType = Android`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to Android's `mapping.txt` file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nativeLibrariesPath"::: -->
:::moniker range=">=azure-pipelines-2020"

**`nativeLibrariesPath`** - **Native Library File Path**<br>
`string`. Optional. Use when `symbolsType == Android`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to the additional native libraries you want to publish (e.g. .so files).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsIncludeParentDirectory"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`symbolsIncludeParentDirectory`** - **Include all items in parent folder**<br>
Input alias: `packParentFolder`. `boolean`. Optional. Use when `symbolsType = Apple`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uploads the selected symbols file or folder and all other items inside the same parent folder. This is required for React Native apps.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotesOption"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`releaseNotesOption`** - **Create release notes**<br>
Input alias: `releaseNotesSelection`. `string`. Required. Allowed values: `input` (Enter Release Notes), `file` (Select Release Notes File). Default value: `input`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The release notes will be attached to the release and shown to testers on the installation page.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotesInput"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`releaseNotesInput`** - **Release notes**<br>
`string`. Required when `releaseNotesSelection = input`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The release notes for this version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseNotesFile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

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
<!-- :::item name="destinationType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`destinationType`** - **Release destination**<br>
`string`. Required. Allowed values: `groups`, `store`. Default value: `groups`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Each release is distributed to either groups or a store.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="distributionGroupId"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`distributionGroupId`** - **Destination IDs**<br>
Input alias: `destinationGroupIds`. `string`. Optional. Use when `destinationType = groups`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The IDs of the distribution groups who will receive the build release. Leave it empty to use the default group, and use commas or semicolons to separate multiple IDs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="destinationStoreId"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`destinationStoreId`** - **Destination ID**<br>
`string`. Required when `destinationType = store`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The IDs of the distribution store that will receive the build release.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isSilent"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`isSilent`** - **Do not notify testers. Release will still be available to install.**<br>
`boolean`. Optional. Use when `destinationType = groups`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Testers do not receive an email for new releases.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="symbolsPdbFiles"::: -->
:::moniker range="=azure-pipelines-2019.1"

**`symbolsPdbFiles`** - **Symbols path (*.pdb)**<br>
Input alias: `pdbPath`. `string`. Optional. Use when `symbolsType = UWP`. Default value: `**/*.pdb`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to PDB symbols files. Path may contain [wildcards](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
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

Use this task to distribute app builds to testers and users through App Center.
- [Sign up with App Center](https://appcenter.ms/signup?utm_source=DevOps&utm_medium=Azure&utm_campaign=docs) first.
- For details about using this task, see the App Center documentation article [Deploy Azure DevOps Builds with App Center](/appcenter/distribution/vsts-deploy).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

This example pipeline builds an Android app, runs tests, and publishes the app using App Center Distribute.

```yaml
# Android
# Build your Android project with Gradle.
# Add steps that test, sign, and distribute the APK, save build artifacts, and more:
# https://learn.microsoft.com/azure/devops/pipelines/ecosystems/android

pool:
  vmImage: 'macOS-latest'
steps:

- script: sudo npm install -g appcenter-cli
- script: appcenter login --token {YOUR_TOKEN}

- task: Gradle@2
  inputs:
    workingDirectory: ''
    gradleWrapperFile: 'gradlew'
    gradleOptions: '-Xmx3072m'
    publishJUnitResults: false
    testResultsFiles: '**/TEST-*.xml'
    tasks: build

- task: CopyFiles@2
  inputs:
    contents: '**/*.apk'
    targetFolder: '$(build.artifactStagingDirectory)'

- task: PublishBuildArtifacts@1
  inputs:
    pathToPublish: '$(build.artifactStagingDirectory)'
    artifactName: 'outputs'
    artifactType: 'container'

# Run tests using the App Center CLI
- script: appcenter test run espresso --app "{APP_CENTER_SLUG}" --devices "{DEVICE}" --app-path {APP_FILE} --test-series "master" --locale "en_US" --build-dir {PAT_ESPRESSO} --debug

# Distribute the app
- task: AppCenterDistribute@3
  inputs:
    serverEndpoint: 'AppCenter'
    appSlug: '$(APP_CENTER_SLUG)'
    appFile: '$(APP_FILE)' # Relative path from the repo root to the APK or IPA file you want to publish
    symbolsOption: 'Android'
    releaseNotesOption: 'input'
    releaseNotesInput: 'Here are the release notes for this version.'
    destinationType: 'groups'
```
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

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2022"

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
