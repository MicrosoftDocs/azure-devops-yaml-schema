---
title: Xcode@2 - Xcode Build v2 task
description: Build an Xcode workspace on Mac OS.
ms.date: 12/21/2023
monikerRange: "<=azure-pipelines"
---

# Xcode@2 - Xcode Build v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to build an Xcode workspace on macOS.
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
    #packageApp: true # boolean. Create App Package. Default: true.
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
    #unlockDefaultKeychain: false # boolean. Optional. Use when signMethod = id. Unlock Default Keychain. Default: false.
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
Specifies a space-delimited list of actions. Valid options are `build`, `clean`, `test`, `analyze`, and `archive`. For example, `build clean` performs a clean build. See the [Apple: Building from the command line with Xcode FAQ](https://developer.apple.com/library/archive/technotes/tn2339/_index.html).
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
Builds an Xcode project or workspace against the specified SDK. Run `xcodebuild -showsdks` to see a valid list of SDKs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcWorkspacePath"::: -->
:::moniker range="<=azure-pipelines"

**`xcWorkspacePath`** - **Workspace/Project Path**<br>
`string`. Default value: `**/*.xcodeproj/*.xcworkspace`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the relative path from the repo root to the Xcode workspace or project. For example: `MyApp/MyApp.xcworkspace` or `MyApp/MyApp.xcworkspace/MyApp.xcodeproj`.  
Leave blank if you intend to use `-target flag` under **Advanced Arguments**.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scheme"::: -->
:::moniker range="<=azure-pipelines"

**`scheme`** - **Scheme**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the Xcode scheme name. *Must be a shared scheme* (shared checkbox under **Managed Schemes** in Xcode). **Required if Workspace is specified.**
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageApp"::: -->
:::moniker range="<=azure-pipelines"

**`packageApp`** - **Create App Package**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether an IPA is generated as a part of the build. For exporting archives with Xcode 7 and Xcode 8, review additional inputs in the **Package Options** section.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageTool"::: -->
:::moniker range="<=azure-pipelines"

**`packageTool`** - **Create Package (IPA) using**<br>
`string`. Required. Allowed values: `xcrun` (xcrun (deprecated by Apple)), `xcodebuild` (xcodebuild archive and export). Default value: `xcodebuild`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the tool to use for generating the IPA.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="archivePath"::: -->
:::moniker range="<=azure-pipelines"

**`archivePath`** - **Archive Path**<br>
`string`. Optional. Use when `packageTool == xcodebuild`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a directory where created archives are placed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportPath"::: -->
:::moniker range="<=azure-pipelines"

**`exportPath`** - **Export Path**<br>
`string`. Optional. Use when `packageTool == xcodebuild`. Default value: `output/$(SDK)/$(Configuration)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the destination for the product exported from the archive.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportOptions"::: -->
:::moniker range="<=azure-pipelines"

**`exportOptions`** - **Export Options**<br>
`string`. Optional. Use when `packageTool == xcodebuild`. Allowed values: `auto`, `plist`, `specify`. Default value: `auto`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a way to pass in **Export Options** when exporting the archive.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportMethod"::: -->
:::moniker range="<=azure-pipelines"

**`exportMethod`** - **Export Method**<br>
`string`. Required when `exportOptions == specify`. Default value: `development`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the method Xcode uses to export the archive. For example, `app-store`, `package`, `ad-hoc`, `enterprise`, or `development`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportTeamId"::: -->
:::moniker range="<=azure-pipelines"

**`exportTeamId`** - **Team ID**<br>
`string`. Optional. Use when `exportOptions == specify`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Apple Developer Portal 10-digit team ID to use for the export.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exportOptionsPlist"::: -->
:::moniker range="<=azure-pipelines"

**`exportOptionsPlist`** - **Export Options Plist**<br>
`string`. Required when `exportOptions == plist`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to a plist file that configures archive exporting.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcode8AutomaticSigning"::: -->
:::moniker range="<=azure-pipelines"

**`xcode8AutomaticSigning`** - **Automatic Signing**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this input if you have an Xcode 8 or Xcode 9 project configured for Automatic Signing.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="teamId"::: -->
:::moniker range="<=azure-pipelines"

**`teamId`** - **Team ID**<br>
`string`. Optional. Use when `xcode8AutomaticSigning = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the 10-digit developer team ID. This is required if you are a member of multiple development teams.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signMethod"::: -->
:::moniker range="<=azure-pipelines"

**`signMethod`** - **Override Using**<br>
`string`. Allowed values: `file` (File Contents), `id` (Identifiers). Default value: `file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this input if the build uses a signing or provisioning method that is different than the default. Choose `File Contents` to use a P12 certificate and provisioning profile. Choose `Identifiers` to retrieve signing settings from the default keychain and pre-installed profiles. Leave the corresponding fields blank if you do not wish to override the default build settings.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="iosSigningIdentity"::: -->
:::moniker range="<=azure-pipelines"

**`iosSigningIdentity`** - **Signing Identity**<br>
`string`. Optional. Use when `signMethod = id`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the signing identity override that is used to sign the build. Defaults to the Xcode project setting. **Unlock Default Keychain** may need to be selected.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="unlockDefaultKeychain"::: -->
:::moniker range="<=azure-pipelines"

**`unlockDefaultKeychain`** - **Unlock Default Keychain**<br>
`boolean`. Optional. Use when `signMethod = id`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Resolves **User interaction is not allowed** errors by unlocking the default keychain.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="defaultKeychainPassword"::: -->
:::moniker range="<=azure-pipelines"

**`defaultKeychainPassword`** - **Default Keychain Password**<br>
`string`. Optional. Use when `signMethod = id`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password to unlock the default keychain.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="provProfileUuid"::: -->
:::moniker range="<=azure-pipelines"

**`provProfileUuid`** - **Provisioning Profile UUID**<br>
`string`. Optional. Use when `signMethod = id`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the UUID of an installed provisioning profile to use for the build. Use separate build tasks with different schemes or targets to specify provisioning profiles by target in a single workspace (iOS, WatchKit, tvOS).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="p12"::: -->
:::moniker range="<=azure-pipelines"

**`p12`** - **P12 Certificate File**<br>
`string`. Optional. Use when `signMethod = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path to a PKCS12 formatted P12 certificate file that contains a signing certificate to be used for the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="p12pwd"::: -->
:::moniker range="<=azure-pipelines"

**`p12pwd`** - **P12 Password**<br>
`string`. Optional. Use when `signMethod = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password to a P12 certificate file if specified. Use a build variable to encrypt.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="provProfile"::: -->
:::moniker range="<=azure-pipelines"

**`provProfile`** - **Provisioning Profile File**<br>
`string`. Optional. Use when `signMethod = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path to a file containing a provisioning profile override to be used for the build. Use separate build tasks with different schemes or targets to specify provisioning profiles by target in a single workspace (iOS, WatchKit, tvOS).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="removeProfile"::: -->
:::moniker range="<=azure-pipelines"

**`removeProfile`** - **Remove Profile After Build**<br>
`boolean`. Optional. Use when `signMethod = file`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Removes the contents of the provisioning profile file from the build agent after the build is complete. **Only check if you are running one agent per user.**
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="args"::: -->
:::moniker range="<=azure-pipelines"

**`args`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional command line arguments used to build. This input is useful if you want to use `-target` or `-project` instead of specifying a workspace and scheme.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cwd"::: -->
:::moniker range="<=azure-pipelines"

**`cwd`** - **Working Directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the working directory for build runs. Defaults to the root of the repository.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputPattern"::: -->
:::moniker range="<=azure-pipelines"

**`outputPattern`** - **Output Directory**<br>
`string`. Required. Default value: `output/$(SDK)/$(Configuration)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path where build output (binaries) are placed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xcodeDeveloperDir"::: -->
:::moniker range="<=azure-pipelines"

**`xcodeDeveloperDir`** - **Xcode Developer Path**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the path to the Xcode Developer folder if it's not the system default. For use when multiple versions of Xcode are installed on a system. For example: `/Applications/Xcode 7.app/Contents/Developer`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useXcpretty"::: -->
:::moniker range="<=azure-pipelines"

**`useXcpretty`** - **Use xcpretty**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Formats `xcodebuild` output and generates a JUnit test results report. Must be installed on agent hosts. Learn more about [xcpretty](https://github.com/supermarin/xcpretty).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range="<=azure-pipelines"

**`publishJUnitResults`** - **Publish to VSTS/TFS**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
JUnit test results that were produced using `xctool` are published to VSTS/TFS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useXctool"::: -->
:::moniker range="<=azure-pipelines"

**`useXctool`** - **Use xctool**<br>
`boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uses `xctool` instead of `xcodebuild`. Must be installed on agent hosts. Learn more about [xctool](https://github.com/facebook/xctool).  
*Note:* `xctool` is deprecated and does not work with Xcode 8.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xctoolReporter"::: -->
:::moniker range="<=azure-pipelines"

**`xctoolReporter`** - **xctool Test Reporter Format**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Tests the reporter format to use when the **test** action is specified and **Use xctool** is checked. Specify `junit:output-file-path-here.xml` to generate a file format compatible with the Publish Test Results task. When specified, **plain** is automatically added. `xctool` must be installed on agent hosts. Learn more about [xctool](https://github.com/facebook/xctool).  
*Note:* `xctool` is deprecated and does not work with Xcode 8.
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