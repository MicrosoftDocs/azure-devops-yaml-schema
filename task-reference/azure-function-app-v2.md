---
title: AzureFunctionApp@2 - Azure Functions Deploy v2 task
description: Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
ms.date: 07/10/2023
monikerRange: "=azure-pipelines"
---

# AzureFunctionApp@2 - Azure Functions Deploy v2 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure Functions Deploy v2
# Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
- task: AzureFunctionApp@2
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    appType: # 'functionApp' | 'functionAppLinux'. Required. App type. 
    appName: # string. Required. Azure Functions App name. 
    #deployToSlotOrASE: false # boolean. Optional. Use when appType != "". Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: production.
    package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #runtimeStack: # 'DOTNET|2.2' | 'DOTNET|3.1' | 'DOTNET|6.0' | 'DOTNET-ISOLATED|7.0' | 'JAVA|8' | 'JAVA|11' | 'NODE|8' | 'NODE|10' | 'NODE|12' | 'NODE|14' | 'NODE|16' | 'NODE|18' | 'PYTHON|3.6' | 'PYTHON|3.7' | 'PYTHON|3.8' | 'PYTHON|3.9' | 'PYTHON|3.10'. Optional. Use when appType = functionAppLinux. Runtime stack. 
  # Application and Configuration Settings
    #appSettings: # string. App settings. 
  # Additional Deployment Options
    #deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required when appType != "" && package NotEndsWith .war && Package NotEndsWith .jar. Deployment method. Default: auto.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the Azure Resource Manager subscription for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appType"::: -->
:::moniker range="=azure-pipelines"

**`appType`** - **App type**<br>
`string`. Required. Allowed values: `functionApp` (Function App on Windows), `functionAppLinux` (Function App on Linux).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Function App type for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appName"::: -->
:::moniker range="=azure-pipelines"

**`appName`** - **Azure Functions App name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters or selects the name of an existing Azure Functions App. The Function Apps listed will be based on the selected app type.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployToSlotOrASE"::: -->
:::moniker range="=azure-pipelines"

**`deployToSlotOrASE`** - **Deploy to Slot or App Service Environment**<br>
`boolean`. Optional. Use when `appType != ""`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Deploys to an existing deployment slot or Azure App Service Environment. For both targets, the task needs a Resource group name.

If the deployment target is a slot, it will default to the **production** slot. Any other existing slot name can also be provided.

If the deployment target is an Azure App Service Environment, leave the slot name as **production** and specify the Resource group name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range="=azure-pipelines"

