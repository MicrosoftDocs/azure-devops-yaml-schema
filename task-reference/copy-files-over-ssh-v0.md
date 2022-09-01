---
title: CopyFilesOverSSH@0 - Copy files over SSH v0 task
description: Copy files or build artifacts to a remote machine over SSH.
ms.date: 09/01/2022
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

:::moniker range=">=azure-pipelines-2022"

```yaml
# Copy files over SSH v0
# Copy files or build artifacts to a remote machine over SSH.
- task: CopyFilesOverSSH@0
  inputs:
    sshEndpoint: # string. Required. SSH service connection. 
    #sourceFolder: # string. Source folder. 
    contents: '**' # string. Required. Contents. Default: '**'.
    #targetFolder: # string. Target folder. 
  # Advanced
    #isWindowsOnTarget: false # boolean. Target machine running Windows. Default: false.
    #cleanTargetFolder: false # boolean. Clean target folder. Default: false.
    #cleanHiddenFilesInTarget: false # boolean. Optional. Use when cleanTargetFolder = true. Remove hidden files in target folder. Default: false.
    readyTimeout: '20000' # string. Required. SSH handshake timeout. Default: '20000'.
    #overwrite: true # boolean. Overwrite. Default: true.
    #failOnEmptySource: false # boolean. Fail if no files found to copy. Default: false.
    #flattenFolders: false # boolean. Flatten folders. Default: false.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

```yaml
# Copy files over SSH v0
# Copy files or build artifacts to a remote machine over SSH.
- task: CopyFilesOverSSH@0
  inputs:
    sshEndpoint: # string. Required. SSH service connection. 
    #sourceFolder: # string. Source folder. 
    contents: '**' # string. Required. Contents. Default: '**'.
    #targetFolder: # string. Target folder. 
  # Advanced
    #isWindowsOnTarget: false # boolean. Target machine running Windows. Default: false.
    #cleanTargetFolder: false # boolean. Clean target folder. Default: false.
    readyTimeout: '20000' # string. Required. SSH handshake timeout. Default: '20000'.
    #overwrite: true # boolean. Overwrite. Default: true.
    #failOnEmptySource: false # boolean. Fail if no files found to copy. Default: false.
    #flattenFolders: false # boolean. Flatten folders. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Copy files over SSH v0
# Copy files or build artifacts to a remote machine over SSH.
- task: CopyFilesOverSSH@0
  inputs:
    sshEndpoint: # string. Required. SSH service connection. 
    #sourceFolder: # string. Source folder. 
    contents: '**' # string. Required. Contents. Default: '**'.
    #targetFolder: # string. Target folder. 
  # Advanced
    #cleanTargetFolder: false # boolean. Clean target folder. Default: false.
    #overwrite: true # boolean. Overwrite. Default: true.
    #failOnEmptySource: false # boolean. Fail if no files found to copy. Default: false.
    #flattenFolders: false # boolean. Flatten folders. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Copy Files Over SSH v0
# Copy files or build artifacts to a remote machine over SSH.
- task: CopyFilesOverSSH@0
  inputs:
    sshEndpoint: # string. Required. SSH service connection. 
    #sourceFolder: # string. Source folder. 
    contents: '**' # string. Required. Contents. Default: '**'.
    #targetFolder: # string. Target folder. 
  # Advanced
    #cleanTargetFolder: false # boolean. Clean target folder. Default: false.
    #overwrite: true # boolean. Overwrite. Default: true.
    #failOnEmptySource: false # boolean. Fail if no files found to copy. Default: false.
    #flattenFolders: false # boolean. Flatten folders. Default: false.
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
<!-- :::item name="sourceFolder"::: -->
:::moniker range="<=azure-pipelines"

**`sourceFolder`** - **Source folder**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The source folder of the files to copy to the remote machine.  When empty, the root of the repository (build) or artifacts directory (release) is used, which is $(System.DefaultWorkingDirectory).  Use [variables](https://go.microsoft.com/fwlink/?LinkID=550988) if files are not in the repository. Example: $(Agent.BuildDirectory).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="contents"::: -->
:::moniker range="<=azure-pipelines"

**`contents`** - **Contents**<br>
Type: string. Required. Default value: '**'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File paths to include as part of the copy. Supports multiple lines of minimatch patterns. [More Information](https://go.microsoft.com/fwlink/?LinkId=821894).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targetFolder"::: -->
:::moniker range="<=azure-pipelines"

**`targetFolder`** - **Target folder**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Target folder on the remote machine to where files will be copied. Example: /home/user/MySite.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isWindowsOnTarget"::: -->
:::moniker range=">=azure-pipelines-2020"

**`isWindowsOnTarget`** - **Target machine running Windows**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Target machine running Windows.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cleanTargetFolder"::: -->
:::moniker range="<=azure-pipelines"

**`cleanTargetFolder`** - **Clean target folder**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Delete all existing files and subfolders in the target folder before copying.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cleanHiddenFilesInTarget"::: -->
:::moniker range=">=azure-pipelines-2022"

**`cleanHiddenFilesInTarget`** - **Remove hidden files in target folder**<br>
Type: boolean. Optional. Use when cleanTargetFolder = true. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When true, removes hidden files in the target folder.
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
<!-- :::item name="overwrite"::: -->
:::moniker range="<=azure-pipelines"

**`overwrite`** - **Overwrite**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Replace existing files in and beneath the target folder.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnEmptySource"::: -->
:::moniker range="<=azure-pipelines"

**`failOnEmptySource`** - **Fail if no files found to copy**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fail if no matching files to be copied are found under the source folder.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="flattenFolders"::: -->
:::moniker range="<=azure-pipelines"

**`flattenFolders`** - **Flatten folders**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Flatten the folder structure and copy all files into the specified target folder on the remote machine.
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