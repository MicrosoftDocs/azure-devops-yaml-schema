---
title: Xcode@4 - Xcode v4 task
description: Build, test, or archive an Xcode workspace on macOS. Optionally package an app (task version 4).
ms.date: 07/21/2025
monikerRange: "<=azure-pipelines"
---

# Xcode@4 - Xcode v4 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to build, test, or archive an Xcode workspace on macOS, and optionally package an app.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Xcode v4
# Build, test, or archive an Xcode workspace on macOS. Optionally package an app.
- task: Xcode@4
  inputs:
    actions: 'build' # string. Required. Actions. Default: build.
    #configuration: '$(Configuration)' # string. Configuration. Default: $(Configuration).
    #sdk: '$(SDK)' # string. SDK. Default: $(SDK).
    #xcWorkspacePath: '**/*.xcodeproj/project.xcworkspace' # string. Workspace or project path. Default: **/*.xcodeproj/project.xcworkspace.
    #scheme: # string. Scheme. 
    #xcodeVersion: 'default' # '8' | '9' | 'default' | 'specifyPath'. Xcode version. Default: default.
    #xcodeDeveloperDir: # string. Optional. Use when xcodeVersion == specifyPath. Xcode developer path. 
  # Package options
    #packageApp: false # boolean. Create app package. Default: false.
    #archivePath: # string. Optional. Use when packageApp == true. Archive path. 
    #exportPath: 'output/$(SDK)/$(Configuration)' # string. Optional. Use when packageApp == true. Export path. Default: output/$(SDK)/$(Configuration).
    #exportOptions: 'auto' # 'auto' | 'plist' | 'specify'. Optional. Use when packageApp == true. Export options. Default: auto.
    #exportMethod: 'development' # string. Required when exportOptions == specify. Export method. Default: development.
    #exportTeamId: # string. Optional. Use when exportOptions == specify. Team ID. 
    #exportOptionsPlist: # string. Required when exportOptions == plist. Export options plist. 
    #exportArgs: # string. Optional. Use when packageApp == true. Export arguments. 
  # Signing & provisioning
    #signingOption: 'nosign' # 'nosign' | 'default' | 'manual' | 'auto'. Signing style. Default: nosign.
    #signingIdentity: # string. Optional. Use when signingOption = manual. Signing identity. 
    #provisioningProfileUuid: # string. Optional. Use when signingOption = manual. Provisioning profile UUID. 
    #teamId: # string. Optional. Use when signingOption = auto. Team ID. 
  # Devices & simulators
    #destinationPlatformOption: 'default' # 'default' | 'iOS' | 'tvOS' | 'macOS' | 'custom'. Destination platform. Default: default.
    #destinationPlatform: # string. Optional. Use when destinationPlatformOption == custom. Custom destination platform. 
    #destinationTypeOption: 'simulators' # 'simulators' | 'devices'. Optional. Use when destinationPlatformOption != default && destinationPlatformOption != macOS. Destination type. Default: simulators.
    #destinationSimulators: 'iPhone 7' # string. Optional. Use when destinationPlatformOption != default && destinationPlatformOption != macOS && destinationTypeOption == simulators. Simulator. Default: iPhone 7.
    #destinationDevices: # string. Optional. Use when destinationPlatformOption != default && destinationPlatformOption != macOS && destinationTypeOption == devices. Device. 
  # Advanced
    #args: # string. Arguments. 
    #workingDirectory: # string. Alias: cwd. Working directory. 
    #outputPattern: # string. Output directory. 
    #useXcpretty: false # boolean. Use xcpretty. Default: false.
    #publishJUnitResults: false # boolean. Publish test results to VSTS/TFS. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="actions"::: -->
:::moniker range="<=azure-pipelines"

