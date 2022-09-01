---
title: SSH@0 - SSH v0 task
description: Run shell commands or a script on a remote machine using SSH.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# SSH@0 - SSH v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Run shell commands or a script on a remote machine using SSH.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020.1"

```yaml
# SSH v0
# Run shell commands or a script on a remote machine using SSH.
- task: SSH@0
  inputs:
    sshEndpoint: # string. Required. SSH service connection. 
    runOptions: 'commands' # 'commands' | 'script' | 'inline'. Required. Run. Default: 'commands'.
    commands: # string. Required when runOptions = commands. Commands. 
    #scriptPath: # string. Required when runOptions = script. Shell script path. 
    #inline: # string. Required when runOptions = inline. Inline Script. 
    #interpreterCommand: '/bin/bash' # string. Optional. Use when runOptions = inline. Interpreter command. Default: '/bin/bash'.
    #args: # string. Optional. Use when runOptions = script. Arguments. 
  # Advanced
    #failOnStdErr: true # boolean. Fail on STDERR. Default: true.
    #interactiveSession: false # boolean. Enable interactive session. Default: false.
    readyTimeout: '20000' # string. Required. SSH handshake timeout. Default: '20000'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# SSH v0
# Run shell commands or a script on a remote machine using SSH.
- task: SSH@0
  inputs:
    sshEndpoint: # string. Required. SSH service connection. 
    runOptions: 'commands' # 'commands' | 'script' | 'inline'. Required. Run. Default: 'commands'.
    commands: # string. Required when runOptions = commands. Commands. 
    #scriptPath: # string. Required when runOptions = script. Shell script path. 
    #inline: # string. Required when runOptions = inline. Inline Script. 
    #args: # string. Optional. Use when runOptions = script. Arguments. 
  # Advanced
    #failOnStdErr: true # boolean. Fail on STDERR. Default: true.
    readyTimeout: '20000' # string. Required. SSH handshake timeout. Default: '20000'.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
# SSH v0
# Run shell commands or a script on a remote machine using SSH.
- task: SSH@0
  inputs:
    sshEndpoint: # string. Required. SSH service connection. 
    runOptions: 'commands' # 'commands' | 'script' | 'inline'. Required. Run. Default: 'commands'.
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
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
SSH service connection with connection details for the remote machine.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`sshEndpoint`** - **SSH endpoint**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
SSH service connection with connection details for the remote machine.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runOptions"::: -->
:::moniker range="<=azure-pipelines"

**`runOptions`** - **Run**<br>
Type: string. Required. Allowed values: 'commands', 'script', 'inline'. Default value: 'commands'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose to either run shell commands or a shell script on the remote machine.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="commands"::: -->
:::moniker range="<=azure-pipelines"

**`commands`** - **Commands**<br>
Type: string. Required when runOptions = commands.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the shell commands to run on the remote machine. Enter each command along with its arguments on a new line. To run multiple commands together, enter them on the same line separated by semi-colons (e.g. cd /home/user/myFolder;build).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`scriptPath`** - **Shell script path**<br>
Type: string. Required when runOptions = script.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the shell script file to run on the remote machine.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="inline"::: -->
:::moniker range="<=azure-pipelines"

**`inline`** - **Inline Script**<br>
Type: string. Required when runOptions = inline.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Write the shell script to run on the remote machine.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="interpreterCommand"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`interpreterCommand`** - **Interpreter command**<br>
Type: string. Optional. Use when runOptions = inline. Default value: '/bin/bash'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the command interpreter used to execute the script. Adds a shebang line to the beginning of the script. Relevant only for UNIX-like operating systems. Please use empty string for Windows-based remote hosts. [See more about shebang (#!)](https://homepages.cwi.nl/~aeb/std/shebang/unix-faq.txt).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="args"::: -->
:::moniker range="<=azure-pipelines"

**`args`** - **Arguments**<br>
Type: string. Optional. Use when runOptions = script.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Arguments to pass to the shell script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStdErr"::: -->
:::moniker range="<=azure-pipelines"

**`failOnStdErr`** - **Fail on STDERR**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this option is selected, the build will fail when the remote commands or script write to STDERR.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="interactiveSession"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`interactiveSession`** - **Enable interactive session**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this option is selected, interactive session will be started - if there's a password request, it will be filled by user's password. It could be useful to run commands like 'sudo'.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="readyTimeout"::: -->
:::moniker range=">=azure-pipelines-2020"

**`readyTimeout`** - **SSH handshake timeout**<br>
Type: string. Required. Default value: '20000'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
How long (in milliseconds) to wait for the SSH handshake to complete.
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
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->