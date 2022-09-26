---
title: AzureResourceManagerTemplateDeployment@3 - ARM template deployment v3 task
description: Deploy an Azure Resource Manager (ARM) template to all the deployment scopes.
ms.date: 09/26/2022
monikerRange: ">=azure-pipelines-2020"
---

# AzureResourceManagerTemplateDeployment@3 - ARM template deployment v3 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Deploy an Azure Resource Manager (ARM) template to all the deployment scopes.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# ARM template deployment v3
# Deploy an Azure Resource Manager (ARM) template to all the deployment scopes.
- task: AzureResourceManagerTemplateDeployment@3
  inputs:
  # Azure Details
    deploymentScope: 'Resource Group' # 'Management Group' | 'Subscription' | 'Resource Group'. Required. Deployment scope. Default: Resource Group.
    azureResourceManagerConnection: # string. Required. Azure Resource Manager connection. 
    #subscriptionId: # string. Required when deploymentScope != Management Group. Subscription. 
    #action: 'Create Or Update Resource Group' # 'Create Or Update Resource Group' | 'DeleteRG'. Required when deploymentScope = Resource Group. Action. Default: Create Or Update Resource Group.
    #resourceGroupName: # string. Required when deploymentScope = Resource Group. Resource group. 
    #location: # string. Required when action = Create Or Update Resource Group || deploymentScope != Resource Group. Location. 
  # Template
    templateLocation: 'Linked artifact' # 'Linked artifact' | 'URL of the file'. Required. Template location. Default: Linked artifact.
    #csmFileLink: # string. Required when templateLocation = URL of the file. Template link. 
    #csmParametersFileLink: # string. Optional. Use when templateLocation = URL of the file. Template parameters link. 
    #csmFile: # string. Required when templateLocation = Linked artifact. Template. 
    #csmParametersFile: # string. Optional. Use when templateLocation = Linked artifact. Template parameters. 
    #overrideParameters: # string. Override template parameters. 
    deploymentMode: 'Incremental' # 'Incremental' | 'Complete' | 'Validation'. Required. Deployment mode. Default: Incremental.
  # Advanced
    #deploymentName: # string. Deployment name. 
    #deploymentOutputs: # string. Deployment outputs. 
    #addSpnToEnvironment: false # boolean. Access service principal details in override parameters. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="deploymentScope"::: -->
:::moniker range=">=azure-pipelines-2020"

**`deploymentScope`** - **Deployment scope**<br>
`string`. Required. Allowed values: `Management Group`, `Subscription`, `Resource Group`. Default value: `Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Deployment scope of the deployment. To know more abour deployment scopes, refer this [link](/Azure/azure-resource-manager/resource-group-template-deploy-rest#deployment-scope).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureResourceManagerConnection"::: -->
:::moniker range=">=azure-pipelines-2020"

**`azureResourceManagerConnection`** - **Azure Resource Manager connection**<br>
Input alias: `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager service connection having access to the selected deployment scope.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="subscriptionId"::: -->
:::moniker range=">=azure-pipelines-2020"

**`subscriptionId`** - **Subscription**<br>
Input alias: `subscriptionName`. `string`. Required when `deploymentScope != Management Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure subscription.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="action"::: -->
:::moniker range=">=azure-pipelines-2020"

**`action`** - **Action**<br>
`string`. Required when `deploymentScope = Resource Group`. Allowed values: `Create Or Update Resource Group`, `DeleteRG` (Delete resource group). Default value: `Create Or Update Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Action to be performed on the Azure resources or resource group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`resourceGroupName`** - **Resource group**<br>
`string`. Required when `deploymentScope = Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of a resource group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="location"::: -->
:::moniker range=">=azure-pipelines-2020"

**`location`** - **Location**<br>
`string`. Required when `action = Create Or Update Resource Group || deploymentScope != Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
For Resource Group deployment scope: Location for deploying the resource group. If the resource group already exists in the subscription, then this value will be ignored.
 For other deployment scope: Location to store deployment metadata.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="templateLocation"::: -->
:::moniker range=">=azure-pipelines-2020"

**`templateLocation`** - **Template location**<br>
`string`. Required. Allowed values: `Linked artifact`, `URL of the file`. Default value: `Linked artifact`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmFileLink"::: -->
:::moniker range=">=azure-pipelines-2020"

