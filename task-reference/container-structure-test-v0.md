---
title: ContainerStructureTest@0 - Container Structure Test v0 task
description: Uses container-structure-test (https://github.com/GoogleContainerTools/container-structure-test) to validate the structure of an image based on four categories of tests - command tests, file existence tests, file content tests and metadata tests.
ms.date: 08/10/2022
monikerRange: ">=azure-pipelines-2020"
---

# ContainerStructureTest@0 - Container Structure Test v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Uses container-structure-test (https://github.com/GoogleContainerTools/container-structure-test) to validate the structure of an image based on four categories of tests - command tests, file existence tests, file content tests and metadata tests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Container Structure Test v0
# Uses container-structure-test (https://github.com/GoogleContainerTools/container-structure-test) to validate the structure of an image based on four categories of tests - command tests, file existence tests, file content tests and metadata tests.
- task: ContainerStructureTest@0
  inputs:
  # Container Repository
    dockerRegistryServiceConnection: # string. Required. Docker registry service connection. 
    repository: # string. Required. Container repository. 
    #tag: '$(Build.BuildId)' # string. Tag. Default: '$(Build.BuildId)'.
    configFile: # string. Required. Config file path. 
    #testRunTitle: # string. Test run title. 
    #failTaskOnFailedTests: false # boolean. Fail task if there are test failures. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="dockerRegistryServiceConnection"::: -->
:::moniker range=">=azure-pipelines-2020"

**`dockerRegistryServiceConnection`** - **Docker registry service connection**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker registry service connection. Required for commands that need to authenticate with a registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="repository"::: -->
:::moniker range=">=azure-pipelines-2020"

**`repository`** - **Container repository**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the repository.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tag"::: -->
:::moniker range=">=azure-pipelines-2020"

**`tag`** - **Tag**<br>
Type: string. Default value: '$(Build.BuildId)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The tag is used in pulling the image from docker registry service connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configFile"::: -->
:::moniker range=">=azure-pipelines-2020"

**`configFile`** - **Config file path**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Config files path, that contains container structure tests. Either .yaml or .json files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range=">=azure-pipelines-2020"

**`testRunTitle`** - **Test run title**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the Test Run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failTaskOnFailedTests"::: -->
:::moniker range=">=azure-pipelines-2020"

**`failTaskOnFailedTests`** - **Fail task if there are test failures**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fail the task if there are any test failures. Check this option to fail the task if test failures are detected.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.0.0 or greater |
| Task category | Test |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->