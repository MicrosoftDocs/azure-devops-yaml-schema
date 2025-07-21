---
title: AzureAppServiceManage@0 - Azure App Service manage v0 task
description: Start, stop, restart, slot swap, slot delete, install site extensions or enable continuous monitoring for an Azure App Service.
ms.date: 07/21/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# AzureAppServiceManage@0 - Azure App Service manage v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Start, stop, restart, slot swap, slot delete, install site extensions, or enable continuous monitoring for an Azure App Service.
<!-- :::editable-content-end::: -->

:::moniker-end

<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Azure App Service manage v0
# Start, stop, restart, slot swap, slot delete, install site extensions or enable continuous monitoring for an Azure App Service.
- task: AzureAppServiceManage@0
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    #Action: 'Swap Slots' # 'Swap Slots' | 'Start Azure App Service' | 'Stop Azure App Service' | 'Restart Azure App Service' | 'Start Swap With Preview' | 'Complete Swap' | 'Cancel Swap' | 'Delete Slot' | 'Install Extensions' | 'Enable Continuous Monitoring' | 'Start all continuous webjobs' | 'Stop all continuous webjobs'. Action. Default: Swap Slots.
    WebAppName: # string. Required. App Service name. 
    #SpecifySlotOrASE: false # boolean. Alias: SpecifySlot. Optional. Use when Action != Swap Slots && Action != Delete Slot && Action != Start Swap With Preview && Action != Complete Swap && Action != Cancel Swap. Specify Slot or App Service Environment. Default: false.
    #ResourceGroupName: # string. Required when Action = Swap Slots || Action = Delete Slot || SpecifySlot = true || Action = Start Swap With Preview || Action = Complete Swap || Action = Cancel Swap. Resource group. 
    #SourceSlot: # string. Required when Action = Swap Slots || Action = Start Swap With Preview  || Action = Complete Swap. Source Slot. 
    #SwapWithProduction: true # boolean. Optional. Use when Action = Swap Slots || Action = Start Swap With Preview  || Action = Complete Swap. Swap with Production. Default: true.
    #TargetSlot: # string. Required when SwapWithProduction = false. Target Slot. 
    #PreserveVnet: false # boolean. Optional. Use when Action = Swap Slots || Action = Start Swap With Preview || Action = Complete Swap. Preserve Vnet. Default: false.
    #Slot: 'production' # string. Required when Action = Delete Slot || Action = Cancel Swap || SpecifySlot = true. Slot. Default: production.
    #ExtensionsList: # string. Required when Action = Install Extensions. Install Extensions. 
    #OutputVariable: # string. Optional. Use when Action = Install Extensions. Output variable. 
    #AppInsightsResourceGroupName: # string. Required when Action == Enable Continuous Monitoring. Resource Group name for Application Insights. 
    #ApplicationInsightsResourceName: # string. Required when Action == Enable Continuous Monitoring. Application Insights resource name. 
  # Advanced Settings
    #ApplicationInsightsWebTestName: # string. Optional. Use when Action == Enable Continuous Monitoring. Application Insights web test name.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
