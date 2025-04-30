---
title: AzureAppConfigurationSnapshot@1 - Azure App Configuration Snapshot v1 task
description: Create a snapshot in an Azure App Configuration instance.
ms.date: 04/30/2025
monikerRange: "=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# AzureAppConfigurationSnapshot@1 - Azure App Configuration Snapshot v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Create a configuration snapshot in Azure App Configuration through build or deployment pipelines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure App Configuration Snapshot v1
# Create a configuration snapshot in Azure App Configuration through build or deployment pipelines.
- task: AzureAppConfigurationSnapshot@1
  inputs:
  # AppConfiguration
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    AppConfigurationEndpoint: # string. Required. App Configuration Endpoint. 
  # Options
    SnapshotName: # string. Required. Snapshot Name. 
    CompositionType: 'key' # 'key' | 'key_label'. Required. Composition Type. Default: key.
    Filters: # string. Required. Filters for key-values. 
    #RetentionPeriod: '30' # string. Days to retain archived snapshot. Default: 30.
    #Tags: # string. Tags.
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
<!-- :::item name="SnapshotName"::: -->
:::moniker range="=azure-pipelines"

**`SnapshotName`** - **Snapshot Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the snapshot.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CompositionType"::: -->
:::moniker range="=azure-pipelines"

**`CompositionType`** - **Composition Type**<br>
`string`. Required. Allowed values: `key` (Key (default)), `key_label` (Key-Label). Default value: `key`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
* **Key** (`key`): The filters are applied in order for this composition type. Each key value in the snapshot is uniquely identified by the key only. If there are multiple key values with the same key and multiple labels, only one key value will be retained based on the last applicable filter.

* **Key-Label** `(key_label`): Filters will be applied and every key value in the resulting snapshot will be uniquely identified by the key and label together.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Filters"::: -->
:::moniker range="=azure-pipelines"

**`Filters`** - **Filters for key-values**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies snapshot filters that represent the key and label filters used to build an App Configuration snapshot. Filters should be of a valid JSON format. Example `[{"key":"abc*", "label":"1.0.0"}]`. At least 1 filter and max of 3 filters can be applied.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RetentionPeriod"::: -->
:::moniker range="=azure-pipelines"

**`RetentionPeriod`** - **Days to retain archived snapshot**<br>
`string`. Default value: `30`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Archived snapshots can be recovered during the retention period. Choose the number of days the snapshot will be retained after it is archived. The value cannot be changed after creation.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Tags"::: -->
:::moniker range="=azure-pipelines"

**`Tags`** - **Tags**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies one or more tags that should be added to a snapshot. Tags should be of a valid JSON format and can span multiple lines. Example: `{"tag1": "value1", "tag2": "value2"}`.
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
## Remarks

This task is used for creating [snapshots](/azure/azure-app-configuration/concept-snapshots) in a given [App Configuration store](/azure/azure-app-configuration/quickstart-azure-app-configuration-create). A snapshot is a named, immutable subset of an App Configuration store's key-values. The task is node based and works on cross platform Azure Pipelines agents running Windows, Linux or Mac.
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