---
title: PublishPipelineArtifact@0 - Publish Pipeline Artifacts v0 task
description: Publish a local directory or file as a named artifact for the current pipeline.
ms.date: 11/03/2022
monikerRange: ">=azure-pipelines-2019"
---

# PublishPipelineArtifact@0 - Publish Pipeline Artifacts v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Use this task to publish a local directory or file as a named artifact for the current pipeline.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to publish a local directory or file as a named artifact for the current pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Publish Pipeline Artifacts v0
# Publish a local directory or file as a named artifact for the current pipeline.
- task: PublishPipelineArtifact@0
  inputs:
    artifactName: 'drop' # string. Required. The name of this artifact. Default: drop.
    targetPath: # string. Required. Path to publish. 
    #properties: # string. Custom properties.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

```yaml
# Publish Pipeline Artifacts v0
# Publish a local directory or file as a named artifact for the current pipeline.
- task: PublishPipelineArtifact@0
  inputs:
    artifactName: 'drop' # string. Required. The name of this artifact. Default: drop.
    targetPath: # string. Required. Path to publish.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
# Publish Pipeline Artifacts v0
# Publish Pipeline Artifact.
- task: PublishPipelineArtifact@0
  inputs:
    artifactName: 'drop' # string. Required. The name of this artifact. Default: drop.
    targetPath: # string. Required. Path to publish.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="artifactName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`artifactName`** - **The name of this artifact**<br>
`string`. Required. Default value: `drop`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the artifact.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targetPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`targetPath`** - **Path to publish**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the folder or file path to publish. This can be a fully qualified path or a path relative to the root of the repository. Wildcards are not supported. [Variables](https://go.microsoft.com/fwlink/?LinkID=550988) are supported.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="properties"::: -->
:::moniker range=">=azure-pipelines-2022"

**`properties`** - **Custom properties**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the custom properties to associate with the artifact. 
Use a valid JSON string with the prefix `user-` on all keys.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019"

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
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.199 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.155.1 or greater |
| Task category | Utility |

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.140.1 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->