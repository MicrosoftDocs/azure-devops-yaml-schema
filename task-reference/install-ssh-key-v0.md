---
title: InstallSSHKey@0 - Install SSH key v0 task
description: Install an SSH key prior to a build or deployment.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# InstallSSHKey@0 - Install SSH key v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Install an SSH key prior to a build or deployment.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Install an SSH key prior to a build or release.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020.1"

```yaml
# Install SSH key v0
# Install an SSH key prior to a build or deployment.
- task: InstallSSHKey@0
  inputs:
    knownHostsEntry: # string. Required. Known Hosts Entry. 
    #sshPublicKey: # string. SSH Public Key. 
    #sshPassphrase: # string. SSH Passphrase. 
    sshKeySecureFile: # string. Required. SSH Key. 
  # Advanced
    #addEntryToConfig: false # boolean. Add entry to SSH config. Default: false.
    #configHostAlias: # string. Required when addEntryToConfig = true. Alias. 
    #configHostname: # string. Required when addEntryToConfig = true. Host name. 
    #configUser: # string. Optional. Use when addEntryToConfig = true. User. 
    #configPort: # string. Optional. Use when addEntryToConfig = true. Port.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Install SSH key v0
# Install an SSH key prior to a build or deployment.
- task: InstallSSHKey@0
  inputs:
    knownHostsEntry: # string. Required. Known Hosts Entry. 
    #sshPublicKey: # string. SSH Public Key. 
    #sshPassphrase: # string. SSH Passphrase. 
    sshKeySecureFile: # string. Required. SSH Key.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Install SSH key v0
# Install an SSH key prior to a build or deployment.
- task: InstallSSHKey@0
  inputs:
    knownHostsEntry: # string. Required. Known Hosts Entry. 
    sshPublicKey: # string. Required. SSH Public Key. 
    #sshPassphrase: # string. SSH Passphrase. 
    sshKeySecureFile: # string. Required. SSH Key.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Install SSH Key v0
# Install an SSH key prior to a build or release.
- task: InstallSSHKey@0
  inputs:
    hostName: # string. Required. Known Hosts Entry. 
    sshPublicKey: # string. Required. SSH Public Key. 
    #sshPassphrase: # string. SSH Passphrase. 
    sshKeySecureFile: # string. Required. SSH Key.
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

<!-- :::item name="knownHostsEntry"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`knownHostsEntry`** - **Known Hosts Entry**<br>
Input alias: `hostName`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The entry for this SSH key for the known_hosts file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sshPublicKey"::: -->
:::moniker range=">=azure-pipelines-2020"

**`sshPublicKey`** - **SSH Public Key**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The contents of the public SSH key.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`sshPublicKey`** - **SSH Public Key**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The contents of the public SSH key.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sshPassphrase"::: -->
:::moniker range="<=azure-pipelines"

**`sshPassphrase`** - **SSH Passphrase**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The passphrase for the SSH key, if any.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sshKeySecureFile"::: -->
:::moniker range="<=azure-pipelines"

**`sshKeySecureFile`** - **SSH Key**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the SSH key that was uploaded to `Secure Files` to install on the agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addEntryToConfig"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`addEntryToConfig`** - **Add entry to SSH config**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Add entry related to the key installed to the SSH config file. The key file will be available for all subsequent tasks.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configHostAlias"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`configHostAlias`** - **Alias**<br>
Type: string. Required when addEntryToConfig = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of SSH config entry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configHostname"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`configHostname`** - **Host name**<br>
Type: string. Required when addEntryToConfig = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Host name property of SSH config entry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configUser"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`configUser`** - **User**<br>
Type: string. Optional. Use when addEntryToConfig = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Username property of SSH config entry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configPort"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`configPort`** - **Port**<br>
Type: string. Optional. Use when addEntryToConfig = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Port of SSH config entry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="hostName"::: -->
:::moniker range="<=azure-pipelines-2019"

**`hostName`** - **Known Hosts Entry**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The entry for this SSH key for the known_hosts file.
<!-- :::editable-content-end::: -->

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

:::moniker range=">=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task runs using the following [command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): restricted |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): SSH_AGENT_PID, SSH_AUTH_SOCK, INSTALL_SSH_KEY_CONFIG_LOCATION, INSTALL_SSH_KEY_KNOWN_HOSTS_LOCATION |
| Agent version |  2.182.1 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.117.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->