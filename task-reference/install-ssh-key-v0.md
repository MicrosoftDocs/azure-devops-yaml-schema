---
title: InstallSSHKey@0 - Install SSH key v0 task
description: Install an SSH key prior to a build or deployment.
ms.date: 04/29/2024
monikerRange: "<=azure-pipelines"
---

# InstallSSHKey@0 - Install SSH key v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task in a pipeline to install an SSH key prior to a build or release step.
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
    knownHostsEntry: # string. Alias: hostName. Required. Known Hosts Entry. 
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
    knownHostsEntry: # string. Alias: hostName. Required. Known Hosts Entry. 
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
    knownHostsEntry: # string. Alias: hostName. Required. Known Hosts Entry. 
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


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="knownHostsEntry"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`knownHostsEntry`** - **Known Hosts Entry**<br>
Input alias: `hostName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SSH key entry for the known_hosts file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sshPublicKey"::: -->
:::moniker range=">=azure-pipelines-2020"

**`sshPublicKey`** - **SSH Public Key**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the contents of the public SSH key.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`sshPublicKey`** - **SSH Public Key**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the contents of the public SSH key.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sshPassphrase"::: -->
:::moniker range="<=azure-pipelines"

**`sshPassphrase`** - **SSH Passphrase**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the passphrase for the SSH key, if any.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sshKeySecureFile"::: -->
:::moniker range="<=azure-pipelines"

**`sshKeySecureFile`** - **SSH Key**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SSH key that was uploaded to `Secure Files` to install on the agent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addEntryToConfig"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`addEntryToConfig`** - **Add entry to SSH config**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Adds an entry related to the key that was installed to the SSH config file. The key file will be available for all subsequent tasks.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configHostAlias"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`configHostAlias`** - **Alias**<br>
`string`. Required when `addEntryToConfig = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the SSH config entry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configHostname"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`configHostname`** - **Host name**<br>
`string`. Required when `addEntryToConfig = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the host name property of SSH config entry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configUser"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`configUser`** - **User**<br>
`string`. Optional. Use when `addEntryToConfig = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the user name property of the SSH config entry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configPort"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`configPort`** - **Port**<br>
`string`. Optional. Use when `addEntryToConfig = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the port of the SSH config entry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="hostName"::: -->
:::moniker range="=azure-pipelines-2019"

**`hostName`** - **Known Hosts Entry**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SSH key entry for the known_hosts file.
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

Use this task in a pipeline to install an SSH key prior to a build or release step.

> [!NOTE]
> This task required Git Bash for Windows on the agent.

### Usage and best practices

If you install an SSH key in the [hosted pools](/azure/devops/pipelines/agents/hosted), in later steps in your pipeline, you can connect to a remote system in which the matching public key is already in place. For example, you can connect to a Git repository or to a VM in Azure.

We recommend that you don't pass in your public key as plain text to the task configuration. Instead, [set a secret variable](/azure/devops/pipelines/process/variables#secret-variables) in your pipeline for the contents of your `mykey.pub` file. Then, call the variable in your pipeline definition as `$(myPubKey)`. For the secret part of your key, use the [Secure File library](/azure/devops/pipelines/library/secure-files) in Azure Pipelines.  

To create your task, use the following example of a well-configured Install SSH Key task:

```yaml
steps:
- task: InstallSSHKey@0
  displayName: 'Install an SSH key'
  inputs:
    knownHostsEntry: 'SHA256:1Hyr55tsxGifESBMc0s+2NtutnR/4+LOkVwrOGrIp8U johndoe@contoso'
    sshPublicKey: '$(myPubKey)'
    sshKeySecureFile: 'id_rsa'
```

> [!NOTE]
> Your public key should be added to the repository\organization; otherwise, there will be access issues. For GitHub, follow [the guide above](#example-setup-using-github). For Azure DevOps Services, use [Add the public key to Azure DevOps Services/TFS](/azure/devops/repos/git/use-ssh-keys-to-authenticate).

### Installing of multiple SSH keys in the same pipeline job

When using more than one key in the same pipeline job, the first one is used by default. To be able to use the desired key when establishing an SSH connection, you can use the `Advanced` section of the `InstallSSHKey` task to set the following parameters: `addEntryToConfig`, `configHostAlias`, `configHostname`, `configUser`, and `configPort`.

These parameters allow you to add a host to the SSH config file (for example, `/root/.ssh/config` for Linux) in order to use it in custom scripts via an alias.

After the build is completed, the task will attempt to restore the original SSH config file. If there was no SSH config file initially, then the host is removed from the agent.

An example of multiple SSH keys installation. The case with several GitHub repos and their own key for each one:
```yml
pool: <Some Agent Pool>

