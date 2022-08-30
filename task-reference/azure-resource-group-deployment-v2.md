---
title: AzureResourceGroupDeployment@2 * Azure resource group deployment v2 task
description: Deploy an Azure Resource Manager (ARM) template to a resource group and manage virtual machines.
ms.date: 08/23/2022
monikerRange: "<=azure-pipelines"
---

# AzureResourceGroupDeployment@2 * Azure resource group deployment v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Deploy an Azure Resource Manager (ARM) template to a resource group and manage virtual machines.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Deploy an Azure resource manager (ARM) template to a resource group. You can also start, stop, delete, deallocate all Virtual Machines (VM) in a resource group.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

<!-- :::editable-content name="description"::: -->
Deploy, start, stop, delete Azure Resource Groups.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Azure resource group deployment v2
# Deploy an Azure Resource Manager (ARM) template to a resource group and manage virtual machines.
- task: AzureResourceGroupDeployment@2
  inputs:
  # Azure Details
    azureSubscription: # string. Required. Azure subscription. 
    action: 'Create Or Update Resource Group' # 'Create Or Update Resource Group' | 'Select Resource Group' | 'Start' | 'Stop' | 'StopWithDeallocate' | 'Restart' | 'Delete' | 'DeleteRG'. Required. Action. Default: 'Create Or Update Resource Group'.
    resourceGroupName: # string. Required. Resource group. 
    #location: # string. Required when action = Create Or Update Resource Group. Location. 
  # Template
    templateLocation: 'Linked artifact' # 'Linked artifact' | 'URL of the file'. Required. Template location. Default: 'Linked artifact'.
    #csmFileLink: # string. Required when templateLocation = URL of the file. Template link. 
    #csmParametersFileLink: # string. Optional. Use when templateLocation = URL of the file. Template parameters link. 
    #csmFile: # string. Required when templateLocation = Linked artifact. Template. 
    #csmParametersFile: # string. Optional. Use when templateLocation = Linked artifact. Template parameters. 
    #overrideParameters: # string. Override template parameters. 
    deploymentMode: 'Incremental' # 'Incremental' | 'Complete' | 'Validation'. Required. Deployment mode. Default: 'Incremental'.
  # Advanced deployment options for virtual machines
    #enableDeploymentPrerequisites: 'None' # 'None' | 'ConfigureVMwithWinRM' | 'ConfigureVMWithDGAgent'. Enable prerequisites. Default: 'None'.
    #teamServicesConnection: # string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Azure Pipelines service connection. 
    #teamProject: # string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Team project. 
    #deploymentGroupName: # string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Deployment Group. 
    #copyAzureVMTags: true # boolean. Optional. Use when enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Copy Azure VM tags to agents. Default: true.
    #runAgentServiceAsUser: false # boolean. Optional. Use when enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Run agent service as a user. Default: false.
    #userName: # string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent && runAgentServiceAsUser = true. User name. 
    #password: # string. Optional. Use when enableDeploymentPrerequisites = ConfigureVMWithDGAgent && runAgentServiceAsUser = true. Password. 
    #outputVariable: # string. Optional. Use when enableDeploymentPrerequisites = ConfigureVMwithWinRM || enableDeploymentPrerequisites = None. VM details for WinRM. 
  # Advanced
    #deploymentName: # string. Deployment name. 
    #deploymentOutputs: # string. Deployment outputs. 
    #addSpnToEnvironment: false # boolean. Access service principal details in override parameters. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Azure Resource Group Deployment v2
