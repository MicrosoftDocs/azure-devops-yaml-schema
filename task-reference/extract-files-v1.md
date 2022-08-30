---
title: ExtractFiles@1 - Extract files v1 task
description: Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# ExtractFiles@1 - Extract files v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip.
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
    archiveFilePatterns: '**/*.zip' # string. Required. Archive file patterns. Default: '**/*.zip'.
    destinationFolder: # string. Required. Destination folder. 
    cleanDestinationFolder: true # boolean. Required. Clean destination folder before extracting. Default: true.
    overwriteExistingFiles: false # boolean. Required. Overwrite existing files. Default: false.
    #pathToSevenZipTool: # string. Path to 7z utility.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

```yaml
# Extract files v1
# Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip.
- task: ExtractFiles@1
  inputs:
    archiveFilePatterns: '**/*.zip' # string. Required. Archive file patterns. Default: '**/*.zip'.
    destinationFolder: # string. Required. Destination folder. 
    cleanDestinationFolder: true # boolean. Required. Clean destination folder before extracting. Default: true.
    overwriteExistingFiles: false # boolean. Required. Overwrite existing files. Default: false.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

```yaml
# Extract files v1
# Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip.
- task: ExtractFiles@1
  inputs:
    archiveFilePatterns: '*.zip' # string. Required. Archive file patterns. Default: '*.zip'.
    destinationFolder: # string. Required. Destination folder. 
    cleanDestinationFolder: true # boolean. Required. Clean destination folder before extracting. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Extract Files v1
# Extract a variety of archive and compression files such as .7z, .rar, .tar.gz, and .zip.
- task: ExtractFiles@1
  inputs:
    archiveFilePatterns: '*.zip' # string. Required. Archive file patterns. Default: '*.zip'.
    destinationFolder: # string. Required. Destination folder. 
    cleanDestinationFolder: true # boolean. Required. Clean destination folder before extracting. Default: true.
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

<!-- :::item name="archiveFilePatterns"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`archiveFilePatterns`** - **Archive file patterns**<br>
Type: string. Required. Default value: '**/*.zip'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File paths or patterns of the archive files to extract.  Supports multiple lines of minimatch patterns.  [More Information](https://go.microsoft.com/fwlink/?LinkId=800269).
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2020"

**`archiveFilePatterns`** - **Archive file patterns**<br>
Type: string. Required. Default value: '*.zip'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File paths or patterns of the archive files to extract.  Supports multiple lines of minimatch patterns.  [More Information](https://go.microsoft.com/fwlink/?LinkId=800269).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="destinationFolder"::: -->
:::moniker range="<=azure-pipelines"

**`destinationFolder`** - **Destination folder**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Destination folder into which archive files should be extracted.  Use [variables](https://go.microsoft.com/fwlink/?LinkID=550988) if files are not in the repo. Example: $(agent.builddirectory).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cleanDestinationFolder"::: -->
:::moniker range="<=azure-pipelines"

**`cleanDestinationFolder`** - **Clean destination folder before extracting**<br>
Type: boolean. Required. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to clean the destination directory before archive contents are extracted into it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overwriteExistingFiles"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`overwriteExistingFiles`** - **Overwrite existing files**<br>
Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to overwrite existing files in the destination directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pathToSevenZipTool"::: -->
:::moniker range=">=azure-pipelines-2022"

**`pathToSevenZipTool`** - **Path to 7z utility**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You can specify custom path to 7z utility. For example, "C:\7z\7z.exe" on Windows and "/usr/local/bin/7z" on MacOS/Ubuntu.
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
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->