---
title: AzureWebAppContainer@1 - Azure Web App for Containers v1 task
description: Deploy containers to Azure App Service.
ms.date: 11/17/2023
monikerRange: ">=azure-pipelines-2019.1"
---

# AzureWebAppContainer@1 - Azure Web App for Containers v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
This task deploys containers to Azure App Service.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Azure Web App for Containers v1
# Deploy containers to Azure App Service.
- task: AzureWebAppContainer@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    appName: # string. Required. App name. 
    #deployToSlotOrASE: false # boolean. Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: production.
    #containers: # string. Alias: imageName. Image name. 
    #multicontainerConfigFile: # string. Configuration File. 
    #containerCommand: # string. Startup command. 
  # Application and Configuration Settings
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azureSubscription`** - **Azure subscription**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the [Azure Resource Manager subscription](/azure/devops/pipelines/library/connect-to-azure) for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appName`** - **App name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of an existing Azure App Service. Only app services based on the selected app type will be listed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployToSlotOrASE"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deployToSlotOrASE`** - **Deploy to Slot or App Service Environment**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the option to deploy to an existing deployment slot or an Azure App Service Environment.  
For both targets, the task needs a resource group name.  
If the deployment target is a slot, the default is the production slot. Any other existing slot name can also be provided.  
If the deployment target is an Azure App Service Environment, leave the slot name as `production`, and specify the resource group name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`resourceGroupName`** - **Resource group**<br>
`string`. Required when `deployToSlotOrASE = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The resource group name is required when the deployment target is either a deployment slot or an Azure App Service Environment.  
Specifies the Azure resource group that contains the Azure App Service indicated above.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="slotName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`slotName`** - **Slot**<br>
`string`. Required when `deployToSlotOrASE = true`. Default value: `production`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an existing slot, excluding the production slot.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containers"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`containers`** - **Image name**<br>
Input alias: `imageName`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the fully qualified container image name. For example, **myregistry.azurecr.io**/nginx:latest or **python:3.7.2-alpine**/.  
For a multi-container scenario, multiple container image names can be provided.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="multicontainerConfigFile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`multicontainerConfigFile`** - **Configuration File**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path of the Docker-Compose file. Must be a fully qualified path or a path relative to the default working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerCommand"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`containerCommand`** - **Startup command**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the start up command.  
For example:  
`dotnet run`  
`dotnet filename.dll`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSettings"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appSettings`** - **App settings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edits the web app application settings using the syntax -key value (for example: `-Port 5000` `-RequestTimeout 5000` `-WEBSITE_TIME_ZONE`). A value containing spaces should be enclosed in double quotes (for example: `"Eastern Standard Time"`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configurationStrings"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`configurationStrings`** - **Configuration settings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edits the web app application settings using the syntax -key value (for example: `-phpVersion 5.6 -linuxFxVersion: node|6.11`). A value containing spaces should be enclosed in double quotes.
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

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="AppServiceApplicationUrl"::: -->
**`AppServiceApplicationUrl`**<br><!-- :::editable-content name="Value"::: -->
The application URL of the selected Azure App Service.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

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

:::moniker range=">=azure-pipelines-2019.1"

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
