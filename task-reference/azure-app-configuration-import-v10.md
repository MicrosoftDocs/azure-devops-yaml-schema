---
title: AzureAppConfigurationImport@10 - Azure App Configuration Import v10 task
description: Import key-values to an Azure App Configuration instance.
ms.date: 10/11/2024
monikerRange: "=azure-pipelines"
---

# AzureAppConfigurationImport@10 - Azure App Configuration Import v10 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Import key-values to an Azure App Configuration instance.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure App Configuration Import v10
# Import key-values to an Azure App Configuration instance.
- task: AzureAppConfigurationImport@10
  inputs:
  # AppConfiguration
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    AppConfigurationEndpoint: # string. Required. App Configuration Endpoint. 
  # Source
    ConfigurationFile: # string. Required. Configuration File Path. 
    #UseFilePathExtension: true # boolean. Use the file path extension to determine the file format. Default: true.
    #FileFormat: # 'json' | 'yaml' | 'properties'. Optional. Use when UseFilePathExtension = false. File Format. 
  # Options
    #FileContentProfile: 'appconfig/default' # 'appconfig/default' | 'appconfig/kvset'. File Content Profile. Default: appconfig/default.
    #Separator: # '.' | '/' | ':' | ';' | ' |' | '-' | '_' | '__'. Optional. Use when FileContentProfile is appconfig/default. Separator. 
    #Depth: # string. Optional. Use when FileContentProfile is appconfig/default. Depth. 
    #Prefix: # string. Optional. Use when FileContentProfile is appconfig/default. Prefix. 
    #Label: # string. Optional. Use when FileContentProfile is appconfig/default. Label. 
    #ContentType: # string. Optional. Use when FileContentProfile is appconfig/default. Content Type. 
    #Tags: # string. Optional. Use when FileContentProfile is appconfig/default. Tags. 
    #ExcludeFeatureFlags: false # boolean. Optional. Use when FileContentProfile is appconfig/default. Exclude feature flags. Default: false.
    #Strict: false # boolean. Delete key-values that are not included in the configuration file. Default: false.
    #DryRun: false # boolean. Dry run. Default: false.
    #ImportMode: 'Ignore-Match' # 'All' | 'Ignore-Match'. Import Mode. Default: Ignore-Match.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `ConnectedServiceName`. `string`. Required.<br>
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
<!-- :::item name="ConfigurationFile"::: -->
:::moniker range="=azure-pipelines"

**`ConfigurationFile`** - **Configuration File Path**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the configuration file (supported: yaml, json, properties).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="UseFilePathExtension"::: -->
:::moniker range="=azure-pipelines"

**`UseFilePathExtension`** - **Use the file path extension to determine the file format**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether or not to use the file path extension to determine the file format.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="FileFormat"::: -->
:::moniker range="=azure-pipelines"

**`FileFormat`** - **File Format**<br>
`string`. Optional. Use when `UseFilePathExtension = false`. Allowed values: `json`, `yaml`, `properties`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The configuration file format. If no format is provided, then the format defaults to the file extension of the configuration file provided.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="FileContentProfile"::: -->
:::moniker range="=azure-pipelines"

**`FileContentProfile`** - **File Content Profile**<br>
`string`. Allowed values: `appconfig/default` (Default), `appconfig/kvset` (KVSet). Default value: `appconfig/default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The configuration file's [content profile](/azure/azure-app-configuration/concept-config-file).
* Default: Refers to the conventional configuration file formats that are directly consumable by applications.
* KVSet: Refers to a [file schema](https://github.com/Azure/AppConfiguration/blob/main/docs/KVSet/KVSet.v1.0.0.schema.json) that contains all properties of an App Configuration key-value
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Separator"::: -->
:::moniker range="=azure-pipelines"

**`Separator`** - **Separator**<br>
`string`. Optional. Use when `FileContentProfile is appconfig/default`. Allowed values: `.` (.  (Period)), `/` (/  (Forward Slash)), `:` (:  (Colon)), `;` (;  (Semicolon)), `,` (,  (Comma)), `-` (-  (Hyphen)), `_` (_  (Underscore)), `__` (__ (Double Underscore)).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Separator is used to flatten the configuration file (json & yaml files). It is required when the depth provided is greater than 1.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Depth"::: -->
:::moniker range="=azure-pipelines"

**`Depth`** - **Depth**<br>
`string`. Optional. Use when `FileContentProfile is appconfig/default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Depth to flatten to in configuration file (json and yaml files).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Prefix"::: -->
:::moniker range="=azure-pipelines"

**`Prefix`** - **Prefix**<br>
`string`. Optional. Use when `FileContentProfile is appconfig/default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A prefix to append to all keys in the configuration file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Label"::: -->
:::moniker range="=azure-pipelines"

**`Label`** - **Label**<br>
`string`. Optional. Use when `FileContentProfile is appconfig/default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a string that's added to each key-value as the label within the App Configuration store.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ContentType"::: -->
:::moniker range="=azure-pipelines"

**`ContentType`** - **Content Type**<br>
`string`. Optional. Use when `FileContentProfile is appconfig/default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Species a string that is added as the content type to all keys in the configuration file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Tags"::: -->
:::moniker range="=azure-pipelines"

**`Tags`** - **Tags**<br>
`string`. Optional. Use when `FileContentProfile is appconfig/default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies one or more tags that should be added to key-value settings being imported to App Configuration. Tags should be of a valid JSON format and can span multiple lines. Example: `{"tag1": "value1", "tag2": "value2"}`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ExcludeFeatureFlags"::: -->
:::moniker range="=azure-pipelines"

**`ExcludeFeatureFlags`** - **Exclude feature flags**<br>
`boolean`. Optional. Use when `FileContentProfile is appconfig/default`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether or not any feature flags provided in the configuration file will be imported to App Configuration.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Strict"::: -->
:::moniker range="=azure-pipelines"

**`Strict`** - **Delete key-values that are not included in the configuration file**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The behavior of this option depends on the configuration file's [content profile](/azure/azure-app-configuration/concept-config-file).
* When `false`: Imports all key-values from the configuration file into the App Configuration store and leaves everything else in the App Configuration store intact.
* When `true`:
  * `Default`: Any key-values in the store with the specified prefix and label that are not included in the configuration file will be deleted. 
  * `KVSet`: Any key-values in the store that are not included in the configuration file will be deleted.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DryRun"::: -->
:::moniker range="=azure-pipelines"

**`DryRun`** - **Dry run**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When dry run is enabled, this task will not perform any updates to App Configuration. Instead, any updates that would have been performed in a normal run will be printed to the console for review.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ImportMode"::: -->
:::moniker range="=azure-pipelines"

**`ImportMode`** - **Import Mode**<br>
`string`. Allowed values: `All`, `Ignore-Match`. Default value: `Ignore-Match`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Determines the behavior when importing key-values. The default value,'Ignore-Match' will only import settings that have no matching key-value in App Configuration. 'All' will import all key-values in the input file to App Configuration.
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
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->