**`csmFileLink`** - **Template link**<br>
`string`. Required when `templateLocation = URL of the file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the URL of the template file. Example: [https://raw.githubusercontent.com/Azure/...](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-vm-simple-windows/azuredeploy.json) 

To deploy a template stored in a private storage account, retrieve and include the shared access signature (SAS) token in the URL of the template. Example: `<blob_storage_url>/template.json?<SAStoken>` To upload a template file (or a linked template) to a storage account and generate a SAS token, you could use [Azure file copy](https://aka.ms/azurefilecopyreadme) task or follow the steps using [PowerShell](https://go.microsoft.com/fwlink/?linkid=838080) or [Azure CLI](https://go.microsoft.com/fwlink/?linkid=836911).

To  view the template parameters in a grid, click on “…” next to Override template parameters text box. This feature requires that CORS rules are enabled at the source. If templates are in Azure storage blob, refer to [this](/rest/api/storageservices/fileservices/Cross-Origin-Resource-Sharing--CORS--Support-for-the-Azure-Storage-Services?redirectedfrom=MSDN#understanding-cors-requests) to enable CORS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmParametersFileLink"::: -->
:::moniker range=">=azure-pipelines-2020"

**`csmParametersFileLink`** - **Template parameters link**<br>
`string`. Optional. Use when `templateLocation = URL of the file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the URL of the parameters file. Example: [https://raw.githubusercontent.com/Azure/...](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-vm-simple-windows/azuredeploy.parameters.json) 

To use a file stored in a private storage account, retrieve and include the shared access signature (SAS) token in the URL of the template. Example: `<blob_storage_url>/template.json?<SAStoken>` To upload a parameters file to a storage account and generate a SAS token, you could use [Azure file copy](https://aka.ms/azurefilecopyreadme) task or follow the steps using [PowerShell](https://go.microsoft.com/fwlink/?linkid=838080) or [Azure CLI](https://go.microsoft.com/fwlink/?linkid=836911). 

To  view the template parameters in a grid, click on “…” next to Override template parameters text box. This feature requires that CORS rules are enabled at the source. If templates are in Azure storage blob, refer to [this](/rest/api/storageservices/fileservices/Cross-Origin-Resource-Sharing--CORS--Support-for-the-Azure-Storage-Services?redirectedfrom=MSDN#understanding-cors-requests) to enable CORS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmFile"::: -->
:::moniker range=">=azure-pipelines-2020"

**`csmFile`** - **Template**<br>
`string`. Required when `templateLocation = Linked artifact`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path or a pattern pointing to the Azure Resource Manager template. For more information about the templates see https://aka.ms/azuretemplates. To get started immediately use template https://aka.ms/sampletemplate.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmParametersFile"::: -->
:::moniker range=">=azure-pipelines-2020"

**`csmParametersFile`** - **Template parameters**<br>
`string`. Optional. Use when `templateLocation = Linked artifact`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path or a pattern pointing for the parameters file for the Azure Resource Manager template.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideParameters"::: -->
:::moniker range=">=azure-pipelines-2020"

**`overrideParameters`** - **Override template parameters**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
To view the template parameters in a grid, click on “…” next to Override Parameters textbox. This feature requires that CORS rules are enabled at the source. If templates are in Azure storage blob, refer to [this](/rest/api/storageservices/fileservices/Cross-Origin-Resource-Sharing--CORS--Support-for-the-Azure-Storage-Services?redirectedfrom=MSDN#understanding-cors-requests) to enable CORS. Or type the template parameters to override in the textbox. Example, <br>–storageName fabrikam –adminUsername $(vmusername) -adminPassword $(password) –azureKeyVaultName $(fabrikamFibre).<br>If the parameter value you're using has multiple words, enclose them in quotes, even if you're passing them using variables. For example, -name "parameter value" -name2 "$(var)"<br>To override object type parameters use stringified JSON objects. For example, -options ["option1"] -map {"key1": "value1" }.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentMode"::: -->
:::moniker range=">=azure-pipelines-2020"

**`deploymentMode`** - **Deployment mode**<br>
`string`. Required. Allowed values: `Incremental`, `Complete`, `Validation` (Validation only). Default value: `Incremental`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Refer to [this](/azure/azure-resource-manager/deployment-modes) for more details. 

 Incremental mode handles deployments as incremental updates to the resource group. It leaves unchanged resources that exist in the resource group but are not specified in the template. 

 Complete mode deletes resources that are not in your template. Complete mode takes relatively more time than incremental mode. If the task times out, consider increasing the timeout, or changing the mode to 'Incremental'. 
 **[Warning] Complete Mode will delete all the existing resources in the resource group that are not specified in the template. Do review if the resource group you're deploying to doesn't contain any necessary resources that are not specified in the template.** 

 Validate mode enables you to find problems with the template before creating actual resources. 

 By default, Incremental mode is used. 

 'Complete' mode is supported for 'Resource Group' Deployment scope only.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`deploymentName`** - **Deployment name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the resource group deployment to create.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentOutputs"::: -->
:::moniker range=">=azure-pipelines-2020"

**`deploymentOutputs`** - **Deployment outputs**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the variable for the output variable which will contain the outputs section of the current deployment object in string format. You can use the “ConvertFrom-Json” PowerShell cmdlet to parse the JSON object and access the individual output values. For more details refer to [this](https://github.com/microsoft/azure-pipelines-tasks/tree/master/Tasks/AzureResourceManagerTemplateDeploymentV3#deployment-outputs).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addSpnToEnvironment"::: -->
:::moniker range=">=azure-pipelines-2020"

**`addSpnToEnvironment`** - **Access service principal details in override parameters**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Adds service principal id and key of the Azure endpoint you chose to the script's execution environment. You can use these variables: `$servicePrincipalId` and `$servicePrincipalKey` in your override parameters like `-key $servicePrincipalKey`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

- Added support for deployment at all the deployment scopes.
   - Removed all the VM related actions.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.119.1 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->