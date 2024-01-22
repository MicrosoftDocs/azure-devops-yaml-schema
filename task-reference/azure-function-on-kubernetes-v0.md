---
title: AzureFunctionOnKubernetes@0 - Azure Function on Kubernetes v0 task
description: Deploy Azure function to Kubernetes cluster (task version 0).
ms.date: 01/22/2024
monikerRange: ">=azure-pipelines-2020"
---

# AzureFunctionOnKubernetes@0 - Azure Function on Kubernetes v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Deploy Azure function to Kubernetes cluster.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Azure Function on Kubernetes v0
# Deploy Azure function to Kubernetes cluster.
- task: AzureFunctionOnKubernetes@0
  inputs:
  # Service Connections
    dockerRegistryServiceConnection: # string. Required. Docker registry service connection. 
    kubernetesServiceConnection: # string. Required. Kubernetes service connection. 
  # Commands
    #namespace: # string. Kubernetes namespace. 
    #secretName: # string. Secret Name. 
    #dockerHubNamespace: # string. Docker Hub namespace. 
    appName: # string. Required. Application Name. 
    #functionRootDirectory: # string. Function root directory. 
    #waitForStability: true # boolean. Wait for stability. Default: true.
    #arguments: # string. Arguments.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="dockerRegistryServiceConnection"::: -->
:::moniker range=">=azure-pipelines-2020"

**`dockerRegistryServiceConnection`** - **Docker registry service connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker registry service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kubernetesServiceConnection"::: -->
:::moniker range=">=azure-pipelines-2020"

**`kubernetesServiceConnection`** - **Kubernetes service connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Kubernetes service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="namespace"::: -->
:::moniker range=">=azure-pipelines-2020"

**`namespace`** - **Kubernetes namespace**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Kubernetes namespace.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secretName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`secretName`** - **Secret Name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Kubernetes secret containing function config data (for ex. AzureWebJobsStorage: `Azure storage connection string`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerHubNamespace"::: -->
:::moniker range=">=azure-pipelines-2020"

**`dockerHubNamespace`** - **Docker Hub namespace**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Docker Hub namespace. Required for private Docker Hub repository.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`appName`** - **Application Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Application Name. The Kubernetes objects created use this name. This should follow Kubernetes naming conventions for resource names.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="functionRootDirectory"::: -->
:::moniker range=">=azure-pipelines-2020"

**`functionRootDirectory`** - **Function root directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Function root directory. Should contain host.json. Docker build and push is performed from this directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="waitForStability"::: -->
:::moniker range=">=azure-pipelines-2020"

**`waitForStability`** - **Wait for stability**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Wait for the Kubernetes objects to reach the desired state.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range=">=azure-pipelines-2020"

**`arguments`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Pass arguments to command. Ex:<br>--no-docker --service-type NodePort.
<!-- :::editable-content-end::: -->
<br>

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
:::moniker range=">azure-pipelines-2022"

## Remarks

> [!NOTE]
> There is a newer version of this task available that provides additional support for targetting a Kubernetes cluster in different ways, using the `connectionType` property. For more information, see [AzureFunctionOnKubernetes@1](./azure-function-on-kubernetes-v1.md) and [AzureFunctionOnKubernetes@1 remarks](./azure-function-on-kubernetes-v1.md#remarks)

:::moniker-end
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
| Agent version | All supported agent versions. |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->