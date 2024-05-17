---
title: AzureFunctionApp@1 - Azure Functions v1 task
description: Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications (task version 1).
ms.date: 05/17/2024
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
# Azure Functions Deploy v1
# Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
- task: AzureFunctionApp@1
  inputs:
    azureSubscription: # string. Required. Azure Resource Manager connection. 
    appType: # 'functionApp' | 'functionAppLinux'. Required. App type. 
    appName: # string. Required. Azure Functions App name. 
    #deployToSlotOrASE: false # boolean. Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: production.
    package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #runtimeStack: # 'DOTNET|6.0' | 'DOTNET-ISOLATED|6.0' | 'DOTNET-ISOLATED|7.0' | 'DOTNET-ISOLATED|8.0' | 'JAVA|8' | 'JAVA|11' | 'JAVA|17' | 'JAVA|21' | 'NODE|14' | 'NODE|16' | 'NODE|18' | 'NODE|20' | 'PYTHON|3.8' | 'PYTHON|3.9' | 'PYTHON|3.10' | 'PYTHON|3.11'. Optional. Use when appType = functionAppLinux. Runtime stack. 
    #startUpCommand: # string. Optional. Use when appType = functionAppLinux. Startup command. 
  # Application and Configuration Settings
    #customWebConfig: # string. Optional. Use when appType != functionAppLinux && package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings. 
  # Additional Deployment Options
    #deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required when appType != functionAppLinux && appType != "" && package NotEndsWith .war && Package NotEndsWith .jar. Deployment method. Default: auto.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2022.1 <=azure-pipelines-2022.2"

```yaml
# Azure Functions Deploy v1
# Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
- task: AzureFunctionApp@1
  inputs:
    azureSubscription: # string. Required. Azure Resource Manager connection. 
    appType: # 'functionApp' | 'functionAppLinux'. Required. App type. 
    appName: # string. Required. Azure Functions App name. 
    #deployToSlotOrASE: false # boolean. Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: production.
    package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #runtimeStack: # 'DOTNET|2.2' | 'DOTNET|3.1' | 'DOTNET|6.0' | 'JAVA|8' | 'JAVA|11' | 'NODE|8' | 'NODE|10' | 'NODE|12' | 'NODE|14' | 'NODE|16' | 'PYTHON|3.6' | 'PYTHON|3.7' | 'PYTHON|3.8' | 'PYTHON|3.9'. Optional. Use when appType = functionAppLinux. Runtime stack. 
    #startUpCommand: # string. Optional. Use when appType = functionAppLinux. Startup command. 
  # Application and Configuration Settings
    #customWebConfig: # string. Optional. Use when appType != functionAppLinux && package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings. 
  # Additional Deployment Options
    #deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required when appType != functionAppLinux && appType != "" && package NotEndsWith .war && Package NotEndsWith .jar. Deployment method. Default: auto.
```

:::moniker-end

:::moniker range="=azure-pipelines-2022"