**`actions`** - **Actions**<br>
`string`. Required. Default value: `build`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a space-delimited list of actions. Valid options are `build`, `clean`, `test`, `analyze`, and `archive`. For example,`clean build` performs a clean build. See the [Apple: Building from the command line with Xcode FAQ](https://developer.apple.com/library/archive/technotes/tn2339/_index.html).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
`string`. Default value: `$(Configuration)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Xcode project or workspace configuration to build. When using a variable, specify a value (for example, `Release`) on the **Variables** tab.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sdk"::: -->
:::moniker range="<=azure-pipelines"

**`sdk`** - **SDK**<br>
`string`. Default value: `$(SDK)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an SDK to use when building the Xcode project or workspace. From the macOS Terminal application, run `xcodebuild -showsdks` to display the valid list of SDKs. When using a variable, specify a value (for example, `iphonesimulator`) on the [Variables](/azure/devops/pipelines/build/variables) tab.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcWorkspacePath"::: -->
:::moniker range="<=azure-pipelines"

**`xcWorkspacePath`** - **Workspace or project path**<br>
`string`. Default value: `**/*.xcodeproj/project.xcworkspace`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies a relative path from the root of the repository to the Xcode workspace or project. If you specify a value, you must also specify the scheme. Do not specify a value if you are specifying `-target flag` in Advanced Arguments. For example, `MyApp/MyApp.xcworkspace` or `MyApp/MyApp.xcodeproj`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scheme"::: -->
:::moniker range="<=azure-pipelines"

**`scheme`** - **Scheme**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies an Xcode scheme name. *Must be a shared scheme* (shared checkbox under **Managed Schemes** in Xcode). If you do not specify a scheme, and the specified workspace has a single shared scheme, the workspace scheme will be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcodeVersion"::: -->
:::moniker range="<=azure-pipelines"

**`xcodeVersion`** - **Xcode version**<br>
`string`. Allowed values: `8` (Xcode 8), `9` (Xcode 9), `default`, `specifyPath` (Specify path). Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the target version of Xcode. Select `Default` to use the default version of Xcode on the agent machine. Specifying a version number (for example, `Xcode 9`) relies on the version's location to be set by environment variables on the agent machine (for example, `XCODE_9_DEVELOPER_DIR=/Applications/Xcode_9.0.0.app/Contents/Developer`). Select `Specify path` to provide a specific path to the Xcode developer directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcodeDeveloperDir"::: -->
:::moniker range="<=azure-pipelines"

**`xcodeDeveloperDir`** - **Xcode developer path**<br>
`string`. Optional. Use when `xcodeVersion == specifyPath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a path to a specific Xcode developer directory (for example, `/Applications/Xcode_9.0.0.app/Contents/Developer`). This input is useful when multiple versions of Xcode are installed on the agent machine.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageApp"::: -->
:::moniker range="<=azure-pipelines"

**`packageApp`** - **Create app package**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether an IPA app package file should be generated as a part of the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="archivePath"::: -->
:::moniker range="<=azure-pipelines"

**`archivePath`** - **Archive path**<br>
`string`. Optional. Use when `packageApp == true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a directory where created archives are placed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportPath"::: -->
:::moniker range="<=azure-pipelines"

**`exportPath`** - **Export path**<br>
`string`. Optional. Use when `packageApp == true`. Default value: `output/$(SDK)/$(Configuration)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the destination for the product exported from the archive.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportOptions"::: -->
:::moniker range="<=azure-pipelines"

**`exportOptions`** - **Export options**<br>
`string`. Optional. Use when `packageApp == true`. Allowed values: `auto` (Automatic), `plist`, `specify`. Default value: `auto`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies options for exporting the archive. When the default value of `Automatic` is selected, the export method is automatically detected from the archive. Select `Plist` to specify a plist file containing export options. Select `Specify` to provide a specific **Export method** and **Team ID**.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportMethod"::: -->
:::moniker range="<=azure-pipelines"

**`exportMethod`** - **Export method**<br>
`string`. Required when `exportOptions == specify`. Default value: `development`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the method that Xcode uses to export the archive. For example: `app-store`, `package`, `ad-hoc`, `enterprise`, or `development`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportTeamId"::: -->
:::moniker range="<=azure-pipelines"

**`exportTeamId`** - **Team ID**<br>
`string`. Optional. Use when `exportOptions == specify`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Apple Developer Portal 10-character team ID to use during the export.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportOptionsPlist"::: -->
:::moniker range="<=azure-pipelines"

**`exportOptionsPlist`** - **Export options plist**<br>
`string`. Required when `exportOptions == plist`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the plist file that contains options to use during the export.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportArgs"::: -->
:::moniker range="<=azure-pipelines"

**`exportArgs`** - **Export arguments**<br>
`string`. Optional. Use when `packageApp == true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional command line arguments used during the export.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingOption"::: -->
:::moniker range="<=azure-pipelines"

**`signingOption`** - **Signing style**<br>
`string`. Allowed values: `nosign` (Do not code sign), `default` (Project defaults), `manual` (Manual signing), `auto` (Automatic signing). Default value: `nosign`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the method of signing the build. Select `Do not code sign` to disable signing. Select `Project defaults` to use only the project's signing configuration. Select `Manual signing` to force manual signing and optionally specify a signing identity and provisioning profile. Select `Automatic signing` to force automatic signing and optionally specify a development team ID. If your project requires signing, use the **Install Apple...** tasks to install certificates and provisioning profiles prior to the Xcode build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingIdentity"::: -->
:::moniker range="<=azure-pipelines"

**`signingIdentity`** - **Signing identity**<br>
`string`. Optional. Use when `signingOption = manual`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a signing identity override with which to sign the build. Unlocking the default keychain on the agent machine may be required. If no value is entered, the Xcode project's setting is used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="provisioningProfileUuid"::: -->
:::moniker range="<=azure-pipelines"

**`provisioningProfileUuid`** - **Provisioning profile UUID**<br>
`string`. Optional. Use when `signingOption = manual`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the UUID of an installed provisioning profile used for the build. Use separate build tasks with different schemes or targets to specify provisioning profiles by target in a single workspace (iOS, tvOS, watchOS).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="teamId"::: -->
:::moniker range="<=azure-pipelines"

**`teamId`** - **Team ID**<br>
`string`. Optional. Use when `signingOption = auto`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
**Required if you are a member of multiple development teams.** Specifies the 10-character development team ID.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="destinationPlatformOption"::: -->
:::moniker range="<=azure-pipelines"

**`destinationPlatformOption`** - **Destination platform**<br>
`string`. Allowed values: `default`, `iOS` (iOS and watchOS), `tvOS`, `macOS`, `custom`. Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the destination device's platform used for UI testing when the generic build device isn't valid. Choose `Custom` to specify a platform not included in the list. When `Default` is selected, no simulators or devices are targeted.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="destinationPlatform"::: -->
:::moniker range="<=azure-pipelines"

**`destinationPlatform`** - **Custom destination platform**<br>
`string`. Optional. Use when `destinationPlatformOption == custom`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a destination device's platform used for UI testing when the generic build device isn't valid.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="destinationTypeOption"::: -->
:::moniker range="<=azure-pipelines"

**`destinationTypeOption`** - **Destination type**<br>
`string`. Optional. Use when `destinationPlatformOption != default && destinationPlatformOption != macOS`. Allowed values: `simulators` (Simulator), `devices` (Connected Device). Default value: `simulators`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the destination type used for UI testing. Devices must be connected to the Mac performing the build via a cable or network connection. See **Devices and Simulators** in Xcode for more information.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="destinationSimulators"::: -->
:::moniker range="<=azure-pipelines"

**`destinationSimulators`** - **Simulator**<br>
`string`. Optional. Use when `destinationPlatformOption != default && destinationPlatformOption != macOS && destinationTypeOption == simulators`. Default value: `iPhone 7`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an Xcode simulator name used for UI testing. For example, `iPhone X` (iOS and watchOS) or `Apple TV 4K` (tvOS). An optional target OS version can be specified in the format `OS=<versionNumber>`, such as `iPhone X,OS=11.1`. Learn more about [installed simulators on the Hosted macOS Preview agent](/mobile-center/build/software).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="destinationDevices"::: -->
:::moniker range="<=azure-pipelines"

**`destinationDevices`** - **Device**<br>
`string`. Optional. Use when `destinationPlatformOption != default && destinationPlatformOption != macOS && destinationTypeOption == devices`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the device used for UI testing, such as `Raisa's iPad`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="args"::: -->
:::moniker range="<=azure-pipelines"

**`args`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies additional command line arguments with which to build. This input is useful for specifying `-target` or `-project` arguments instead of a workspace/project and scheme. See the [Apple: Building from the command line with Xcode FAQ](https://developer.apple.com/library/archive/technotes/tn2339/_index.html).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `cwd`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the working directory in which to run the build. If no value is entered, the root of the repository is used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputPattern"::: -->
:::moniker range="<=azure-pipelines"

**`outputPattern`** - **Output directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies a relative path to the working directory where build output (binaries) are placed. For example: `output/$(SDK)/$(Configuration)` or `output/$(TestSDK)/$(TestConfiguration)`. Archive and export paths are configured separately. Specify values on the [Variables tab](/azure/devops/pipelines/build/variables).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useXcpretty"::: -->
:::moniker range="<=azure-pipelines"

**`useXcpretty`** - **Use xcpretty**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether to use `xcpretty` to format `xcodebuild` output, and generates JUnit test results. `xcpretty` must be installed on the agent machine (It is preinstalled on VSTS hosted build agents). See [xcpretty](https://github.com/supermarin/xcpretty) for more information.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range="<=azure-pipelines"

**`publishJUnitResults`** - **Publish test results to VSTS/TFS**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If `xcpretty` is enabled, this input specifies whether to publish the JUnit test results to VSTS/TFS.
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

Use this task to build an Xcode workspace on macOS.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

* [Build, test, and deploy Xcode apps](/azure/devops/pipelines/ecosystems/xcode)
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: xcode |
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