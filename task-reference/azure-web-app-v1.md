---
title: AzureWebApp@1 - Azure Web App v1 task
description: Deploy an Azure Web App for Linux or Windows.
ms.date: 09/26/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# AzureWebApp@1 - Azure Web App v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Deploy an Azure Web App for Linux or Windows.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Azure Web App v1
# Deploy an Azure Web App for Linux or Windows.
- task: AzureWebApp@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    appType: # 'webApp' | 'webAppLinux'. Required. App type. 
    appName: # string. Required. App name. 
    #deployToSlotOrASE: false # boolean. Optional. Use when appType != "". Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: production.
    package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #customDeployFolder: # string. Optional. Use when package EndsWith .war. Custom Deploy Folder. 
    #runtimeStack: # string. Optional. Use when appType = webAppLinux. Runtime stack. 
    #startUpCommand: # string. Optional. Use when appType = webAppLinux. Startup command. 
  # Application and Configuration Settings
    #customWebConfig: # string. Optional. Use when appType != webAppLinux && package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings. 
  # Additional Deployment Options
    deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required. Deployment method. Default: auto.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Azure Web App v1
# Deploy an Azure Web App for Linux or Windows.
- task: AzureWebApp@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    appType: # 'webApp' | 'webAppLinux'. Required. App type. 
    appName: # string. Required. App name. 
    #deployToSlotOrASE: false # boolean. Optional. Use when appType != "". Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: production.
    package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #runtimeStack: # string. Optional. Use when appType = webAppLinux. Runtime stack. 
    #startUpCommand: # string. Optional. Use when appType = webAppLinux. Startup command. 
  # Application and Configuration Settings
    #customWebConfig: # string. Optional. Use when appType != webAppLinux && package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings. 
  # Additional Deployment Options
    deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required. Deployment method. Default: auto.
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
Select the (Azure Resource Manager subscription connection)[/azure/devops/pipelines/library/connect-to-azure] for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appType`** - **App type**<br>
`string`. Required. Allowed values: `webApp` (Web App on Windows), `webAppLinux` (Web App on Linux).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Web App type
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appName`** - **App name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter or select the name of an existing Azure App Service. App services based on selected app type will only be listed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployToSlotOrASE"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deployToSlotOrASE`** - **Deploy to Slot or App Service Environment**<br>
`boolean`. Optional. Use when `appType != ""`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to deploy to an existing deployment slot or Azure App Service Environment.<br />For both the targets, the task needs Resource group name.<br />In case the deployment target is a slot, by default the deployment is done to the production slot. Any other existing slot name can also be provided.<br />In case the deployment target is an Azure App Service environment, leave the slot name as ‘production’ and just specify the Resource group name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`resourceGroupName`** - **Resource group**<br>
`string`. Required when `deployToSlotOrASE = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Resource group name is required when the deployment target is either a deployment slot or an App Service Environment.<br />Enter or select the Azure Resource group that contains the Azure App Service specified above.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="slotName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`slotName`** - **Slot**<br>
`string`. Required when `deployToSlotOrASE = true`. Default value: `production`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter or select an existing slot other than the Production slot.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="package"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`package`** - **Package or folder**<br>
`string`. Required. Default value: `$(System.DefaultWorkingDirectory)/**/*.zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File path to the package or a folder containing app service contents generated by MSBuild or a compressed zip or war file.<br />Variables ( [Build](/azure/devops/pipelines/build/variables) | [Release](/azure/devops/pipelines/release/variables#default-variables)), wildcards are supported. <br/> For example, $(System.DefaultWorkingDirectory)/\*\*/\*.zip or $(System.DefaultWorkingDirectory)/\*\*/\*.war.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customDeployFolder"::: -->
:::moniker range=">=azure-pipelines-2020"

**`customDeployFolder`** - **Custom Deploy Folder**<br>
`string`. Optional. Use when `package EndsWith .war`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify custom folder name you want to deploy to. <br/>If the field is empty, package is deployed to `<appname>.azurewebsites.net/<warpackagename>`<br/> If ROOT is entered, package is deployed to `<appname>.azurewebsited.net` <br/>else it is deployed to `<appname>.azurewebsited.net/<customWarName>`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runtimeStack"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`runtimeStack`** - **Runtime stack**<br>
`string`. Optional. Use when `appType = webAppLinux`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Web App on Linux offers two different options to publish your application, one is custom image deployment (Web App for Containers) and the other is app deployment with a built-in platform image (Web App on Linux). You will see this parameter only when you select **Linux Web App** in the app type selection option in the task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="startUpCommand"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`startUpCommand`** - **Startup command**<br>
`string`. Optional. Use when `appType = webAppLinux`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the start up command. For ex.<br/>dotnet run<br/>dotnet filename.dll.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customWebConfig"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`customWebConfig`** - **Generate web.config parameters for Python, Node.js, Go and Java apps**<br>
`string`. Optional. Use when `appType != webAppLinux && package NotEndsWith .war`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A standard Web.config will be generated and deployed to Azure App Service if the application does not have one. The values in web.config can be edited and vary based on the application framework. For example for node.js application, web.config will have startup file and iis_node module values. This edit feature is only for the generated web.config. [Learn more](https://go.microsoft.com/fwlink/?linkid=843469).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSettings"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appSettings`** - **App settings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edit web app application settings following the syntax -key value . Value containing spaces should be enclosed in double quotes.<br /> <b>Example</b> : -Port 5000 -RequestTimeout 5000 <br /> -WEBSITE_TIME_ZONE "Eastern Standard Time".
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configurationStrings"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`configurationStrings`** - **Configuration settings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edit web app configuration settings following the syntax -key value. Value containing spaces should be enclosed in double quotes.<br /> Example : -phpVersion 5.6 -linuxFxVersion: node|6.11.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentMethod"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deploymentMethod`** - **Deployment method**<br>
`string`. Required. Allowed values: `auto` (Auto-detect), `zipDeploy` (Zip Deploy), `runFromPackage` (Run From Package). Default value: `auto`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose the (deployment method)[/azure/devops/pipelines/tasks/deploy/azure-rm-web-app#deployment-methods] for the app. Acceptable values are **auto**, **zipDeploy**, **runFromPackage**.
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
Application URL of the selected App Service.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to deploy web applications to Azure App Service.

### Deployment methods

Several deployment methods are available in this task. `Auto` is the default option. 

To change the deployment option in designer task, expand Additional Deployment Options and enable **Select deployment method** to choose from additional package-based deployment options.

Based on the type of Azure App Service and Azure Pipelines agent, the task chooses a suitable deployment technology. The different deployment technologies used by the task are:

* Kudu REST APIs
* Zip Deploy
* RunFromPackage

By default the task tries to select the appropriate deployment technology given the input package, app service type and agent OS.

* When the App Service type is Web App on Linux App, use Zip Deploy 
* If War file is provided, use War Deploy 
* If Jar file is provided, use Run From package 
* For all others, use Run From Zip (via Zip Deploy) 

On non-Windows agent (for any App service type), the task relies on [Kudu REST APIs](https://github.com/projectkudu/kudu/wiki/REST-API) to deploy the Web App.

### Kudu REST APIs

* [Kudu REST APIs](https://github.com/projectkudu/kudu/wiki/REST-API)
Works on Windows as well as Linux automation agent when the target is Web App on Windows or Web App on Linux (built-in source) or Function App. The task uses Kudu to copy files to the Azure App service.

### Zip Deploy

Creates a .zip deployment package of the chosen Package or folder and deploys the file contents to the wwwroot folder of the App Service name function app in Azure. This option overwrites all existing contents in the wwwroot folder. For more information, see [Zip deployment for Azure Functions](/azure/azure-functions/deployment-zip-push).

### RunFromPackage

Creates the same deployment package as Zip Deploy. However, instead of deploying files to the wwwroot folder, the entire package is mounted by the Functions runtime. With this option, files in the wwwroot folder become read-only. For more information, see [Run your Azure Functions from a package file](/azure/azure-functions/run-functions-from-deployment-package).

[!INCLUDE [rm-app-service-troubleshoot-shared](includes/rm-app-service-troubleshoot-shared.md)]

[!INCLUDE [rm-webapp-functionapp-troubleshoot-shared.md](includes/rm-webapp-functionapp-troubleshoot-shared.md)]

### Web app deployment on Windows is successful but the app is not working

This may be because web.config is not present in your app. You can either add a web.config file to your source or auto-generate one using the Application and Configuration Settings of the task.

* Click on the task and go to Generate web.config parameters for Python, Node.js, Go and Java apps.

    :::image type="content" source="media/azure-rm-web-app-01.png" alt-text="Screenshpt of Generate web.config parameters dialog.":::

* Click on the more button Generate web.config parameters for Python, Node.js, Go and Java apps to edit the parameters.

    :::image type="content" source="media/azure-rm-web-app-deployment-02.png" alt-text="Screenshot of drop dow dialog.":::


* Select your application type from the drop down.
* Click on OK. This will populate web.config parameters required to generate web.config.

### Web app deployment on App Service Environment (ASE) is not working

* Ensure that the Azure DevOps build agent is on the same VNET (subnet can be different) as the Internal Load Balancer (ILB) of  ASE. This will enable the agent to pull code from Azure DevOps and deploy to ASE. 
* If you are using Azure DevOps, the agent neednt be accessible from internet but needs only outbound access to connect to Azure DevOps Service. 
* If you are using TFS/Azure DevOps Server deployed in a Virtual Network, the agent can be completely isolated.
* Build agent must be configured with the DNS configuration of the Web App it needs to deploy to. Since the private resources in the Virtual Network don't have entries in Azure DNS, this needs to be added to the hosts file on the agent machine.
* If a self-signed certificate is used for the ASE configuration, "-allowUntrusted" option needs to be set in the deploy task for MSDeploy.It is also recommended to set the variable VSTS_ARM_REST_IGNORE_SSL_ERRORS to true. If a certificate from a certificate authority is used for ASE configuration, this should not be necessary.

[!INCLUDE [rm-app-service-FAQs-shared](includes/rm-app-service-faqs-shared.md)]
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
Following is an example YAML snippet to deploy web application to the Azure Web App service running on Windows.

## Examples

Following is an example YAML snippet to deploy web application to the Azure Web App service running on Windows.

```YAML
variables:
  azureSubscription: Contoso
  # To ignore SSL error uncomment the below variable
  # VSTS_ARM_REST_IGNORE_SSL_ERRORS: true

steps:

- task: AzureWebApp@1
  displayName: Azure Web App Deploy
  inputs:
    azureSubscription: $(azureSubscription)
    appName: samplewebapp
    package: $(System.DefaultWorkingDirectory)/**/*.zip
```

To deploy Web App on Linux, add the appType parameter and set it to `appType: webAppLinux`.

To specify the deployment method as Zip Deploy, add the parameter `deploymentMethod: zipDeploy`. Other supported value for this parameter is `runFromPackage`.

If not specified, `auto` is taken as the default value.
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