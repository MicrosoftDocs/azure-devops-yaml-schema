---
title: AzureFunctionOnKubernetes@1 - Azure Function on Kubernetes v1 task
description: Deploy Azure function to Kubernetes cluster.
ms.date: 04/12/2023
monikerRange: "=azure-pipelines"
---

# AzureFunctionOnKubernetes@1 - Azure Function on Kubernetes v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Deploy Azure function to Kubernetes cluster.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure Function on Kubernetes v1
# Deploy Azure function to Kubernetes cluster.
- task: AzureFunctionOnKubernetes@1
  inputs:
  # Service Connections
    connectionType: 'Kubernetes Service Connection' # 'Azure Resource Manager' | 'Kubernetes Service Connection'. Required. Service connection type. Default: Kubernetes Service Connection.
    dockerRegistryServiceConnection: # string. Required. Docker registry service connection. 
    #kubernetesServiceConnection: # string. Alias: kubernetesServiceEndpoint. Required when connectionType = Kubernetes Service Connection. Kubernetes service connection. 
    #azureSubscriptionConnection: # string. Alias: azureSubscriptionEndpoint. Required when connectionType = Azure Resource Manager. Azure subscription. 
    #azureResourceGroup: # string. Required when connectionType = Azure Resource Manager. Resource group. 
    #kubernetesCluster: # string. Required when connectionType = Azure Resource Manager. Kubernetes cluster. 
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

<!-- :::item name="connectionType"::: -->
:::moniker range="=azure-pipelines"

**`connectionType`** - **Service connection type**<br>
`string`. Required. Allowed values: `Azure Resource Manager`, `Kubernetes Service Connection`. Default value: `Kubernetes Service Connection`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Kubernetes service connection type.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerRegistryServiceConnection"::: -->
:::moniker range="=azure-pipelines"

**`dockerRegistryServiceConnection`** - **Docker registry service connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker registry service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kubernetesServiceConnection"::: -->
:::moniker range="=azure-pipelines"

**`kubernetesServiceConnection`** - **Kubernetes service connection**<br>
Input alias: `kubernetesServiceEndpoint`. `string`. Required when `connectionType = Kubernetes Service Connection`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Kubernetes service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscriptionConnection"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscriptionConnection`** - **Azure subscription**<br>
Input alias: `azureSubscriptionEndpoint`. `string`. Required when `connectionType = Azure Resource Manager`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription, which contains Azure Container Registry.Note: To configure new service connection, select the Azure subscription from the list and click 'Authorize'. If your subscription is not listed or if you want to use an existing Service Principal, you can setup an Azure service connection using 'Add' or 'Manage' button.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureResourceGroup"::: -->
:::moniker range="=azure-pipelines"

**`azureResourceGroup`** - **Resource group**<br>
`string`. Required when `connectionType = Azure Resource Manager`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure resource group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kubernetesCluster"::: -->
:::moniker range="=azure-pipelines"

**`kubernetesCluster`** - **Kubernetes cluster**<br>
`string`. Required when `connectionType = Azure Resource Manager`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure managed cluster.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="namespace"::: -->
:::moniker range="=azure-pipelines"

**`namespace`** - **Kubernetes namespace**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Kubernetes namespace.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secretName"::: -->
:::moniker range="=azure-pipelines"

**`secretName`** - **Secret Name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Kubernetes secret containing function config data (for ex. AzureWebJobsStorage: `Azure storage connection string`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerHubNamespace"::: -->
:::moniker range="=azure-pipelines"

**`dockerHubNamespace`** - **Docker Hub namespace**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Docker Hub namespace. Required for private Docker Hub repository.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appName"::: -->
:::moniker range="=azure-pipelines"

**`appName`** - **Application Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Application Name. The Kubernetes objects created use this name. This should follow Kubernetes naming conventions for resource names.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="functionRootDirectory"::: -->
:::moniker range="=azure-pipelines"

**`functionRootDirectory`** - **Function root directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Function root directory. Should contain host.json. Docker build and push is performed from this directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="waitForStability"::: -->
:::moniker range="=azure-pipelines"

**`waitForStability`** - **Wait for stability**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Wait for the Kubernetes objects to reach the desired state.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="=azure-pipelines"

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

:::moniker range="=azure-pipelines"

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

:::moniker range="=azure-pipelines"

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