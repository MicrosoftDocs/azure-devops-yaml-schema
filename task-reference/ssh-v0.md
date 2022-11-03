---
title: SSH@0 - SSH v0 task
description: Run shell commands or a script on a remote machine using SSH.
ms.date: 11/03/2022
monikerRange: "<=azure-pipelines"
---

# SSH@0 - SSH v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to run shell commands or a script on a remote machine using SSH. This task enables you to connect to a remote machine using SSH and run commands or a script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# SSH v0
# Run shell commands or a script on a remote machine using SSH.
- task: SSH@0
  inputs:
    sshEndpoint: # string. Required. SSH service connection. 
    runOptions: 'commands' # 'commands' | 'script' | 'inline'. Required. Run. Default: commands.
    commands: # string. Required when runOptions = commands. Commands. 
    #scriptPath: # string. Required when runOptions = script. Shell script path. 
    #inline: # string. Required when runOptions = inline. Inline Script. 
    #interpreterCommand: '/bin/bash' # string. Optional. Use when runOptions = inline. Interpreter command. Default: /bin/bash.
    #args: # string. Optional. Use when runOptions = script. Arguments. 
  # Advanced
    #failOnStdErr: true # boolean. Fail on STDERR. Default: true.
    #interactiveSession: false # boolean. Enable interactive session. Default: false.
    readyTimeout: '20000' # string. Required. SSH handshake timeout. Default: 20000.
    #interactiveKeyboardAuthentication: false # boolean. Use interactive-keyboard authentication. Default: false.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020.1 <=azure-pipelines-2022"

