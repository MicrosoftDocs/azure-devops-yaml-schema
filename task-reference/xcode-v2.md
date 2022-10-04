---
title: Xcode@2 - Xcode Build v2 task
description: Build an Xcode workspace on Mac OS.
ms.date: 09/26/2022
monikerRange: "<=azure-pipelines"
---

# Xcode@2 - Xcode Build v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Build an Xcode workspace on Mac OS.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Xcode Build v2
# Build an Xcode workspace on Mac OS.
- task: Xcode@2
  inputs:
    actions: 'build' # string. Required. Actions. Default: build.
    #configuration: '$(Configuration)' # string. Configuration. Default: $(Configuration).
    #sdk: '$(SDK)' # string. SDK. Default: $(SDK).
    #xcWorkspacePath: '**/*.xcodeproj/*.xcworkspace' # string. Workspace/Project Path. Default: **/*.xcodeproj/*.xcworkspace.
    #scheme: # string. Scheme. 
    packageApp: true # boolean. Required. Create App Package. Default: true.
  # Package Options
    packageTool: 'xcodebuild' # 'xcrun' | 'xcodebuild'. Required. Create Package (IPA) using. Default: xcodebuild.
    #archivePath: # string. Optional. Use when packageTool == xcodebuild. Archive Path. 
    #exportPath: 'output/$(SDK)/$(Configuration)' # string. Optional. Use when packageTool == xcodebuild. Export Path. Default: output/$(SDK)/$(Configuration).
    #exportOptions: 'auto' # 'auto' | 'plist' | 'specify'. Optional. Use when packageTool == xcodebuild. Export Options. Default: auto.
    #exportMethod: 'development' # string. Required when exportOptions == specify. Export Method. Default: development.
    #exportTeamId: # string. Optional. Use when exportOptions == specify. Team ID. 
    #exportOptionsPlist: # string. Required when exportOptions == plist. Export Options Plist. 
  # Signing & Provisioning
    #xcode8AutomaticSigning: false # boolean. Automatic Signing. Default: false.
    #teamId: # string. Optional. Use when xcode8AutomaticSigning = true. Team ID. 
    #signMethod: 'file' # 'file' | 'id'. Override Using. Default: file.
    #iosSigningIdentity: # string. Optional. Use when signMethod = id. Signing Identity. 
    #unlockDefaultKeychain: false # boolean. Required when signMethod = id. Unlock Default Keychain. Default: false.
    #defaultKeychainPassword: # string. Optional. Use when signMethod = id. Default Keychain Password. 
    #provProfileUuid: # string. Optional. Use when signMethod = id. Provisioning Profile UUID. 
    #p12: # string. Optional. Use when signMethod = file. P12 Certificate File. 
    #p12pwd: # string. Optional. Use when signMethod = file. P12 Password. 
    #provProfile: # string. Optional. Use when signMethod = file. Provisioning Profile File. 
    #removeProfile: false # boolean. Optional. Use when signMethod = file. Remove Profile After Build. Default: false.
  # Advanced
    #args: # string. Arguments. 
    #cwd: # string. Working Directory. 
    outputPattern: 'output/$(SDK)/$(Configuration)' # string. Required. Output Directory. Default: output/$(SDK)/$(Configuration).
    #xcodeDeveloperDir: # string. Xcode Developer Path. 
    #useXcpretty: false # boolean. Use xcpretty. Default: false.
    #publishJUnitResults: false # boolean. Publish to VSTS/TFS. Default: false.
  # xctool (deprecated)
    #useXctool: # boolean. Use xctool. 
    #xctoolReporter: # string. xctool Test Reporter Format.
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

<!-- :::item name="actions"::: -->
:::moniker range="<=azure-pipelines"

