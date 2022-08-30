---
title: InstallAppleCertificate@2 - Install Apple certificate v2 task
description: Install an Apple certificate required to build on a macOS agent machine.
ms.date: 08/10/2022
monikerRange: ">=azure-pipelines-2019"
---

# InstallAppleCertificate@2 - Install Apple certificate v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Install an Apple certificate required to build on a macOS agent machine.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Install an Apple certificate required to build on a macOS agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Install Apple certificate v2
# Install an Apple certificate required to build on a macOS agent machine.
- task: InstallAppleCertificate@2
  inputs:
    certSecureFile: # string. Required. Certificate (P12). 
    #certPwd: # string. Certificate (P12) password. 
  # Advanced
    keychain: 'temp' # 'default' | 'temp' | 'custom'. Required. Keychain. Default: 'temp'.
    #keychainPassword: # string. Required when keychain = custom || keychain = default. Keychain password. 
    #customKeychainPath: # string. Required when keychain = custom. Custom keychain path. 
    #deleteCert: # boolean. Optional. Use when keychain = custom || keychain = default. Delete certificate from keychain. 
    #deleteCustomKeychain: # boolean. Optional. Use when keychain = custom. Delete custom keychain. 
    #signingIdentity: # string. Certificate signing identity. 
    #setUpPartitionIdACLForPrivateKey: # boolean. Set up partition_id ACL for the imported private key.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

```yaml
# Install Apple certificate v2
# Install an Apple certificate required to build on a macOS agent machine.
- task: InstallAppleCertificate@2
  inputs:
    certSecureFile: # string. Required. Certificate (P12). 
    #certPwd: # string. Certificate (P12) password. 
  # Advanced
    keychain: 'temp' # 'default' | 'temp' | 'custom'. Required. Keychain. Default: 'temp'.
    #keychainPassword: # string. Required when keychain = custom || keychain = default. Keychain password. 
    #customKeychainPath: # string. Required when keychain = custom. Custom keychain path. 
    #deleteCert: # boolean. Optional. Use when keychain = custom || keychain = default. Delete certificate from keychain. 
    #deleteCustomKeychain: # boolean. Optional. Use when keychain = custom. Delete custom keychain. 
    #signingIdentity: # string. Certificate signing identity.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Install Apple Certificate v2
# Install an Apple certificate required to build on a macOS agent.
- task: InstallAppleCertificate@2
  inputs:
    certSecureFile: # string. Required. Certificate (P12). 
    #certPwd: # string. Certificate (P12) password. 
  # Advanced
    keychain: 'temp' # 'default' | 'temp' | 'custom'. Required. Keychain. Default: 'temp'.
    #keychainPassword: # string. Required when keychain = custom || keychain = default. Keychain password. 
    #customKeychainPath: # string. Required when keychain = custom. Custom keychain path. 
    #deleteCert: # boolean. Optional. Use when keychain = custom || keychain = default. Delete certificate from keychain. 
    #deleteCustomKeychain: # boolean. Optional. Use when keychain = custom. Delete custom keychain. 
    #signingIdentity: # string. Certificate signing identity.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="certSecureFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`certSecureFile`** - **Certificate (P12)**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the certificate (.p12) that was uploaded to `Secure Files` to install on the macOS agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="certPwd"::: -->
:::moniker range=">=azure-pipelines-2019"

**`certPwd`** - **Certificate (P12) password**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password to the Apple certificate (.p12). Use a new build variable with its lock enabled on the `Variables` tab to encrypt this value.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="keychain"::: -->
:::moniker range=">=azure-pipelines-2019"

**`keychain`** - **Keychain**<br>
Type: string. Required. Allowed values: 'default', 'temp', 'custom'. Default value: 'temp'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the keychain in which to install the Apple certificate. For Microsoft hosted builds, use `Temporary Keychain`. A temporary keychain will always be deleted after the build or release is complete.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="keychainPassword"::: -->
:::moniker range=">=azure-pipelines-2019"

**`keychainPassword`** - **Keychain password**<br>
Type: string. Required when keychain = custom || keychain = default.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password to unlock the keychain. Use a new build variable with its lock enabled on the `Variables` tab to encrypt this value.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customKeychainPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`customKeychainPath`** - **Custom keychain path**<br>
Type: string. Required when keychain = custom.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Full path to a custom keychain file. The keychain will be created if it does not exist.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deleteCert"::: -->
:::moniker range=">=azure-pipelines-2019"

**`deleteCert`** - **Delete certificate from keychain**<br>
Type: boolean. Optional. Use when keychain = custom || keychain = default.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select to delete the certificate from the keychain after the build or release is complete.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deleteCustomKeychain"::: -->
:::moniker range=">=azure-pipelines-2019"

**`deleteCustomKeychain`** - **Delete custom keychain**<br>
Type: boolean. Optional. Use when keychain = custom.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select to delete the custom keychain from the agent after the build or release is complete.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signingIdentity"::: -->
:::moniker range=">=azure-pipelines-2019"

**`signingIdentity`** - **Certificate signing identity**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Common Name of the subject in the signing certificate.  Will attempt to parse the Common Name if this is left empty.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="setUpPartitionIdACLForPrivateKey"::: -->
:::moniker range=">=azure-pipelines-2022"

**`setUpPartitionIdACLForPrivateKey`** - **Set up partition_id ACL for the imported private key**<br>
Type: boolean.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If true - sets the partition_id ACL for the imported private key, so codesign won't prompt to use the key for signing. This isn't necessary for temporary keychains, at least on MacOS High Sierra. See the [link](http://www.openradar.me/28524119) for more details.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="signingIdentity"::: -->
**`signingIdentity`**<br><!-- :::editable-content name="Value"::: -->
The resolved Common Name of the subject in the signing certificate. Either supplied as an input or parsed from the P12 certificate file.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="keychainPath"::: -->
**`keychainPath`**<br><!-- :::editable-content name="Value"::: -->
The path for the keychain file with the certificate.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Fixes codesign hangs on a self hosted agent. Keychain password is now required to use `Default Keychain` or `Custom Keychain`. Microsoft hosted builds should use `Temporary Keychain`.
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
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): signingIdentity, keychainPassword, keychainPath, APPLE_CERTIFICATE_SIGNING_IDENTITY, APPLE_CERTIFICATE_KEYCHAIN |
| Agent version |  2.182.1 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020.1"

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