```yaml
# Azure Functions Deploy v1
# Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
- task: AzureFunctionApp@1
  inputs:
    azureSubscription: # string. Required. Azure Resource Manager connection. 
    appType: # 'functionApp' | 'functionAppLinux'. Required. App type. 
    appName: # string. Required. Azure Functions App name. 
    #deployToSlotOrASE: false # boolean. Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: production.
    package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #runtimeStack: # 'DOTNET|2.2' | 'DOTNET|3.1' | 'JAVA|8' | 'JAVA|11' | 'NODE|8' | 'NODE|10' | 'NODE|12' | 'NODE|14' | 'PYTHON|3.6' | 'PYTHON|3.7' | 'PYTHON|3.8'. Optional. Use when appType = functionAppLinux. Runtime stack. 
    #startUpCommand: # string. Optional. Use when appType = functionAppLinux. Startup command. 
  # Application and Configuration Settings
    #customWebConfig: # string. Optional. Use when appType != functionAppLinux && package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings. 
  # Additional Deployment Options
    #deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required when appType != functionAppLinux && appType != "" && package NotEndsWith .war && Package NotEndsWith .jar. Deployment method. Default: auto.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

```yaml
# Azure Functions Deploy v1
# Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
- task: AzureFunctionApp@1
  inputs:
    azureSubscription: # string. Required. Azure Resource Manager connection. 
    appType: # 'functionApp' | 'functionAppLinux'. Required. App type. 
    appName: # string. Required. App name. 
    #deployToSlotOrASE: false # boolean. Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: production.
    package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #runtimeStack: # 'DOTNET|2.2' | 'DOTNET|3.1' | 'JAVA|8' | 'JAVA|11' | 'NODE|8' | 'NODE|10' | 'NODE|12' | 'NODE|14' | 'PYTHON|3.6' | 'PYTHON|3.7' | 'PYTHON|3.8'. Optional. Use when appType = functionAppLinux. Runtime stack. 
    #startUpCommand: # string. Optional. Use when appType = functionAppLinux. Startup command. 
  # Application and Configuration Settings
    #customWebConfig: # string. Optional. Use when appType != functionAppLinux && package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings. 
  # Additional Deployment Options
    #deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required when appType != functionAppLinux && appType != "" && package NotEndsWith .war && Package NotEndsWith .jar. Deployment method. Default: auto.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Azure Functions Deploy v1
# Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
- task: AzureFunctionApp@1
  inputs:
    azureSubscription: # string. Required. Azure Resource Manager connection. 
    appType: # 'functionApp' | 'functionAppLinux'. Required. App type. 
    appName: # string. Required. App name. 
    #deployToSlotOrASE: false # boolean. Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: production.
    package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #runtimeStack: # 'DOCKER|microsoft/azure-functions-dotnet-core2.0:2.0' | 'DOCKER|microsoft/azure-functions-node8:2.0'. Optional. Use when appType = functionAppLinux. Runtime stack. 
    #startUpCommand: # string. Optional. Use when appType = functionAppLinux. Startup command. 
  # Application and Configuration Settings
    #customWebConfig: # string. Optional. Use when appType != functionAppLinux && package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings. 
  # Additional Deployment Options
    #deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required when appType != functionAppLinux && appType != "" && package NotEndsWith .war && Package NotEndsWith .jar. Deployment method. Default: auto.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Azure Functions Deploy v1
# Deploy an Azure Function for Linux or Windows.
- task: AzureFunctionApp@1
  inputs:
    azureSubscription: # string. Required. Azure Resource Manager connection. 
    appType: # 'functionApp' | 'functionAppLinux'. Required. App type. 
    appName: # string. Required. App name. 
    #deployToSlotOrASE: false # boolean. Deploy to Slot or App Service Environment. Default: false.
    #resourceGroupName: # string. Required when deployToSlotOrASE = true. Resource group. 
    #slotName: 'production' # string. Required when deployToSlotOrASE = true. Slot. Default: production.
    package: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #runtimeStack: # 'DOCKER|microsoft/azure-functions-dotnet-core2.0:2.0' | 'DOCKER|microsoft/azure-functions-node8:2.0'. Optional. Use when appType = functionAppLinux. Runtime stack. 
    #startUpCommand: # string. Optional. Use when appType = functionAppLinux. Startup command. 
  # Application and Configuration Settings
    #customWebConfig: # string. Optional. Use when appType != functionAppLinux && package NotEndsWith .war. Generate web.config parameters for Python, Node.js, Go and Java apps. 
    #appSettings: # string. App settings. 
    #configurationStrings: # string. Configuration settings. 
  # Additional Deployment Options
    #deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required when appType != functionAppLinux && appType != "" && package NotEndsWith .war && Package NotEndsWith .jar. Deployment method. Default: auto.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azureSubscription`** - **Azure Resource Manager connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the Azure Resource Manager subscription for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`appType`** - **App type**<br>
