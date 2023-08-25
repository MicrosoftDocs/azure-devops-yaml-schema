---
title: AzureWebApp@1 - Azure Web App v1 task
description: Deploy an Azure Web App for Linux or Windows.
ms.date: 08/25/2023
monikerRange: ">=azure-pipelines-2019.1"
---

# AzureWebApp@1 - Azure Web App v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
This task deploys an Azure Web App for Linux or Windows.
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
    #deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required when appType != webAppLinux && appType != "" && package NotEndsWith .war && package NotEndsWith .jar. Deployment method. Default: auto.
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
    #deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required when appType != webAppLinux && appType != "" && package NotEndsWith .war && package NotEndsWith .jar. Deployment method. Default: auto.
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
Specifies the [Azure Resource Manager subscription connection](/azure/devops/pipelines/library/connect-to-azure) for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appType`** - **App type**<br>
`string`. Required. Allowed values: `webApp` (Web App on Windows), `webAppLinux` (Web App on Linux).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure Web App type.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appName`** - **App name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of an existing Azure App Service. Only app services that are based on the selected app type will be listed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployToSlotOrASE"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deployToSlotOrASE`** - **Deploy to Slot or App Service Environment**<br>
`boolean`. Optional. Use when `appType != ""`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the option to deploy to an existing deployment slot or an Azure App Service Environment.  
For both targets, the task needs a resource group name.  
If the deployment target is a slot, the default is the production slot. Any other existing slot name can also be provided.  
If the deployment target is an Azure App Service Environment, leave the slot name as ‘production’, and specify the resource group name.
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
<!-- :::item name="package"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`package`** - **Package or folder**<br>
`string`. Required. Default value: `$(System.DefaultWorkingDirectory)/**/*.zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file path to the package or folder that contains App Service content generated by MSBuild, a compressed zip file, or a war file. Variables ( [Build](/azure/devops/pipelines/build/variables) | [Release](/azure/devops/pipelines/release/variables#default-variables)) and wildcards are supported. For example, `$(System.DefaultWorkingDirectory)/**/*.zip` or `$(System.DefaultWorkingDirectory)/**/*.war`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customDeployFolder"::: -->
:::moniker range=">=azure-pipelines-2020"

**`customDeployFolder`** - **Custom Deploy Folder**<br>
`string`. Optional. Use when `package EndsWith .war`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the custom folder name you want to deploy to.  
If the field is empty, the package is deployed to `<appname>.azurewebsites.net/<warpackagename>`.  
If ROOT is entered, the package is deployed to `<appname>.azurewebsited.net`.  
In all other instances, it is deployed to `<appname>.azurewebsited.net/<customWarName>`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runtimeStack"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`runtimeStack`** - **Runtime stack**<br>
`string`. Optional. Use when `appType = webAppLinux`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Web App on Linux offers two different options to publish your application: custom image deployment (Web App for Containers) and app deployment with a built-in platform image (Web App on Linux). This parameter is only available when **Linux Web App** is selected as an app type in the task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="startUpCommand"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`startUpCommand`** - **Startup command**<br>
`string`. Optional. Use when `appType = webAppLinux`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the start up command.  
For example:  
`dotnet run`  
`dotnet filename.dll.`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customWebConfig"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`customWebConfig`** - **Generate web.config parameters for Python, Node.js, Go and Java apps**<br>
`string`. Optional. Use when `appType != webAppLinux && package NotEndsWith .war`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A standard web.config will be generated and deployed to Azure App Service if the application does not have one. The values in web.config vary based on the application framework, and they can be edited. For example, for the node.js application, web.config will have a startup file and iis_node module values. This edit feature is only for the [generated web.config](https://github.com/microsoft/azure-pipelines-tasks/blob/master/Tasks/AzureRmWebAppDeploymentV4/README.md#parameters-of-the-task).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSettings"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appSettings`** - **App settings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the web app application settings using the syntax `-key value` (for example: `-Port 5000` `-RequestTimeout 5000` `-WEBSITE_TIME_ZONE`). Enclose values that contain spaces in double quotes (for example: `"Eastern Standard Time"`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configurationStrings"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`configurationStrings`** - **Configuration settings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the web app configuration settings using the syntax `-key value` (for example: `-phpVersion 5.6` `-linuxFxVersion: node|6.11`). Enclose values that contain spaces in double quotes.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentMethod"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deploymentMethod`** - **Deployment method**<br>
`string`. Required when `appType != webAppLinux && appType != "" && package NotEndsWith .war && package NotEndsWith .jar`. Allowed values: `auto` (Auto-detect), `zipDeploy` (Zip Deploy), `runFromPackage` (Run From Package). Default value: `auto`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose the [deployment method](/azure/devops/pipelines/tasks/deploy/azure-rm-web-app#deployment-methods) for the app. Acceptable values are **auto**, **zipDeploy**, and **runFromPackage**.
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
## Remarks

Use this task to deploy web applications to Azure App Service.

### Deployment methods

Several deployment methods are available in this task. `Auto` is the default option.

To change the package-based deployment option in designer task, expand **Additional Deployment Options** and enable **Select Deployment Method**.

Based on the type of Azure App Service and Azure Pipelines agent, the task chooses a suitable deployment technology. The different deployment technologies used by the task are:

* Kudu REST APIs
* Zip Deploy
* RunFromPackage

By default, the task tries to select the appropriate deployment technology given the input package, app service type, and agent OS.

* When the app service type is Web App on Linux App, use **Zip Deploy**
* If a War file is provided, use **War Deploy**
* If a Jar file is provided, use **Run From Package**
* For all others, use **Run From Zip** (via Zip Deploy)

On a non-Windows agent (for any app service type), the task relies on [Kudu REST APIs](https://github.com/projectkudu/kudu/wiki/REST-API) to deploy the web app.

### Kudu REST APIs

[Kudu REST APIs](https://github.com/projectkudu/kudu/wiki/REST-API) work on Windows or Linux automation agents when the target is Web App on Windows, Web App on Linux (built-in source), or Function App. The task uses Kudu to copy files to the Azure App Service.

### Zip Deploy

Creates a .zip deployment package of the chosen package or folder. The file contents are then deployed to the wwwroot folder of the function app in Azure App Service. This option overwrites all existing contents in the wwwroot folder. For more information, see [Zip deployment for Azure Functions](/azure/azure-functions/deployment-zip-push).

### RunFromPackage

Creates the same deployment package as Zip Deploy. However, instead of deploying files to the wwwroot folder, the entire package is mounted by the Azure Functions runtime. With this option, files in the wwwroot folder become read-only. For more information, see [Run your Azure Functions from a package file](/azure/azure-functions/run-functions-from-deployment-package).

[!INCLUDE [rm-app-service-troubleshoot-shared](includes/rm-app-service-troubleshoot-shared.md)]

[!INCLUDE [rm-webapp-functionapp-troubleshoot-shared.md](includes/rm-webapp-functionapp-troubleshoot-shared.md)]

### Web app deployment on Windows is successful but the app is not working

This may be because web.config is not present in your app. You can either add a web.config file to your source or auto-generate one using **Application and Configuration Settings**.

* Click on the task and go to **Generate web.config parameters for Python, Node.js, Go and Java apps**.

    :::image type="content" source="media/azure-rm-web-app-01.png" alt-text="Screenshot of the Generate web.config parameters dialog.":::

* Click on the more button `...` to edit the parameters.

    :::image type="content" source="media/azure-rm-web-app-deployment-02.png" alt-text="Screenshot of the drop down dialog.":::


* Select your application type from the drop down.
* Click OK. This will populate the web.config parameters required to generate web.config.

### Web app deployment on App Service Environment (ASE) is not working

* Ensure that the Azure DevOps build agent is on the same VNET (subnet can be different) as the Internal Load Balancer (ILB) of  ASE. This will enable the agent to pull code from Azure DevOps and deploy to ASE.
* If you are using Azure DevOps, the agent doesn't need to be accessible from the internet but needs only outbound access to connect to Azure DevOps Service.
* If you are using TFS/Azure DevOps Server deployed in a Virtual Network, the agent can be completely isolated.
* The build agent must be configured with the DNS configuration of the Web App it needs to deploy to. The private resources in the Virtual Network don't have entries in Azure DNS, so this needs to be added to the host's file on the agent machine.
* If a self-signed certificate is used for the ASE configuration, the `-allowUntrusted` option needs to be set in the deploy task for MSDeploy. It is also recommended to set the variable `VSTS_ARM_REST_IGNORE_SSL_ERRORS` to `true`. If a certificate from a certificate authority is used for ASE configuration, this should not be necessary.

[!INCLUDE [rm-app-service-FAQs-shared](includes/rm-app-service-faqs-shared.md)]
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

Following is an example YAML snippet to deploy web application to the Azure Web App Service running on Windows.

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

To deploy Web App on Linux, add the `appType` parameter and set it to `appType: webAppLinux`.

To specify the deployment method as Zip Deploy, add the parameter `deploymentMethod: zipDeploy`. Another supported value for this parameter is `runFromPackage`.

If not specified, `auto` is the default value.
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
