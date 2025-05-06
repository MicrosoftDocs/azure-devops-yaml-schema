---
title: ContainerBuild@0 - Container Build v0 task
description: Container Build Task.
ms.date: 05/06/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# ContainerBuild@0 - Container Build v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Container Build Task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Container Build v0
# Container Build Task.
- task: ContainerBuild@0
  inputs:
    #dockerRegistryServiceConnection: # string. Docker registry service connection. 
    #repository: # string. Container repository. 
    Dockerfile: 'Dockerfile' # string. Required. Dockerfile. Default: Dockerfile.
    #buildContext: '.' # string. Build context. Default: ..
    #tags: '$(Build.BuildId)' # string. Tags. Default: $(Build.BuildId).
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="dockerRegistryServiceConnection"::: -->
:::moniker range="<=azure-pipelines"

**`dockerRegistryServiceConnection`** - **Docker registry service connection**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a Docker registry service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="repository"::: -->
:::moniker range="<=azure-pipelines"

**`repository`** - **Container repository**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the repository within the container registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Dockerfile"::: -->
:::moniker range="<=azure-pipelines"

**`Dockerfile`** - **Dockerfile**<br>
`string`. Required. Default value: `Dockerfile`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the Dockerfile.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildContext"::: -->
:::moniker range="<=azure-pipelines"

**`buildContext`** - **Build context**<br>
`string`. Default value: `.`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the build context.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
:::moniker range="<=azure-pipelines"

**`tags`** - **Tags**<br>
`string`. Default value: `$(Build.BuildId)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The list of tags in separate lines. Tags are used while building and pushing the image to container registry.
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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: Buildctl |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->