**`actions`** - **Actions**<br>
`string`. Required. Default value: `build`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Space delimited list of actions.  Valid options are build, clean, test, analyze, and archive.  For example: `build clean` would do a clean build.  See [xcodebuild man page](https://developer.apple.com/library/mac/documentation/Darwin/Reference/ManPages/man1/xcodebuild.1.html).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
`string`. Default value: `$(Configuration)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the Xcode project or workspace configuration to be built. The default value of this field is the variable `$(Configuration)`. When using a variable, make sure to specify a value (for example, `Release`) on the **Variables** tab.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sdk"::: -->
:::moniker range="<=azure-pipelines"

**`sdk`** - **SDK**<br>
`string`. Default value: `$(SDK)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Build an Xcode project or workspace against the specified SDK.  Run *xcodebuild -showsdks* to see the valid list of SDKs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcWorkspacePath"::: -->
:::moniker range="<=azure-pipelines"

**`xcWorkspacePath`** - **Workspace/Project Path**<br>
`string`. Default value: `**/*.xcodeproj/*.xcworkspace`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional relative path from repo root to the Xcode workspace or project. For example: `MyApp/MyApp.xcworkspace` or `MyApp/MyApp.xcworkspace/MyApp.xcodeproj`. Leave blank if you intend to use the -target flag under Advanced Arguments.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scheme"::: -->
:::moniker range="<=azure-pipelines"

**`scheme`** - **Scheme**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional scheme name in Xcode. *Must be a shared scheme* (shared checkbox under managed schemes in Xcode). **Required if Workspace is specified.**.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageApp"::: -->
:::moniker range="<=azure-pipelines"

**`packageApp`** - **Create App Package**<br>
`boolean`. Required. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicates whether an IPA should be generated as a part of the build. For exporting archives with Xcode 7 and Xcode 8, review additional inputs in the `Package Options` section.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageTool"::: -->
:::moniker range="<=azure-pipelines"

**`packageTool`** - **Create Package (IPA) using**<br>
`string`. Required. Allowed values: `xcrun` (xcrun (deprecated by Apple)), `xcodebuild` (xcodebuild archive and export). Default value: `xcodebuild`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose the tool to use for generating the IPA.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="archivePath"::: -->
:::moniker range="<=azure-pipelines"

**`archivePath`** - **Archive Path**<br>
`string`. Optional. Use when `packageTool == xcodebuild`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally specify a directory where created archives should be placed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportPath"::: -->
:::moniker range="<=azure-pipelines"

**`exportPath`** - **Export Path**<br>
`string`. Optional. Use when `packageTool == xcodebuild`. Default value: `output/$(SDK)/$(Configuration)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally specify the destination for the product exported from the archive.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportOptions"::: -->
:::moniker range="<=azure-pipelines"

**`exportOptions`** - **Export Options**<br>
`string`. Optional. Use when `packageTool == xcodebuild`. Allowed values: `auto`, `plist`, `specify`. Default value: `auto`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Pick a way to pass in Export Options when exporting the archive.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportMethod"::: -->
:::moniker range="<=azure-pipelines"

**`exportMethod`** - **Export Method**<br>
`string`. Required when `exportOptions == specify`. Default value: `development`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Method for how Xcode should export the archive. E.g. app-store, package, ad-hoc, enterprise, development.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportTeamId"::: -->
:::moniker range="<=azure-pipelines"

**`exportTeamId`** - **Team ID**<br>
`string`. Optional. Use when `exportOptions == specify`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The 10 digit Team ID from the Apple Developer Portal to use for this export.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportOptionsPlist"::: -->
:::moniker range="<=azure-pipelines"

**`exportOptionsPlist`** - **Export Options Plist**<br>
`string`. Required when `exportOptions == plist`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to a plist file that configures archive exporting.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcode8AutomaticSigning"::: -->
:::moniker range="<=azure-pipelines"

**`xcode8AutomaticSigning`** - **Automatic Signing**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this if you have an Xcode 8 or Xcode 9 project configured for Automatic Signing.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="teamId"::: -->
:::moniker range="<=azure-pipelines"

**`teamId`** - **Team ID**<br>
`string`. Optional. Use when `xcode8AutomaticSigning = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the 10 digit developer Team ID. This is required if you are a member of multiple development teams.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signMethod"::: -->
:::moniker range="<=azure-pipelines"

**`signMethod`** - **Override Using**<br>
`string`. Allowed values: `file` (File Contents), `id` (Identifiers). Default value: `file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the build should use a signing or provisioning method that is different than the default, choose that method here. Choose 'File Contents' to use a P12 certificate and provisioning profile. Choose 'Identifiers' to retrieve signing settings from the default Keychain and pre-installed profiles. Leave the corresponding fields blank if you do not wish to override default build settings.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="iosSigningIdentity"::: -->
:::moniker range="<=azure-pipelines"

**`iosSigningIdentity`** - **Signing Identity**<br>
`string`. Optional. Use when `signMethod = id`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional signing identity override that should be used to sign the build. Defaults to Xcode Project setting. You may need to select Unlock Default Keychain if you use this option.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="unlockDefaultKeychain"::: -->
:::moniker range="<=azure-pipelines"

**`unlockDefaultKeychain`** - **Unlock Default Keychain**<br>
`boolean`. Required when `signMethod = id`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Resolve "User interaction is not allowed" errors by unlocking the default keychain.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="defaultKeychainPassword"::: -->
:::moniker range="<=azure-pipelines"

**`defaultKeychainPassword`** - **Default Keychain Password**<br>
`string`. Optional. Use when `signMethod = id`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password to unlock the default keychain when this option is set.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="provProfileUuid"::: -->
:::moniker range="<=azure-pipelines"

**`provProfileUuid`** - **Provisioning Profile UUID**<br>
`string`. Optional. Use when `signMethod = id`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional UUID of an installed provisioning profile to be used for this build. Use separate build tasks with different Schemes or Targets to specify separate provisioning profiles by target in a single workspace (iOS, WatchKit, tvOS).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="p12"::: -->
:::moniker range="<=azure-pipelines"

**`p12`** - **P12 Certificate File**<br>
`string`. Optional. Use when `signMethod = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional relative path to a PKCS12 formatted p12 certificate file containing a signing certificate to be used for this build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="p12pwd"::: -->
:::moniker range="<=azure-pipelines"

**`p12pwd`** - **P12 Password**<br>
`string`. Optional. Use when `signMethod = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password to P12 Certificate File if specified. Use a Build Variable to encrypt.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="provProfile"::: -->
:::moniker range="<=azure-pipelines"

**`provProfile`** - **Provisioning Profile File**<br>
`string`. Optional. Use when `signMethod = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional relative path to file containing provisioning profile override to be used for this build. Use separate build tasks with different Schemes or Targets to specify separate provisioning profiles by target in a single workspace (iOS, WatchKit, tvOS).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="removeProfile"::: -->
:::moniker range="<=azure-pipelines"

**`removeProfile`** - **Remove Profile After Build**<br>
`boolean`. Optional. Use when `signMethod = file`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies that the contents of the Provisioning Profile File should be removed from the build agent after the build is complete. **Only check if you are running one agent per user.**.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="args"::: -->
:::moniker range="<=azure-pipelines"

**`args`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional command line arguments that should be used to build. Useful if you want to use -target or -project instead of specifying a Workspace and Scheme.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cwd"::: -->
:::moniker range="<=azure-pipelines"

**`cwd`** - **Working Directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Working directory for build runs. Defaults to the root of the repository.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputPattern"::: -->
:::moniker range="<=azure-pipelines"

**`outputPattern`** - **Output Directory**<br>
`string`. Required. Default value: `output/$(SDK)/$(Configuration)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path where build output (binaries) will be placed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcodeDeveloperDir"::: -->
:::moniker range="<=azure-pipelines"

**`xcodeDeveloperDir`** - **Xcode Developer Path**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional path to Xcode Developer folder if not the system default. For use when multiple versions of Xcode are installed on a system. Ex: /Applications/Xcode 7.app/Contents/Developer.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useXcpretty"::: -->
:::moniker range="<=azure-pipelines"

**`useXcpretty`** - **Use xcpretty**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use xcpretty to format xcodebuild output and generate JUnit test results report. Requires xcpretty be installed on agent hosts. See [xcpretty](https://github.com/supermarin/xcpretty) for details.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range="<=azure-pipelines"

**`publishJUnitResults`** - **Publish to VSTS/TFS**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish JUnit Test results produced above using xctool to VSTS/TFS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useXctool"::: -->
:::moniker range="<=azure-pipelines"

**`useXctool`** - **Use xctool**<br>
`boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use xctool instead of xcodebuild. Requires xctool be installed on agent hosts. See [xctool](https://github.com/facebook/xctool) for details. Note: xctool has been deprecated and does not work with Xcode 8.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xctoolReporter"::: -->
:::moniker range="<=azure-pipelines"

**`xctoolReporter`** - **xctool Test Reporter Format**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Test reporter format to use when "test" action is specified and "Use xctool" is checked. Specify "junit:output-file-path-here.xml" to generate a file format compatible with the Publish Test Results task. When specified, "plain" is automatically added as well. Requires xctool be installed on agent hosts. See [xctool](https://github.com/facebook/xctool) for details. Note: xctool has been deprecated and does not work with Xcode 8.
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

:::moniker range=">=azure-pipelines-2019"

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

:::moniker range="=azure-pipelines-2018"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | All |
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