**`resourceGroupName`** - **Resource group**<br>
`string`. Required when `deployToSlotOrASE = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Resource group name is required when the deployment target is either a deployment slot or an App Service Environment. 

Enters or selects the Azure Resource group that contains the Azure App Service specified above.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="slotName"::: -->
:::moniker range="=azure-pipelines"

**`slotName`** - **Slot**<br>
`string`. Required when `deployToSlotOrASE = true`. Default value: `production`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters or selects an existing slot, excluding the Production slot.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="package"::: -->
:::moniker range="=azure-pipelines"

**`package`** - **Package or folder**<br>
`string`. Required. Default value: `$(System.DefaultWorkingDirectory)/**/*.zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file path to the package or folder that contains App Service content generated by MSBuild or a compressed zip file. Variables ( [Build](/azure/devops/pipelines/build/variables) | [Release](/azure/devops/pipelines/release/variables#default-variables)) and wildcards are supported. For example, `$(System.DefaultWorkingDirectory)/**/*.zip`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runtimeStack"::: -->
:::moniker range="=azure-pipelines"

**`runtimeStack`** - **Runtime stack**<br>
`string`. Optional. Use when `appType = functionAppLinux`. Allowed values: `DOTNET|2.2` (DOTNET|2.2 (functionapp v2)), `DOTNET|3.1` (DOTNET|3.1 (functionapp v3)), `DOTNET|6.0` (DOTNET|6.0 (functionapp v4)), `DOTNET-ISOLATED|7.0` (DOTNET-ISOLATED|7.0 (functionapp v4)), `JAVA|8` (JAVA|8 (functionapp v2/v3/v4)), `JAVA|11` (JAVA|11  (functionapp v3/v4)), `NODE|8` (NODE|8 (functionapp v2)), `NODE|10` (NODE|10 (functionapp v2/v3)), `NODE|12` (NODE|12 (functionapp v3)), `NODE|14` (NODE|14 (functionapp v3/v4)), `NODE|16` (NODE|16 (functionapp v4)), `NODE|18` (NODE|18 (functionapp v4)), `PYTHON|3.6` (PYTHON|3.6 (functionapp v2/v3)), `PYTHON|3.7` (PYTHON|3.7 (functionapp v2/v3/v4)), `PYTHON|3.8` (PYTHON|3.8 (functionapp v3/v4)), `PYTHON|3.9` (PYTHON|3.9 (functionapp v3/v4)), `PYTHON|3.10` (PYTHON|3.10 (functionapp v3/v4)).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Learn about [supported runtime versions](/azure/azure-functions/functions-versions#languages).  Old values like `DOCKER|microsoft/azure-functions-*` are deprecated. New values are listed in the dropdown menu.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSettings"::: -->
:::moniker range="=azure-pipelines"

**`appSettings`** - **App settings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the application settings using the syntax `-key value` (for example: `-Port 5000` `-RequestTimeout 5000` `-WEBSITE_TIME_ZONE`). Enclose values that contain spaces in double quotes (for example: `"Eastern Standard Time"`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentMethod"::: -->
:::moniker range="=azure-pipelines"

**`deploymentMethod`** - **Deployment method**<br>
`string`. Required when `appType != "" && package NotEndsWith .war && Package NotEndsWith .jar`. Allowed values: `auto` (Auto-detect), `zipDeploy` (Zip Deploy), `runFromPackage` (Zip Deploy with Run From Package). Default value: `auto`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Chooses the [deployment method](#deployment-methods) for the app.
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

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="AppServiceApplicationUrl"::: -->
**`AppServiceApplicationUrl`**<br><!-- :::editable-content name="Value"::: -->
Application URL of the selected Azure Function App.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

The Azure Function Deployment task is used to update Azure Functions to deploy [Functions](/azure/azure-functions/) to Azure. The task works on cross platform Azure Pipelines agents running Windows, Linux or Mac and uses the underlying deployment technologies of RunFromPackage, Zip Deploy and [Kudu REST APIs](https://github.com/projectkudu/kudu/wiki/REST-API).

The task works for the Azure Functions [supported languages](/azure/azure-functions/supported-languages).

### Pre-requisites for the task

The following pre-requisites need to be setup in the target machine(s) for the task to work properly.

##### Azure Function

The task is used to deploy an Azure Functions project to an existing Azure Function. The Azure Function app should exist prior to running the task. The Azure Function App can be created from the [Azure portal](/azure/azure-functions/functions-create-function-app-portal). Alternatively, the [Azure PowerShell task](azure-powershell-v5.md) can be used to run [AzureRM PowerShell scripts](/powershell/azure/new-azureps-module-az) to provision and configure the Azure Function app.

The task can be used to deploy [Azure Functions](/azure/azure-functions/functions-reference) (Windows/Linux).

##### Azure Subscription

To deploy to Azure, an Azure subscription has to be linked to Azure Pipelines using the Services tab in the Account Administration section. Add the Azure subscription to use in the Build or Release Management definition by opening the Account Administration screen (gear icon on the top-right of the screen) and then click on the Services Tab.

Create the [ARM](/azure/azure-resource-manager/management/overview) service endpoint and use **Azure Resource Manager** endpoint type. For more details, follow the steps listed in the link [here](/azure/devops/pipelines/library/service-endpoints#azure-resource-manager-service-connection).

The task does not work with the Azure Classic service endpoint and it will not list these connections in the parameters in the task.

### Deployment methods

Several deployment methods are available in this task.

To change the package-based deployment option in a designer task, expand **Additional Deployment Options** and enable **Select Deployment Method**.

Based on the type of Azure App Service and Azure Pipelines agent, the task uses a suitable deployment technology. The deployment technologies used by tasks are as follows:

* [Kudu REST API](#kudu-rest-api)
* [Zip Deploy](#zip-deploy)
* [Run From Package](#run-from-package)

By default, the task attempts to select the appropriate deployment technology based on the input package, App Service type, and agent OS.

* If a post-deployment script is provided, use Zip Deploy.
* If the App Service type is Web App on Linux, use Zip Deploy.
* If a .war file is provided, use War Deploy.
* If a .jar file is provided, use Run-From-Zip.
* For all other tasks, use Run From Package (via Zip Deploy).

On a non-Windows agent (for any App Service type), the task relies on the [Kudu REST API](https://github.com/projectkudu/kudu/wiki/REST-API) to deploy the web app.

#### Kudu REST API

The [Kudu REST API](https://github.com/projectkudu/kudu/wiki/REST-API) works on both Windows and Linux automation agents when the target is a Web App on Windows, a Web App on Linux (built-in source), or a function app. The task uses Kudu to copy files to the Azure App Service.

#### Zip Deploy

Zip Deploy creates a .zip deployment package from the chosen package or folder. It then deploys the file contents to the wwwroot folder of the App Service name function app in Azure. This option overwrites all existing content in the wwwroot folder. For more information, see [Zip deployment for Azure Functions](/azure/azure-functions/deployment-zip-push).

#### Run From Package

Run From Package creates the same deployment package as Zip Deploy. Instead of deploying files to the wwwroot folder, the Functions runtime mounts the entire package. When you use this option, files in the wwwroot folder become read-only. For more information, see [Run your Azure Functions from a package file](/azure/azure-functions/run-functions-from-deployment-package).

### Troubleshooting

* To ignore SSL error set a Variable of name VSTS_ARM_REST_IGNORE_SSL_ERRORS with value : true in the release definition.
* The task works with the [Azure Resource Manager APIs](/rest/api/resources) only.
* For avoiding deployment failure with error code ERROR_FILE_IN_USE we recommend defaulting to using the Run From Package option [Run your functions from a package file in Azure](/azure/azure-functions/run-functions-from-deployment-package). For zero downtime deployment use slot swap.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

Here's a sample YAML snippet that deploys Azure functions on Windows:
```YAML

variables:
  azureSubscription: Contoso
  # To ignore SSL error, uncomment the below variable
  # VSTS_ARM_REST_IGNORE_SSL_ERRORS: true

steps:
- task: AzureFunctionApp@2
  displayName: Azure Function App Deploy
  inputs:
    azureSubscription: $(azureSubscription)
    appName: samplefunctionapp
    appType: functionApp
    package: $(System.DefaultWorkingDirectory)/**/*.zip
```
To deploy a function on Linux, add the `appType` parameter and set it to `appType: functionAppLinux`. If you don't specify a value, `functionApp` is the default.

To explicitly specify the deployment method as Zip Deploy, add the parameter `deploymentMethod: zipDeploy`. Another supported value for this parameter is `runFromPackage`.
If you don't specify a value, `auto` is the default.

For a walkthrough that shows how to create a CI/CD pipeline, see [Build and deploy Java to Azure Functions](/azure/azure-functions/functions-how-to-azure-devops).
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
| Agent version |  2.104.1 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
