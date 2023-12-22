---
title: CopyPublishBuildArtifacts@1 - Copy and Publish Build Artifacts v1 task
description: CopyPublishBuildArtifacts@1 is deprecated. Use the Copy Files task and the Publish Build Artifacts task instead.
ms.date: 12/21/2023
monikerRange: "<=azure-pipelines"
---

# CopyPublishBuildArtifacts@1 - Copy and Publish Build Artifacts v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to copy build artifacts to a staging folder and then publish them to the server or a file share. Files are copied to the `$(Build.ArtifactStagingDirectory)` staging folder and then published.

> [!IMPORTANT]
> This task is deprecated. We recommend that you use [Pipeline Artifacts](/azure/devops/pipelines/artifacts/pipeline-artifacts) and the [Copy Files task](copy-files-v2.md) and the [Publish Build Artifacts](publish-build-artifacts-v1.md) task instead.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Copy and Publish Build Artifacts v1
# CopyPublishBuildArtifacts@1 is deprecated. Use the Copy Files task and the Publish Build Artifacts task instead.
- task: CopyPublishBuildArtifacts@1
  inputs:
    #CopyRoot: # string. Copy Root. 
    Contents: # string. Required. Contents. 
    ArtifactName: # string. Required. Artifact Name. 
    ArtifactType: # 'Container' | 'FilePath'. Required. Artifact Type. 
    #TargetPath: '\\my\share\$(Build.DefinitionName)\$(Build.BuildNumber)' # string. Optional. Use when ArtifactType = FilePath. Path. Default: \\my\share\$(Build.DefinitionName)\$(Build.BuildNumber).
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

<!-- :::item name="CopyRoot"::: -->
:::moniker range="<=azure-pipelines"

**`CopyRoot`** - **Copy Root**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The folder that contains the files you want to copy. If the folder is empty, the task copies files from the root folder of the repo as though [**`$(Build.SourcesDirectory)`**](/azure/devops/pipelines/build/variables) was specified.

If your build produces artifacts outside of the sources directory, specify `$(Agent.BuildDirectory)` to copy files from the build agent working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Contents"::: -->
:::moniker range="<=azure-pipelines"

**`Contents`** - **Contents**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies pattern filters (one on each line) that you want to apply to the list of files to be copied. For example:

- `**` copies all files in the root folder.
- `**\*` copies all files in the root folder and all files in all sub-folders.
- `**\bin` copies files in any sub-folder named `bin`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ArtifactName"::: -->
:::moniker range="<=azure-pipelines"

**`ArtifactName`** - **Artifact Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the artifact to create.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ArtifactType"::: -->
:::moniker range="<=azure-pipelines"

**`ArtifactType`** - **Artifact Type**<br>
`string`. Required. Allowed values: `Container` (Server), `FilePath` (File share).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether to store the artifact on TFS/Team Services or to copy it to a file share that must be accessible from the build agent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetPath"::: -->
:::moniker range="<=azure-pipelines"

**`TargetPath`** - **Path**<br>
`string`. Optional. Use when `ArtifactType = FilePath`. Default value: `\\my\share\$(Build.DefinitionName)\$(Build.BuildNumber)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The UNC file path location where the artifact is copied. It must be accessible from the build agent.
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

> [!IMPORTANT]
> This task is deprecated. We recommend that you use [Pipeline Artifacts](/azure/devops/pipelines/artifacts/pipeline-artifacts) and the [Copy Files task](copy-files-v2.md) and the [Publish Build Artifacts](publish-build-artifacts-v1.md) task instead.

### This step didn't produce the outcome I was expecting. How can I fix it?

This task has a couple of known issues:

- Some minimatch patterns don't work.
- It eliminates the most common root path for all paths matched.

You can avoid these issues by instead using the [Copy Files task](copy-files-v2.md) and the [Publish Build Artifacts task](publish-build-artifacts-v1.md).
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
| Agent version |  1.83.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->