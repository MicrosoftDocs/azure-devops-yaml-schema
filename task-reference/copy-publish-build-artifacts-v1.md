---
title: CopyPublishBuildArtifacts@1 - Copy and Publish Build Artifacts v1 task
description: CopyPublishBuildArtifacts@1 is deprecated. Use the Copy Files task and the Publish Build Artifacts task instead.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# CopyPublishBuildArtifacts@1 - Copy and Publish Build Artifacts v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
CopyPublishBuildArtifacts@1 is deprecated. Use the Copy Files task and the Publish Build Artifacts task instead.
<!-- :::editable-content-end::: -->

This task is deprecated.

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
    #TargetPath: '\\my\share\$(Build.DefinitionName)\$(Build.BuildNumber)' # string. Optional. Use when ArtifactType = FilePath. Path. Default: '\\my\share\$(Build.DefinitionName)\$(Build.BuildNumber)'.
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
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Root folder to which file matching patterns should apply. If no value is provided, the repo root is used. Use variables to specify a folder outside of the repo, such as: $(Agent.BuildDirectory).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Contents"::: -->
:::moniker range="<=azure-pipelines"

**`Contents`** - **Contents**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File or folder paths to include as part of the artifact. Supports multiple lines of minimatch patterns. [More Information](https://go.microsoft.com/fwlink/?LinkID=613725).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ArtifactName"::: -->
:::moniker range="<=azure-pipelines"

**`ArtifactName`** - **Artifact Name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the artifact to create.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ArtifactType"::: -->
:::moniker range="<=azure-pipelines"

**`ArtifactType`** - **Artifact Type**<br>
Type: string. Required. Allowed values: 'Container', 'FilePath'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose whether to store the artifact on TFS/Team Services, or to copy it to a file share that must be accessible from the build agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetPath"::: -->
:::moniker range="<=azure-pipelines"

**`TargetPath`** - **Path**<br>
Type: string. Optional. Use when ArtifactType = FilePath. Default value: '\\my\share\$(Build.DefinitionName)\$(Build.BuildNumber)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The UNC file path location to copy the artifact. It must be accessible from the build agent.
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