---
title: XamariniOS@1 - Xamarin.iOS v1 task
description: Build an iOS app with Xamarin on macOS (task version 1).
ms.date: 05/06/2025
monikerRange: "<=azure-pipelines"
author: steved0x
ms.author: sdanie
---

# XamariniOS@1 - Xamarin.iOS v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task in a pipeline to build an iOS app with Xamarin on macOS. For more information, see the [Xamarin guidance](/azure/devops/pipelines/ecosystems/xamarin) and [Sign your app during CI](/azure/devops/pipelines/apps/mobile/app-signing).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Xamarin.iOS v1
# Build an iOS app with Xamarin on macOS.
- task: XamariniOS@1
  inputs:
    solutionFile: '**/*.sln' # string. Alias: solution. Required. Solution. Default: **/*.sln.
    configuration: 'Release' # string. Required. Configuration. Default: Release.
    #clean: false # boolean. Clean. Default: false.
    #packageApp: true # boolean. Create app package. Default: true.
    #buildForSimulator: false # boolean. Alias: forSimulator. Build for iOS Simulator. Default: false.
  # Advanced
    #runNugetRestore: true # boolean. Run NuGet restore. Default: true.
    #args: # string. Arguments. 
    #workingDirectory: # string. Alias: cwd. Working directory. 
    #buildToolOption: 'xbuild' # 'xbuild' | 'msbuild'. Alias: buildTool. Build tool. Default: xbuild.
    #mdtoolFile: # string. Alias: mdtoolLocation. Build tool path. 
  # Signing & Provisioning
    #signingOption: 'file' # 'file' | 'id'. Alias: signMethod. Override using. Default: file.
    #signingIdentity: # string. Alias: iosSigningIdentity. Optional. Use when signMethod = id. Signing identity. 
    #signingUnlockDefaultKeychain: false # boolean. Alias: unlockDefaultKeychain. Optional. Use when signMethod = id. Unlock default keychain. Default: false.
    #signingDefaultKeychainPassword: # string. Alias: defaultKeychainPassword. Optional. Use when signMethod = id. Default keychain password. 
    #signingProvisioningProfileID: # string. Alias: provProfileUuid. Optional. Use when signMethod = id. Provisioning profile UUID. 
    #signingP12File: # string. Alias: p12. Optional. Use when signMethod = file. P12 certificate file. 
    #signingP12Password: # string. Alias: p12pwd. Optional. Use when signMethod = file. P12 password. 
    #signingProvisioningProfileFile: # string. Alias: provProfile. Optional. Use when signMethod = file. Provisioning profile file. 
    #signingRemoveProfile: false # boolean. Alias: removeProfile. Optional. Use when signMethod = file. Remove profile after build. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="solutionFile"::: -->
:::moniker range="<=azure-pipelines"