```yaml
# SSH v0
# Run shell commands or a script on a remote machine using SSH.
- task: SSH@0
  inputs:
    sshEndpoint: # string. Required. SSH service connection. 
    runOptions: 'commands' # 'commands' | 'script' | 'inline'. Required. Run. Default: commands.
    commands: # string. Required when runOptions = commands. Commands. 
    #scriptPath: # string. Required when runOptions = script. Shell script path. 
    #inline: # string. Required when runOptions = inline. Inline Script. 
    #interpreterCommand: '/bin/bash' # string. Optional. Use when runOptions = inline. Interpreter command. Default: /bin/bash.
    #args: # string. Optional. Use when runOptions = script. Arguments. 
  # Advanced
    #failOnStdErr: true # boolean. Fail on STDERR. Default: true.
    #interactiveSession: false # boolean. Enable interactive session. Default: false.
    readyTimeout: '20000' # string. Required. SSH handshake timeout. Default: 20000.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# SSH v0
# Run shell commands or a script on a remote machine using SSH.
- task: SSH@0
  inputs:
    sshEndpoint: # string. Required. SSH service connection. 
    runOptions: 'commands' # 'commands' | 'script' | 'inline'. Required. Run. Default: commands.
    commands: # string. Required when runOptions = commands. Commands. 
    #scriptPath: # string. Required when runOptions = script. Shell script path. 
    #inline: # string. Required when runOptions = inline. Inline Script. 
    #args: # string. Optional. Use when runOptions = script. Arguments. 
  # Advanced
    #failOnStdErr: true # boolean. Fail on STDERR. Default: true.
    readyTimeout: '20000' # string. Required. SSH handshake timeout. Default: 20000.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
# SSH v0
# Run shell commands or a script on a remote machine using SSH.
- task: SSH@0
  inputs:
    sshEndpoint: # string. Required. SSH service connection. 
    runOptions: 'commands' # 'commands' | 'script' | 'inline'. Required. Run. Default: commands.
    commands: # string. Required when runOptions = commands. Commands. 
    #scriptPath: # string. Required when runOptions = script. Shell script path. 
    #inline: # string. Required when runOptions = inline. Inline Script. 
    #args: # string. Optional. Use when runOptions = script. Arguments. 
  # Advanced
    #failOnStdErr: true # boolean. Fail on STDERR. Default: true.
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

<!-- :::item name="sshEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`sshEndpoint`** - **SSH service connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of an SSH service connection containing connection details for the remote machine. The hostname or IP address of the remote machine, the port number, and the user name are required to create an SSH service connection.

- The private key and the passphrase must be specified for authentication.
- A password can be used to authenticate to remote Linux machines, but this is not supported for macOS or Windows systems.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`sshEndpoint`** - **SSH endpoint**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of an SSH service connection containing connection details for the remote machine. The hostname or IP address of the remote machine, the port number, and the user name are required to create an SSH service connection.

- The private key and the passphrase must be specified for authentication.
- A password can be used to authenticate to remote Linux machines, but this is not supported for macOS or Windows systems.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runOptions"::: -->
:::moniker range="<=azure-pipelines"

**`runOptions`** - **Run**<br>
`string`. Required. Allowed values: `commands`, `script` (Script File), `inline` (Inline Script). Default value: `commands`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs shell commands or a shell script on the remote machine.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="commands"::: -->
:::moniker range="<=azure-pipelines"

**`commands`** - **Commands**<br>
`string`. Required when `runOptions = commands`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the shell commands to run on the remote machine. This parameter is available only when **Commands** is selected for the **Run** option. Enter each command together with its arguments on a new line of the multi-line textbox. To run multiple commands together, enter them on the same line separated by semicolons. Example: `cd /home/user/myFolder;build`.

> [!NOTE]
> Each command runs in a separate process. If you want to run a series of commands that are interdependent (for example, changing the current folder before executing a command), use the **Inline Script** option instead.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`scriptPath`** - **Shell script path**<br>
`string`. Required when `runOptions = script`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the shell script file to run on the remote machine. This parameter is available only when **Shell script** is selected for the **Run** option.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="inline"::: -->
:::moniker range="<=azure-pipelines"

**`inline`** - **Inline Script**<br>
`string`. Required when `runOptions = inline`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Writes the shell script to run on the remote machine.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="interpreterCommand"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`interpreterCommand`** - **Interpreter command**<br>
`string`. Optional. Use when `runOptions = inline`. Default value: `/bin/bash`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the command interpreter used to execute the script. Adds a shebang line to the beginning of the script. Relevant only for UNIX-like operating systems. Use an empty string for Windows-based remote hosts. Learn more about [shebang (#!)](https://homepages.cwi.nl/~aeb/std/shebang/unix-faq.txt).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="args"::: -->
:::moniker range="<=azure-pipelines"

**`args`** - **Arguments**<br>
`string`. Optional. Use when `runOptions = script`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the arguments to pass to the shell script. This parameter is available only when **Shell script** is selected for the **Run** option.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStdErr"::: -->
:::moniker range="<=azure-pipelines"

**`failOnStdErr`** - **Fail on STDERR**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the value is `true`, the build fails when the remote commands or script write to `STDERR`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="interactiveSession"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`interactiveSession`** - **Enable interactive session**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Starts an interactive session. Password requests are filled by the user's password. Interactive sessions can be useful for running commands, such as `sudo`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="readyTimeout"::: -->
:::moniker range=">=azure-pipelines-2020"

**`readyTimeout`** - **SSH handshake timeout**<br>
`string`. Required. Default value: `20000`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies how long (in milliseconds) the task waits for the SSH handshake to complete.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="interactiveKeyboardAuthentication"::: -->
:::moniker range="=azure-pipelines"

**`interactiveKeyboardAuthentication`** - **Use interactive-keyboard authentication**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enables interactive-keyboard authentication. Use this value if `PasswordAuthentication` is disabled on the target machine.
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

Use this task to run shell commands or a script on a remote machine using SSH.
This task enables you to connect to a remote machine using SSH and run commands or a script.

### Prerequisites

* The task supports use of an SSH key pair to connect to the remote machine(s).
* The public key must be pre-installed or copied to the remote machine(s).

### Supported algorithms

#### Key pair algorithms

* RSA
* DSA

#### Encryption algorithms

* aes256-cbc
* aes192-cbc
* aes128-cbc
* blowfish-cbc
* 3des-cbc
* arcfour256
* arcfour128
* cast128-cbc
* arcfour

For OpenSSL v1.0.1 and higher (on agent):
* aes256-ctr
* aes192-ctr
* aes128-ctr

For OpenSSL v1.0.1 and higher, NodeJS v0.11.12 and higher (on agent):
* aes128-gcm
* aes128-gcm@openssh.com
* aes256-gcm
* aes256-gcm@openssh.com
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Deploy |

:::moniker-end

:::moniker range="<=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.102.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Install SSH Key task](install-ssh-key-v0.md)
* [Copy Files Over SSH](copy-files-over-ssh-v0.md)
* Blog post [SSH build task](https://devblogs.microsoft.com/devops/ssh-build-task/)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->