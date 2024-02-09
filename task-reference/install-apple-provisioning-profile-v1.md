---
title: InstallAppleProvisioningProfile@1 - Install Apple provisioning profile v1 task
description: Install an Apple provisioning profile required to build on a macOS agent machine.
ms.date: 02/09/2024
monikerRange: "<=azure-pipelines"
---

# InstallAppleProvisioningProfile@1 - Install Apple provisioning profile v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to install an Apple provisioning profile, which is required in order to build on a macOS agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Install Apple provisioning profile v1
# Install an Apple provisioning profile required to build on a macOS agent machine.
- task: InstallAppleProvisioningProfile@1
  inputs:
    provisioningProfileLocation: 'secureFiles' # 'secureFiles' | 'sourceRepository'. Required. Provisioning profile location. Default: secureFiles.
    provProfileSecureFile: # string. Required when provisioningProfileLocation == secureFiles. Provisioning profile. 
    #provProfileSourceRepository: # string. Required when provisioningProfileLocation == sourceRepository. Provisioning profile. 
    #removeProfile: true # boolean. Remove profile after build. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Install Apple Provisioning Profile v1
# Install an Apple provisioning profile required to build on a macOS agent.
- task: InstallAppleProvisioningProfile@1
  inputs:
    provisioningProfileLocation: 'secureFiles' # 'secureFiles' | 'sourceRepository'. Required. Provisioning profile location. Default: secureFiles.
    provProfileSecureFile: # string. Required when provisioningProfileLocation == secureFiles. Provisioning profile. 
    #provProfileSourceRepository: # string. Required when provisioningProfileLocation == sourceRepository. Provisioning profile. 
    #removeProfile: true # boolean. Remove profile after build. Default: true.
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

<!-- :::item name="provisioningProfileLocation"::: -->
:::moniker range="<=azure-pipelines"

**`provisioningProfileLocation`** - **Provisioning profile location**<br>
`string`. Required. Allowed values: `secureFiles` (Secure Files), `sourceRepository` (Source Repository). Default value: `secureFiles`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the provisioning profile to install. The provisioning profile can be uploaded to `Secure Files`, or stored in your source repository or a local path on the agent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="provProfileSecureFile"::: -->
:::moniker range="<=azure-pipelines"

**`provProfileSecureFile`** - **Provisioning profile**<br>
`string`. Required when `provisioningProfileLocation == secureFiles`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the provisioning profile that was uploaded to `Secure Files` to install on the macOS agent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="provProfileSourceRepository"::: -->
:::moniker range="<=azure-pipelines"

**`provProfileSourceRepository`** - **Provisioning profile**<br>
`string`. Required when `provisioningProfileLocation == sourceRepository`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the provisioning profile from the source repository or the local path to a provisioning profile on the macOS agent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="removeProfile"::: -->
:::moniker range="<=azure-pipelines"

**`removeProfile`** - **Remove profile after build**<br>
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

:::moniker range=">=azure-pipelines-2019"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="provisioningProfileUuid"::: -->
**`provisioningProfileUuid`**<br><!-- :::editable-content name="Value"::: -->
The UUID property for the selected provisioning profile.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="provisioningProfileName"::: -->
**`provisioningProfileName`**<br><!-- :::editable-content name="Value"::: -->
The Name property for the selected provisioning profile.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="provisioningProfileUuid"::: -->
**`provisioningProfileUuid`**<br><!-- :::editable-content name="Value"::: -->
The UUID property for the selected provisioning profile.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

You can use this task to install provisioning profiles needed to build iOS Apps, Apple WatchKit apps, and App extensions.

You can install an Apple provisioning profile that is:

- Stored as a [secure file](/azure/devops/pipelines/library/secure-files) on the server.
- Committed to the source repository or copied to a local path on the macOS agent. You should encrypt the provisioning profiles if you are committing them to the source repository. The **Decrypt File** task can be used to decrypt the profiles during a build or release.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: xcode |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task runs using the following [command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): restricted |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): provisioningProfileUuid, provisioningProfileName, APPLE_PROV_PROFILE_UUID |
| Agent version |  2.182.1 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

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