---
title: AzureAppServiceSettings@1 - Azure App Service Settings v1 task
description: Update/Add App settings an Azure Web App for Linux or Windows.
ms.date: 09/08/2023
monikerRange: ">=azure-pipelines-2020"
---

# AzureAppServiceSettings@1 - Azure App Service Settings v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Updates or adds app service settings in an Azure Web App for Linux or Windows.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Azure App Service Settings v1
# Update/Add App settings an Azure Web App for Linux or Windows.
- task: AzureAppServiceSettings@1
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    appName: # string. Required. App Service name. 
    resourceGroupName: # string. Required. Resource group. 
    #slotName: 'production' # string. Slot. Default: production.
  # Application and Configuration Settings
    #appSettings: # string. App settings. 
    #generalSettings: # string. General settings. 
    #connectionStrings: # string. Connection Strings.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2020"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the Azure Resource Manager subscription.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`appName`** - **App Service name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters or selects the name of an existing Azure App Service.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`resourceGroupName`** - **Resource group**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters or selects the Azure Resource Group that contains the Azure App Service specified above.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="slotName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`slotName`** - **Slot**<br>
`string`. Default value: `production`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters or selects an existing slot. If you don't select a slot, changes are made to production.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSettings"::: -->
:::moniker range=">=azure-pipelines-2020"

**`appSettings`** - **App settings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Application settings in JSON syntax. Enclose values containing spaces in double quotes. For more information, see [Configure app settings](/azure/app-service/configure-common?tabs=portal#configure-app-settings).

The following is an example of the JSON syntax:

```json
[
   {
    "name": "key1",
    "value": "valueabcd",
    "slotSetting": false
   },
   {
    "name": "key2",
    "value": "valueefgh",
    "slotSetting": true
   }
]
```
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="generalSettings"::: -->
:::moniker range=">=azure-pipelines-2020"

**`generalSettings`** - **General settings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
General settings in JSON syntax. Enclose values containing spaces in double quotes. For a list of the available properties, see the [App Service SiteConfig object documentation](/azure/templates/microsoft.web/sites). For more information, see [Configure general settings](/azure/app-service/configure-common#configure-general-settings).

The following is an example of the JSON syntax:

```json
[
   {
    "alwaysOn": true,
    "webSocketsEnabled": false
   }
]
```
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="connectionStrings"::: -->
:::moniker range=">=azure-pipelines-2020"

**`connectionStrings`** - **Connection Strings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Connection strings in JSON syntax. Enclose values containing spaces in double quotes. For more information, see [Configure connection strings](/azure/app-service/configure-common#configure-connection-strings).

The following is an example of the JSON syntax:

```json
[
   {
    "name": "key1",
    "value": "valueabcd",
    "type": "MySql",
    "slotSetting": false
   },
   {
    "name": "key2",
    "value": "valueefgh",
    "type": "Custom",
    "slotSetting": true
   }
]
```
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
## Remarks

Use this task to configure App settings, connection strings and other general settings in bulk using JSON syntax on your web app or any of its deployment slots. 
The task works on cross platform Azure Pipelines agents running Windows, Linux or Mac.
The task works for ASP.NET, ASP.NET Core, PHP, Java, Python, Go and Node.js based web applications.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

The following example YAML snippet deploys a web application to an Azure Web App service running on windows.

```YAML

variables:
  azureSubscription: Contoso
  WebApp_Name: sampleWebApp
  # To ignore SSL error uncomment the below variable
  # VSTS_ARM_REST_IGNORE_SSL_ERRORS: true

steps:

- task: AzureWebApp@1
  displayName: Azure Web App Deploy
  inputs:
    azureSubscription: $(azureSubscription)
    appName: $(WebApp_Name)
    package: $(System.DefaultWorkingDirectory)/**/*.zip

- task: AzureAppServiceSettings@1
  displayName: Azure App Service Settings
  inputs:
    azureSubscription: $(azureSubscription)
    appName: $(WebApp_Name)
   # To deploy the settings on a slot, provide slot name as below. By default, the settings would be applied to the actual Web App (Production slot)
   # slotName: staging
    appSettings: |
      [
        {
          "name": "APPINSIGHTS_INSTRUMENTATIONKEY",
          "value": "$(Key)",
          "slotSetting": false
        },
        {
          "name": "MYSQL_DATABASE_NAME",
          "value": "$(DB_Name)", 
          "slotSetting": false
        }
      ]
    generalSettings: |
      [
        {
          "alwaysOn": true,
          "webSocketsEnabled": false
        }
      ]
    connectionStrings: |
      [
        {
          "name": "MysqlCredentials",
          "value": "$(MySQl_ConnectionString)",
          "type": "MySql",
          "slotSetting": false
        }
      ]

```
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
| Agent version |  2.104.1 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->