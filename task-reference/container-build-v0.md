---
title: ContainerBuild@0 - Container Build v0 task
description: Container Build Task.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2020"
---

# ContainerBuild@0 - Container Build v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Container Build Task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Container Build v0
# Container Build Task.
- task: ContainerBuild@0
  inputs:
    #dockerRegistryServiceConnection: # string. Docker registry service connection. 
    #repository: # string. Container repository. 
    Dockerfile: 'Dockerfile' # string. Required. Dockerfile. Default: 'Dockerfile'.
    #buildContext: '.' # string. Build context. Default: '.'.
    #tags: '$(Build.BuildId)' # string. Tags. Default: '$(Build.BuildId)'.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="dockerRegistryServiceConnection"::: -->
:::moniker range=">=azure-pipelines-2020"

**`dockerRegistryServiceConnection`** - **Docker registry service connection**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker registry service connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="repository"::: -->
:::moniker range=">=azure-pipelines-2020"

**`repository`** - **Container repository**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the repository within the container registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Dockerfile"::: -->
:::moniker range=">=azure-pipelines-2020"

**`Dockerfile`** - **Dockerfile**<br>
Type: string. Required. Default value: 'Dockerfile'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to Dockerfile.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildContext"::: -->
:::moniker range=">=azure-pipelines-2020"

**`buildContext`** - **Build context**<br>
Type: string. Default value: '.'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to Build context.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
:::moniker range=">=azure-pipelines-2020"

**`tags`** - **Tags**<br>
Type: string. Default value: '$(Build.BuildId)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A list of tags in separate lines. Tags are used while building and pushing the image to container registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020"

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

:::moniker range=">=azure-pipelines-2020"

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