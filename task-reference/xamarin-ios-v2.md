---
title: XamariniOS@2 - Xamarin.iOS v2 task
description: Build an iOS app with Xamarin on macOS.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019"
---

# XamariniOS@2 - Xamarin.iOS v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Build an iOS app with Xamarin on macOS.
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
    solutionFile: '**/*.sln' # string. Required. Solution. Default: '**/*.sln'.
    configuration: 'Release' # string. Required. Configuration. Default: 'Release'.
    #clean: false # boolean. Clean. Default: false.
    packageApp: true # boolean. Required. Create app package. Default: true.
    #buildForSimulator: false # boolean. Build for iOS Simulator. Default: false.
  # Advanced
    runNugetRestore: false # boolean. Required. Run NuGet restore. Default: false.
    #args: # string. Arguments. 
    #workingDirectory: # string. Working directory. 
    #mdtoolFile: # string. Build tool path. 
  # Signing & Provisioning
    #signingIdentity: # string. Signing identity. 
    #signingProvisioningProfileID: # string. Provisioning profile UUID.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="solutionFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`solutionFile`** - **Solution**<br>
Input alias: `solution`. Type: string. Required. Default value: '**/*.sln'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repository root of the Xamarin.iOS solution to build. May contain wildcards.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range=">=azure-pipelines-2019"

**`configuration`** - **Configuration**<br>
Type: string. Required. Default value: 'Release'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Standard configurations are Ad-Hoc, AppStore, Debug, Release.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="clean"::: -->
:::moniker range=">=azure-pipelines-2019"

**`clean`** - **Clean**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run a clean build (/t:clean) prior to the build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageApp"::: -->
:::moniker range=">=azure-pipelines-2019"

**`packageApp`** - **Create app package**<br>
Type: boolean. Required. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicates whether an IPA should be generated as a part of the build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildForSimulator"::: -->
:::moniker range=">=azure-pipelines-2019"

**`buildForSimulator`** - **Build for iOS Simulator**<br>
Input alias: `forSimulator`. Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally build for the iOS Simulator instead of physical iOS devices.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runNugetRestore"::: -->
:::moniker range=">=azure-pipelines-2019"

**`runNugetRestore`** - **Run NuGet restore**<br>
Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally run `nuget restore` on the Xamarin iOS solution to install all referenced packages before build. The 'nuget' tool in the PATH of the build agent machine will be used. To use a different version of NuGet or set additional arguments, use the [NuGet Tool Installer](https://go.microsoft.com/fwlink/?linkid=852538) task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="args"::: -->
:::moniker range=">=azure-pipelines-2019"

**`args`** - **Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional command line arguments that should be used to build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`workingDirectory`** - **Working directory**<br>
Input alias: `cwd`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Working directory in which builds will run. When empty, the root of the repository is used.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mdtoolFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`mdtoolFile`** - **Build tool path**<br>
Input alias: `buildToolLocation | mdtoolLocation`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the full path to MSBuild (the Visual Studio for Mac build tool). When empty, the default MSBuild path is used.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingIdentity"::: -->
:::moniker range=">=azure-pipelines-2019"

**`signingIdentity`** - **Signing identity**<br>
Input alias: `iosSigningIdentity`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally override the signing identity that will be used to sign the build. If nothing is entered, the setting in the project will be used.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingProvisioningProfileID"::: -->
:::moniker range=">=azure-pipelines-2019"

**`signingProvisioningProfileID`** - **Provisioning profile UUID**<br>
Input alias: `provProfileUuid`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional UUID of an installed provisioning profile to be used for this build.
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

What's new in this task version.

* iOS signing set up has been removed from the task. Use `Secure Files` with supporting tasks `Install Apple Certificate` and `Install Apple Provisioning Profile` to setup signing. Updated options to work better with `Visual Studio for Mac`.
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