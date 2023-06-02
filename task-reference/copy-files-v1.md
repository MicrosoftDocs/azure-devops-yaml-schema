---
title: CopyFiles@1 - Copy Files v1 task
description: Copy files from source folder to target folder using minimatch patterns (The minimatch patterns will only match file paths, not folder paths).
ms.date: 06/02/2023
monikerRange: "<=azure-pipelines"
---

# CopyFiles@1 - Copy Files v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to copy files from a source folder to a target folder using match patterns. (The match patterns will only match file paths, not folder paths).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Copy Files v1
# Copy files from source folder to target folder using minimatch patterns (The minimatch patterns will only match file paths, not folder paths).
- task: CopyFiles@1
  inputs:
    #SourceFolder: # string. Source Folder. 
    Contents: '**' # string. Required. Contents. Default: **.
    TargetFolder: # string. Required. Target Folder. 
  # Advanced
    #CleanTargetFolder: false # boolean. Clean Target Folder. Default: false.
    #OverWrite: false # boolean. Overwrite. Default: false.
    #flattenFolders: false # boolean. Flatten Folders. Default: false.
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
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. The folder that contains the files you want to copy. If the folder is empty, then the task copies files from the root folder of the repo as though [**`$(Build.SourcesDirectory)`**](/azure/devops/pipelines/build/variables) was specified.

If your build produces artifacts outside of the sources directory, specify `$(Agent.BuildDirectory)` to copy files from the directory created for the pipeline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Contents"::: -->
:::moniker range="<=azure-pipelines"

**`Contents`** - **Contents**<br>
`string`. Required. Default value: `**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file paths to include as part of the copy. This string supports multiple lines of match patterns.

For example:

* `*` copies all files in the specified source folder.
* `**` copies all files in the specified source folder and all files in all sub-folders.
* `**\bin\**` copies all files recursively from any bin folder.

The pattern is used to match only file paths, not folder paths. Specify patterns, such as `**\bin\**` instead of `**\bin`.

Use the path separator that matches your build agent type. For example, `/` must be used for Linux agents. More examples are shown below.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetFolder"::: -->
:::moniker range="<=azure-pipelines"

**`TargetFolder`** - **Target Folder**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The target folder or UNC path that will contain the copied files. You can use [variables](/azure/devops/pipelines/build/variables). Example: `$(build.artifactstagingdirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CleanTargetFolder"::: -->
:::moniker range="<=azure-pipelines"

**`CleanTargetFolder`** - **Clean Target Folder**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Deletes all existing files in the target folder before the copy process.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="OverWrite"::: -->
:::moniker range="<=azure-pipelines"

**`OverWrite`** - **Overwrite**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Replaces the existing files in the target folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="flattenFolders"::: -->
:::moniker range="<=azure-pipelines"

**`flattenFolders`** - **Flatten Folders**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Flattens the folder structure and copies all files into the specified target folder.
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

There is a newer version of this task available at [CopyFiles@2](copy-files-v2.md).

If no files match, the task will still report success. If a matched file already exists in the target folder, the task will report failure unless `Overwrite` is set to true.
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
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.91.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [CopyFiles@2](copy-files-v2.md)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->