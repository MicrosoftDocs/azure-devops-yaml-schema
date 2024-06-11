---
title: ExtractFiles@1 - Extract files v1 task
description: Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip.
ms.date: 06/11/2024
monikerRange: "<=azure-pipelines"
---

# ExtractFiles@1 - Extract files v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to extract a variety of archive and compression files, such as .7z, .rar, .tar.gz, and .zip.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Extract files v1
# Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip.
- task: ExtractFiles@1
  inputs:
    archiveFilePatterns: '**/*.zip' # string. Required. Archive file patterns. Default: **/*.zip.
    destinationFolder: # string. Required. Destination folder. 
    #cleanDestinationFolder: true # boolean. Clean destination folder before extracting. Default: true.
    #overwriteExistingFiles: false # boolean. Overwrite existing files. Default: false.
    #pathToSevenZipTool: # string. Path to 7z utility.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

```yaml
# Extract files v1
# Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip.
- task: ExtractFiles@1
  inputs:
    archiveFilePatterns: '**/*.zip' # string. Required. Archive file patterns. Default: **/*.zip.
    destinationFolder: # string. Required. Destination folder. 
    #cleanDestinationFolder: true # boolean. Clean destination folder before extracting. Default: true.
    #overwriteExistingFiles: false # boolean. Overwrite existing files. Default: false.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

```yaml
# Extract files v1
# Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip.
- task: ExtractFiles@1
  inputs:
    archiveFilePatterns: '*.zip' # string. Required. Archive file patterns. Default: *.zip.
    destinationFolder: # string. Required. Destination folder. 
    #cleanDestinationFolder: true # boolean. Clean destination folder before extracting. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Extract Files v1
# Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip.
- task: ExtractFiles@1
  inputs:
    archiveFilePatterns: '*.zip' # string. Required. Archive file patterns. Default: *.zip.
    destinationFolder: # string. Required. Destination folder. 
    #cleanDestinationFolder: true # boolean. Clean destination folder before extracting. Default: true.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="archiveFilePatterns"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`archiveFilePatterns`** - **Archive file patterns**<br>
`string`. Required. Default value: `**/*.zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the file paths or patterns of the archive files to extract.  Supports multiple lines of minimatch patterns. Learn more about the [Extract Files task](/azure/devops/pipelines/tasks/utility/extract-files).

Specifies the patterns to match the archives you want to extract. By default, patterns start in the root folder of the repo (same as if you had specified `$(Build.SourcesDirectory)`.  
Specifies the pattern filters, one per line, that match the archives to extract. For example:
* `test.zip` extracts the test.zip file in the root folder.
* `test/*.zip` extracts all .zip files in the test folder.
* `**/*.tar` extracts all .tar files in the root folder and sub-folders.
* `**/bin/*.7z` extracts all .7z files in any sub-folder named "bin".  
The pattern is used to match only archive file paths, not folder paths, and not archive contents to be extracted. So, you should specify patterns, such as `**/bin/**` instead of `**/bin`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2020"

**`archiveFilePatterns`** - **Archive file patterns**<br>
`string`. Required. Default value: `*.zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the file paths or patterns of the archive files to extract.  Supports multiple lines of minimatch patterns.  Learn more about the [Extract Files task](/azure/devops/pipelines/tasks/utility/extract-files).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="destinationFolder"::: -->
:::moniker range="<=azure-pipelines"

**`destinationFolder`** - **Destination folder**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the destination folder into which archive files should be extracted. Use [variables](/azure/devops/pipelines/build/variables) if files are not in the repo. For example: `$(agent.builddirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cleanDestinationFolder"::: -->
:::moniker range="<=azure-pipelines"

**`cleanDestinationFolder`** - **Clean destination folder before extracting**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to clean the destination directory before archive contents are extracted into it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overwriteExistingFiles"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`overwriteExistingFiles`** - **Overwrite existing files**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to overwrite existing files in the destination directory if they already exist. If the option is `false`, the script prompts on existing files, asking whether you want to overwrite them.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pathToSevenZipTool"::: -->
:::moniker range=">=azure-pipelines-2022"

**`pathToSevenZipTool`** - **Path to 7z utility**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the custom path to 7z utility. For example, `C:\7z\7z.exe` on Windows and `/usr/local/bin/7z` on MacOS/Ubuntu. If it's not specified on Windows, the default 7zip version supplied with a task will be used.
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

Use this task to extract files from archives to a target folder using match patterns. A range of standard archive formats is supported, including .zip, .jar, .war, .ear, .tar, .7z, and more.

For more information about file matching patterns, see the [File matching patterns reference](/azure/devops/pipelines/tasks/file-matching-patterns).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Extract all .zip files recursively

This example will extract all .zip files recursively, including both root files and files from sub-folders.

```yaml
steps:
- task: ExtractFiles@1
  inputs:
    archiveFilePatterns: '**/*.zip'
    cleanDestinationFolder: true
    overwriteExistingFiles: false
```

### Extract all .zip files from subfolder

This example will extract `test/one.zip` and `test/two.zip`, but will leave `test/nested/three.zip`.

```yaml
steps:
- task: ExtractFiles@1
  inputs:
    archiveFilePatterns: 'test/*.zip'
    cleanDestinationFolder: true
    overwriteExistingFiles: false
```
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
| Agent version | All supported agent versions. |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [File matching patterns reference](/azure/devops/pipelines/tasks/file-matching-patterns)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
