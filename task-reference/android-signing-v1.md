---
title: AndroidSigning@1 - Android Signing v1 task
description: Sign and align Android APK files (task version 1).
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# AndroidSigning@1 - Android Signing v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Sign and align Android APK files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Android Signing v1
# Sign and align Android APK files.
- task: AndroidSigning@1
  inputs:
    files: # string. Required. APK Files. 
  # Signing Options
    #jarsign: true # boolean. Sign the APK. Default: true.
    keystoreFile: # string. Required when jarsign = true. Keystore File. 
    #keystorePass: # string. Optional. Use when jarsign = true. Keystore Password. 
    #keystoreAlias: # string. Optional. Use when jarsign = true. Alias. 
    #keyPass: # string. Optional. Use when jarsign = true. Key Password. 
    #jarsignerArguments: '-verbose -sigalg MD5withRSA -digestalg SHA1' # string. Optional. Use when jarsign = true. Jarsigner Arguments. Default: '-verbose -sigalg MD5withRSA -digestalg SHA1'.
  # Zipalign Options
    #zipalign: true # boolean. Zipalign. Default: true.
    #zipalignLocation: # string. Optional. Use when zipalign = true. Zipalign Location.
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

<!-- :::item name="files"::: -->
:::moniker range="<=azure-pipelines"

**`files`** - **APK Files**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repo root to the APK(s) you want to sign. You can use wildcards to specify multiple files. For example, `**/bin/*.apk` for all .APK files in the 'bin' subfolder.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jarsign"::: -->
:::moniker range="<=azure-pipelines"

**`jarsign`** - **Sign the APK**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to sign the APK with a provided keystore file. Unsigned APKs can only run in an emulator. APKs must be signed to run on a device.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="keystoreFile"::: -->
:::moniker range="<=azure-pipelines"

**`keystoreFile`** - **Keystore File**<br>
Type: string. Required when jarsign = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the file path to the keystore file that should be used to sign the APK. It can either be checked into source control or placed on the build machine directly by an administrator. It is recommended to encrypt the keystore file in source control and use the 'Decrypt File' task to decrypt the file during the build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="keystorePass"::: -->
:::moniker range="<=azure-pipelines"

**`keystorePass`** - **Keystore Password**<br>
Type: string. Optional. Use when jarsign = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the password for the provided keystore file. Use a new variable with its lock enabled on the Variables tab to encrypt this value.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="keystoreAlias"::: -->
:::moniker range="<=azure-pipelines"

**`keystoreAlias`** - **Alias**<br>
Type: string. Optional. Use when jarsign = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the alias that identifies the public/private key pair to be used in the keystore file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="keyPass"::: -->
:::moniker range="<=azure-pipelines"

**`keyPass`** - **Key Password**<br>
Type: string. Optional. Use when jarsign = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the key password for the alias and keystore file. Use a new variable with its lock enabled on the Variables tab to encrypt this value.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jarsignerArguments"::: -->
:::moniker range="<=azure-pipelines"

**`jarsignerArguments`** - **Jarsigner Arguments**<br>
Type: string. Optional. Use when jarsign = true. Default value: '-verbose -sigalg MD5withRSA -digestalg SHA1'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide any options to pass to the jarsigner command line. Default is: -verbose -sigalg MD5withRSA -digestalg SHA1.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="zipalign"::: -->
:::moniker range="<=azure-pipelines"

**`zipalign`** - **Zipalign**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select if you want to zipalign your package. This reduces the amount of RAM consumed by an app.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="zipalignLocation"::: -->
:::moniker range="<=azure-pipelines"

**`zipalignLocation`** - **Zipalign Location**<br>
Type: string. Optional. Use when zipalign = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally specify the location of the zipalign executable used during signing. This defaults to the zipalign found in the Android SDK version folder that your application builds against.
<!-- :::editable-content-end::: -->

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

:::moniker range=">=azure-pipelines-2019"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: JDK, AndroidSDK |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.98.1 or greater |
| Task category | Build |

:::moniker-end

:::moniker range="=azure-pipelines-2018"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | All |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: JDK, AndroidSDK |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.98.1 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->