steps:
- task: InstallSSHKey@0
  inputs:
    knownHostsEntry: $(known_host)
    sshPublicKey: $(first_public_key)
    sshKeySecureFile: $(first_private_key)
    addEntryToConfig: true
    configHostAlias: <first-host-alias>
    configHostname: github.com
    configUser: git
  displayName: Install First Repo SSH Key

- task: InstallSSHKey@0
  inputs:
    knownHostsEntry: $(known_host)
    sshPublicKey: $(second_public_key)
    sshKeySecureFile: $(second_private_key)
    addEntryToConfig: true
    configHostAlias: <second-host-alias>
    configHostname: github.com
    configUser: git
  displayName: Install Second Repo SSH Key

- bash: git clone git@<first-host-alias>:<owner>/<first-repo>.git
  displayName: Clone First Repo

- bash: git clone git@<second-host-alias>:<owner>/<second-repo>.git
  displayName: Clone Second Repo
```

[Related GitHub docs](https://docs.github.com/en/developers/overview/managing-deploy-keys#using-multiple-repositories-on-one-server).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Example setup using GitHub

This section describes how to use a private GitHub repository with YAML from within Azure Pipelines.

If you have a repository that you don't want to expose to the open-source community, a common practice is to make the repository private. However, a CI/CD tool like Azure DevOps needs access to the repository if you want to use the tool to manage the repository. To give Azure DevOps access, you might need an SSH key to authenticate access to GitHub.

Here are the steps to use an SSH key to authenticate access to GitHub:

1. Generate a key pair to use to authenticate access from GitHub to Azure DevOps:

   1. In GitBash, run the following command:

       ```bash
       ssh-keygen -t rsa
       ```

    1. Enter a name for the SSH key pair. In our example, we use **myKey**.

        :::image type="content" alt-text="Screenshot of the GitBash prompt to enter a name for your SSH key pair." source="./media/ssh-task-01.png":::
     
    1. (Optional) You can enter a passphrase to encrypt your private key. This step is optional. Using a passphrase is more secure than not using one.
   
        :::image type="content" alt-text="Screenshot of the GitBash prompt to enter a passphrase for your SSH key pair." source="./media/ssh-task-02.png":::
   
       `ssh-keygen` creates the SSH key pairs, and the following success message appears:
   
       :::image type="content" alt-text="Screenshot of the GitBash message that shows that an SSH key pair was created." source="./media/ssh-task-03.png":::
     
    1. In Windows File Explorer, check your newly created key pair:
   
        :::image type="content" alt-text="Screenshot of the key pair files in Windows File Explorer." source="./media/ssh-task-04.png":::
     
2. Add the public key to the GitHub repository. (The public key ends in  ".pub"). To do this, go the following URL in your browser: `https://github.com/(organization-name)/(repository-name)/settings/keys`.  

    1. Select **Add deploy key**.
   
    1. In the **Add new** dialog box, enter a title, and then copy and paste the SSH key:
   
        :::image type="content" alt-text="Screenshot of the Add new dialog box." source="./media/ssh-task-05.png":::
     
    1.  Select **Add key**.
   
 3. Upload your private key to Azure DevOps:
 
    1. In Azure DevOps, in the left menu, select **Pipelines** > **Library**.
   
        :::image type="content" alt-text="Screenshot of the Azure Pipelines menu." source="./media/ssh-task-06.png":::
     
    1.  Select **Secure files** > **+ Secure file**:
   
        :::image type="content" alt-text="Screenshot of the Secure files menu." source="./media/ssh-task-07.png":::
     
    1.  Select **Browse**, and then select your private key:
     
        :::image type="content" alt-text="Screenshot of the Upload file dialog box and the Browse button." source="./media/ssh-task-08.png":::
       
  4. Recover your "Known Hosts Entry". In GitBash, enter the following command:
   
      ```bash
      ssh-keyscan github.com
      ```
   
      Your "Known Hosts Entry" is the displayed value that doesn't begin with **#** in the GitBash results:
     
      :::image type="content" alt-text="Screenshot of key search results in GitBash." source="./media/ssh-task-09.png":::
    
  5. Create a YAML pipeline.
  
     To create a YAML pipeline, in the YAML definition, add the following task:
  
     ```bash
     - task: InstallSSHKey@0
      inputs:
        knownHostsEntry: #{Enter your Known Hosts Entry Here}
        sshPublicKey: #{Enter your Public key Here}
        sshKeySecureFile: #{Enter the name of your key in "Secure Files" Here}
     ```
  
The SSH keys are now installed, and you can proceed with the script to connect by using SSH, and not the default HTTPS.
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