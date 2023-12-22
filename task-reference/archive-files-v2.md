---
title: ArchiveFiles@2 - Archive files v2 task
description: Compress files into .7z, .tar.gz, or .zip.
ms.date: 12/21/2023
monikerRange: "<=azure-pipelines"
---

# ArchiveFiles@2 - Archive files v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Archive files using compression formats such as .7z, .tar, .gz, and .zip.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Archive files using compression formats such as .7z, .rar, .tar., .gz, and .zip.
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
    rootFolderOrFile: '$(Build.BinariesDirectory)' # string. Required. Root folder or file to archive. Default: $(Build.BinariesDirectory).
    #includeRootFolder: true # boolean. Prepend root folder name to archive paths. Default: true.
  # Archive
    archiveType: 'zip' # 'zip' | '7z' | 'tar' | 'wim'. Required. Archive type. Default: zip.
    #sevenZipCompression: 'normal' # 'ultra' | 'maximum' | 'normal' | 'fast' | 'fastest' | 'none'. Optional. Use when archiveType = 7z. 7z compression. Default: normal.
    #tarCompression: 'gz' # 'gz' | 'bz2' | 'xz' | 'none'. Optional. Use when archiveType = tar. Tar compression. Default: gz.
    archiveFile: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip' # string. Required. Archive file to create. Default: $(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip.
    #replaceExistingArchive: true # boolean. Replace existing archive. Default: true.
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
    rootFolderOrFile: '$(Build.BinariesDirectory)' # string. Required. Root folder or file to archive. Default: $(Build.BinariesDirectory).
    #includeRootFolder: true # boolean. Prepend root folder name to archive paths. Default: true.
  # Archive
    archiveType: 'zip' # 'zip' | '7z' | 'tar' | 'wim'. Required. Archive type. Default: zip.
    #sevenZipCompression: '5' # 'ultra' | 'maximum' | 'normal' | 'fast' | 'fastest' | 'none'. Optional. Use when archiveType = 7z. 7z compression. Default: 5.
    #tarCompression: 'gz' # 'gz' | 'bz2' | 'xz' | 'none'. Optional. Use when archiveType = tar. Tar compression. Default: gz.
    archiveFile: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip' # string. Required. Archive file to create. Default: $(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip.
    #replaceExistingArchive: true # boolean. Replace existing archive. Default: true.
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
    rootFolderOrFile: '$(Build.BinariesDirectory)' # string. Required. Root folder or file to archive. Default: $(Build.BinariesDirectory).
    #includeRootFolder: true # boolean. Prepend root folder name to archive paths. Default: true.
  # Archive
    archiveType: 'zip' # 'zip' | '7z' | 'tar' | 'wim'. Required. Archive type. Default: zip.
    #tarCompression: 'gz' # 'gz' | 'bz2' | 'xz' | 'none'. Optional. Use when archiveType = tar. Tar compression. Default: gz.
    archiveFile: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip' # string. Required. Archive file to create. Default: $(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip.
    #replaceExistingArchive: true # boolean. Replace existing archive. Default: true.
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
    rootFolderOrFile: '$(Build.BinariesDirectory)' # string. Required. Root folder or file to archive. Default: $(Build.BinariesDirectory).
    #includeRootFolder: true # boolean. Prepend root folder name to archive paths. Default: true.
  # Archive
    archiveType: 'zip' # 'zip' | '7z' | 'tar' | 'wim'. Required. Archive type. Default: zip.
    #tarCompression: 'gz' # 'gz' | 'bz2' | 'xz' | 'none'. Optional. Use when archiveType = tar. Tar compression. Default: gz.
    archiveFile: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip' # string. Required. Archive file to create. Default: $(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip.
    #replaceExistingArchive: true # boolean. Replace existing archive. Default: true.
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
`string`. Required. Default value: `$(Build.BinariesDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the root folder or the file path to files to add to the archive. For folders, everything in the named folder is added to the archive.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeRootFolder"::: -->
:::moniker range="<=azure-pipelines"

**`includeRootFolder`** - **Prepend root folder name to archive paths**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prepends the root folder name to file paths in the archive. Otherwise, all file paths will start one level lower.

For example, if the root folder is: `/home/user/output/classes/` and the file path: `com/acme/Main.class`. The resulting archive will contain: `classes/com/acme/Main.class`. Otherwise, the resulting archive will contain: `com/acme/Main.class`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="archiveType"::: -->
:::moniker range="<=azure-pipelines"

**`archiveType`** - **Archive type**<br>
`string`. Required. Allowed values: `zip`, `7z`, `tar`, `wim`. Default value: `zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a compression format.  Valid formats include:

- `zip` - Default. Choose this format for all zip compatible types such as .zip, .jar, .war, .ear
- `7z` - 7-Zip format, (.7z)
- `tar` - tar format, use for compressed tars including .tar.gz, .tar.bz2, .tar.xz
- `wim` - wim format, .wim

Example, to create an archive named `foo.jar`:

- Select compression format `zip`  
- Specify the name of the archive file to create: `foo.jar`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sevenZipCompression"::: -->
:::moniker range=">=azure-pipelines-2022"

**`sevenZipCompression`** - **7z compression**<br>
`string`. Optional. Use when `archiveType = 7z`. Allowed values: `ultra`, `maximum`, `normal`, `fast`, `fastest`, `none`. Default value: `normal`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set compression level or `None` to create an uncompressed .7z file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

**`sevenZipCompression`** - **7z compression**<br>
`string`. Optional. Use when `archiveType = 7z`. Allowed values: `ultra`, `maximum`, `normal`, `fast`, `fastest`, `none`. Default value: `5`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set a compression format or `None` to create an uncompressed .7z file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tarCompression"::: -->
:::moniker range="<=azure-pipelines"

**`tarCompression`** - **Tar compression**<br>
`string`. Optional. Use when `archiveType = tar`. Allowed values: `gz`, `bz2`, `xz`, `none`. Default value: `gz`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set a compression format or choose `None` to create an uncompressed .tar file.

- `gz` - Default format for gzip compression (.tar.gz, .tar.tgz, .taz)
- `bz2` - bzip2 compression (.tar.bz2, .tz2, .tbz2)
- `xz` - xz compression (.tar.xz, .txz)
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="archiveFile"::: -->
:::moniker range="<=azure-pipelines"

**`archiveFile`** - **Archive file to create**<br>
`string`. Required. Default value: `$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the archive file to create.  For example, to create `foo.tgz`:

- Set archive type: `tar`
- Set tar compression: `gz`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="replaceExistingArchive"::: -->
:::moniker range="<=azure-pipelines"

**`replaceExistingArchive`** - **Replace existing archive**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
By default, overwrites an existing archive. Otherwise, when set to `false`, uncompressed tar files are added to the existing archive.

Supported file formats that can be added to an existing archive:

- `zip`
- `7z`
- `tar` - Only uncompressed
- `wim`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbose"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`verbose`** - **Force verbose output**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to true, forces tools to use verbose output. Overrides the 'quiet' setting.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="quiet"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`quiet`** - **Force quiet output**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, forces tools to use quiet output. The `verbose` setting (or equivalent) can override this setting.
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

Use this task to create an archive file from a source folder.
Standard archive formats are supported including .zip, .jar, .war, .ear, .tar, .7z, and more.
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