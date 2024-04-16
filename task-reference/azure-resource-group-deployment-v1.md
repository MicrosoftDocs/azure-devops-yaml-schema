---
title: AzureResourceGroupDeployment@1 - Azure Resource Group Deployment v1 task
description: Deploy, start, stop, delete Azure Resource Groups.
ms.date: 04/16/2024
monikerRange: "<=azure-pipelines"
---

# AzureResourceGroupDeployment@1 - Azure Resource Group Deployment v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to deploy, start, stop, and delete Azure Resource Groups.

This task is deprecated; use [AzureResourceGroupDeployment@2](./azure-resource-group-deployment-v2.md).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

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
    #ConnectedServiceNameSelector: 'ConnectedServiceName' # 'ConnectedServiceName' | 'ConnectedServiceNameClassic'. Azure Connection Type. Default: ConnectedServiceName.
    ConnectedServiceName: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Subscription. 
    #ConnectedServiceNameClassic: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameClassic. Azure Classic Subscription. 
    action: 'Create Or Update Resource Group' # 'Create Or Update Resource Group' | 'Select Resource Group' | 'Start' | 'Stop' | 'Restart' | 'Delete' | 'DeleteRG'. Required when ConnectedServiceNameSelector = ConnectedServiceName. Action. Default: Create Or Update Resource Group.
    #actionClassic: 'Select Resource Group' # 'Select Resource Group'. Required when ConnectedServiceNameSelector = ConnectedServiceNameClassic. Action. Default: Select Resource Group.
    resourceGroupName: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName. Resource Group. 
    #cloudService: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameClassic. Cloud Service. 
    #location: 'East US' # 'Australia East' | 'Australia Southeast' | 'Brazil South' | 'Canada Central' | 'Canada East' | 'Central India' | 'Central US' | 'East Asia' | 'East US' | 'East US 2 ' | 'Japan East' | 'Japan West' | 'North Central US' | 'North Europe' | 'South Central US' | 'South India' | 'Southeast Asia' | 'UK South' | 'UK West' | 'West Central US' | 'West Europe' | 'West India' | 'West US' | 'West US 2'. Required when action = Create Or Update Resource Group. Location. Default: East US.
    #csmFile: # string. Required when action = Create Or Update Resource Group. Template. 
    #csmParametersFile: # string. Optional. Use when action = Create Or Update Resource Group. Template Parameters. 
    #overrideParameters: # string. Optional. Use when action = Create Or Update Resource Group. Override Template Parameters. 
    #deploymentMode: 'Incremental' # 'Validation' | 'Incremental' | 'Complete'. Required when action = Create Or Update Resource Group. Deployment Mode. Default: Incremental.
    #enableDeploymentPrerequisitesForCreate: false # boolean. Optional. Use when action = Create Or Update Resource Group. Enable Deployment Prerequisites. Default: false.
    #enableDeploymentPrerequisitesForSelect: false # boolean. Optional. Use when action = Select Resource Group. Enable Deployment Prerequisites. Default: false.
  # Output
    #outputVariable: # string. Resource Group.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="ConnectedServiceNameSelector"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectedServiceNameSelector`** - **Azure Connection Type**<br>
`string`. Allowed values: `ConnectedServiceName` (Azure Resource Manager), `ConnectedServiceNameClassic` (Azure Classic). Default value: `ConnectedServiceName`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Required. Selects the service connection that contains an Azure Subscription for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectedServiceName"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectedServiceName`** - **Azure Subscription**<br>
`string`. Required when `ConnectedServiceNameSelector = ConnectedServiceName`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Required. Selects the service connection that contains an Azure Subscription for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ConnectedServiceNameClassic"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectedServiceNameClassic`** - **Azure Classic Subscription**<br>
`string`. Required when `ConnectedServiceNameSelector = ConnectedServiceNameClassic`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects an Azure Classic subscription for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="action"::: -->
:::moniker range="<=azure-pipelines"

**`action`** - **Action**<br>
`string`. Required when `ConnectedServiceNameSelector = ConnectedServiceName`. Allowed values: `Create Or Update Resource Group`, `Select Resource Group`, `Start` (Start Virtual Machines), `Stop` (Stop Virtual Machines), `Restart` (Restart Virtual Machines), `Delete` (Delete Virtual Machines), `DeleteRG` (Delete Resource Group). Default value: `Create Or Update Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The action to be performed on the Azure resources or resource group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="actionClassic"::: -->
:::moniker range="<=azure-pipelines"

**`actionClassic`** - **Action**<br>
`string`. Required when `ConnectedServiceNameSelector = ConnectedServiceNameClassic`. Allowed values: `Select Resource Group` (Select Cloud Service). Default value: `Select Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The action to be performed on the Azure resources or cloud service.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range="<=azure-pipelines"

**`resourceGroupName`** - **Resource Group**<br>
`string`. Required when `ConnectedServiceNameSelector = ConnectedServiceName`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides the name of the resource group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cloudService"::: -->
:::moniker range="<=azure-pipelines"

**`cloudService`** - **Cloud Service**<br>
`string`. Required when `ConnectedServiceNameSelector = ConnectedServiceNameClassic`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides the name of the cloud service.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="location"::: -->
:::moniker range="<=azure-pipelines"

**`location`** - **Location**<br>
`string`. Required when `action = Create Or Update Resource Group`. Allowed values: `Australia East`, `Australia Southeast`, `Brazil South`, `Canada Central`, `Canada East`, `Central India`, `Central US`, `East Asia`, `East US`, `East US 2 `, `Japan East`, `Japan West`, `North Central US`, `North Europe`, `South Central US`, `South India`, `Southeast Asia`, `UK South`, `UK West`, `West Central US`, `West Europe`, `West India`, `West US`, `West US 2`. Default value: `East US`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The location to deploy the resource group. If the resource group already exists in the subscription, then this value will be ignored.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmFile"::: -->
:::moniker range="<=azure-pipelines"

