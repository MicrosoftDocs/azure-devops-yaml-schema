---
title: DeleteFiles@1 - Delete files v1 task
description: Delete folders, or files matching a pattern.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# DeleteFiles@1 - Delete files v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Delete folders, or files matching a pattern.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Delete files or folders. (The minimatch patterns will only match file paths, not folder paths).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Delete files v1
# Delete folders, or files matching a pattern.
- task: DeleteFiles@1
  inputs:
    #SourceFolder: # string. Source Folder. 
    Contents: 'myFileShare' # string. Required. Contents. Default: 'myFileShare'.
    #RemoveSourceFolder: false # boolean. Remove SourceFolder. Default: false.
  # Advanced
    #RemoveDotFiles: false # boolean. Remove files starting with a dot. Default: false.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

```yaml
# Delete files v1
# Delete folders, or files matching a pattern.
- task: DeleteFiles@1
  inputs:
    #SourceFolder: # string. Source Folder. 
    Contents: 'myFileShare' # string. Required. Contents. Default: 'myFileShare'.
    #RemoveSourceFolder: false # boolean. Remove SourceFolder. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Delete files v1
# Delete folders, or files matching a pattern.
- task: DeleteFiles@1
  inputs:
    #SourceFolder: # string. Source Folder. 
    Contents: 'myFileShare' # string. Required. Contents. Default: 'myFileShare'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Delete Files v1
# Delete files or folders. (The minimatch patterns will only match file paths, not folder paths).
- task: DeleteFiles@1
  inputs:
    #SourceFolder: # string. Source Folder. 
    Contents: 'myFileShare' # string. Required. Contents. Default: 'myFileShare'.
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

<!-- :::item name="SourceFolder"::: -->
:::moniker range="<=azure-pipelines"

**`SourceFolder`** - **Source Folder**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If you leave it empty, the deletions are done from the root folder of the repository (same as if you had specified [$(Build.SourcesDirectory))](/azure/devops/pipelines/build/variables).
If your build produces artifacts outside of the sources directory, specify `$(Agent.BuildDirectory)` to delete files from the build agent working directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Contents"::: -->
:::moniker range="<=azure-pipelines"

**`Contents`** - **Contents**<br>
Type: string. Required. Default value: 'myFileShare'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File/folder paths to delete. Supports multiple lines of minimatch patterns; each one is processed before moving onto the next line. [More Information](/azure/devops/pipelines/tasks/file-matching-patterns).
For example:
- `**/*` deletes all files and folders in the root folder.
- `temp` deletes the *temp* folder in the root folder.
- `temp*` deletes any file or folder in the root folder with a name that begins with *temp*.
- `**/temp/*` deletes all files and folders in any sub-folder named *temp*.
- `**/temp*` deletes any file or folder with a name that begins with *temp*.
- `!(*.vsix)` deletes all files in the root folder that do not have a *.vsix* extension.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RemoveSourceFolder"::: -->
:::moniker range=">=azure-pipelines-2020"

**`RemoveSourceFolder`** - **Remove SourceFolder**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Attempt to remove the source folder after attempting to remove `Contents`. If you want to remove the whole folder, set this to `true` and set `Contents` to `*`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RemoveDotFiles"::: -->
:::moniker range=">=azure-pipelines-2022"

**`RemoveDotFiles`** - **Remove files starting with a dot**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Delete files starting with a dot (.git, .dockerfile). Omits these files if it's not specified explicitly (for example, '/.*'). Please see this [link](https://github.com/isaacs/minimatch#dot) for more info.
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
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task runs using the following [command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): restricted |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): Setting variables is disabled |
| Agent version |  2.182.1 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.92.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