**`solutionFile`** - **Solution**<br>
[Input alias](index.md#what-are-task-input-aliases): `solution`. `string`. Required. Default value: `**/*.sln`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path from the repository root of the `Xamarin.iOS` solution to the build. May contain wildcards.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
`string`. Required. Default value: `Release`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the configuration. Standard configurations are Ad-Hoc, AppStore, Debug, and Release.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="clean"::: -->
:::moniker range="<=azure-pipelines"

**`clean`** - **Clean**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Runs a clean build (`/t:clean`) prior to the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageApp"::: -->
:::moniker range="<=azure-pipelines"

**`packageApp`** - **Create app package**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, generates an IPA as a part of the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildForSimulator"::: -->
:::moniker range="<=azure-pipelines"

**`buildForSimulator`** - **Build for iOS Simulator**<br>
[Input alias](index.md#what-are-task-input-aliases): `forSimulator`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Builds for the iOS Simulator instead of physical iOS devices.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runNugetRestore"::: -->
:::moniker range="<=azure-pipelines"

**`runNugetRestore`** - **Run NuGet restore**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs `nuget restore` on the Xamarin iOS solution to install all referenced packages before the build. The `nuget` tool in the PATH of the build agent machine is used. To use a different version of NuGet or set additional arguments, use the [NuGet Installer Task](https://www.visualstudio.com/docs/build/steps/package/nuget-installer).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="args"::: -->
:::moniker range="<=azure-pipelines"

**`args`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies additional command line arguments that are used to the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `cwd`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the working directory in which builds will run. If the value is empty, the root of the repository is used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildToolOption"::: -->
:::moniker range="<=azure-pipelines"

**`buildToolOption`** - **Build tool**<br>
[Input alias](index.md#what-are-task-input-aliases): `buildTool`. `string`. Allowed values: `xbuild` (xbuild (Xamarin Studio)), `msbuild` (MSBuild (Visual Studio for Mac)). Default value: `xbuild`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the build tools that the task will use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mdtoolFile"::: -->
:::moniker range="<=azure-pipelines"

**`mdtoolFile`** - **Build tool path**<br>
[Input alias](index.md#what-are-task-input-aliases): `mdtoolLocation`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Supplies the path to xbuild (the Xamarin Studio mono build tool) or MSBuild (the Visual Studio for Mac build tool). If the value is empty, the default xbuild or MSBuild path is used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingOption"::: -->
:::moniker range="<=azure-pipelines"

**`signingOption`** - **Override using**<br>
[Input alias](index.md#what-are-task-input-aliases): `signMethod`. `string`. Allowed values: `file` (File Contents), `id` (Identifiers). Default value: `file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this input if the build uses a signing or provisioning method that is different than the default. Choose `file` to use a P12 certificate and provisioning profile. Choose `id` to retrieve signing settings from the default Keychain and pre-installed profiles. Leave the corresponding fields blank if you do not wish to override the default build settings.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingIdentity"::: -->
:::moniker range="<=azure-pipelines"

**`signingIdentity`** - **Signing identity**<br>
[Input alias](index.md#what-are-task-input-aliases): `iosSigningIdentity`. `string`. Optional. Use when `signMethod = id`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Overrides the signing identity that will be used to sign the build. If the value is empty, the setting in the Xcode project will be used. You may need to select `signingUnlockDefaultKeychain` if you use this option.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingUnlockDefaultKeychain"::: -->
:::moniker range="<=azure-pipelines"

**`signingUnlockDefaultKeychain`** - **Unlock default keychain**<br>
[Input alias](index.md#what-are-task-input-aliases): `unlockDefaultKeychain`. `boolean`. Optional. Use when `signMethod = id`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Resolves "User interaction is not allowed" errors by unlocking the default keychain.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingDefaultKeychainPassword"::: -->
:::moniker range="<=azure-pipelines"

**`signingDefaultKeychainPassword`** - **Default keychain password**<br>
[Input alias](index.md#what-are-task-input-aliases): `defaultKeychainPassword`. `string`. Optional. Use when `signMethod = id`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password to unlock the default keychain when `signingUnlockDefaultKeychain` is set.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingProvisioningProfileID"::: -->
:::moniker range="<=azure-pipelines"

**`signingProvisioningProfileID`** - **Provisioning profile UUID**<br>
[Input alias](index.md#what-are-task-input-aliases): `provProfileUuid`. `string`. Optional. Use when `signMethod = id`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the UUID of an installed provisioning profile to be used for this build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingP12File"::: -->
:::moniker range="<=azure-pipelines"

**`signingP12File`** - **P12 certificate file**<br>
[Input alias](index.md#what-are-task-input-aliases): `p12`. `string`. Optional. Use when `signMethod = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path to a PKCS12-formatted P12 certificate file containing a signing certificate to be used for this build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingP12Password"::: -->
:::moniker range="<=azure-pipelines"

**`signingP12Password`** - **P12 password**<br>
[Input alias](index.md#what-are-task-input-aliases): `p12pwd`. `string`. Optional. Use when `signMethod = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password to the P12 certificate file. Use a build variable to encrypt this value.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingProvisioningProfileFile"::: -->
:::moniker range="<=azure-pipelines"

**`signingProvisioningProfileFile`** - **Provisioning profile file**<br>
[Input alias](index.md#what-are-task-input-aliases): `provProfile`. `string`. Optional. Use when `signMethod = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the UUID of an installed provisioning profile override to be used for this build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingRemoveProfile"::: -->
:::moniker range="<=azure-pipelines"

**`signingRemoveProfile`** - **Remove profile after build**<br>
[Input alias](index.md#what-are-task-input-aliases): `removeProfile`. `boolean`. Optional. Use when `signMethod = file`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies that the contents of the provisioning profile file should be removed from the build agent after the build is complete. **Only enable this if you are running one agent per user.**.
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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: Xamarin.iOS |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->