---
title: InstallAppleProvisioningProfile@0 - Install Apple Provisioning Profile v0 task
description: Install an Apple provisioning profile required to build on a macOS agent.
ms.date: 04/16/2024
monikerRange: "<=azure-pipelines"
---

# InstallAppleProvisioningProfile@0 - Install Apple Provisioning Profile v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to install an Apple provisioning profile, which is required in order to build on a macOS agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Install Apple Provisioning Profile v0
# Install an Apple provisioning profile required to build on a macOS agent.
- task: InstallAppleProvisioningProfile@0
  inputs:
    provProfileSecureFile: # string. Required. Provisioning Profile. 
    #removeProfile: true # boolean. Remove Profile After Build. Default: true.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="provProfileSecureFile"::: -->
:::moniker range="<=azure-pipelines"

**`provProfileSecureFile`** - **Provisioning Profile**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the provisioning profile that was uploaded to `Secure Files` to install on the macOS agent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="removeProfile"::: -->
:::moniker range="<=azure-pipelines"

**`removeProfile`** - **Remove Profile After Build**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies that the provisioning profile should be removed from the agent after the build or release is complete.
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

You can use this task to install provisioning profiles needed to build iOS Apps, Apple WatchKit apps, and App extensions.

You can install an Apple provisioning profile that is:

- Stored as a [secure file](/azure/devops/pipelines/library/secure-files) on the server.
- Committed to the source repository or copied to a local path on the macOS agent. You should encrypt the provisioning profiles if you are committing them to the source repository. You can use the **Decrypt File** task to decrypt the profiles during a build or release.
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
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: xcode |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.116.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->