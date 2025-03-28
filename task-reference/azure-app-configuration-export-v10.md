---
title: AzureAppConfigurationExport@10 - Azure App Configuration Export v10 task
description: Export key-values to task variables from Azure App Configuration.
ms.date: 03/28/2025
monikerRange: "=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# AzureAppConfigurationExport@10 - Azure App Configuration Export v10 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Export key-values from Azure App Configuration to task variables in your build or deployment pipelines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure App Configuration Export v10
# Export key-values to task variables from Azure App Configuration.
- task: AzureAppConfigurationExport@10
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    AppConfigurationEndpoint: # string. Required. App Configuration Endpoint. 
    #SelectionMode: 'Default' # 'Default' | 'Snapshot'. Selection Mode. Default: Default.
    KeyFilter: '*' # string. Required when SelectionMode = Default. Key Filter. Default: *.
    #Label: # string. Optional. Use when SelectionMode = Default. Label. 
    #SnapshotName: # string. Required when SelectionMode = Snapshot. Snapshot name. 
    #TrimKeyPrefix: # string. Trim Key Prefix. 
    #SuppressWarningForOverriddenKeys: false # boolean. Suppress warning for overridden keys. Default: false.
    #TreatKeyVaultErrorsAsWarning: false # boolean. Treat key vault resolution errors as warnings. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
[Input alias](index.md#what-are-task-input-aliases): `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Subscription for the Azure App Configuration instance.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppConfigurationEndpoint"::: -->
:::moniker range="=azure-pipelines"

**`AppConfigurationEndpoint`** - **App Configuration Endpoint**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the endpoint of an existing [Azure App Configuration](/azure/azure-app-configuration/concept-key-value).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SelectionMode"::: -->
:::moniker range="=azure-pipelines"

**`SelectionMode`** - **Selection Mode**<br>
`string`. Allowed values: `Default`, `Snapshot`. Default value: `Default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selection mode specifies how the key-values read from a configuration store are selected. The `Default` selection mode allows the use of key and label filters. The `Snapshot` selection mode allows key-values to be selected from a snapshot.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="KeyFilter"::: -->
:::moniker range="=azure-pipelines"

**`KeyFilter`** - **Key Filter**<br>
`string`. Required when `SelectionMode = Default`. Default value: `*`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The filter can be used to select what key-values are requested from Azure App Configuration. A value of `*` will select all key-values. [Reference for key-values query](/azure/azure-app-configuration/concept-key-value#query-key-values).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Label"::: -->
:::moniker range="=azure-pipelines"

**`Label`** - **Label**<br>
`string`. Optional. Use when `SelectionMode = Default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies which label should be used when selecting key-values from App Configuration. If no label is provided then key-values with the _null_ label will be retrieved. The following characters are not allowed: `,` `*`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SnapshotName"::: -->
:::moniker range="=azure-pipelines"

**`SnapshotName`** - **Snapshot name**<br>
`string`. Required when `SelectionMode = Snapshot`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies snapshot from which key-values should be retrieved in Azure App Configuration.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TrimKeyPrefix"::: -->
:::moniker range="=azure-pipelines"

**`TrimKeyPrefix`** - **Trim Key Prefix**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies one or more prefixes that should be trimmed from App Configuration keys before setting them as variables. Multiple prefixes can be separated by a new-line character.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SuppressWarningForOverriddenKeys"::: -->
:::moniker range="=azure-pipelines"

**`SuppressWarningForOverriddenKeys`** - **Suppress warning for overridden keys**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether or not to suppress the warning shown when existing keys are overridden.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TreatKeyVaultErrorsAsWarning"::: -->
:::moniker range="=azure-pipelines"

**`TreatKeyVaultErrorsAsWarning`** - **Treat key vault resolution errors as warnings**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether to display key vault resolution errors as warning. By default, the task fails when encountering key vault resolution errors.
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
| Agent version |  2.144.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->