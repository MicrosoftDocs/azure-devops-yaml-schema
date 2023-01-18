---
title: XamariniOS@2 - Xamarin.iOS v2 task
description: Build an iOS app with Xamarin on macOS.
ms.date: 01/18/2023
monikerRange: ">=azure-pipelines-2019"
---

# XamariniOS@2 - Xamarin.iOS v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task in a pipeline to build an iOS app with Xamarin on macOS. For more information, see the [Xamarin guidance](/azure/devops/pipelines/ecosystems/xamarin) and [Sign your app during CI](/azure/devops/pipelines/apps/mobile/app-signing).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Xamarin.iOS v2
# Build an iOS app with Xamarin on macOS.
- task: XamariniOS@2
  inputs:
    solutionFile: '**/*.sln' # string. Alias: solution. Required. Solution. Default: **/*.sln.
    configuration: 'Release' # string. Required. Configuration. Default: Release.
    #clean: false # boolean. Clean. Default: false.
    packageApp: true # boolean. Required. Create app package. Default: true.
    #buildForSimulator: false # boolean. Alias: forSimulator. Build for iOS Simulator. Default: false.
  # Advanced
    runNugetRestore: false # boolean. Required. Run NuGet restore. Default: false.
    #args: # string. Arguments. 
    #workingDirectory: # string. Alias: cwd. Working directory. 
    #mdtoolFile: # string. Alias: buildToolLocation | mdtoolLocation. Build tool path. 
  # Signing & Provisioning
    #signingIdentity: # string. Alias: iosSigningIdentity. Signing identity. 
    #signingProvisioningProfileID: # string. Alias: provProfileUuid. Provisioning profile UUID.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="solutionFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`solutionFile`** - **Solution**<br>
Input alias: `solution`. `string`. Required. Default value: `**/*.sln`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path from the repository root of the `Xamarin.iOS` solution or csproj project to the build. May contain wildcards.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range=">=azure-pipelines-2019"

**`configuration`** - **Configuration**<br>
`string`. Required. Default value: `Release`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the configuration. Standard configurations are Ad-Hoc, AppStore, Debug, and Release.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="clean"::: -->
:::moniker range=">=azure-pipelines-2019"

**`clean`** - **Clean**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Runs a clean build (`/t:clean`) prior to the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageApp"::: -->
:::moniker range=">=azure-pipelines-2019"

**`packageApp`** - **Create app package**<br>
`boolean`. Required. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, generates an IPA as a part of the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildForSimulator"::: -->
:::moniker range=">=azure-pipelines-2019"

**`buildForSimulator`** - **Build for iOS Simulator**<br>
Input alias: `forSimulator`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Builds for the iOS Simulator instead of physical iOS devices.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runNugetRestore"::: -->
:::moniker range=">=azure-pipelines-2019"

**`runNugetRestore`** - **Run NuGet restore**<br>
`boolean`. Required. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs `nuget restore` on the Xamarin iOS solution to install all referenced packages before the build. The `nuget` tool in the PATH of the build agent machine is used. To use a different version of NuGet or set additional arguments, use the [NuGet Installer Task](https://www.visualstudio.com/docs/build/steps/package/nuget-installer).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="args"::: -->
:::moniker range=">=azure-pipelines-2019"

**`args`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies additional command line arguments that are used to build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`workingDirectory`** - **Working directory**<br>
Input alias: `cwd`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the working directory in which builds will run. If the value is empty, the root of the repository is used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mdtoolFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`mdtoolFile`** - **Build tool path**<br>
Input alias: `buildToolLocation | mdtoolLocation`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Supplies the path to xbuild (the Xamarin Studio mono build tool) or MSBuild (the Visual Studio for Mac build tool). If the value is empty, the default xbuild or MSBuild path is used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingIdentity"::: -->
:::moniker range=">=azure-pipelines-2019"

**`signingIdentity`** - **Signing identity**<br>
Input alias: `iosSigningIdentity`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Overrides the signing identity that will be used to sign the build. If the value is empty, the setting in the Xcode project will be used. You may need to select `signingUnlockDefaultKeychain` if you use this option.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingProvisioningProfileID"::: -->
:::moniker range=">=azure-pipelines-2019"

**`signingProvisioningProfileID`** - **Provisioning profile UUID**<br>
Input alias: `provProfileUuid`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the UUID of an installed provisioning profile override to be used for this build.
<!-- :::editable-content-end::: -->
<br>

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

Use this task in a pipeline to build an iOS app with Xamarin on macOS. For more information, see the [Xamarin guidance](/azure/devops/pipelines/ecosystems/xamarin) and [Sign your app during CI](/azure/devops/pipelines/apps/mobile/app-signing).

### What's new in this task version

* iOS signing set up has been removed from the task. Use `Secure Files` with supporting tasks `Install Apple Certificate` and `Install Apple Provisioning Profile` to setup signing. Updated options to work better with `Visual Studio for Mac`.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

* [Build your Xamarin app](/azure/devops/pipelines/ecosystems/xamarin)
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019"

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