[Input alias](index.md#what-are-task-input-aliases): `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the Azure Resource Manager subscription.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Action"::: -->
:::moniker range="<=azure-pipelines"

**`Action`** - **Action**<br>
`string`. Allowed values: `Swap Slots`, `Start Azure App Service` (Start App Service), `Stop Azure App Service` (Stop App Service), `Restart Azure App Service` (Restart App Service), `Start Swap With Preview`, `Complete Swap` (Complete Swap With Preview), `Cancel Swap` (Cancel Swap With Preview), `Delete Slot`, `Install Extensions`, `Enable Continuous Monitoring`, `Start all continuous webjobs`, `Stop all continuous webjobs`. Default value: `Swap Slots`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Defines the action to perform on the App Service. You can start, stop, restart, slot swap, start swap with a preview, complete swap with a preview, cancel swap with a preview, install site extensions, or enable continuous monitoring for an Azure App Service.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebAppName"::: -->
:::moniker range="<=azure-pipelines"

**`WebAppName`** - **App Service name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters or selects the name of an existing Azure App Service.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SpecifySlotOrASE"::: -->
:::moniker range="<=azure-pipelines"

**`SpecifySlotOrASE`** - **Specify Slot or App Service Environment**<br>
[Input alias](index.md#what-are-task-input-aliases): `SpecifySlot`. `boolean`. Optional. Use when `Action != Swap Slots && Action != Delete Slot && Action != Start Swap With Preview && Action != Complete Swap && Action != Cancel Swap`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceGroupName"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceGroupName`** - **Resource group**<br>
`string`. Required when `Action = Swap Slots || Action = Delete Slot || SpecifySlot = true || Action = Start Swap With Preview || Action = Complete Swap || Action = Cancel Swap`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters or selects the Azure Resource Group that contains the Azure App Service specified above.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SourceSlot"::: -->
:::moniker range="<=azure-pipelines"

**`SourceSlot`** - **Source Slot**<br>
`string`. Required when `Action = Swap Slots || Action = Start Swap With Preview  || Action = Complete Swap`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Used as source slot when `action == Swap Slots`. The swap action directs destination slot's traffic to the source slot.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SwapWithProduction"::: -->
:::moniker range="<=azure-pipelines"

**`SwapWithProduction`** - **Swap with Production**<br>
`boolean`. Optional. Use when `Action = Swap Slots || Action = Start Swap With Preview  || Action = Complete Swap`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Swaps the traffic of the source slot with production. If you don't select this option, then you need to provide the source and target slot names.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetSlot"::: -->
:::moniker range="<=azure-pipelines"

**`TargetSlot`** - **Target Slot**<br>
`string`. Required when `SwapWithProduction = false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use as the destination slot when `action == Swap Slots`. The swap action directs the destination slot's traffic to the source slot.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="PreserveVnet"::: -->
:::moniker range="<=azure-pipelines"

**`PreserveVnet`** - **Preserve Vnet**<br>
`boolean`. Optional. Use when `Action = Swap Slots || Action = Start Swap With Preview || Action = Complete Swap`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Preserves the virtual network settings.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Slot"::: -->
:::moniker range="<=azure-pipelines"

**`Slot`** - **Slot**<br>
`string`. Required when `Action = Delete Slot || Action = Cancel Swap || SpecifySlot = true`. Default value: `production`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ExtensionsList"::: -->
:::moniker range="<=azure-pipelines"

**`ExtensionsList`** - **Install Extensions**<br>
`string`. Required when `Action = Install Extensions`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Site extensions run on Microsoft Azure App Service. You can install a set of tools as a site extension and better manage your Azure App Service. Restart the App Service so the latest changes take effect.

> [!IMPORTANT]
> Extensions are supported only for Web App on Windows.

You can specify extensions as `name@version` (e.g., `PythonExtension@3.9.0`). If a version is specified, that exact version will be installed. If you specify `latest` as the version, the latest available version will be installed (in case it already has the latest version, installation will be skipped). If no version is specified, the extension will only be installed if it is not already present. Example: `MyExtension@1.2.3, OtherExtension@latest, LegacyExtension`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="OutputVariable"::: -->
:::moniker range="<=azure-pipelines"

**`OutputVariable`** - **Output variable**<br>
`string`. Optional. Use when `Action = Install Extensions`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides the variable name for the selected extension's local installation path.

This field is now deprecated and will be removed. Use the `LocalPathsForInstalledExtensions` variable from the Output Variables section in subsequent tasks.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppInsightsResourceGroupName"::: -->
:::moniker range="<=azure-pipelines"

**`AppInsightsResourceGroupName`** - **Resource Group name for Application Insights**<br>
`string`. Required when `Action == Enable Continuous Monitoring`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters or selects the resource group where your Application Insights resource is available.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ApplicationInsightsResourceName"::: -->
:::moniker range="<=azure-pipelines"

**`ApplicationInsightsResourceName`** - **Application Insights resource name**<br>
`string`. Required when `Action == Enable Continuous Monitoring`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the Application Insights resource where continuous monitoring data is recorded.

If your Application Insights resource is not listed here and you want to create a new resource, select **+New**. Once you create the resource in the Azure portal, come back here and select **Refresh**.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ApplicationInsightsWebTestName"::: -->
:::moniker range="<=azure-pipelines"

**`ApplicationInsightsWebTestName`** - **Application Insights web test name**<br>
`string`. Optional. Use when `Action == Enable Continuous Monitoring`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Enters the Application Insights web test name you want to create or update.

If you don't provide a web test name, the default test name is used.
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

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="LocalPathsForInstalledExtensions"::: -->
**`LocalPathsForInstalledExtensions`**<br><!-- :::editable-content name="Value"::: -->
This input is the local installation paths for the extensions you select.

If you select multiple extensions, the output is a comma-separated list of local paths for each of the extensions you select. The output lists the paths in the order they appear in the Install Extensions field.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to start, stop, restart, slot swap, Swap with Preview, install site extensions, or enable continuous monitoring for an Azure App Service.

### What happens during a swap

When you swap two slots (usually from a staging slot into the production slot), make sure that the production slot is always the target slot. This way, the swap operation doesn't affect your production app.

Also at any point of the swap (or swap with preview) operation, all work of initializing the swapped apps happens on the source slot. The target slot remains online while the source slot is being prepared and warmed up, regardless of where the swap succeeds or fails.

For more information, see [Set up staging environments in Azure App Service](/azure/app-service/deploy-staging-slots#AboutConfiguration).
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
| Agent version |  1.102.0 or greater |
| Task category | Deploy |

:::moniker-end

<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->