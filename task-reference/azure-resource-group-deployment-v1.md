---
title: AzureResourceGroupDeployment@1 - Azure Resource Group Deployment v1 task
description: Deploy, start, stop, delete Azure Resource Groups.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# AzureResourceGroupDeployment@1 - Azure Resource Group Deployment v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Deploy, start, stop, delete Azure Resource Groups.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Azure Resource Group Deployment v1
# Deploy, start, stop, delete Azure Resource Groups.
- task: AzureResourceGroupDeployment@1
  inputs:
    #ConnectedServiceNameSelector: 'ConnectedServiceName' # 'ConnectedServiceName' | 'ConnectedServiceNameClassic'. Azure Connection Type. Default: 'ConnectedServiceName'.
    ConnectedServiceName: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Subscription. 
    #ConnectedServiceNameClassic: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameClassic. Azure Classic Subscription. 
    action: 'Create Or Update Resource Group' # 'Create Or Update Resource Group' | 'Select Resource Group' | 'Start' | 'Stop' | 'Restart' | 'Delete' | 'DeleteRG'. Required when ConnectedServiceNameSelector = ConnectedServiceName. Action. Default: 'Create Or Update Resource Group'.
    #actionClassic: 'Select Resource Group' # 'Select Resource Group'. Required when ConnectedServiceNameSelector = ConnectedServiceNameClassic. Action. Default: 'Select Resource Group'.
    resourceGroupName: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName. Resource Group. 
    #cloudService: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameClassic. Cloud Service. 
    #location: 'East US' # 'Australia East' | 'Australia Southeast' | 'Brazil South' | 'Canada Central' | 'Canada East' | 'Central India' | 'Central US' | 'East Asia' | 'East US' | 'East US 2 ' | 'Japan East' | 'Japan West' | 'North Central US' | 'North Europe' | 'South Central US' | 'South India' | 'Southeast Asia' | 'UK South' | 'UK West' | 'West Central US' | 'West Europe' | 'West India' | 'West US' | 'West US 2'. Required when action = Create Or Update Resource Group. Location. Default: 'East US'.
    #csmFile: # string. Required when action = Create Or Update Resource Group. Template. 
    #csmParametersFile: # string. Optional. Use when action = Create Or Update Resource Group. Template Parameters. 
    #overrideParameters: # string. Optional. Use when action = Create Or Update Resource Group. Override Template Parameters. 
    #deploymentMode: 'Incremental' # 'Validation' | 'Incremental' | 'Complete'. Required when action = Create Or Update Resource Group. Deployment Mode. Default: 'Incremental'.
    #enableDeploymentPrerequisitesForCreate: false # boolean. Optional. Use when action = Create Or Update Resource Group. Enable Deployment Prerequisites. Default: false.
    #enableDeploymentPrerequisitesForSelect: false # boolean. Optional. Use when action = Select Resource Group. Enable Deployment Prerequisites. Default: false.
  # Output
    #outputVariable: # string. Resource Group.
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

<!-- :::item name="ConnectedServiceNameSelector"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectedServiceNameSelector`** - **Azure Connection Type**<br>
Type: string. Allowed values: 'ConnectedServiceName', 'ConnectedServiceNameClassic'. Default value: 'ConnectedServiceName'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectedServiceName"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectedServiceName`** - **Azure Subscription**<br>
Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceName.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription for the deployment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectedServiceNameClassic"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectedServiceNameClassic`** - **Azure Classic Subscription**<br>
Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceNameClassic.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Classic subscription for the deployment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="action"::: -->
:::moniker range="<=azure-pipelines"

**`action`** - **Action**<br>
Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceName. Allowed values: 'Create Or Update Resource Group', 'Select Resource Group', 'Start', 'Stop', 'Restart', 'Delete', 'DeleteRG'. Default value: 'Create Or Update Resource Group'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Action to be performed on the Azure resources or resource group.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="actionClassic"::: -->
:::moniker range="<=azure-pipelines"

**`actionClassic`** - **Action**<br>
Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceNameClassic. Allowed values: 'Select Resource Group'. Default value: 'Select Resource Group'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Action to be performed on the Azure resources or cloud service.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range="<=azure-pipelines"

