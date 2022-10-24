---
title: XamariniOS@1 - Xamarin.iOS v1 task
description: Build an iOS app with Xamarin on macOS (task version 1).
ms.date: 10/21/2022
monikerRange: "<=azure-pipelines"
---

# XamariniOS@1 - Xamarin.iOS v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Build an iOS app with Xamarin on macOS.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Xamarin.iOS v1
# Build an iOS app with Xamarin on macOS.
- task: XamariniOS@1
  inputs:
    solutionFile: '**/*.sln' # string. Alias: solution. Required. Solution. Default: **/*.sln.
    configuration: 'Release' # string. Required. Configuration. Default: Release.
    #clean: false # boolean. Clean. Default: false.
    packageApp: true # boolean. Required. Create app package. Default: true.
    #buildForSimulator: false # boolean. Alias: forSimulator. Build for iOS Simulator. Default: false.
  # Advanced
    runNugetRestore: true # boolean. Required. Run NuGet restore. Default: true.
    #args: # string. Arguments. 
    #workingDirectory: # string. Alias: cwd. Working directory. 
    #buildToolOption: 'xbuild' # 'xbuild' | 'msbuild'. Alias: buildTool. Build tool. Default: xbuild.
    #mdtoolFile: # string. Alias: mdtoolLocation. Build tool path. 
  # Signing & Provisioning
    #signingOption: 'file' # 'file' | 'id'. Alias: signMethod. Override using. Default: file.
    #signingIdentity: # string. Alias: iosSigningIdentity. Optional. Use when signMethod = id. Signing identity. 
    #signingUnlockDefaultKeychain: false # boolean. Alias: unlockDefaultKeychain. Required when signMethod = id. Unlock default keychain. Default: false.
    #signingDefaultKeychainPassword: # string. Alias: defaultKeychainPassword. Optional. Use when signMethod = id. Default keychain password. 
    #signingProvisioningProfileID: # string. Alias: provProfileUuid. Optional. Use when signMethod = id. Provisioning profile UUID. 
    #signingP12File: # string. Alias: p12. Optional. Use when signMethod = file. P12 certificate file. 
    #signingP12Password: # string. Alias: p12pwd. Optional. Use when signMethod = file. P12 password. 
    #signingProvisioningProfileFile: # string. Alias: provProfile. Optional. Use when signMethod = file. Provisioning profile file. 
    #signingRemoveProfile: false # boolean. Alias: removeProfile. Optional. Use when signMethod = file. Remove profile after build. Default: false.
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

<!-- :::item name="solutionFile"::: -->
:::moniker range="<=azure-pipelines"

**`solutionFile`** - **Solution**<br>
Input alias: `solution`. `string`. Required. Default value: `**/*.sln`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repository root of the Xamarin.iOS solution to build. May contain wildcards.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
`string`. Required. Default value: `Release`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Standard configurations are Ad-Hoc, AppStore, Debug, Release.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="clean"::: -->
:::moniker range="<=azure-pipelines"

**`clean`** - **Clean**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run a clean build (/t:clean) prior to the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageApp"::: -->
:::moniker range="<=azure-pipelines"

**`packageApp`** - **Create app package**<br>
`boolean`. Required. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicates whether an IPA should be generated as a part of the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildForSimulator"::: -->
:::moniker range="<=azure-pipelines"

**`buildForSimulator`** - **Build for iOS Simulator**<br>
Input alias: `forSimulator`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally build for the iOS Simulator instead of physical iOS devices.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runNugetRestore"::: -->
:::moniker range="<=azure-pipelines"

