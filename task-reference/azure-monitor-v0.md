---
title: AzureMonitor@0 - Query Classic Azure Monitor alerts v0 task
description: Observe the configured classic Azure Monitor rules for active alerts.
ms.date: 08/19/2024
monikerRange: "<=azure-pipelines"
---

# AzureMonitor@0 - Query Classic Azure Monitor alerts v0 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Observe the configured classic Azure Monitor rules for active alerts.

> [!IMPORTANT]
> [!INCLUDE [task-deprecation](includes/task-deprecation.md)] Use [AzureMonitor@1](./azure-monitor-v1.md).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range=">=azure-pipelines-2022 <=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Observe the configured classic Azure Monitor rules for active alerts.

This task is deprecated; use [AzureMonitor@1](./azure-monitor-v1.md).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

<!-- :::editable-content name="description"::: -->
Observe the configured classic Azure Monitor rules for active alerts.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Observe the configured Azure monitor rules for active alerts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Query Classic Azure Monitor alerts v0
# Observe the configured classic Azure Monitor rules for active alerts.
- task: AzureMonitor@0
  inputs:
    connectedServiceNameARM: # string. Required. Azure subscription. 
    ResourceGroupName: # string. Required. Resource group. 
    ResourceType: 'Microsoft.Insights/components' # 'Microsoft.Insights/components' | 'Microsoft.Web/sites' | 'Microsoft.Storage/storageAccounts' | 'Microsoft.Compute/virtualMachines'. Required. Resource type. Default: Microsoft.Insights/components.
    resourceName: # string. Required. Resource name. 
    alertRules: # string. Required. Alert rules.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Query Azure Monitor Alerts v0
# Observe the configured Azure monitor rules for active alerts.
- task: AzureMonitor@0
  inputs:
    connectedServiceNameARM: # string. Required. Azure subscription. 
    ResourceGroupName: # string. Required. Resource group. 
    ResourceType: 'Microsoft.Insights/components' # 'Microsoft.Insights/components' | 'Microsoft.Web/sites' | 'Microsoft.Storage/storageAccounts' | 'Microsoft.Compute/virtualMachines'. Required. Resource type. Default: Microsoft.Insights/components.
    resourceName: # string. Required. Resource name. 
    alertRules: # string. Required. Alert rules.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="connectedServiceNameARM"::: -->
:::moniker range="<=azure-pipelines"

**`connectedServiceNameARM`** - **Azure subscription**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects an Azure Resource Manager subscription to monitor.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceGroupName"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceGroupName`** - **Resource group**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides the name of a resource group to monitor.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceType"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceType`** - **Resource type**<br>
`string`. Required. Allowed values: `Microsoft.Insights/components` (Application Insights), `Microsoft.Web/sites` (App Services), `Microsoft.Storage/storageAccounts` (Storage Account), `Microsoft.Compute/virtualMachines` (Virtual Machines). Default value: `Microsoft.Insights/components`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the Azure resource type to monitor.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceName"::: -->
:::moniker range="<=azure-pipelines"

**`resourceName`** - **Resource name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the name of the Azure resource to monitor.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="alertRules"::: -->
:::moniker range="<=azure-pipelines"

**`alertRules`** - **Alert rules**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A list of Azure alert rules to monitor.
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
| Runs on | Server, ServerGate |
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
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->