---
title: InstallAppleCertificate@1 - Install Apple Certificate v1 task
description: Install an Apple certificate required to build on a macOS agent (task version 1).
ms.date: 09/26/2022
monikerRange: "<=azure-pipelines"
---

# InstallAppleCertificate@1 - Install Apple Certificate v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to install the Apple certificate that is required to build on a macOS agent. You can use this task to install an Apple certificate that is stored as a [secure file](/azure/devops/pipelines/library/secure-files) on the server.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Install Apple Certificate v1
# Install an Apple certificate required to build on a macOS agent.
- task: InstallAppleCertificate@1
  inputs:
    certSecureFile: # string. Required. Certificate (P12). 
    #certPwd: # string. Certificate (P12) password. 
  # Advanced
    keychain: 'temp' # 'default' | 'temp' | 'custom'. Required. Keychain. Default: temp.
    #keychainPassword: # string. Keychain password. 
    #customKeychainPath: # string. Required when keychain = custom. Custom keychain path. 
    #deleteCert: # boolean. Optional. Use when keychain = custom || keychain = default. Delete certificate from keychain. 
    #deleteCustomKeychain: # boolean. Optional. Use when keychain = custom. Delete custom keychain. 
    #signingIdentity: # string. Certificate signing identity.
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

<!-- :::item name="certSecureFile"::: -->
:::moniker range="<=azure-pipelines"

**`certSecureFile`** - **Certificate (P12)**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the certificate (.p12) that was uploaded to `Secure Files` to install on the macOS agent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="certPwd"::: -->
:::moniker range="<=azure-pipelines"

**`certPwd`** - **Certificate (P12) password**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password to the Apple certificate (.p12). Use a new build variable with its lock enabled on the `Variables` tab to encrypt this value.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="keychain"::: -->
:::moniker range="<=azure-pipelines"

**`keychain`** - **Keychain**<br>
`string`. Required. Allowed values: `default` (Default Keychain), `temp` (Temporary Keychain), `custom` (Custom Keychain). Default value: `temp`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the keychain in which to install the Apple certificate. A temporary keychain will always be deleted after the build or release is complete.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="keychainPassword"::: -->
:::moniker range="<=azure-pipelines"

**`keychainPassword`** - **Keychain password**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password to unlock the keychain. Use a new build variable with its lock enabled on the `Variables` tab to encrypt this value. A password is generated for the temporary keychain if one is not already specified.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customKeychainPath"::: -->
:::moniker range="<=azure-pipelines"

**`customKeychainPath`** - **Custom keychain path**<br>
`string`. Required when `keychain = custom`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the full path to a custom keychain file. The keychain will be created if it does not already exist.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deleteCert"::: -->
:::moniker range="<=azure-pipelines"

**`deleteCert`** - **Delete certificate from keychain**<br>
`boolean`. Optional. Use when `keychain = custom || keychain = default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the certificate to delete from the keychain after the build or release is complete.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deleteCustomKeychain"::: -->
:::moniker range="<=azure-pipelines"

**`deleteCustomKeychain`** - **Delete custom keychain**<br>
`boolean`. Optional. Use when `keychain = custom`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the custom keychain to delete from the agent after the build or release is complete.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingIdentity"::: -->
:::moniker range="<=azure-pipelines"

**`signingIdentity`** - **Certificate signing identity**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the `Common Name` of the subject in the signing certificate. Will attempt to parse the `Common Name` if this is left empty.
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

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="signingIdentity"::: -->
**`signingIdentity`**<br><!-- :::editable-content name="Value"::: -->
Specifies the resolved `Common Name` of the subject in the signing certificate. Either supplied as an input or parsed from the P12 certificate file.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="keychainPath"::: -->
**`keychainPath`**<br><!-- :::editable-content name="Value"::: -->
Specifies the path for the keychain file with the certificate.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

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