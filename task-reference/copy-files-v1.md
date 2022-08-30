---
title: CopyFiles@1 - Copy Files v1 task
description: Copy files from source folder to target folder using minimatch patterns (The minimatch patterns will only match file paths, not folder paths).
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# CopyFiles@1 - Copy Files v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Copy files from source folder to target folder using minimatch patterns (The minimatch patterns will only match file paths, not folder paths).
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
    Contents: '**' # string. Required. Contents. Default: '**'.
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
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Folder that contains the files you want to copy. If you leave it empty, the copying is done from the root folder of the repo (same as if you had specified [**`$(Build.SourcesDirectory)`**](/azure/devops/pipelines/build/variables)).

If your build produces artifacts outside of the sources directory, specify `$(Agent.BuildDirectory)` to copy files from the directory created for the pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Contents"::: -->
:::moniker range="<=azure-pipelines"

**`Contents`** - **Contents**<br>
Type: string. Required. Default value: '**'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File paths to include as part of the copy. Supports multiple lines of match patterns.

For example:

* `*` copies all files in the specified source folder
* `**` copies all files in the specified source folder and all files in all sub-folders
* `**\bin\**` copies all files recursively from any bin folder

The pattern is used to match only file paths, not folder paths. So you should specify patterns such as `**\bin\**` instead of `**\bin`.

You must use the path separator that matches your build agent type, for example `/`must be used for Linux agents. More examples are shown below.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetFolder"::: -->
:::moniker range="<=azure-pipelines"

**`TargetFolder`** - **Target Folder**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Target folder or UNC path files will copy to. You can use [variables](/azure/devops/pipelines/build/variables). Example: `$(build.artifactstagingdirectory)`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CleanTargetFolder"::: -->
:::moniker range="<=azure-pipelines"

**`CleanTargetFolder`** - **Clean Target Folder**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Delete all existing files in target folder before copy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="OverWrite"::: -->
:::moniker range="<=azure-pipelines"

**`OverWrite`** - **Overwrite**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Replace existing file in target folder.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="flattenFolders"::: -->
:::moniker range="<=azure-pipelines"

**`flattenFolders`** - **Flatten Folders**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Flatten the folder structure and copy all files into the specified target folder.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
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

If no files are matched, the task will still report success. If a matched file already exists in the target, the task will report failure unless `Overwrite` is set to true.
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