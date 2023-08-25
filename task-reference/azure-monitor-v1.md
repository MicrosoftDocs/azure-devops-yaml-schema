---
title: AzureMonitor@1 - Query Azure Monitor alerts v1 task
description: Observe the configured Azure Monitor rules for active alerts.
ms.date: 08/25/2023
monikerRange: ">=azure-pipelines-2019.1"
---

# AzureMonitor@1 - Query Azure Monitor alerts v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Observe the configured Azure Monitor rules for active alerts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Query Azure Monitor alerts v1
# Observe the configured Azure Monitor rules for active alerts.
- task: AzureMonitor@1
  inputs:
    connectedServiceNameARM: # string. Required. Azure subscription. 
    ResourceGroupName: # string. Required. Resource group. 
  # Advanced
    filterType: 'none' # 'resource' | 'alertrule' | 'none'. Required. Filter type. Default: none.
    #resource: # string. Required when filterType = resource. Resource. 
    #alertRule: # string. Required when filterType = alertrule. Alert rule. 
    #severity: 'Sev0,Sev1,Sev2,Sev3,Sev4' # 'Sev0' | 'Sev1' | 'Sev2' | 'Sev3' | 'Sev4'. Severity. Default: Sev0,Sev1,Sev2,Sev3,Sev4.
    #timeRange: '1h' # '1h' | '1d' | '7d' | '30d'. Time range. Default: 1h.
    #alertState: 'Acknowledged,New' # 'New' | 'Acknowledged' | 'Closed'. Alert state. Default: Acknowledged,New.
    #monitorCondition: 'Fired' # 'Fired ' | 'Resolved'. Monitor condition. Default: Fired.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="connectedServiceNameARM"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`connectedServiceNameARM`** - **Azure subscription**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects an Azure Resource Manager subscription to monitor.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceGroupName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ResourceGroupName`** - **Resource group**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides the name of a resource group to monitor in the subscription.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="filterType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`filterType`** - **Filter type**<br>
`string`. Required. Allowed values: `resource` (By resource), `alertrule` (By alert rule), `none`. Default value: `none`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Filters the type by a specific resource or alert rule.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resource"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`resource`** - **Resource**<br>
`string`. Required when `filterType = resource`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the Azure resource to monitor.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="alertRule"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`alertRule`** - **Alert rule**<br>
`string`. Required when `filterType = alertrule`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects from the currently configured alert rules to query for the status.

The default value is to select all.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="severity"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`severity`** - **Severity**<br>
`string`. Allowed values: `Sev0`, `Sev1`, `Sev2`, `Sev3`, `Sev4`. Default value: `Sev0,Sev1,Sev2,Sev3,Sev4`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Filters by severity.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="timeRange"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`timeRange`** - **Time range**<br>
`string`. Allowed values: `1h` (Past hour), `1d` (Past 24 hours), `7d` (Past 7 days), `30d` (Past 30 days). Default value: `1h`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Filters by the time range.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="alertState"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`alertState`** - **Alert state**<br>
`string`. Allowed values: `New`, `Acknowledged`, `Closed`. Default value: `Acknowledged,New`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Filters by the state of the alert instance.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="monitorCondition"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`monitorCondition`** - **Monitor condition**<br>
`string`. Allowed values: `Fired ` (Fired), `Resolved`. Default value: `Fired`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Represents whether the underlying conditions have crossed the defined alert rule thresholds.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019.1"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

To observe the configured Azure monitor rules for active alerts, use this task in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) of a release pipeline.

> [!NOTE]
> This task can only be used in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) of a release pipeline.

The task succeeds if none of the alert rules are activated at the time of sampling.

For more information about using this task, see [Approvals and gates overview](/azure/devops/pipelines/release/approvals/).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019.1"

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