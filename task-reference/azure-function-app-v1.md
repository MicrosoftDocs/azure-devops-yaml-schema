---
title: AzureFunctionApp@1 - Azure Functions v1 task
description: Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# AzureFunctionApp@1 - Azure Functions v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Deploy an Azure Function for Linux or Windows.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure Functions v1
# Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
- task: AzureFunctionApp@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    appType: # 'functionApp' | 'functionAppLinux'. Required. App type. 
    appName: # string. Required. Azure Functions App name. 
    #deployToSlotOrASE: false # boolean. Optional. Use when appType != "". Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: 'production'.
    package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: '$(System.DefaultWorkingDirectory)/**/*.zip'.
    #runtimeStack: # 'DOTNET|2.2' | 'DOTNET|3.1' | 'DOTNET|6.0' | 'JAVA|8' | 'JAVA|11' | 'NODE|8' | 'NODE|10' | 'NODE|12' | 'NODE|14' | 'NODE|16' | 'PYTHON|3.6' | 'PYTHON|3.7' | 'PYTHON|3.8' | 'PYTHON|3.9'. Optional. Use when appType = functionAppLinux. Runtime stack. 
    #startUpCommand: # string. Optional. Use when appType = functionAppLinux. Startup command. 
  # Application and Configuration Settings
    #customWebConfig: # string. Optional. Use when appType != functionAppLinux && package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings. 
  # Additional Deployment Options
    deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required. Deployment method. Default: 'auto'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2022"

```yaml
# Azure Functions v1
# Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
- task: AzureFunctionApp@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    appType: # 'functionApp' | 'functionAppLinux'. Required. App type. 
    appName: # string. Required. Azure Functions App name. 
    #deployToSlotOrASE: false # boolean. Optional. Use when appType != "". Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: 'production'.
    package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: '$(System.DefaultWorkingDirectory)/**/*.zip'.
    #runtimeStack: # 'DOTNET|2.2' | 'DOTNET|3.1' | 'JAVA|8' | 'JAVA|11' | 'NODE|8' | 'NODE|10' | 'NODE|12' | 'NODE|14' | 'PYTHON|3.6' | 'PYTHON|3.7' | 'PYTHON|3.8'. Optional. Use when appType = functionAppLinux. Runtime stack. 
    #startUpCommand: # string. Optional. Use when appType = functionAppLinux. Startup command. 
  # Application and Configuration Settings
    #customWebConfig: # string. Optional. Use when appType != functionAppLinux && package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings. 
  # Additional Deployment Options
    deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required. Deployment method. Default: 'auto'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

```yaml
# Azure Functions v1
# Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
- task: AzureFunctionApp@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    appType: # 'functionApp' | 'functionAppLinux'. Required. App type. 
    appName: # string. Required. App name. 
    #deployToSlotOrASE: false # boolean. Optional. Use when appType != "". Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: 'production'.
    package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: '$(System.DefaultWorkingDirectory)/**/*.zip'.
    #runtimeStack: # 'DOTNET|2.2' | 'DOTNET|3.1' | 'JAVA|8' | 'JAVA|11' | 'NODE|8' | 'NODE|10' | 'NODE|12' | 'NODE|14' | 'PYTHON|3.6' | 'PYTHON|3.7' | 'PYTHON|3.8'. Optional. Use when appType = functionAppLinux. Runtime stack. 
    #startUpCommand: # string. Optional. Use when appType = functionAppLinux. Startup command. 
  # Application and Configuration Settings
    #customWebConfig: # string. Optional. Use when appType != functionAppLinux && package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings. 
  # Additional Deployment Options
    deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required. Deployment method. Default: 'auto'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Azure Functions v1
# Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
- task: AzureFunctionApp@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    appType: # 'functionApp' | 'functionAppLinux'. Required. App type. 
    appName: # string. Required. App name. 
    #deployToSlotOrASE: false # boolean. Optional. Use when appType != "". Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: 'production'.
    package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: '$(System.DefaultWorkingDirectory)/**/*.zip'.
    #runtimeStack: # 'DOCKER|microsoft/azure-functions-dotnet-core2.0:2.0' | 'DOCKER|microsoft/azure-functions-node8:2.0'. Optional. Use when appType = functionAppLinux. Runtime stack. 
    #startUpCommand: # string. Optional. Use when appType = functionAppLinux. Startup command. 
  # Application and Configuration Settings
    #customWebConfig: # string. Optional. Use when appType != functionAppLinux && package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings. 
  # Additional Deployment Options
    deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required. Deployment method. Default: 'auto'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Azure Function v1
# Deploy an Azure Function for Linux or Windows.
- task: AzureFunctionApp@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    appType: # 'functionApp' | 'functionAppLinux'. Required. App type. 
    appName: # string. Required. App name. 
    #deployToSlotOrASE: false # boolean. Optional. Use when appType != "". Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: 'production'.
    package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: '$(System.DefaultWorkingDirectory)/**/*.zip'.
    #runtimeStack: # 'DOCKER|microsoft/azure-functions-dotnet-core2.0:2.0' | 'DOCKER|microsoft/azure-functions-node8:2.0'. Optional. Use when appType = functionAppLinux. Runtime stack. 
    #startUpCommand: # string. Optional. Use when appType = functionAppLinux. Startup command. 
  # Application and Configuration Settings
    #customWebConfig: # string. Optional. Use when appType != functionAppLinux && package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings. 
  # Additional Deployment Options
    deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required. Deployment method. Default: 'auto'.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azureSubscription`** - **Azure subscription**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription for the deployment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appType`** - **App type**<br>