**`csmFile`** - **Template**<br>
`string`. Required when `action = Create Or Update Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path or a pattern pointing to the Azure Resource Manager template. Learn more about [Azure Resource Manager templates](https://github.com/Azure/azure-quickstart-templates). To get started immediately, use [this sample template](https://github.com/Azure/azure-quickstart-templates/tree/master/demos/vm-winrm-windows).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmParametersFile"::: -->
:::moniker range="<=azure-pipelines"

**`csmParametersFile`** - **Template Parameters**<br>
`string`. Optional. Use when `action = Create Or Update Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the URL of the parameters file. An example URL: `https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-vm-simple-windows/azuredeploy.parameters.json`

To use a file stored in a private storage account, retrieve and include the shared access signature (SAS) token in the URL of the template. Example: `<blob_storage_url>/template.json?<SAStoken>` To upload a parameters file to a storage account and generate a SAS token, use the [Azure file copy](https://aka.ms/azurefilecopyreadme) task or follow the steps using [PowerShell](https://go.microsoft.com/fwlink/?linkid=838080) or [Azure CLI](https://go.microsoft.com/fwlink/?linkid=836911).

To view the template parameters in a grid, click on `…` next to the override template parameters text box. This feature requires that CORS rules are enabled at the source. If templates are in Azure storage blob, refer to [Cross-Origin Resource Sharing](/rest/api/storageservices/fileservices/Cross-Origin-Resource-Sharing--CORS--Support-for-the-Azure-Storage-Services?redirectedfrom=MSDN#understanding-cors-requests) to enable CORS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideParameters"::: -->
:::moniker range="<=azure-pipelines"

**`overrideParameters`** - **Override Template Parameters**<br>
`string`. Optional. Use when `action = Create Or Update Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the template parameters to override.

To view the template parameters in a grid, click on `...` next to the Override Parameters textbox. This feature requires that CORS rules are enabled at the source. If the templates are in the Azure storage blob, reference this string to enable CORS, or type the template parameters to override in the textbox.

Example: `-storageName fabrikam -adminUsername $(vmusername) -adminPassword (ConvertTo-SecureString -String '$(password)' -AsPlainText -Force) -azureKeyVaultName $(fabrikamFibre)`.

If the parameter value has multiple words, enclose the words in quotes, even if you're passing the value by using variables.
For example, `-name "parameter value" -name2 "$(var)"`.
To override object type parameters, use stringified JSON objects.
For example, `-options ["option1"] -map {"key1": "value1" }`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentMode"::: -->
:::moniker range="<=azure-pipelines"

**`deploymentMode`** - **Deployment Mode**<br>
`string`. Required when `action = Create Or Update Resource Group`. Allowed values: `Validation` (Validation Only), `Incremental`, `Complete`. Default value: `Incremental`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The `Incremental` mode handles deployments as incremental updates to the resource group. It leaves unchanged resources that exist in the resource group but are not specified in the template.

`Complete` mode deletes resources that are not in your template. Complete mode takes relatively more time than incremental mode. If the task times out, consider increasing the timeout or changing to the `Incremental` mode.

> [!WARNING]
> Complete mode will delete all the existing resources in the resource group that are not specified in the template. Do review if the resource group you're deploying to doesn't contain any necessary resources that are not specified in the template.

`Validate` mode enables you to find problems with the template before creating actual resources.

> [!NOTE]
> The `Validate` mode always creates a resource group, even if no resources are deployed.

Learn more about [deployment modes](/azure/azure-resource-manager/deployment-modes).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableDeploymentPrerequisitesForCreate"::: -->
:::moniker range="<=azure-pipelines"

**`enableDeploymentPrerequisitesForCreate`** - **Enable Deployment Prerequisites**<br>
`boolean`. Optional. Use when `action = Create Or Update Resource Group`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Applicable only when the resource group contains virtual machines.

Choosing the Deployment Group option configures the Deployment Group agent on each of the virtual machines.

Selecting the WinRM option configures the Windows Remote Management (WinRM) listener over HTTPS protocol on port 5986 using a self-signed certificate. This configuration is required for performing deployment operation on Azure machines. If the target virtual machines are backed by a load balancer, ensure the Inbound NAT rules are configured for the target port (5986).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableDeploymentPrerequisitesForSelect"::: -->
:::moniker range="<=azure-pipelines"

**`enableDeploymentPrerequisitesForSelect`** - **Enable Deployment Prerequisites**<br>
`boolean`. Optional. Use when `action = Select Resource Group`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Applicable only when the resource group contains virtual machines.

Choosing the Deployment Group option configures the Deployment Group agent on each of the virtual machines.

Selecting the WinRM option configures the Windows Remote Management (WinRM) listener over HTTPS protocol on port 5986 using a self-signed certificate. This configuration is required for performing deployment operation on Azure machines. If the target virtual machines are backed by a load balancer, ensure the Inbound NAT rules are configured for the target port (5986).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputVariable"::: -->
:::moniker range="<=azure-pipelines"

**`outputVariable`** - **Resource Group**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Required when an existing resource group is selected. Provides a name for the resource group variable. The variable can be used as `$(variableName)` to refer to the resource group in subsequent tasks, such as in PowerShell on Target Machines task for deploying applications.

Valid only when the selected action is `Create`, `Update`, or `Select`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
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


<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