# Deploy an Azure resource manager (ARM) template to a resource group. You can also start, stop, delete, deallocate all Virtual Machines (VM) in a resource group.
- task: AzureResourceGroupDeployment@2
  inputs:
  # Azure Details
    azureSubscription: # string. Required. Azure subscription. 
    action: 'Create Or Update Resource Group' # 'Create Or Update Resource Group' | 'Select Resource Group' | 'Start' | 'Stop' | 'StopWithDeallocate' | 'Restart' | 'Delete' | 'DeleteRG'. Required. Action. Default: 'Create Or Update Resource Group'.
    resourceGroupName: # string. Required. Resource group. 
    #location: # string. Required when action = Create Or Update Resource Group. Location. 
  # Template
    templateLocation: 'Linked artifact' # 'Linked artifact' | 'URL of the file'. Required. Template location. Default: 'Linked artifact'.
    #csmFileLink: # string. Required when templateLocation = URL of the file. Template link. 
    #csmParametersFileLink: # string. Optional. Use when templateLocation = URL of the file. Template parameters link. 
    #csmFile: # string. Required when templateLocation = Linked artifact. Template. 
    #csmParametersFile: # string. Optional. Use when templateLocation = Linked artifact. Template parameters. 
    #overrideParameters: # string. Override template parameters. 
    deploymentMode: 'Incremental' # 'Incremental' | 'Complete' | 'Validation'. Required. Deployment mode. Default: 'Incremental'.
  # Advanced deployment options for virtual machines
    #enableDeploymentPrerequisites: 'None' # 'None' | 'ConfigureVMwithWinRM' | 'ConfigureVMWithDGAgent'. Enable prerequisites. Default: 'None'.
    #teamServicesConnection: # string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Azure Pipelines/TFS service connection. 
    #teamProject: # string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Team project. 
    #deploymentGroupName: # string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Deployment Group. 
    #copyAzureVMTags: true # boolean. Optional. Use when enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Copy Azure VM tags to agents. Default: true.
    #runAgentServiceAsUser: false # boolean. Optional. Use when enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Run agent service as a user. Default: false.
    #userName: # string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent && runAgentServiceAsUser = true. User name. 
    #password: # string. Optional. Use when enableDeploymentPrerequisites = ConfigureVMWithDGAgent && runAgentServiceAsUser = true. Password. 
    #outputVariable: # string. Optional. Use when enableDeploymentPrerequisites = ConfigureVMwithWinRM || enableDeploymentPrerequisites = None. VM details for WinRM. 
  # Outputs
    #deploymentOutputs: # string. Deployment outputs.
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

<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `ConnectedServiceName`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription for the deployment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="action"::: -->
:::moniker range="<=azure-pipelines"

**`action`** - **Action**<br>
Type: string. Required. Allowed values: 'Create Or Update Resource Group', 'Select Resource Group', 'Start', 'Stop', 'StopWithDeallocate', 'Restart', 'Delete', 'DeleteRG'. Default value: 'Create Or Update Resource Group'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Action to be performed on the Azure resources or resource group.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range="<=azure-pipelines"

**`resourceGroupName`** - **Resource group**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of a resource group.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="location"::: -->
:::moniker range="<=azure-pipelines"

**`location`** - **Location**<br>
Type: string. Required when action = Create Or Update Resource Group.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Location for deploying the resource group. If the resource group already exists in the subscription, then this value will be ignored.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="templateLocation"::: -->
:::moniker range="<=azure-pipelines"

**`templateLocation`** - **Template location**<br>
Type: string. Required. Allowed values: 'Linked artifact', 'URL of the file'. Default value: 'Linked artifact'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmFileLink"::: -->
:::moniker range="<=azure-pipelines"

