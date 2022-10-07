---
title: AzureMonitorAlerts@0 - Azure Monitor alerts (Deprecated) v0 task
description: Configure alerts on available metrics for an Azure resource (Deprecated).
ms.date: 09/26/2022
monikerRange: "<=azure-pipelines"
---

# AzureMonitorAlerts@0 - Azure Monitor alerts (Deprecated) v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Configure alerts on available metrics for an Azure resource (Deprecated).
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Configure alerts on available metrics for an Azure resource.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Azure Monitor alerts (Deprecated) v0
# Configure alerts on available metrics for an Azure resource (Deprecated).
- task: AzureMonitorAlerts@0
  inputs:
    azureSubscription: # string. Required. Azure Subscription. 
    ResourceGroupName: # string. Required. Resource Group. 
    ResourceType: 'Microsoft.Insights/components' # 'Microsoft.Insights/components' | 'Microsoft.Web/sites' | 'Microsoft.Storage/storageAccounts' | 'Microsoft.Compute/virtualMachines'. Required. Resource Type. Default: Microsoft.Insights/components.
    ResourceName: # string. Required. Resource name. 
    AlertRules: # string. Required. Alert rules. 
  # Notify via email
    #NotifyServiceOwners: # boolean. Subscription owners, contributors and readers. 
    #NotifyEmails: # string. Additional administrator emails.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Azure Monitor alerts v0
# Configure alerts on available metrics for an Azure resource.
- task: AzureMonitorAlerts@0
  inputs:
    azureSubscription: # string. Required. Azure Subscription. 
    ResourceGroupName: # string. Required. Resource Group. 
    ResourceType: 'Microsoft.Insights/components' # 'Microsoft.Insights/components' | 'Microsoft.Web/sites' | 'Microsoft.Storage/storageAccounts' | 'Microsoft.Compute/virtualMachines'. Required. Resource Type. Default: Microsoft.Insights/components.
    ResourceName: # string. Required. Resource name. 
    AlertRules: # string. Required. Alert rules. 
  # Notify via email
    #NotifyServiceOwners: # boolean. Subscription owners, contributors and readers. 
    #NotifyEmails: # string. Additional administrator emails.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Azure Monitor Alerts v0
# Configure alerts on available metrics for an Azure resource.
- task: AzureMonitorAlerts@0
  inputs:
    azureSubscription: # string. Required. Azure Subscription. 
    ResourceGroupName: # string. Required. Resource Group. 
    ResourceType: 'Microsoft.Insights/components' # 'Microsoft.Insights/components' | 'Microsoft.Web/sites' | 'Microsoft.Storage/storageAccounts' | 'Microsoft.Compute/virtualMachines'. Required. Resource Type. Default: Microsoft.Insights/components.
    ResourceName: # string. Required. Resource name. 
    AlertRules: # string. Required. Alert rules. 
  # Notify via email
    #NotifyServiceOwners: # boolean. Subscription owners, contributors and readers. 
    #NotifyEmails: # string. Additional administrator emails.
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
Selects the Azure Resource Manager subscription.

**Note:** To configure new service connection, select the Azure subscription from the list and click `Authorize`.

If your subscription is not listed or if you want to use an existing service principal, you can setup an Azure service connection using the `Add` or `Manage` button.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceGroupName"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceGroupName`** - **Resource Group**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the Azure Resource Group that contains the Azure resource where you want to configure an alert.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceType"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceType`** - **Resource Type**<br>
`string`. Required. Allowed values: `Microsoft.Insights/components` (Application Insights), `Microsoft.Web/sites` (App Services), `Microsoft.Storage/storageAccounts` (Storage Account), `Microsoft.Compute/virtualMachines` (Virtual Machines). Default value: `Microsoft.Insights/components`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the Azure resource type.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceName"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceName`** - **Resource name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the name of the Azure resource where you want to configure an alert.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AlertRules"::: -->
:::moniker range="<=azure-pipelines"

**`AlertRules`** - **Alert rules**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The list of the Azure monitor alerts that are configured on the selected Azure resource.

To add or modify alerts, click the `…` button.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="NotifyServiceOwners"::: -->
:::moniker range="<=azure-pipelines"

**`NotifyServiceOwners`** - **Subscription owners, contributors and readers**<br>
`boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Sends an email notification to everyone who has access to the specified resource group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="NotifyEmails"::: -->
:::moniker range="<=azure-pipelines"

**`NotifyEmails`** - **Additional administrator emails**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Add email addresses separated by semicolons (;) if you want to include additional email notification recipients. This feature can be incorporated whether or not the "subscription owners..." box is checked.
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

Use this task to configure alerts on available metrics for an Azure resource.
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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.111.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
