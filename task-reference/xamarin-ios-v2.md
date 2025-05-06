---
title: XamariniOS@2 - Xamarin.iOS v2 task
description: Build an iOS app with Xamarin on macOS.
ms.date: 05/06/2025
monikerRange: "<=azure-pipelines"
---

# XamariniOS@2 - Xamarin.iOS v2 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Build an iOS app with Xamarin on macOS.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Build an iOS app with Xamarin on macOS.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Xamarin.iOS v2
# Build an iOS app with Xamarin on macOS.
- task: XamariniOS@2
  inputs:
    solutionFile: '**/*.sln' # string. Alias: solution. Required. Solution. Default: **/*.sln.
    configuration: 'Release' # string. Required. Configuration. Default: Release.
    #clean: false # boolean. Clean. Default: false.
    #packageApp: true # boolean. Create app package. Default: true.
    #buildForSimulator: false # boolean. Alias: forSimulator. Build for iOS Simulator. Default: false.
  # Advanced
    #runNugetRestore: false # boolean. Run NuGet restore. Default: false.
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
:::moniker range="<=azure-pipelines"

**`solutionFile`** - **Solution**<br>
[Input alias](index.md#what-are-task-input-aliases): `solution`. `string`. Required. Default value: `**/*.sln`.<br>
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
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicates whether an IPA should be generated as a part of the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildForSimulator"::: -->
:::moniker range="<=azure-pipelines"

**`buildForSimulator`** - **Build for iOS Simulator**<br>
[Input alias](index.md#what-are-task-input-aliases): `forSimulator`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally build for the iOS Simulator instead of physical iOS devices.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runNugetRestore"::: -->
:::moniker range="<=azure-pipelines"

**`runNugetRestore`** - **Run NuGet restore**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally run `nuget restore` on the Xamarin iOS solution to install all referenced packages before build. The 'nuget' tool in the PATH of the build agent machine will be used. To use a different version of NuGet or set additional arguments, use the [NuGet Tool Installer](https://go.microsoft.com/fwlink/?linkid=852538) task.
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
[Input alias](index.md#what-are-task-input-aliases): `cwd`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Working directory in which builds will run. When empty, the root of the repository is used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mdtoolFile"::: -->
:::moniker range="<=azure-pipelines"

**`mdtoolFile`** - **Build tool path**<br>
[Input alias](index.md#what-are-task-input-aliases): `buildToolLocation | mdtoolLocation`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the full path to MSBuild (the Visual Studio for Mac build tool). When empty, the default MSBuild path is used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingIdentity"::: -->
:::moniker range="<=azure-pipelines"

**`signingIdentity`** - **Signing identity**<br>
[Input alias](index.md#what-are-task-input-aliases): `iosSigningIdentity`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally override the signing identity that will be used to sign the build. If nothing is entered, the setting in the project will be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingProvisioningProfileID"::: -->
:::moniker range="<=azure-pipelines"

**`signingProvisioningProfileID`** - **Provisioning profile UUID**<br>
[Input alias](index.md#what-are-task-input-aliases): `provProfileUuid`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional UUID of an installed provisioning profile to be used for this build.
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