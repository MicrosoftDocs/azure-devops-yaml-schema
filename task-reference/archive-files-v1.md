---
title: ArchiveFiles@1 - Archive Files v1 task
description: Archive files using compression formats such as .7z, .rar, .tar.gz, and .zip.
ms.date: 09/26/2022
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
    rootFolder: '$(Build.BinariesDirectory)' # string. Required. Root folder (or file) to archive. Default: $(Build.BinariesDirectory).
    includeRootFolder: true # boolean. Required. Prefix root folder name to archive paths. Default: true.
  # Archive
    archiveType: 'default' # 'default' | '7z' | 'tar' | 'wim'. Required. Archive type. Default: default.
    #tarCompression: 'gz' # 'gz' | 'bz2' | 'xz' | 'none'. Optional. Use when archiveType = tar. Tar compression. Default: gz.
    archiveFile: '$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip' # string. Required. Archive file to create. Default: $(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip.
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
`string`. Required. Default value: `$(Build.BinariesDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the root folder or file to archive.  For folders, everything in the named folder is added to the archive.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeRootFolder"::: -->
:::moniker range="<=azure-pipelines"

**`includeRootFolder`** - **Prefix root folder name to archive paths**<br>
`boolean`. Required. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prepends the root folder name to file paths within the archive.  Otherwise, all file paths will start one level lower.

For example, if the root folder path is: `/home/user/output/classes/` and the file path: `com/acme/Main.class`. The resulting archive will contain: `classes/com/acme/Main.class`. Otherwise, the resulting archive will contain: `com/acme/Main.class`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="archiveType"::: -->
:::moniker range="<=azure-pipelines"

**`archiveType`** - **Archive type**<br>
`string`. Required. Allowed values: `default` (zip), `7z`, `tar`, `wim`. Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a compression format.  

For example, to create an archive named `foo.jar`:

- Select compression format: `zip`
- Specify the archive name: `foo.jar`  

For all tar files (including compressed ones), choose `tar`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tarCompression"::: -->
:::moniker range="<=azure-pipelines"

**`tarCompression`** - **Tar compression**<br>
`string`. Optional. Use when `archiveType = tar`. Allowed values: `gz`, `bz2`, `xz`, `none`. Default value: `gz`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Select a compression scheme or `None` to create an uncompressed tar file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="archiveFile"::: -->
:::moniker range="<=azure-pipelines"

**`archiveFile`** - **Archive file to create**<br>
`string`. Required. Default value: `$(Build.ArtifactStagingDirectory)/$(Build.BuildId).zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the archive file to create.  For example, to create <b>`foo.tgz`</b>, select the <b>`tar`</b> archive type and <b>`gz`</b> for tar compression.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="replaceExistingArchive"::: -->
:::moniker range="<=azure-pipelines"

**`replaceExistingArchive`** - **Replace existing archive**<br>
`boolean`. Required. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Overwrites an existing archive.  If not specified, files are added to the archive.
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

There is a newer version of the Archive Files task available.

* [Archive Files v2](archive-files-v2.md)
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
## See also

* [Archive Files v2](archive-files-v2.md)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->