**`resourceGroupName`** - **Resource Group**<br>
Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceName.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of the resource group.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cloudService"::: -->
:::moniker range="<=azure-pipelines"

**`cloudService`** - **Cloud Service**<br>
Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceNameClassic.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of the cloud service.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="location"::: -->
:::moniker range="<=azure-pipelines"

**`location`** - **Location**<br>
Type: string. Required when action = Create Or Update Resource Group. Allowed values: 'Australia East', 'Australia Southeast', 'Brazil South', 'Canada Central', 'Canada East', 'Central India', 'Central US', 'East Asia', 'East US', 'East US 2 ', 'Japan East', 'Japan West', 'North Central US', 'North Europe', 'South Central US', 'South India', 'Southeast Asia', 'UK South', 'UK West', 'West Central US', 'West Europe', 'West India', 'West US', 'West US 2'. Default value: 'East US'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Location for deploying the resource group. If the resource group already exists in the subscription, then this value will be ignored.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmFile"::: -->
:::moniker range="<=azure-pipelines"

**`csmFile`** - **Template**<br>
Type: string. Required when action = Create Or Update Resource Group.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path to the Azure Resource Manager template. For more information about the templates see https://aka.ms/azuretemplates. To get started immediately use template https://aka.ms/sampletemplate.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmParametersFile"::: -->
:::moniker range="<=azure-pipelines"

**`csmParametersFile`** - **Template Parameters**<br>
Type: string. Optional. Use when action = Create Or Update Resource Group.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path for the parameters file for the Azure Resource Manager Template.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideParameters"::: -->
:::moniker range="<=azure-pipelines"

**`overrideParameters`** - **Override Template Parameters**<br>
Type: string. Optional. Use when action = Create Or Update Resource Group.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the template parameters to override like, <br>-storageName fabrikam -adminUsername $(vmusername) -adminPassword (ConvertTo-SecureString -String '$(password)' -AsPlainText -Force) -azureKeyVaultName $(fabrikamFibre).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentMode"::: -->
:::moniker range="<=azure-pipelines"

**`deploymentMode`** - **Deployment Mode**<br>
Type: string. Required when action = Create Or Update Resource Group. Allowed values: 'Validation', 'Incremental', 'Complete'. Default value: 'Incremental'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Incremental mode handles deployments as incremental updates to the resource group . It leaves unchanged resources that exist in the resource group but are not specified in the template. 

 Complete mode deletes resources that are not in your template. 

 Validate mode enables you to find problems with the template before creating actual resources. 

 By default, Incremental mode is used.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableDeploymentPrerequisitesForCreate"::: -->
:::moniker range="<=azure-pipelines"

**`enableDeploymentPrerequisitesForCreate`** - **Enable Deployment Prerequisites**<br>
Type: boolean. Optional. Use when action = Create Or Update Resource Group. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enabling this option configures Windows Remote Management (WinRM) listener over HTTPS protocol on port 5986, using a self-signed certificate. This configuration is required for performing deployment operation on Azure machines. If the target Virtual Machines are backed by a Load balancer, ensure Inbound NAT rules are configured for target port (5986).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableDeploymentPrerequisitesForSelect"::: -->
:::moniker range="<=azure-pipelines"

**`enableDeploymentPrerequisitesForSelect`** - **Enable Deployment Prerequisites**<br>
Type: boolean. Optional. Use when action = Select Resource Group. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enabling this option configures Windows Remote Management (WinRM) listener over HTTPS protocol on port 5986, using a self-signed certificate. This configuration is required for performing deployment operation on Azure machines. If the target Virtual Machines are backed by a Load balancer, ensure Inbound NAT rules are configured for target port (5986).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputVariable"::: -->
:::moniker range="<=azure-pipelines"

**`outputVariable`** - **Resource Group**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the variable for the resource group. The variable can be used as $(variableName) to refer to the resource group in subsequent tasks like in the PowerShell on Target Machines task for deploying applications. <br>Valid only when the selected action is Create, Update or Select, and required when an existing resource group is selected.
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

:::moniker range=">=azure-pipelines-2019"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: azureps |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.103.0 or greater |
| Task category | Deploy |

:::moniker-end

:::moniker range="=azure-pipelines-2018"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | All |
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