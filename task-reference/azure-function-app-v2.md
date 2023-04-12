---
title: AzureFunctionApp@2 - Azure Functions Deploy v2 task
description: Update a function app with .NET, Python, JavaScript, PowerShell, Java based web applications.
ms.date: 04/12/2023
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
    #runtimeStack: # 'DOTNET|2.2' | 'DOTNET|3.1' | 'DOTNET|6.0' | 'DOTNET-ISOLATED|7.0' | 'JAVA|8' | 'JAVA|11' | 'NODE|8' | 'NODE|10' | 'NODE|12' | 'NODE|14' | 'NODE|16' | 'NODE|18' | 'PYTHON|3.6' | 'PYTHON|3.7' | 'PYTHON|3.8' | 'PYTHON|3.9'. Optional. Use when appType = functionAppLinux. Runtime stack. 
  # Application and Configuration Settings
    #appSettings: # string. App settings. 
  # Additional Deployment Options
    deploymentMethod: 'auto' # 'auto' | 'zipDeploy' | 'runFromPackage'. Required. Deployment method. Default: auto.
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
Select the Azure Resource Manager subscription for the deployment.
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
Enter or Select the name of an existing Azure Functions App. The Function Apps listed will be based on the selected app type.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployToSlotOrASE"::: -->
:::moniker range="=azure-pipelines"

**`deployToSlotOrASE`** - **Deploy to Slot or App Service Environment**<br>
`boolean`. Optional. Use when `appType != ""`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to deploy to an existing deployment slot or Azure App Service Environment.<br />For both the targets, the task needs Resource group name.<br />In case the deployment target is a slot, by default the deployment is done to the production slot. Any other existing slot name can also be provided.<br />In case the deployment target is an Azure App Service environment, leave the slot name as ‘production’ and just specify the Resource group name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range="=azure-pipelines"

**`resourceGroupName`** - **Resource group**<br>
`string`. Required when `deployToSlotOrASE = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Resource group name is required when the deployment target is either a deployment slot or an App Service Environment.<br />Enter or Select the Azure Resource group that contains the Azure App Service specified above.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="slotName"::: -->
:::moniker range="=azure-pipelines"

**`slotName`** - **Slot**<br>
`string`. Required when `deployToSlotOrASE = true`. Default value: `production`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter or Select an existing Slot other than the Production slot.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="package"::: -->
:::moniker range="=azure-pipelines"

**`package`** - **Package or folder**<br>
`string`. Required. Default value: `$(System.DefaultWorkingDirectory)/**/*.zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File path to the package or a folder containing app service contents generated by MSBuild or a compressed zip or war file.<br />Variables ( [Build](https://docs.microsoft.com/vsts/pipelines/build/variables) | [Release](https://docs.microsoft.com/vsts/pipelines/release/variables#default-variables)), wildcards are supported. <br/> For example, $(System.DefaultWorkingDirectory)/\*\*/\*.zip or $(System.DefaultWorkingDirectory)/\*\*/\*.war.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runtimeStack"::: -->
:::moniker range="=azure-pipelines"

**`runtimeStack`** - **Runtime stack**<br>
`string`. Optional. Use when `appType = functionAppLinux`. Allowed values: `DOTNET|2.2` (DOTNET|2.2 (functionapp v2)), `DOTNET|3.1` (DOTNET|3.1 (functionapp v3)), `DOTNET|6.0` (DOTNET|6.0 (functionapp v4)), `DOTNET-ISOLATED|7.0` (DOTNET-ISOLATED|7.0 (functionapp v4)), `JAVA|8` (JAVA|8 (functionapp v2/v3/v4)), `JAVA|11` (JAVA|11  (functionapp v3/v4)), `NODE|8` (NODE|8 (functionapp v2)), `NODE|10` (NODE|10 (functionapp v2/v3)), `NODE|12` (NODE|12 (functionapp v3)), `NODE|14` (NODE|14 (functionapp v3/v4)), `NODE|16` (NODE|16 (functionapp v4)), `NODE|18` (NODE|18 (functionapp v4)), `PYTHON|3.6` (PYTHON|3.6 (functionapp v2/v3)), `PYTHON|3.7` (PYTHON|3.7 (functionapp v2/v3/v4)), `PYTHON|3.8` (PYTHON|3.8 (functionapp v3/v4)), `PYTHON|3.9` (PYTHON|3.9 (functionapp v3/v4)).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Refer [this doc](https://docs.microsoft.com/azure/azure-functions/functions-versions#languages) for supported runtime versions.  Old values like `DOCKER|microsoft/azure-functions-*` are deprecated, please use the new values from dropdown.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSettings"::: -->
:::moniker range="=azure-pipelines"

**`appSettings`** - **App settings**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Edit web app application settings following the syntax -key value . Value containing spaces should be enclosed in double quotes.<br /> <b>Example</b> : -Port 5000 -RequestTimeout 5000 <br /> -WEBSITE_TIME_ZONE "Eastern Standard Time".
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentMethod"::: -->
:::moniker range="=azure-pipelines"

**`deploymentMethod`** - **Deployment method**<br>
`string`. Required. Allowed values: `auto` (Auto-detect), `zipDeploy` (Zip Deploy), `runFromPackage` (Zip Deploy with Run From Package). Default value: `auto`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose the deployment method for your Function app. Please note that Linux Consumption apps do not support this configuration.
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
| Agent version |  2.104.1 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->