**`runNugetRestore`** - **Run NuGet restore**<br>
`boolean`. Required. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally run `nuget restore` on the Xamarin iOS solution to install all referenced packages before build. The 'nuget' tool in the PATH of the build agent machine will be used. To use a different version of NuGet or set additional arguments, use the [NuGet Installer Task](https://www.visualstudio.com/docs/build/steps/package/nuget-installer).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="args"::: -->
:::moniker range="<=azure-pipelines"

**`args`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional command line arguments that should be used to build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working directory**<br>
Input alias: `cwd`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Working directory in which builds will run. When empty, the root of the repository is used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildToolOption"::: -->
:::moniker range="<=azure-pipelines"

**`buildToolOption`** - **Build tool**<br>
Input alias: `buildTool`. `string`. Allowed values: `xbuild` (xbuild (Xamarin Studio)), `msbuild` (MSBuild (Visual Studio for Mac)). Default value: `xbuild`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mdtoolFile"::: -->
:::moniker range="<=azure-pipelines"

**`mdtoolFile`** - **Build tool path**<br>
Input alias: `mdtoolLocation`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the path to xbuild (the Xamarin Studio mono build tool) or MSBuild (the Visual Studio for Mac build tool). When empty, the default xbuild or MSBuild path is used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingOption"::: -->
:::moniker range="<=azure-pipelines"

**`signingOption`** - **Override using**<br>
Input alias: `signMethod`. `string`. Allowed values: `file` (File Contents), `id` (Identifiers). Default value: `file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the build should use a signing or provisioning method that is different than the default, choose that method here. Choose 'File Contents' to use a P12 certificate and provisioning profile. Choose 'Identifiers' to retrieve signing settings from the default Keychain and pre-installed profiles. Leave the corresponding fields blank if you do not wish to override default build settings.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingIdentity"::: -->
:::moniker range="<=azure-pipelines"

**`signingIdentity`** - **Signing identity**<br>
Input alias: `iosSigningIdentity`. `string`. Optional. Use when `signMethod = id`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally override the signing identity that will be used to sign the build. If nothing is entered, the setting in the Xcode project will be used. You may need to select 'Unlock Default Keychain' if you use this option.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingUnlockDefaultKeychain"::: -->
:::moniker range="<=azure-pipelines"

**`signingUnlockDefaultKeychain`** - **Unlock default keychain**<br>
Input alias: `unlockDefaultKeychain`. `boolean`. Required when `signMethod = id`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Resolve "User interaction is not allowed" errors by unlocking the default keychain.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingDefaultKeychainPassword"::: -->
:::moniker range="<=azure-pipelines"

**`signingDefaultKeychainPassword`** - **Default keychain password**<br>
Input alias: `defaultKeychainPassword`. `string`. Optional. Use when `signMethod = id`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password to unlock the default keychain when that option is set.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingProvisioningProfileID"::: -->
:::moniker range="<=azure-pipelines"

**`signingProvisioningProfileID`** - **Provisioning profile UUID**<br>
Input alias: `provProfileUuid`. `string`. Optional. Use when `signMethod = id`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional UUID of an installed provisioning profile to be used for this build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingP12File"::: -->
:::moniker range="<=azure-pipelines"

**`signingP12File`** - **P12 certificate file**<br>
Input alias: `p12`. `string`. Optional. Use when `signMethod = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional relative path to a PKCS12-formatted P12 certificate file containing a signing certificate to be used for this build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingP12Password"::: -->
:::moniker range="<=azure-pipelines"

**`signingP12Password`** - **P12 password**<br>
Input alias: `p12pwd`. `string`. Optional. Use when `signMethod = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password to the P12 certificate file, if specified. Use a build variable to encrypt this value.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingProvisioningProfileFile"::: -->
:::moniker range="<=azure-pipelines"

**`signingProvisioningProfileFile`** - **Provisioning profile file**<br>
Input alias: `provProfile`. `string`. Optional. Use when `signMethod = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional relative path to a file containing the provisioning profile override to be used for this build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingRemoveProfile"::: -->
:::moniker range="<=azure-pipelines"

**`signingRemoveProfile`** - **Remove profile after build**<br>
Input alias: `removeProfile`. `boolean`. Optional. Use when `signMethod = file`. Default value: `false`.<br>
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