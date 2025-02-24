---
title: AndroidBuild@1 - Android Build v1 task
description: AndroidBuild@1 is deprecated. Use Gradle.
ms.date: 02/24/2025
monikerRange: "<=azure-pipelines"
---

# AndroidBuild@1 - Android Build v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to build an Android app using Gradle and (optionally) start the emulator for unit tests.

The AndroidBuild@1 task is deprecated. Use the [Gradle task](/azure/devops/pipelines/tasks/reference/gradle-v3) instead.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Android Build v1
# AndroidBuild@1 is deprecated. Use Gradle.
- task: AndroidBuild@1
  inputs:
    #gradleWrapper: # string. Location of Gradle Wrapper. 
    #gradleProj: # string. Project Directory. 
    #gradleArguments: 'build' # string. Gradle Arguments. Default: build.
  # Android Virtual Device (AVD) Options
    avdName: 'AndroidBuildEmulator' # string. Required. Name. Default: AndroidBuildEmulator.
    #createAvd: AndroidBuildEmulator # boolean. Create AVD. Default: AndroidBuildEmulator.
    #emulatorTarget: 'android-19' # string. Required when createAvd = true. AVD Target SDK. Default: android-19.
    #emulatorDevice: 'Nexus 5' # string. Optional. Use when createAvd = true. AVD Device. Default: Nexus 5.
    #avdAbi: 'default/armeabi-v7a' # string. Required when createAvd = true. AVD ABI. Default: default/armeabi-v7a.
    #avdForce: false # boolean. Optional. Use when createAvd = true. Overwrite Existing AVD. Default: false.
    #avdOptionalArgs: # string. Optional. Use when createAvd = true. Create AVD Optional Arguments. 
  # Emulator Options
    #startEmulator: false # boolean. Start and Stop Android Emulator. Default: false.
    #emulatorTimeout: '300' # string. Required when startEmulator = true. Timeout in Seconds. Default: 300.
    #emulatorHeadless: false # boolean. Optional. Use when startEmulator = true. Headless Display. Default: false.
    #emulatorOptionalArgs: '-no-snapshot-load -no-snapshot-save' # string. Optional. Use when startEmulator = true. Emulator Optional Arguments. Default: -no-snapshot-load -no-snapshot-save.
    #deleteAvd: false # boolean. Optional. Use when startEmulator = true. Delete AVD. Default: false.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="gradleWrapper"::: -->
:::moniker range="<=azure-pipelines"

**`gradleWrapper`** - **Location of Gradle Wrapper**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The location of the `gradlew` wrapper that is used for the build. Agents on Windows (including Microsoft-hosted agents) must use the `gradlew.bat` wrapper. Agents on Linux or macOS can use the `gradlew` shell script. Learn more about [the Gradle Wrapper](/azure/devops/pipelines/tasks/reference/gradle-v3).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="gradleProj"::: -->
:::moniker range="<=azure-pipelines"

**`gradleProj`** - **Project Directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root to the root directory of the application. This is most likely to be where the `build.gradle` file is located.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="gradleArguments"::: -->
:::moniker range="<=azure-pipelines"

**`gradleArguments`** - **Gradle Arguments**<br>
`string`. Default value: `build`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides any options to pass to the Gradle command line. Learn more about the [Gradle command line](https://docs.gradle.org/current/userguide/command_line_interface.html).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="avdName"::: -->
:::moniker range="<=azure-pipelines"

**`avdName`** - **Name**<br>
`string`. Required. Default value: `AndroidBuildEmulator`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Android Virtual Device (AVD) to be started or created.

You must deploy your own agent to use this string. You cannot use a Microsoft-hosted pool if you want to create an AVD.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="createAvd"::: -->
:::moniker range="<=azure-pipelines"

**`createAvd`** - **Create AVD**<br>
`boolean`. Default value: `AndroidBuildEmulator`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Creates the named Android Virtual Device (AVD).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="emulatorTarget"::: -->
:::moniker range="<=azure-pipelines"

**`emulatorTarget`** - **AVD Target SDK**<br>
`string`. Required when `createAvd = true`. Default value: `android-19`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Android SDK version that the Android Virtual Device (AVD) targets.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="emulatorDevice"::: -->
:::moniker range="<=azure-pipelines"

**`emulatorDevice`** - **AVD Device**<br>
`string`. Optional. Use when `createAvd = true`. Default value: `Nexus 5`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The device pipeline that may be used. This can be a device index or an Id.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="avdAbi"::: -->
:::moniker range="<=azure-pipelines"

**`avdAbi`** - **AVD ABI**<br>
`string`. Required when `createAvd = true`. Default value: `default/armeabi-v7a`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Application Binary Interface (ABI) to use for the Android Virtual Device (AVD). Learn more about [ABI Management](https://developer.android.com/ndk/guides/abis.html).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="avdForce"::: -->
:::moniker range="<=azure-pipelines"

**`avdForce`** - **Overwrite Existing AVD**<br>
`boolean`. Optional. Use when `createAvd = true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Overwrites an existing AVD by passing `--force` to the `android create avd` command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="avdOptionalArgs"::: -->
:::moniker range="<=azure-pipelines"

**`avdOptionalArgs`** - **Create AVD Optional Arguments**<br>
`string`. Optional. Use when `createAvd = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Creates additional arguments to pass to `android create avd`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="startEmulator"::: -->
:::moniker range="<=azure-pipelines"

**`startEmulator`** - **Start and Stop Android Emulator**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Starts and stops the Android emulator after the Android Build task finishes.

You must deploy your own agent to use this boolean. You cannot use a Microsoft-hosted pool if you want to use an emulator. Learn more about [Azure Pipeline agents](/azure/devops/pipelines/agents/agents).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="emulatorTimeout"::: -->
:::moniker range="<=azure-pipelines"

**`emulatorTimeout`** - **Timeout in Seconds**<br>
`string`. Required when `startEmulator = true`. Default value: `300`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Defines how long (in seconds) the build will wait for the emulator to start.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="emulatorHeadless"::: -->
:::moniker range="<=azure-pipelines"

**`emulatorHeadless`** - **Headless Display**<br>
`boolean`. Optional. Use when `startEmulator = true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Starts the emulator with no GUI (headless mode) by using the `-no-skin -no-audio -no-window` value.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="emulatorOptionalArgs"::: -->
:::moniker range="<=azure-pipelines"

**`emulatorOptionalArgs`** - **Emulator Optional Arguments**<br>
`string`. Optional. Use when `startEmulator = true`. Default value: `-no-snapshot-load -no-snapshot-save`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides additional arguments to pass to the `emulator` command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deleteAvd"::: -->
:::moniker range="<=azure-pipelines"

**`deleteAvd`** - **Delete AVD**<br>
`boolean`. Optional. Use when `startEmulator = true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Deletes the AVD upon task completion.
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

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: AndroidSDK |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.83.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
