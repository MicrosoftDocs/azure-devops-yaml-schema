---
title: ArchiveFiles@2 - Archive files v2 task
description: Compress files into .7z, .tar.gz, or .zip.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# ArchiveFiles@2 - Archive files v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Compress files into .7z, .tar.gz, or .zip.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Archive files using compression formats such as .7z, .rar, .tar.gz, and .zip.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Archive files v2
# Compress files into .7z, .tar.gz, or .zip.
- task: ArchiveFiles@2
  inputs:
    rootFolderOrFile: '$(Build.BinariesDirectory)' # string. Required. Root folder or file to archive. Default: '$(Build.BinariesDirectory)'.
    includeRootFolder: true # boolean. Required. Prepend root folder name to archive paths. Default: true.
  # Archive
    archiveType: 'zip' # 'zip' | '7z' | 'tar' | 'wim'. Required. Archive type. Default: 'zip'.
    #sevenZipCompression: 'normal' # 'ultra' | 'maximum' | 'normal' | 'fast' | 'fastest' | 'none'. Optional. Use when archiveType = 7z. 7z compression. Default: 'normal'.
    #tarCompression: 'gz' # 'gz' | 'bz2' | 'xz' | 'none'. Optional. Use when archiveType = tar. Tar compression. Default: 'gz'.
    archiveFile: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip' # string. Required. Archive file to create. Default: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip'.
    replaceExistingArchive: true # boolean. Required. Replace existing archive. Default: true.
    #verbose: false # boolean. Force verbose output. Default: false.
    #quiet: false # boolean. Force quiet output. Default: false.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