Type: string. Required. Allowed values: 'functionApp', 'functionAppLinux'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appName"::: -->
:::moniker range=">=azure-pipelines-2022"

**`appName`** - **Azure Functions App name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter or Select the name of an existing Azure Functions App. The Function Apps listed will be based on the selected app type.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

**`appName`** - **App name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter or Select the name of an existing Azure Functions App. The Function Apps listed will be based on the selected app type.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployToSlotOrASE"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deployToSlotOrASE`** - **Deploy to Slot or App Service Environment**<br>
Type: boolean. Optional. Use when appType != "". Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to deploy to an existing deployment slot or Azure App Service Environment.<br />For both the targets, the task needs Resource group name.<br />In case the deployment target is a slot, by default the deployment is done to the production slot. Any other existing slot name can also be provided.<br />In case the deployment target is an Azure App Service environment, leave the slot name as ‘production’ and just specify the Resource group name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`resourceGroupName`** - **Resource group**<br>
Type: string. Required when deployToSlotOrASE = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Resource group name is required when the deployment target is either a deployment slot or an App Service Environment.<br />Enter or Select the Azure Resource group that contains the Azure App Service specified above.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="slotName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`slotName`** - **Slot**<br>
Type: string. Required when deployToSlotOrASE = true. Default value: 'production'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter or Select an existing Slot other than the Production slot.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="package"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`package`** - **Package or folder**<br>
Type: string. Required. Default value: '$(System.DefaultWorkingDirectory)/**/*.zip'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File path to the package or a folder containing app service contents generated by MSBuild or a compressed zip or war file.<br />Variables ( [Build](/azure/devops/pipelines/build/variables) | [Release](/azure/devops/pipelines/release/variables#default-variables)), wildcards are supported. <br/> For example, $(System.DefaultWorkingDirectory)/\*\*/\*.zip or $(System.DefaultWorkingDirectory)/\*\*/\*.war.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runtimeStack"::: -->
:::moniker range="=azure-pipelines"

**`runtimeStack`** - **Runtime stack**<br>
Type: string. Optional. Use when appType = functionAppLinux. Allowed values: 'DOTNET|2.2', 'DOTNET|3.1', 'DOTNET|6.0', 'JAVA|8', 'JAVA|11', 'NODE|8', 'NODE|10', 'NODE|12', 'NODE|14', 'NODE|16', 'PYTHON|3.6', 'PYTHON|3.7', 'PYTHON|3.8', 'PYTHON|3.9'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Refer [this doc](/azure/azure-functions/functions-versions#languages) for supported runtime versions.  Old values like `DOCKER|microsoft/azure-functions-*` are deprecated, please use the new values from dropdown.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2020.1 <=azure-pipelines-2022"

**`runtimeStack`** - **Runtime stack**<br>
Type: string. Optional. Use when appType = functionAppLinux. Allowed values: 'DOTNET|2.2', 'DOTNET|3.1', 'JAVA|8', 'JAVA|11', 'NODE|8', 'NODE|10', 'NODE|12', 'NODE|14', 'PYTHON|3.6', 'PYTHON|3.7', 'PYTHON|3.8'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Refer [this doc](/azure/azure-functions/functions-versions#languages) for supported runtime versions.  Old values like `DOCKER|microsoft/azure-functions-*` are deprecated, please use the new values from dropdown.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

**`runtimeStack`** - **Runtime stack**<br>
Type: string. Optional. Use when appType = functionAppLinux. Allowed values: 'DOCKER|microsoft/azure-functions-dotnet-core2.0:2.0', 'DOCKER|microsoft/azure-functions-node8:2.0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Refer [this doc](/azure/azure-functions/functions-versions#languages) for supported runtime versions.  Old values like `DOCKER|microsoft/azure-functions-*` are deprecated, please use the new values from dropdown.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="startUpCommand"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`startUpCommand`** - **Startup command**<br>
Type: string. Optional. Use when appType = functionAppLinux.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the start up command. For ex.<br/>dotnet run<br/>dotnet filename.dll.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customWebConfig"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`customWebConfig`** - **Generate web.config parameters for Python, Node.js, Go and Java apps**<br>
Type: string. Optional. Use when appType != functionAppLinux && package NotEndsWith .war.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A standard Web.config will be generated and deployed to Azure App Service if the application does not have one. The values in web.config can be edited and vary based on the application framework. For example for node.js application, web.config will have startup file and iis_node module values. This edit feature is only for the generated web.config. [Learn more](https://go.microsoft.com/fwlink/?linkid=843469).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSettings"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appSettings`** - **App settings**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edit web app application settings following the syntax -key value . Value containing spaces should be enclosed in double quotes.<br /> <b>Example</b> : -Port 5000 -RequestTimeout 5000 <br /> -WEBSITE_TIME_ZONE "Eastern Standard Time".
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configurationStrings"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`configurationStrings`** - **Configuration settings**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edit web app configuration settings following the syntax -key value. Value containing spaces should be enclosed in double quotes.<br /> Example : -phpVersion 5.6 -linuxFxVersion: node|6.11.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentMethod"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deploymentMethod`** - **Deployment method**<br>
Type: string. Required. Allowed values: 'auto', 'zipDeploy', 'runFromPackage'. Default value: 'auto'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose the deployment method for the app.
<!-- :::editable-content-end::: -->

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