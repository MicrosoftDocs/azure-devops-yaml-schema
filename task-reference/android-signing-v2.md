---
title: AndroidSigning@2 - Android Signing v2 task
description: Sign and align Android APK files (task version 2).
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# AndroidSigning@2 - Android Signing v2 task

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
# Android Signing v2
# Sign and align Android APK files.
- task: AndroidSigning@2
  inputs:
    apkFiles: '**/*.apk' # string. Required. APK files. Default: '**/*.apk'.
  # Signing Options
    #jarsign: true # boolean. Sign the APK. Default: true.
    jarsignerKeystoreFile: # string. Required when jarsign = true. Keystore file. 
    #jarsignerKeystorePassword: # string. Optional. Use when jarsign = true. Keystore password. 
    #jarsignerKeystoreAlias: # string. Optional. Use when jarsign = true. Alias. 
    #jarsignerKeyPassword: # string. Optional. Use when jarsign = true. Key password. 
    #jarsignerArguments: '-verbose -sigalg MD5withRSA -digestalg SHA1' # string. Optional. Use when jarsign = true. Jarsigner arguments. Default: '-verbose -sigalg MD5withRSA -digestalg SHA1'.
  # Zipalign Options
    #zipalign: true # boolean. Zipalign. Default: true.
    #zipalignFile: # string. Optional. Use when zipalign = true. Zipalign location.
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

<!-- :::item name="apkFiles"::: -->
:::moniker range="<=azure-pipelines"

**`apkFiles`** - **APK files**<br>
Input alias: `files`. Type: string. Required. Default value: '**/*.apk'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repo root to the APK(s) you want to sign. You can use wildcards to specify multiple files ([more information](https://go.microsoft.com/fwlink/?linkid=856077)). For example, `**/bin/*.apk` for all .APK files in the 'bin' subfolder.
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
<!-- :::item name="jarsignerKeystoreFile"::: -->
:::moniker range="<=azure-pipelines"

**`jarsignerKeystoreFile`** - **Keystore file**<br>
Input alias: `keystoreFile`. Type: string. Required when jarsign = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the keystore file that was uploaded to `Secure Files` to be used to sign the APK.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jarsignerKeystorePassword"::: -->
:::moniker range="<=azure-pipelines"

**`jarsignerKeystorePassword`** - **Keystore password**<br>
Input alias: `keystorePass`. Type: string. Optional. Use when jarsign = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the password for the provided keystore file. Use a new variable with its lock enabled on the Variables tab to encrypt this value.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jarsignerKeystoreAlias"::: -->
:::moniker range="<=azure-pipelines"

**`jarsignerKeystoreAlias`** - **Alias**<br>
Input alias: `keystoreAlias`. Type: string. Optional. Use when jarsign = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the alias that identifies the public/private key pair to be used in the keystore file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jarsignerKeyPassword"::: -->
:::moniker range="<=azure-pipelines"

**`jarsignerKeyPassword`** - **Key password**<br>
Input alias: `keyPass`. Type: string. Optional. Use when jarsign = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the key password for the alias and keystore file. Use a new variable with its lock enabled on the Variables tab to encrypt this value.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jarsignerArguments"::: -->
:::moniker range="<=azure-pipelines"

**`jarsignerArguments`** - **Jarsigner arguments**<br>
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
<!-- :::item name="zipalignFile"::: -->
:::moniker range="<=azure-pipelines"

**`zipalignFile`** - **Zipalign location**<br>
Input alias: `zipalignLocation`. Type: string. Optional. Use when zipalign = true.<br>
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

:::moniker range=">=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: JDK |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task runs using the following [command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): restricted |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): Setting variables is disabled |
| Agent version |  2.182.1 or greater |
| Task category | Build |

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: JDK |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.116.0 or greater |
| Task category | Build |

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: JDK, AndroidSDK |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.116.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->