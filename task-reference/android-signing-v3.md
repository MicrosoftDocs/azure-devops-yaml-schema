---
title: AndroidSigning@3 - Android Signing v3 task
description: Sign and align Android APK files.
ms.date: 06/24/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# AndroidSigning@3 - Android Signing v3 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task in a pipeline to sign and align Android APK files.
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
    apkFiles: '**/*.apk' # string. Alias: files. Required. APK files. Default: **/*.apk.
  # Signing Options
    #apksign: true # boolean. Sign the APK. Default: true.
    apksignerKeystoreFile: # string. Alias: keystoreFile. Required when apksign = true. Keystore file. 
    #apksignerKeystorePassword: # string. Alias: keystorePass. Optional. Use when apksign = true. Keystore password. 
    #apksignerKeystoreAlias: # string. Alias: keystoreAlias. Optional. Use when apksign = true. Alias. 
    #apksignerKeyPassword: # string. Alias: keyPass. Optional. Use when apksign = true. Key password. 
    #apksignerVersion: 'latest' # string. Optional. Use when apksign = true. apksigner version. Default: latest.
    #apksignerArguments: '--verbose' # string. Optional. Use when apksign = true. apksigner arguments. Default: --verbose.
    #apksignerFile: # string. Alias: apksignerLocation. Optional. Use when apksign = true. apksigner location. 
  # Zipalign Options
    #zipalign: true # boolean. Zipalign. Default: true.
    #zipalignVersion: 'latest' # string. Optional. Use when zipalign = true. Zipalign version. Default: latest.
    #zipalignFile: # string. Alias: zipalignLocation. Optional. Use when zipalign = true. Zipalign location.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Android Signing v3
# Sign and align Android APK files.
- task: AndroidSigning@3
  inputs:
    apkFiles: '**/*.apk' # string. Alias: files. Required. APK files. Default: **/*.apk.
  # Signing Options
    #apksign: true # boolean. Sign the APK. Default: true.
    apksignerKeystoreFile: # string. Alias: keystoreFile. Required when apksign = true. Keystore file. 
    #apksignerKeystorePassword: # string. Alias: keystorePass. Optional. Use when apksign = true. Keystore password. 
    #apksignerKeystoreAlias: # string. Alias: keystoreAlias. Optional. Use when apksign = true. Alias. 
    #apksignerKeyPassword: # string. Alias: keyPass. Optional. Use when apksign = true. Key password. 
    #apksignerArguments: '--verbose' # string. Optional. Use when apksign = true. apksigner arguments. Default: --verbose.
    #apksignerFile: # string. Alias: apksignerLocation. Optional. Use when apksign = true. apksigner location. 
  # Zipalign Options
    #zipalign: true # boolean. Zipalign. Default: true.
    #zipalignFile: # string. Alias: zipalignLocation. Optional. Use when zipalign = true. Zipalign location.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="apkFiles"::: -->
:::moniker range="<=azure-pipelines"

**`apkFiles`** - **APK files**<br>
[Input alias](index.md#what-are-task-input-aliases): `files`. `string`. Required. Default value: `**/*.apk`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to the APK(s) you want to sign. You can use [wildcards](/azure/devops/pipelines/tasks/file-matching-patterns) to specify multiple files. For example:

- `outputs\apk*.apk` to sign all .APK files in the `outputs\apk\` subfolder.
- `**/bin/*.apk` to sign all .APK files in all `bin` subfolders.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksign"::: -->
:::moniker range="<=azure-pipelines"

**`apksign`** - **Sign the APK**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Signs the APK with a provided Android Keystore file. Unsigned APKs can only run in an emulator. APKs must be signed to run on a device.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksignerKeystoreFile"::: -->
:::moniker range="<=azure-pipelines"

**`apksignerKeystoreFile`** - **Keystore file**<br>
[Input alias](index.md#what-are-task-input-aliases): `keystoreFile`. `string`. Required when `apksign = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file path to the Android Keystore file that is used to sign the APK. This file must be uploaded to the [secure files](/azure/devops/pipelines/library/secure-files) library, where it is securely stored with encryption. The Android Keystore file is removed from the agent machine when the pipeline completes.

The file can either be checked into source control or placed on the build machine directly by an administrator. It is recommended to encrypt the keystore file in source control and use the `Decrypt File` task to decrypt the file during the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksignerKeystorePassword"::: -->
:::moniker range="<=azure-pipelines"

**`apksignerKeystorePassword`** - **Keystore password**<br>
[Input alias](index.md#what-are-task-input-aliases): `keystorePass`. `string`. Optional. Use when `apksign = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The key password for the provided Android Keystore file.
> [!IMPORTANT]
> Use a new variable with its lock enabled on the Variables pane to encrypt this value. See [secret variables](/azure/devops/pipelines/process/variables).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksignerKeystoreAlias"::: -->
:::moniker range="<=azure-pipelines"

**`apksignerKeystoreAlias`** - **Alias**<br>
[Input alias](index.md#what-are-task-input-aliases): `keystoreAlias`. `string`. Optional. Use when `apksign = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The alias that identifies the public/private key pair to be used in the Android Keystore file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksignerKeyPassword"::: -->
:::moniker range="<=azure-pipelines"

**`apksignerKeyPassword`** - **Key password**<br>
[Input alias](index.md#what-are-task-input-aliases): `keyPass`. `string`. Optional. Use when `apksign = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The key password for the alias and keystore file.

> [!IMPORTANT]
> Use a new variable with its lock enabled on the Variables pane to encrypt this value. See [secret variables](/azure/devops/pipelines/process/variables).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksignerVersion"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`apksignerVersion`** - **apksigner version**<br>
`string`. Optional. Use when `apksign = true`. Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Android SDK build-tools version that the `apksigner` executable uses for the task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksignerArguments"::: -->
:::moniker range="<=azure-pipelines"

**`apksignerArguments`** - **apksigner arguments**<br>
`string`. Optional. Use when `apksign = true`. Default value: `--verbose`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides options to pass to the `apksigner` command line. See the [apksigner documentation](https://developer.android.com/studio/command-line/apksigner).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="apksignerFile"::: -->
:::moniker range="<=azure-pipelines"

**`apksignerFile`** - **apksigner location**<br>
[Input alias](index.md#what-are-task-input-aliases): `apksignerLocation`. `string`. Optional. Use when `apksign = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the apksigner executable used during signing. This defaults to the apksigner found in the Android SDK version folder that your application builds against.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="zipalign"::: -->
:::moniker range="<=azure-pipelines"

**`zipalign`** - **Zipalign**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select if you want to zipalign your package. This reduces the amount of RAM consumed by an app.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="zipalignVersion"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`zipalignVersion`** - **Zipalign version**<br>
`string`. Optional. Use when `zipalign = true`. Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Android SDK build-tools version that the `zipalign` executable uses for the task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="zipalignFile"::: -->
:::moniker range="<=azure-pipelines"

**`zipalignFile`** - **Zipalign location**<br>
[Input alias](index.md#what-are-task-input-aliases): `zipalignLocation`. `string`. Optional. Use when `zipalign = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the `zipalign` executable used during signing. This defaults to the `zipalign` found in the Android SDK version folder that your application builds against.
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

Use this task in a pipeline to sign and align Android APK files.

This version of the task uses `apksigner` instead of `jarsigner` to sign APKs. [AdnroidSigning@2](./android-signing-v2.md) uses jarsigner to sign APKs and AABs.
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

:::moniker range="<=azure-pipelines-2020.1"

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

<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->