---
title: ArchiveFiles@1 - Archive Files v1 task
description: Archive files using compression formats such as .7z, .rar, .tar.gz, and .zip.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# ArchiveFiles@1 - Archive Files v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Archive files using compression formats such as .7z, .rar, .tar.gz, and .zip.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Archive Files v1
# Archive files using compression formats such as .7z, .rar, .tar.gz, and .zip.
- task: ArchiveFiles@1
  inputs:
    rootFolder: '$(Build.BinariesDirectory)' # string. Required. Root folder (or file) to archive. Default: '$(Build.BinariesDirectory)'.
    includeRootFolder: true # boolean. Required. Prefix root folder name to archive paths. Default: true.
  # Archive
    archiveType: 'default' # 'default' | '7z' | 'tar' | 'wim'. Required. Archive type. Default: 'default'.
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

<!-- :::item name="rootFolder"::: -->
:::moniker range="<=azure-pipelines"

**`rootFolder`** - **Root folder (or file) to archive**<br>
Type: string. Required. Default value: '$(Build.BinariesDirectory)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The root folder to add to the archive.  Everything under this folder will be added to the resulting archive.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeRootFolder"::: -->
:::moniker range="<=azure-pipelines"

**`includeRootFolder`** - **Prefix root folder name to archive paths**<br>
Type: boolean. Required. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If selected, the root folder name will be prefixed to file paths within the archive.  Otherwise, all file paths will start one level lower.<p>For example, suppose the selected root folder is: <b>`/home/user/output/classes/`</b>, and contains: <b>`com/acme/Main.class`</b>. <ul><li>If selected, the resulting archive would contain: <b>`classes/com/acme/Main.class`</b>.</li><li>Otherwise, the resulting archive would contain: <b>`com/acme/Main.class`</b>.</li></ul>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="archiveType"::: -->
:::moniker range="<=azure-pipelines"

**`archiveType`** - **Archive type**<br>
Type: string. Required. Allowed values: 'default', '7z', 'tar', 'wim'. Default value: 'default'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the compression scheme used.  To create <b>`foo.jar`</b>, for example, choose <b>`zip`</b> for the compression, and specify <b>`foo.jar`</b> as the archive file to create.  For all tar files (including compressed ones), choose <b>`tar`</b>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tarCompression"::: -->
:::moniker range="<=azure-pipelines"

**`tarCompression`** - **Tar compression**<br>
Type: string. Optional. Use when archiveType = tar. Allowed values: 'gz', 'bz2', 'xz', 'none'. Default value: 'gz'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally choose a compression scheme, or choose <b>`None`</b> to create an uncompressed tar file.
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
If an existing archive exists, specify whether to overwrite it.  Otherwise, files will be added to it.
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

:::moniker range="<=azure-pipelines"

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