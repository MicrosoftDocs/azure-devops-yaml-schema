---
title: AndroidSigning@3 - Android Signing v3 task
description: Sign and align Android APK files.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019"
---

# AndroidSigning@3 - Android Signing v3 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Sign and align Android APK files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020.1"

```yaml
# Android Signing v3
# Sign and align Android APK files.
- task: AndroidSigning@3
  inputs:
    apkFiles: '**/*.apk' # string. Required. APK files. Default: '**/*.apk'.
  # Signing Options
    #apksign: true # boolean. Sign the APK. Default: true.
    apksignerKeystoreFile: # string. Required when apksign = true. Keystore file. 
    #apksignerKeystorePassword: # string. Optional. Use when apksign = true. Keystore password. 
    #apksignerKeystoreAlias: # string. Optional. Use when apksign = true. Alias. 
    #apksignerKeyPassword: # string. Optional. Use when apksign = true. Key password. 
    #apksignerVersion: 'latest' # string. Optional. Use when apksign = true. apksigner version. Default: 'latest'.
    #apksignerArguments: '--verbose' # string. Optional. Use when apksign = true. apksigner arguments. Default: '--verbose'.
    #apksignerFile: # string. Optional. Use when apksign = true. apksigner location. 
  # Zipalign Options
    #zipalign: true # boolean. Zipalign. Default: true.
    #zipalignVersion: 'latest' # string. Optional. Use when zipalign = true. Zipalign version. Default: 'latest'.
    #zipalignFile: # string. Optional. Use when zipalign = true. Zipalign location.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020"

```yaml
# Android Signing v3
# Sign and align Android APK files.
- task: AndroidSigning@3
  inputs:
    apkFiles: '**/*.apk' # string. Required. APK files. Default: '**/*.apk'.
  # Signing Options
    #apksign: true # boolean. Sign the APK. Default: true.
    apksignerKeystoreFile: # string. Required when apksign = true. Keystore file. 
    #apksignerKeystorePassword: # string. Optional. Use when apksign = true. Keystore password. 
    #apksignerKeystoreAlias: # string. Optional. Use when apksign = true. Alias. 
    #apksignerKeyPassword: # string. Optional. Use when apksign = true. Key password. 
    #apksignerArguments: '--verbose' # string. Optional. Use when apksign = true. apksigner arguments. Default: '--verbose'.
    #apksignerFile: # string. Optional. Use when apksign = true. apksigner location. 
  # Zipalign Options
    #zipalign: true # boolean. Zipalign. Default: true.
    #zipalignFile: # string. Optional. Use when zipalign = true. Zipalign location.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="apkFiles"::: -->
:::moniker range=">=azure-pipelines-2019"

**`apkFiles`** - **APK files**<br>
Input alias: `files`. Type: string. Required. Default value: '**/*.apk'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repo root to the APK(s) you want to sign. You can use wildcards to specify multiple files ([more information](https://go.microsoft.com/fwlink/?linkid=856077)). For example, `**\bin\*.apk` to sign all .APK files in all 'bin' subfolder and `outputs\apk*.apk` to sign all .APK files in the outputs\apk\ subfolder
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksign"::: -->
:::moniker range=">=azure-pipelines-2019"

**`apksign`** - **Sign the APK**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to sign the APK with a provided keystore file. Unsigned APKs can only run in an emulator. APKs must be signed to run on a device.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksignerKeystoreFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`apksignerKeystoreFile`** - **Keystore file**<br>
Input alias: `keystoreFile`. Type: string. Required when apksign = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select or enter the file name of the Android Keystore file that should be used to sign the APK. This file must be uploaded to the [secure files](/azure/devops/pipelines/library/secure-files) library where it is securely stored with encryption. The Android Keystore file will be used to sign the APK, but will be removed from the agent machine when the pipeline completes.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksignerKeystorePassword"::: -->
:::moniker range=">=azure-pipelines-2019"

**`apksignerKeystorePassword`** - **Keystore password**<br>
Input alias: `keystorePass`. Type: string. Optional. Use when apksign = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the password for the provided keystore file.
> [!IMPORTANT]
> Use a new variable with its lock enabled on the Variables pane to encrypt this value. See [secret variables](/azure/devops/pipelines/process/variables).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksignerKeystoreAlias"::: -->
:::moniker range=">=azure-pipelines-2019"

**`apksignerKeystoreAlias`** - **Alias**<br>
Input alias: `keystoreAlias`. Type: string. Optional. Use when apksign = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the alias that identifies the public/private key pair to be used in the keystore file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksignerKeyPassword"::: -->
:::moniker range=">=azure-pipelines-2019"

**`apksignerKeyPassword`** - **Key password**<br>
Input alias: `keyPass`. Type: string. Optional. Use when apksign = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the key password for the alias and keystore file.

> [!IMPORTANT]
> Use a new variable with its lock enabled on the Variables pane to encrypt this value. See [secret variables](/azure/devops/pipelines/process/variables). 
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksignerVersion"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`apksignerVersion`** - **apksigner version**<br>
Type: string. Optional. Use when apksign = true. Default value: 'latest'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter Android SDK build-tools version to look apksigner executable from.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksignerArguments"::: -->
:::moniker range=">=azure-pipelines-2019"

**`apksignerArguments`** - **apksigner arguments**<br>
Type: string. Optional. Use when apksign = true. Default value: '--verbose'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide any options to pass to the apksigner command line. Default is: --verbose. See the [apksigner documentation](https://developer.android.com/studio/command-line/apksigner).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksignerFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`apksignerFile`** - **apksigner location**<br>
Input alias: `apksignerLocation`. Type: string. Optional. Use when apksign = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally specify the location of the apksigner executable used during signing. This defaults to the apksigner found in the Android SDK version folder that your application builds against.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="zipalign"::: -->
:::moniker range=">=azure-pipelines-2019"

**`zipalign`** - **Zipalign**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select if you want to zipalign your package. This reduces the amount of RAM consumed by an app.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="zipalignVersion"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`zipalignVersion`** - **Zipalign version**<br>
Type: string. Optional. Use when zipalign = true. Default value: 'latest'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter Android SDK build-tools version to look zipalign executable from.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="zipalignFile"::: -->
:::moniker range=">=azure-pipelines-2019"

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

:::moniker range=">=azure-pipelines-2019"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task in a pipeline to sign and align Android APK files.

This version of the task uses apksigner instead of jarsigner to sign APKs.
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

:::moniker range="=azure-pipelines-2019"

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