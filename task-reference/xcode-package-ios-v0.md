---
title: XcodePackageiOS@0 - Xcode Package iOS v0 task
description: Generate an .ipa file from Xcode build output using xcrun (Xcode 7 or below).
ms.date: 03/21/2024
monikerRange: "<=azure-pipelines"
---

# XcodePackageiOS@0 - Xcode Package iOS v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to generate an .ipa file from Xcode build output using xcrun (Xcode 7 or below).

This task is deprecated.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Xcode Package iOS v0
# Generate an .ipa file from Xcode build output using xcrun (Xcode 7 or below).
- task: XcodePackageiOS@0
  inputs:
    appName: 'name.app' # string. Required. Name of .app. Default: name.app.
    ipaName: 'name.ipa' # string. Required. Name of .ipa. Default: name.ipa.
    provisioningProfile: # string. Required. Provisioning Profile Name. 
    sdk: 'iphoneos' # string. Required. SDK. Default: iphoneos.
  # Advanced
    appPath: '$(SDK)/$(Configuration)/build.sym/$(Configuration)-$(SDK)' # string. Required. Path to .app. Default: $(SDK)/$(Configuration)/build.sym/$(Configuration)-$(SDK).
    ipaPath: '$(SDK)/$(Configuration)/build.sym/$(Configuration)-$(SDK)/output' # string. Required. Path to place .ipa. Default: $(SDK)/$(Configuration)/build.sym/$(Configuration)-$(SDK)/output.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="appName"::: -->
:::moniker range="<=azure-pipelines"

**`appName`** - **Name of .app**<br>
`string`. Required. Default value: `name.app`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the .app, which is sometimes different from the .ipa.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ipaName"::: -->
:::moniker range="<=azure-pipelines"

**`ipaName`** - **Name of .ipa**<br>
`string`. Required. Default value: `name.ipa`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the .ipa, which is sometimes different from the .app.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="provisioningProfile"::: -->
:::moniker range="<=azure-pipelines"

**`provisioningProfile`** - **Provisioning Profile Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the provisioning profile to use when signing.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sdk"::: -->
:::moniker range="<=azure-pipelines"

**`sdk`** - **SDK**<br>
`string`. Required. Default value: `iphoneos`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SDK. Run **xcodebuild -showsdks** to see the valid list of SDKs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appPath"::: -->
:::moniker range="<=azure-pipelines"

**`appPath`** - **Path to .app**<br>
`string`. Required. Default value: `$(SDK)/$(Configuration)/build.sym/$(Configuration)-$(SDK)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path to the built .app file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ipaPath"::: -->
:::moniker range="<=azure-pipelines"

**`ipaPath`** - **Path to place .ipa**<br>
`string`. Required. Default value: `$(SDK)/$(Configuration)/build.sym/$(Configuration)-$(SDK)/output`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path where the .ipa is placed. The directory is created if it doesn't exist.
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

Use this task to generate an .ipa file from Xcode build output.

> [!IMPORTANT]
> The Xcode Package iOS task has been deprecated.
It is relevant only if you are using Xcode 6.4.
Otherwise, use the [latest version of the Xcode task](xcode-v5.md).
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