`string`. Required. Allowed values: `functionApp` (Function App on Windows), `functionAppLinux` (Function App on Linux).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appName"::: -->
:::moniker range=">=azure-pipelines-2022"

**`appName`** - **Azure Functions App name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters or selects the name of an existing Azure Functions App. The Function Apps listed will be based on the selected app type.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

**`appName`** - **App name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters or selects the name of an existing Azure Functions App. The Function Apps listed will be based on the selected app type.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployToSlotOrASE"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deployToSlotOrASE`** - **Deploy to Slot or App Service Environment**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Deploys to an existing deployment slot or Azure App Service Environment. For both targets, the task needs a Resource group name.

If the deployment target is a slot, it will default to the **production** slot. Any other existing slot name can also be provided.

If the deployment target is an Azure App Service Environment, leave the slot name as **production** and specify the Resource group name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

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
:::moniker range=">=azure-pipelines-2019.1"

**`slotName`** - **Slot**<br>
`string`. Required when `deployToSlotOrASE = true`. Default value: `production`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters or selects an existing slot, excluding the Production slot.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="package"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`package`** - **Package or folder**<br>
`string`. Required. Default value: `$(System.DefaultWorkingDirectory)/**/*.zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file path to the package or folder that contains App Service content generated by MSBuild, a compressed zip file, or a war file. Variables ( [Build](/azure/devops/pipelines/build/variables) | [Release](/azure/devops/pipelines/release/variables#default-variables)) and wildcards are supported. For example, `$(System.DefaultWorkingDirectory)/**/*.zip or $(System.DefaultWorkingDirectory)/**/*.war`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runtimeStack"::: -->
:::moniker range="=azure-pipelines"

**`runtimeStack`** - **Runtime stack**<br>
`string`. Optional. Use when `appType = functionAppLinux`. Allowed values: `DOTNET|6.0`, `DOTNET-ISOLATED|6.0`, `DOTNET-ISOLATED|7.0`, `DOTNET-ISOLATED|8.0`, `JAVA|8`, `JAVA|11`, `JAVA|17`, `JAVA|21`, `NODE|14`, `NODE|16`, `NODE|18`, `NODE|20`, `PYTHON|3.8`, `PYTHON|3.9`, `PYTHON|3.10`, `PYTHON|3.11`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the framework and version your function app will run on. You can use any of the [supported runtime versions](/azure/azure-functions/functions-versions#languages). Old values like `DOCKER|microsoft/azure-functions-*` are deprecated. New values are listed in the drop-down list in the [task assistant](/azure/devops/pipelines/get-started/yaml-pipeline-editor#use-task-assistant). If there is a newer version of a framework available in the [supported runtime versions](/azure/azure-functions/functions-versions#languages) you can specify it even if it is not in the list.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2022.2"

**`runtimeStack`** - **Runtime stack**<br>
`string`. Optional. Use when `appType = functionAppLinux`. Allowed values: `DOTNET|2.2` (DOTNET|2.2 (functionapp v2)), `DOTNET|3.1` (DOTNET|3.1 (functionapp v3)), `DOTNET|6.0` (DOTNET|6.0 (functionapp v4)), `JAVA|8` (JAVA|8 (functionapp v2/v3/v4)), `JAVA|11` (JAVA|11  (functionapp v3/v4)), `NODE|8` (NODE|8 (functionapp v2)), `NODE|10` (NODE|10 (functionapp v2/v3)), `NODE|12` (NODE|12 (functionapp v3)), `NODE|14` (NODE|14 (functionapp v3/v4)), `NODE|16` (NODE|16 (functionapp v4)), `PYTHON|3.6` (PYTHON|3.6 (functionapp v2/v3)), `PYTHON|3.7` (PYTHON|3.7 (functionapp v2/v3/v4)), `PYTHON|3.8` (PYTHON|3.8 (functionapp v3/v4)), `PYTHON|3.9` (PYTHON|3.9 (functionapp v3/v4)).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the framework and version your function app will run on. You can use any of the [supported runtime versions](/azure/azure-functions/functions-versions#languages). Old values like `DOCKER|microsoft/azure-functions-*` are deprecated. New values are listed in the drop-down list in the [task assistant](/azure/devops/pipelines/get-started/yaml-pipeline-editor#use-task-assistant). If there is a newer version of a framework available in the [supported runtime versions](/azure/azure-functions/functions-versions#languages) you can specify it even if it is not in the list.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2022.1"

**`runtimeStack`** - **Runtime stack**<br>
`string`. Optional. Use when `appType = functionAppLinux`. Allowed values: `DOTNET|2.2` (DOTNET|2.2 (functionapp v2)), `DOTNET|3.1` (DOTNET|3.1 (functionapp v3)), `DOTNET|6.0` (DOTNET|6.0 (functionapp v4)), `JAVA|8` (JAVA|8 (functionapp v2/v3/v4)), `JAVA|11` (JAVA|11  (functionapp v3/v4)), `NODE|8` (NODE|8 (functionapp v2)), `NODE|10` (NODE|10 (functionapp v2/v3)), `NODE|12` (NODE|12 (functionapp v3)), `NODE|14` (NODE|14 (functionapp v3/v4)), `NODE|16` (NODE|16 (functionapp v4)), `PYTHON|3.6` (PYTHON|3.6 (functionapp v2/v3)), `PYTHON|3.7` (PYTHON|3.7 (functionapp v2/v3/v4)), `PYTHON|3.8` (PYTHON|3.8 (functionapp v3/v4)), `PYTHON|3.9` (PYTHON|3.9 (functionapp v3/v4)).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the framework and version your function app will run on. You can use any of the [supported runtime versions](/azure/azure-functions/functions-versions#languages). Old values like `DOCKER|microsoft/azure-functions-*` are deprecated. New values are listed in the drop-down list in the [task assistant](/azure/devops/pipelines/get-started/yaml-pipeline-editor#use-task-assistant). If there is a newer version of a framework available in the [supported runtime versions](/azure/azure-functions/functions-versions#languages) you can specify it even if it is not in the list.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2020.1 <=azure-pipelines-2022"

**`runtimeStack`** - **Runtime stack**<br>
`string`. Optional. Use when `appType = functionAppLinux`. Allowed values: `DOTNET|2.2` (DOTNET|2.2 (functionapp v2)), `DOTNET|3.1` (DOTNET|3.1 (functionapp v3)), `JAVA|8` (JAVA|8 (functionapp v2/v3)), `JAVA|11` (JAVA|11  (functionapp v3)), `NODE|8` (NODE|8 (functionapp v2)), `NODE|10` (NODE|10 (functionapp v2/v3)), `NODE|12` (NODE|12 (functionapp v3)), `NODE|14` (NODE|14 (functionapp v3)), `PYTHON|3.6` (PYTHON|3.6 (functionapp v2/v3)), `PYTHON|3.7` (PYTHON|3.7 (functionapp v2/v3)), `PYTHON|3.8` (PYTHON|3.8 (functionapp v3)).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the framework and version your function app will run on. You can use any of the [supported runtime versions](/azure/azure-functions/functions-versions#languages). Old values like `DOCKER|microsoft/azure-functions-*` are deprecated. New values are listed in the drop-down list in the [task assistant](/azure/devops/pipelines/get-started/yaml-pipeline-editor#use-task-assistant). If there is a newer version of a framework available in the [supported runtime versions](/azure/azure-functions/functions-versions#languages) you can specify it even if it is not in the list.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

**`runtimeStack`** - **Runtime stack**<br>
`string`. Optional. Use when `appType = functionAppLinux`. Allowed values: `DOCKER|microsoft/azure-functions-dotnet-core2.0:2.0` (.NET), `DOCKER|microsoft/azure-functions-node8:2.0` (JavaScript).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the framework and version your function app will run on. You can use any of the [supported runtime versions](/azure/azure-functions/functions-versions#languages). Old values like `DOCKER|microsoft/azure-functions-*` are deprecated. New values are listed in the drop-down list in the [task assistant](/azure/devops/pipelines/get-started/yaml-pipeline-editor#use-task-assistant). If there is a newer version of a framework available in the [supported runtime versions](/azure/azure-functions/functions-versions#languages) you can specify it even if it is not in the list.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="startUpCommand"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`startUpCommand`** - **Startup command**<br>
`string`. Optional. Use when `appType = functionAppLinux`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters the start up command. For example:

`dotnet run`  
`dotnet filename.dll`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customWebConfig"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`customWebConfig`** - **Generate web.config parameters for Python, Node.js, Go and Java apps**<br>
`string`. Optional. Use when `appType != functionAppLinux && package NotEndsWith .war`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A standard Web.config will be generated and deployed to Azure App Service if the application does not have one. The values in web.config vary based on the application framework, and they can be edited. For example, for the node.js application, web.config will have a startup file and iis_node module values. This edit feature is only for the [generated web.config](https://github.com/microsoft/azure-pipelines-tasks/blob/master/Tasks/AzureRmWebAppDeploymentV4/README.md#parameters-of-the-task).
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
<!-- :::item name="deploymentMethod"::: -->
:::moniker range=">=azure-pipelines-2022"

**`deploymentMethod`** - **Deployment method**<br>
`string`. Required when `appType != functionAppLinux && appType != "" && package NotEndsWith .war && Package NotEndsWith .jar`. Allowed values: `auto` (Auto-detect), `zipDeploy` (Zip Deploy), `runFromPackage` (Zip Deploy with Run From Package). Default value: `auto`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Chooses the [deployment method](#deployment-methods) for the app.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

**`deploymentMethod`** - **Deployment method**<br>
`string`. Required when `appType != functionAppLinux && appType != "" && package NotEndsWith .war && Package NotEndsWith .jar`. Allowed values: `auto` (Auto-detect), `zipDeploy` (Zip Deploy), `runFromPackage` (Run From Package). Default value: `auto`.<br>
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

Use the Azure Function App task to deploy [functions](/azure/azure-functions/) to Azure.

### Deployment methods

Several deployment methods are available in this task. The default value is `auto`.

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

[!INCLUDE [rm-app-service-troubleshoot-shared](./includes/rm-app-service-troubleshoot-shared.md)]

[!INCLUDE [rm-webapp-functionapp-troubleshoot-shared.md](./includes/rm-webapp-functionapp-troubleshoot-shared.md)]

#### Function app deployment on Windows succeeds but the app doesn't work

This problem could occur if a web.config file isn't present in your app. You can either add a web.config file to your source or automatically generate one by using the **Application and Configuration Settings** of the task.

1. Select the task and go to **Generate web.config parameters for Python, Node.js, Go and Java apps**:

   :::image type="content" source="media/azure-rm-function-app-01.png" alt-text="Screenshot that shows the Generate web.config parameters section.":::


1. Select the More button (...) under **Generate web.config parameters for Python, Node.js, Go and Java apps** to edit the parameters:

   :::image type="content" source="media/azure-rm-web-app-deployment-02.png" alt-text="Screenshot that shows the Generate web.config parameters.":::

1. Select your application type in the **Application framework** list.
1. Select **OK**. Doing so will populate the web.config parameters required to generate the web.config file.

### FAQs

[!INCLUDE [rm-app-service-FAQs-shared](./includes/rm-app-service-faqs-shared.md)]

#### I can't deploy to an internal App Service Environment by using an Azure Resource Manager service connection and a Microsoft-hosted agent

By design, a Microsoft-hosted agent won't work with an App Service Environment. Instead, you need to configure a private agent on a virtual machine that's in the same virtual network as the App Service Environment. Also, set a private DNS zone to enable communication between the resources.
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
- task: AzureFunctionApp@1
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
