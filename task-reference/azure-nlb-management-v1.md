---
title: AzureNLBManagement@1 - Azure Network Load Balancer v1 task
description: Connect or disconnect an Azure virtual machine's network interface to a Load Balancer's back end address pool.
ms.date: 10/21/2022
monikerRange: "<=azure-pipelines"
---

# AzureNLBManagement@1 - Azure Network Load Balancer v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Connect or disconnect an Azure virtual machine's network interface to a Load Balancer's back end address pool.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Connect/Disconnect an Azure virtual machine's network interface to a Load Balancer's backend address pool.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Azure Network Load Balancer v1
# Connect or disconnect an Azure virtual machine's network interface to a Load Balancer's back end address pool.
- task: AzureNLBManagement@1
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure Subscription. 
    ResourceGroupName: # string. Required. Resource Group. 
    LoadBalancer: # string. Required. Load Balancer Name. 
    Action: # 'Disconnect' | 'Connect'. Required. Action.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Azure Network Load Balancer v1
# Connect/Disconnect an Azure virtual machine's network interface to a Load Balancer's backend address pool.
- task: AzureNLBManagement@1
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure Subscription. 
    ResourceGroupName: # string. Required. Resource Group. 
    LoadBalancer: # string. Required. Load Balancer Name. 
    Action: # 'Disconnect' | 'Connect'. Required. Action.
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

<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure Subscription**<br>
Input alias: `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceGroupName"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceGroupName`** - **Resource Group**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the resource group name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="LoadBalancer"::: -->
:::moniker range="<=azure-pipelines"

**`LoadBalancer`** - **Load Balancer Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select or enter the load balancer.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Action"::: -->
:::moniker range="<=azure-pipelines"

**`Action`** - **Action**<br>
`string`. Required. Allowed values: `Disconnect` (Disconnect Primary Network Interface), `Connect` (Connect Primary Network Interface).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
**Disconnect:**  Removes the virtual machine’s primary network interface from the load balancer’s backend pool, so it stops receiving network traffic.

**Connect:** Adds the virtual machine’s primary network interface to load balancer backend pool, so it starts receiving network traffic based on the load balancing rules for the load balancer resource.
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

Use this task to connect or disconnect an Azure virtual machine's network interface to a load balancer's address pool.
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
| Runs on | DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.95.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->