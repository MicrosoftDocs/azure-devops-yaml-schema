---
title: AzureFunctionAppContainer@1 - Azure Functions for container v1 task
description: Update a function app with a Docker container.
ms.date: 12/19/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# AzureFunctionAppContainer@1 - Azure Functions for container v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Update a function app with a Docker container.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Update Function Apps with Docker containers.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Azure Functions for container v1
# Update a function app with a Docker container.
- task: AzureFunctionAppContainer@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    appName: # string. Required. App name. 
    #deployToSlotOrASE: false # boolean. Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: production.
    imageName: # string. Required. Image name. 
    #containerCommand: # string. Startup command. 
  # Application and Configuration Settings
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Azure Function for container v1
# Update Function Apps with Docker containers.
- task: AzureFunctionAppContainer@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    appName: # string. Required. App name. 
    #deployToSlotOrASE: false # boolean. Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: production.
    imageName: # string. Required. Image name. 
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
Selects the [Azure Resource Manager subscription](/azure/devops/pipelines/library/connect-to-azure) for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appName`** - **App name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Function App for Containers.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployToSlotOrASE"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deployToSlotOrASE`** - **Deploy to Slot or App Service Environment**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set this input to `true` to deploy to an existing deployment slot or Azure App Service Environment. The task needs a Resource Group name for both targets. For the deployment slot option, the default deploys to the **production** slot, or you can specify any other existing slot name. If the deployment target is an Azure App Service Environment, leave the slot name as **production** and specify the Resource Group name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`resourceGroupName`** - **Resource group**<br>
`string`. Required when `deployToSlotOrASE = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Resource Group that contains the Function App for Containers.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="slotName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`slotName`** - **Slot**<br>
`string`. Required when `deployToSlotOrASE = true`. Default value: `production`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters or selects an existing slot, excluding the **production** slot.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`imageName`** - **Image name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A globally unique top-level domain name for your specific registry or namespace.

*Note:* A fully qualified image name will be of the format: `<registry or namespace> <repository> <tag>`. For example, `myregistry.azurecr.io/nginx:latest`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerCommand"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`containerCommand`** - **Startup command**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The startup command that executes after deployment. For example, `dotnet run` `dotnet filename.dll.`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSettings"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appSettings`** - **App settings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the application settings using the syntax `-key value` (for example: `-Port 5000` `-RequestTimeout 5000` `-WEBSITE_TIME_ZONE`). Enclose values that contain spaces in double quotes (for example: `"Eastern Standard Time"`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configurationStrings"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`configurationStrings`** - **Configuration settings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the configuration strings using the syntax `-key value` (for example: `-phpVersion 5.6` `-linuxFxVersion: node|6.11`). Enclose values that contain spaces in double quotes.
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
The application URL of the selected App Service.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to deploy an Azure Function on Linux using a [custom image](/azure/azure-functions/functions-create-function-linux-custom-image).

[!INCLUDE [rm-app-service-troubleshoot-shared](includes/rm-app-service-troubleshoot-shared.md)]

[!INCLUDE [rm-app-service-FAQs-shared](includes/rm-app-service-faqs-shared.md)]
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

This example deploys Azure Functions on Linux using containers:

```YAML

variables:
  imageName: contoso.azurecr.io/azurefunctions-containers:$(build.buildId)
  azureSubscription: Contoso
  # To ignore SSL error uncomment the following variable
  # VSTS_ARM_REST_IGNORE_SSL_ERRORS: true

steps:
- task: AzureFunctionAppContainer@1
  displayName: Azure Function App on Container deploy
  inputs:
    azureSubscription: $(azureSubscription)
    appName: functionappcontainers
    imageName: $(imageName)
```
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
