---
title: AzureWebPowerShellDeployment@1 - Azure App Service Classic (Deprecated) v1 task
description: Create or update Azure App Service using Azure PowerShell.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# AzureWebPowerShellDeployment@1 - Azure App Service Classic (Deprecated) v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Create or update Azure App Service using Azure PowerShell.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Azure App Service Classic (Deprecated) v1
# Create or update Azure App Service using Azure PowerShell.
- task: AzureWebPowerShellDeployment@1
  inputs:
    ConnectedServiceName: # string. Required. Azure Subscription (Classic). 
    WebSiteLocation: # string. Required. Web App Location. 
    WebSiteName: # string. Required. Web App Name. 
    #Slot: # string. Slot. 
    Package: # string. Required. Web Deploy Package. 
    #doNotDelete: false # boolean. Set DoNotDelete flag. Default: false.
    #AdditionalArguments: # string. Additional Arguments.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="ConnectedServiceName"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectedServiceName`** - **Azure Subscription (Classic)**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Classic subscription to target for deployment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebSiteLocation"::: -->
:::moniker range="<=azure-pipelines"

**`WebSiteLocation`** - **Web App Location**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a location for website.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WebSiteName"::: -->
:::moniker range="<=azure-pipelines"

**`WebSiteName`** - **Web App Name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the website name or Select from the list.<br>Note: Only the websites associated with Default App Service plan for the selected region are listed.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Slot"::: -->
:::moniker range="<=azure-pipelines"

**`Slot`** - **Slot**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Slot.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Package"::: -->
:::moniker range="<=azure-pipelines"

**`Package`** - **Web Deploy Package**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the Visual Studio Web Deploy package under the default artifact directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="doNotDelete"::: -->
:::moniker range="<=azure-pipelines"

**`doNotDelete`** - **Set DoNotDelete flag**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
By enabling this, additional files in web deployment package are preserved while publishing website.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`AdditionalArguments`** - **Additional Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

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

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: azureps |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.103.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->