```yaml
# Archive files v2
# Compress files into .7z, .tar.gz, or .zip.
- task: ArchiveFiles@2
  inputs:
    rootFolderOrFile: '$(Build.BinariesDirectory)' # string. Required. Root folder or file to archive. Default: '$(Build.BinariesDirectory)'.
    includeRootFolder: true # boolean. Required. Prepend root folder name to archive paths. Default: true.
  # Archive
    archiveType: 'zip' # 'zip' | '7z' | 'tar' | 'wim'. Required. Archive type. Default: 'zip'.
    #sevenZipCompression: '5' # 'ultra' | 'maximum' | 'normal' | 'fast' | 'fastest' | 'none'. Optional. Use when archiveType = 7z. 7z compression. Default: '5'.
    #tarCompression: 'gz' # 'gz' | 'bz2' | 'xz' | 'none'. Optional. Use when archiveType = tar. Tar compression. Default: 'gz'.
    archiveFile: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip' # string. Required. Archive file to create. Default: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip'.
    replaceExistingArchive: true # boolean. Required. Replace existing archive. Default: true.
    #verbose: false # boolean. Force verbose output. Default: false.
    #quiet: false # boolean. Force quiet output. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Archive files v2
# Compress files into .7z, .tar.gz, or .zip.
- task: ArchiveFiles@2
  inputs:
    rootFolderOrFile: '$(Build.BinariesDirectory)' # string. Required. Root folder or file to archive. Default: '$(Build.BinariesDirectory)'.
    includeRootFolder: true # boolean. Required. Prepend root folder name to archive paths. Default: true.
  # Archive
    archiveType: 'zip' # 'zip' | '7z' | 'tar' | 'wim'. Required. Archive type. Default: 'zip'.
    #tarCompression: 'gz' # 'gz' | 'bz2' | 'xz' | 'none'. Optional. Use when archiveType = tar. Tar compression. Default: 'gz'.
    archiveFile: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip' # string. Required. Archive file to create. Default: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip'.
    replaceExistingArchive: true # boolean. Required. Replace existing archive. Default: true.
    #verbose: false # boolean. Force verbose output. Default: false.
    #quiet: false # boolean. Force quiet output. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Archive Files v2
# Archive files using compression formats such as .7z, .rar, .tar.gz, and .zip.
- task: ArchiveFiles@2
  inputs:
    rootFolderOrFile: '$(Build.BinariesDirectory)' # string. Required. Root folder or file to archive. Default: '$(Build.BinariesDirectory)'.
    includeRootFolder: true # boolean. Required. Prepend root folder name to archive paths. Default: true.
  # Archive
    archiveType: 'zip' # 'zip' | '7z' | 'tar' | 'wim'. Required. Archive type. Default: 'zip'.
    #tarCompression: 'gz' # 'gz' | 'bz2' | 'xz' | 'none'. Optional. Use when archiveType = tar. Tar compression. Default: 'gz'.
    archiveFile: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip' # string. Required. Archive file to create. Default: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip'.
    replaceExistingArchive: true # boolean. Required. Replace existing archive. Default: true.
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

<!-- :::item name="rootFolderOrFile"::: -->
:::moniker range="<=azure-pipelines"

**`rootFolderOrFile`** - **Root folder or file to archive**<br>
Type: string. Required. Default value: '$(Build.BinariesDirectory)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the root folder or file path to add to the archive. If a folder, everything under the folder will be added to the resulting archive.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeRootFolder"::: -->
:::moniker range="<=azure-pipelines"

**`includeRootFolder`** - **Prepend root folder name to archive paths**<br>
Type: boolean. Required. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If selected, the root folder name will be prepended to file paths within the archive. Otherwise, all file paths will start one level lower.<p>For example, suppose the selected root folder is: <b>`/home/user/output/classes/`</b>, and contains: <b>`com/acme/Main.class`</b>. <ul><li>If selected, the resulting archive would contain: <b>`classes/com/acme/Main.class`</b>.</li><li>Otherwise, the resulting archive would contain: <b>`com/acme/Main.class`</b>.</li></ul>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="archiveType"::: -->
:::moniker range="<=azure-pipelines"

**`archiveType`** - **Archive type**<br>
Type: string. Required. Allowed values: 'zip', '7z', 'tar', 'wim'. Default value: 'zip'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the compression scheme used.  To create <b>`foo.jar`</b>, for example, choose <b>`zip`</b> for the compression, and specify <b>`foo.jar`</b> as the archive file to create.  For all tar files (including compressed ones), choose <b>`tar`</b>.

- `zip` - default, zip format, choose this for all zip compatible types, (.zip, .jar, .war, .ear)
- `7z` - 7-Zip format, (.7z)
- `tar` - tar format, choose this for compressed tars, (.tar.gz, .tar.bz2, .tar.xz)
- `wim` - wim format, (.wim)
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sevenZipCompression"::: -->
:::moniker range=">=azure-pipelines-2022"

**`sevenZipCompression`** - **7z compression**<br>
Type: string. Optional. Use when archiveType = 7z. Allowed values: 'ultra', 'maximum', 'normal', 'fast', 'fastest', 'none'. Default value: 'normal'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally choose a compression level, or choose <b>`None`</b> to create an uncompressed 7z file.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

**`sevenZipCompression`** - **7z compression**<br>
Type: string. Optional. Use when archiveType = 7z. Allowed values: 'ultra', 'maximum', 'normal', 'fast', 'fastest', 'none'. Default value: '5'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally choose a compression level, or choose <b>`None`</b> to create an uncompressed 7z file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tarCompression"::: -->
:::moniker range="<=azure-pipelines"

**`tarCompression`** - **Tar compression**<br>
Type: string. Optional. Use when archiveType = tar. Allowed values: 'gz', 'bz2', 'xz', 'none'. Default value: 'gz'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally choose a compression scheme, or choose <b>`None`</b> to create an uncompressed tar file.

- `gz` - default, gzip compression (.tar.gz, .tar.tgz, .taz)
- `bz2` - bzip2 compression (.tar.bz2, .tz2, .tbz2)
- `xz` - xz compression (.tar.xz, .txz)
- `None` - no compression, choose this to create a uncompressed tar file (.tar)
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="archiveFile"::: -->
:::moniker range="<=azure-pipelines"

**`archiveFile`** - **Archive file to create**<br>
Type: string. Required. Default value: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the archive file to create.  For example, to create <b>`foo.tgz`</b>, select the <b>`tar`</b> archive type and <b>`gz`</b> for tar compression.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="replaceExistingArchive"::: -->
:::moniker range="<=azure-pipelines"

**`replaceExistingArchive`** - **Replace existing archive**<br>
Type: boolean. Required. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If an existing archive exists, specify whether to overwrite it. Otherwise, files will be added to it as long as it is not a compressed tar.

If adding to an existing archive, these types are supported:

- `zip`
- `7z`
- `tar` - uncompressed only
- `wim`
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbose"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`verbose`** - **Force verbose output**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to true, forces tools to use verbose output. Overrides 'quiet'.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="quiet"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`quiet`** - **Force quiet output**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to true, forces tools to use quiet output. Can be overridden by 'verbose'.
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