**`csmFileLink`** - **Template link**<br>
Type: string. Required when templateLocation = URL of the file.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the URL of the template file. Example: [https://raw.githubusercontent.com/Azure/...](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-vm-simple-windows/azuredeploy.json) 

To deploy a template stored in a private storage account, retrieve and include the shared access signature (SAS) token in the URL of the template. Example: `<blob_storage_url>/template.json?<SAStoken>` To upload a template file (or a linked template) to a storage account and generate a SAS token, you could use [Azure file copy](https://aka.ms/azurefilecopyreadme) task or follow the steps using [PowerShell](https://go.microsoft.com/fwlink/?linkid=838080) or [Azure CLI](https://go.microsoft.com/fwlink/?linkid=836911).

To  view the template parameters in a grid, click on “…” next to Override template parameters text box. This feature requires that CORS rules are enabled at the source. If templates are in Azure storage blob, refer to [this](/rest/api/storageservices/fileservices/Cross-Origin-Resource-Sharing--CORS--Support-for-the-Azure-Storage-Services?redirectedfrom=MSDN#understanding-cors-requests) to enable CORS.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmParametersFileLink"::: -->
:::moniker range="<=azure-pipelines"

**`csmParametersFileLink`** - **Template parameters link**<br>
Type: string. Optional. Use when templateLocation = URL of the file.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the URL of the parameters file. Example: [https://raw.githubusercontent.com/Azure/...](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-vm-simple-windows/azuredeploy.parameters.json) 

To use a file stored in a private storage account, retrieve and include the shared access signature (SAS) token in the URL of the template. Example: `<blob_storage_url>/template.json?<SAStoken>` To upload a parameters file to a storage account and generate a SAS token, you could use [Azure file copy](https://aka.ms/azurefilecopyreadme) task or follow the steps using [PowerShell](https://go.microsoft.com/fwlink/?linkid=838080) or [Azure CLI](https://go.microsoft.com/fwlink/?linkid=836911). 

To  view the template parameters in a grid, click on “…” next to Override template parameters text box. This feature requires that CORS rules are enabled at the source. If templates are in Azure storage blob, refer to [this](/rest/api/storageservices/fileservices/Cross-Origin-Resource-Sharing--CORS--Support-for-the-Azure-Storage-Services?redirectedfrom=MSDN#understanding-cors-requests) to enable CORS.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmFile"::: -->
:::moniker range="<=azure-pipelines"

**`csmFile`** - **Template**<br>
Type: string. Required when templateLocation = Linked artifact.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path or a pattern pointing to the Azure Resource Manager template. For more information about the templates see https://aka.ms/azuretemplates. To get started immediately use template https://aka.ms/sampletemplate.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmParametersFile"::: -->
:::moniker range="<=azure-pipelines"

**`csmParametersFile`** - **Template parameters**<br>
Type: string. Optional. Use when templateLocation = Linked artifact.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path or a pattern pointing for the parameters file for the Azure Resource Manager template.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideParameters"::: -->
:::moniker range="<=azure-pipelines"

**`overrideParameters`** - **Override template parameters**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
To view the template parameters in a grid, click on “…” next to Override Parameters textbox. This feature requires that CORS rules are enabled at the source. If templates are in Azure storage blob, refer to [this](/rest/api/storageservices/fileservices/Cross-Origin-Resource-Sharing--CORS--Support-for-the-Azure-Storage-Services?redirectedfrom=MSDN#understanding-cors-requests) to enable CORS. Or type the template parameters to override in the textbox. Example, <br>–storageName fabrikam –adminUsername $(vmusername) -adminPassword $(password) –azureKeyVaultName $(fabrikamFibre).<br>If the parameter value you're using has multiple words, enclose them in quotes, even if you're passing them using variables. For example, -name "parameter value" -name2 "$(var)"<br>To override object type parameters use stringified JSON objects. For example, -options ["option1"] -map {"key1": "value1" }.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentMode"::: -->
:::moniker range="<=azure-pipelines"

**`deploymentMode`** - **Deployment mode**<br>
Type: string. Required. Allowed values: 'Incremental', 'Complete', 'Validation'. Default value: 'Incremental'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Refer to [this](/azure/azure-resource-manager/deployment-modes) for more details. 

 Incremental mode handles deployments as incremental updates to the resource group. It leaves unchanged resources that exist in the resource group but are not specified in the template. 

 Complete mode deletes resources that are not in your template. Complete mode takes relatively more time than incremental mode. If the task times out, consider increasing the timeout, or changing the mode to 'Incremental'. 
 **[Warning] Complete mode will delete all the existing resources in the resource group that are not specified in the template. Do review if the resource group you're deploying to doesn't contain any necessary resources that are not specified in the template.** 

 Validate mode enables you to find problems with the template before creating actual resources. 

 By default, Incremental mode is used.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableDeploymentPrerequisites"::: -->
:::moniker range="<=azure-pipelines"

**`enableDeploymentPrerequisites`** - **Enable prerequisites**<br>
Type: string. Allowed values: 'None', 'ConfigureVMwithWinRM', 'ConfigureVMWithDGAgent'. Default value: 'None'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
These options would be applicable only when the Resource group contains virtual machines. <br><br>Choosing Deployment Group option would configure Deployment Group agent on each of the virtual machines. <br><br>Selecting WinRM option configures Windows Remote Management (WinRM) listener over HTTPS protocol on port 5986, using a self-signed certificate. This configuration is required for performing deployment operation on Azure machines. If the target Virtual Machines are backed by a Load balancer, ensure Inbound NAT rules are configured for target port (5986).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="teamServicesConnection"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`teamServicesConnection`** - **Azure Pipelines service connection**<br>
Input alias: `deploymentGroupEndpoint`. Type: string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the service connection to connect to an Azure DevOps organization or collection for agent registration.<br><br>You can create a service connection using "+New", and select "Token-based authentication". You need a [personal access token(PAT)](/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate) to setup a service connection. <br><br>​Click "Manage" to update the service connection details.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`teamServicesConnection`** - **Azure Pipelines/TFS service connection**<br>
Input alias: `deploymentGroupEndpoint`. Type: string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the service connection to connect to an Azure DevOps organization or TFS collection for agent registration.<br><br>You can create a service connection using "+New", and select "Token-based authentication". You need a [personal access token(PAT)](/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate) to setup a service connection. <br><br>​Click "Manage" to update the service connection details.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`teamServicesConnection`** - **TFS/VSTS endpoint**<br>
Input alias: `deploymentGroupEndpoint`. Type: string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Agent registration with Deployment group requires access to your Visual Studio project.​ <br><br>Click "Add" to create an endpoint using personal access token (PAT) with scope restricted to "Deployment Group" and a default expiration time of 90 days. <br><br>​Click "Manage" to update endpoint details.​.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="teamProject"::: -->
:::moniker range="<=azure-pipelines"

**`teamProject`** - **Team project**<br>
Input alias: `project`. Type: string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Team Project which has the Deployment Group defined in it​.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentGroupName"::: -->
:::moniker range="<=azure-pipelines"

**`deploymentGroupName`** - **Deployment Group**<br>
Type: string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Deployment Group against which the agent(s) will be registered. For more guidance, refer to [Deployment Groups](https://aka.ms/832442).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="copyAzureVMTags"::: -->
:::moniker range="<=azure-pipelines"

**`copyAzureVMTags`** - **Copy Azure VM tags to agents**<br>
Type: boolean. Optional. Use when enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose if the tags configured on the Azure VM need to be copied to the corresponding Deployment Group agent. <br><br>​By default all Azure tags will be copied following the format “Key: Value”. Example: An Azure Tag “Role : Web” would be copied  as-is to the Agent machine. <br><br>For more information on how tag Azure resources refer to [link](/azure/azure-resource-manager/resource-group-using-tags​).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runAgentServiceAsUser"::: -->
:::moniker range=">=azure-pipelines-2019"

**`runAgentServiceAsUser`** - **Run agent service as a user**<br>
Type: boolean. Optional. Use when enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Decide whether to run the agent service as a user other than the default. <br>The default user is "NT AUTHORITY\SYSTEM" in Windows and "root" in Linux.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="userName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`userName`** - **User name**<br>
Type: string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent && runAgentServiceAsUser = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The username to run the agent service on the virtual machines. <br>For domain users, please enter values as "domain\username" or "username@domain.com". For local users, please enter just the user name. <br>It is assumed that the same domain user\a local user with the same name, respectively, is present on all the virtual machines in the resource group.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="password"::: -->
:::moniker range=">=azure-pipelines-2019"

**`password`** - **Password**<br>
Type: string. Optional. Use when enableDeploymentPrerequisites = ConfigureVMWithDGAgent && runAgentServiceAsUser = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The password for the user to run the agent service on the Windows VMs. <br>It is assumed that the password is the same for the specified user on all the VMs. <br>It can accept variable defined in build or release pipelines as '$(passwordVariable)'. You may mark variable as 'secret' to secure it. <br>For linux VMs, a password is not required and will be ignored.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputVariable"::: -->
:::moniker range="<=azure-pipelines"

**`outputVariable`** - **VM details for WinRM**<br>
Type: string. Optional. Use when enableDeploymentPrerequisites = ConfigureVMwithWinRM || enableDeploymentPrerequisites = None.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the variable for the resource group. The variable can be used as $(variableName) to refer to the resource group in subsequent tasks like in the PowerShell on Target Machines task for deploying applications. <br>Valid only when the selected action is Create, Update or Select, and required when an existing resource group is selected.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deploymentName`** - **Deployment name**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the resource group deployment to create.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentOutputs"::: -->
:::moniker range="<=azure-pipelines"

**`deploymentOutputs`** - **Deployment outputs**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the variable for the output variable which will contain the outputs section of the current deployment object in string format. You can use the “ConvertFrom-Json” PowerShell cmdlet to parse the JSON object and access the individual output values.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addSpnToEnvironment"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`addSpnToEnvironment`** - **Access service principal details in override parameters**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Adds service principal id and key of the Azure endpoint you chose to the script's execution environment. You can use these variables: `$servicePrincipalId` and `$servicePrincipalKey` in your override parameters like `-key $servicePrincipalKey`.
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
## Remarks

### What's new in task version 2

* Works with cross-platform agents (Linux, macOS, or Windows)
* Supports Template JSONs located at any publicly accessible http/https URLs.
* Enhanced UX for Override parameters which can now be viewed/edited in a grid.
* NAT rule mapping for VMs which are backed by an Load balancer.
* "Resource group" field is now renamed as "VM details for  WinRM" and is included in the section "Advanced deployment options for virtual machines".
* Limitations:
  * No support for Classic subscriptions. Only ARM subscriptions are supported.
  * No support for PowerShell syntax as the task is now node.js based. Ensure the case sensitivity of the parameter names match, when you override the template parameters. Also, remove the PowerShell cmdlets like "ConvertTo-SecureString" when you migrate from version 1.0 to version 2.0.

### Troubleshooting

#### Error: Internal Server Error

These issues are mostly transient in nature. There are multiple reasons why it could be happening:
* One of the Azure services you're trying to deploy is undergoing maintenance in the region you're trying to deploy to. Keep an eye out on `https://status.azure.com/` to check downtimes of Azure Services.
* Azure Pipelines service itself is going through maintenance. Keep an eye out on `https://status.dev.azure.com/` for downtimes.

However, we've seen some instances where this is due to an error in the ARM template, such as the Azure service you're trying to deploy doesn't support the region you've chosen for the resource.

#### Error: Timeout

Timeout issues could be coming from two places:

* Azure Pipelines Agent
* Portal Deployment

You can identify if the timeout is from portal, by checking for the portal deployment link that'll be in the task logs. If there's no link, this is likely due to Azure Pipelines agent. If there's a link, follow the link to see if there's a timeout that has happened in the portal deployment.

#### Error: CORS rules to be enabled while overriding parameters

If the template file is being referred from a BLOB, while overriding parameters in the pipeline, you might see the following warning message:

`Warning: Failed to download the file from template path.`

This feature requires the CORS rules to be enabled at the source. If templates are in Azure storage blob, see [Cross-origin resource sharing support](/rest/api/storageservices/cross-origin-resource-sharing--cors--support-for-the-azure-storage-services?redirectedfrom=MSDN#understanding-cors-requests) to enable CORS.

Besides enabling CORS, ensure that the SAS token specified in the link of the template is "srt-sco". This token is required for you to download the file and proceed.

##### Azure Pipelines Agent

If the issue is coming from Azure Pipelines agent, you can increase the timeout by setting timeoutInMinutes as key in the YAML to 0. For more information, see [Specify jobs in your pipeline](/azure/devops/pipelines/process/phases).

##### Portal Deployment

Check out this doc on how to identify if the error came from the Azure portal: [View deployment history with Azure Resource Manager](/azure/azure-resource-manager/templates/deployment-history).

In case of portal deployment, try setting "timeoutInMinutes" in the ARM template to "0". If not specified, the value assumed is 60 minutes. 0 makes sure the deployment will run for as long as it can to succeed.

This could also be happening because of transient issues in the system. Keep an eye on  `https://status.dev.azure.com/` to check if there's a downtime in Azure Pipelines service.

#### Error: Azure Resource Manager (ARM) template failed validation

This issue happens mostly because of an invalid parameter in the ARM template, such as an unsupported SKU or region. If the validation fails, check the error message. It should point you to the resource and parameter that's invalid.

This issue also might occur because of multiline strings. Currently, the Azure Resource Group Deployment task doesn't support multiline strings in an ARM template or parameter JSON file.

In addition, refer to this article regarding structure and syntax of ARM Templates: [Understand the structure and syntax of ARM templates](/azure/azure-resource-manager/templates/template-syntax).
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