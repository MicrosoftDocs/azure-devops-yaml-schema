---
title: CopyFilesOverSSH@0 - Copy files over SSH v0 task
description: Copy files or build artifacts to a remote machine over SSH.
ms.date: 03/20/2025
monikerRange: "<=azure-pipelines"
---

# CopyFilesOverSSH@0 - Copy files over SSH v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Copy files or build artifacts to a remote machine over SSH.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Copy files over SSH v0
# Copy files or build artifacts to a remote machine over SSH.
- task: CopyFilesOverSSH@0
  inputs:
    sshEndpoint: # string. Required. SSH service connection. 
    #sourceFolder: # string. Source folder. 
    contents: '**' # string. Required. Contents. Default: **.
    #targetFolder: # string. Target folder. 
  # Advanced
    #isWindowsOnTarget: false # boolean. Target machine running Windows. Default: false.
    #cleanTargetFolder: false # boolean. Clean target folder. Default: false.
    #cleanHiddenFilesInTarget: false # boolean. Optional. Use when cleanTargetFolder = true. Remove hidden files in target folder. Default: false.
    readyTimeout: '20000' # string. Required. SSH handshake timeout. Default: 20000.
    #overwrite: true # boolean. Overwrite. Default: true.
    #failOnEmptySource: false # boolean. Fail if no files found to copy. Default: false.
    #flattenFolders: false # boolean. Flatten folders. Default: false.
    #concurrentUploads: '10' # string. Number of concurrent uploads when copying files. Default: 10.
    #delayBetweenUploads: '50' # string. Delay between queueing uploads (in milliseconds). Default: 50.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2022 <=azure-pipelines-2022.2"

```yaml
# Copy files over SSH v0
# Copy files or build artifacts to a remote machine over SSH.
- task: CopyFilesOverSSH@0
  inputs:
    sshEndpoint: # string. Required. SSH service connection. 
    #sourceFolder: # string. Source folder. 
    contents: '**' # string. Required. Contents. Default: **.
    #targetFolder: # string. Target folder. 
  # Advanced
    #isWindowsOnTarget: false # boolean. Target machine running Windows. Default: false.
    #cleanTargetFolder: false # boolean. Clean target folder. Default: false.
    #cleanHiddenFilesInTarget: false # boolean. Optional. Use when cleanTargetFolder = true. Remove hidden files in target folder. Default: false.
    readyTimeout: '20000' # string. Required. SSH handshake timeout. Default: 20000.
    #overwrite: true # boolean. Overwrite. Default: true.
    #failOnEmptySource: false # boolean. Fail if no files found to copy. Default: false.
    #flattenFolders: false # boolean. Flatten folders. Default: false.
```

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

```yaml
# Copy files over SSH v0
# Copy files or build artifacts to a remote machine over SSH.
- task: CopyFilesOverSSH@0
  inputs:
    sshEndpoint: # string. Required. SSH service connection. 
    #sourceFolder: # string. Source folder. 
    contents: '**' # string. Required. Contents. Default: **.
    #targetFolder: # string. Target folder. 
  # Advanced
    #isWindowsOnTarget: false # boolean. Target machine running Windows. Default: false.
    #cleanTargetFolder: false # boolean. Clean target folder. Default: false.
    readyTimeout: '20000' # string. Required. SSH handshake timeout. Default: 20000.
    #overwrite: true # boolean. Overwrite. Default: true.
    #failOnEmptySource: false # boolean. Fail if no files found to copy. Default: false.
    #flattenFolders: false # boolean. Flatten folders. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="sshEndpoint"::: -->
:::moniker range="<=azure-pipelines"

**`sshEndpoint`** - **SSH service connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of an [SSH service connection](/azure/devops/pipelines/library/service-endpoints#ssh-service-connection) containing connection details for the remote machine.

- The hostname or IP address of the remote machine, the port number, and the user name are required to create an SSH service connection.
- The private key and the passphrase must be specified for authentication.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sourceFolder"::: -->
:::moniker range="<=azure-pipelines"

**`sourceFolder`** - **Source folder**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The source folder of the files to copy to the remote machine.  When empty, the root of the repository (build) or artifacts directory (release) is used, which is `$(System.DefaultWorkingDirectory)`.  Use [variables](/azure/devops/pipelines/build/variables) if files are not in the repository. Example: `$(Agent.BuildDirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="contents"::: -->
:::moniker range="<=azure-pipelines"

**`contents`** - **Contents**<br>
`string`. Required. Default value: `**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file paths to include as part of the copy. Supports multiple lines of [minimatch patterns](/azure/devops/pipelines/tasks/file-matching-patterns). The default value is `**`, which includes all files (including sub-folders) under the source folder.

- Example: `**/*.*(jar|war)` includes all .jar and .war files (including sub-folders) under the source folder.
- Example: `"** \n !**/*.xml"` includes all files (including sub-folders) under the source folder, but excludes xml files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targetFolder"::: -->
:::moniker range="<=azure-pipelines"

**`targetFolder`** - **Target folder**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The target folder on the remote machine, where files will be copied. Example: `/home/user/MySite`. Preface with a tilde `(~)` to specify the user's home directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isWindowsOnTarget"::: -->
:::moniker range="<=azure-pipelines"

**`isWindowsOnTarget`** - **Target machine running Windows**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Checks if the target machine is running Windows.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cleanTargetFolder"::: -->
:::moniker range="<=azure-pipelines"

**`cleanTargetFolder`** - **Clean target folder**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Deletes all existing files and sub-folders in the target folder before copying.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cleanHiddenFilesInTarget"::: -->
:::moniker range=">=azure-pipelines-2022"

**`cleanHiddenFilesInTarget`** - **Remove hidden files in target folder**<br>
`boolean`. Optional. Use when `cleanTargetFolder = true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When set to `true`, removes hidden files in the target folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="readyTimeout"::: -->
:::moniker range="<=azure-pipelines"

**`readyTimeout`** - **SSH handshake timeout**<br>
`string`. Required. Default value: `20000`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
How long (in milliseconds) to wait for the SSH handshake to complete.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overwrite"::: -->
:::moniker range="<=azure-pipelines"

**`overwrite`** - **Overwrite**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Replaces existing files in and beneath the target folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnEmptySource"::: -->
:::moniker range="<=azure-pipelines"

**`failOnEmptySource`** - **Fail if no files found to copy**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fails if no matching files to be copied are found under the source folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="flattenFolders"::: -->
:::moniker range="<=azure-pipelines"

**`flattenFolders`** - **Flatten folders**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Flattens the folder structure and copies all files into the specified target folder on the remote machine.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="concurrentUploads"::: -->
:::moniker range="=azure-pipelines"

**`concurrentUploads`** - **Number of concurrent uploads when copying files**<br>
`string`. Default value: `10`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Number of concurrent uploads when copying files. Default is 10.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="delayBetweenUploads"::: -->
:::moniker range="=azure-pipelines"

**`delayBetweenUploads`** - **Delay between queueing uploads (in milliseconds)**<br>
`string`. Default value: `50`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Delay between queueing uploads (in milliseconds). Default is 50.
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

:::moniker range="=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task runs using the following [command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): restricted |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): Setting variables is disabled |
| Agent version |  2.206.1 or greater |
| Task category | Deploy |

:::moniker-end

:::moniker range=">=azure-pipelines-2022 <=azure-pipelines-2022.2"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task runs using the following [command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): restricted |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): Setting variables is disabled |
| Agent version |  2.182.1 or greater |
| Task category | Deploy |

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

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

:::moniker range="=azure-pipelines-2020"

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
