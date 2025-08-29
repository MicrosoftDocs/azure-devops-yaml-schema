---
title: AzureResourceGroupDeployment@2 - Azure resource group deployment v2 task
description: Deploy an Azure Resource Manager (ARM) template to a resource group and manage virtual machines.
ms.date: 08/29/2025
monikerRange: "<=azure-pipelines"
---

# AzureResourceGroupDeployment@2 - Azure resource group deployment v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Deploy an Azure Resource Manager (ARM) template to a resource group and manage virtual machines.
<!-- :::editable-content-end::: -->

:::moniker-end

<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.1"

```yaml
# Azure resource group deployment v2
# Deploy an Azure Resource Manager (ARM) template to a resource group and manage virtual machines.
- task: AzureResourceGroupDeployment@2
  inputs:
  # Azure Details
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    action: 'Create Or Update Resource Group' # 'Create Or Update Resource Group' | 'Select Resource Group' | 'Start' | 'Stop' | 'StopWithDeallocate' | 'Restart' | 'Delete' | 'DeleteRG'. Required. Action. Default: Create Or Update Resource Group.
    resourceGroupName: # string. Required. Resource group. 
    #location: # string. Required when action = Create Or Update Resource Group. Location. 
  # Template
    #templateLocation: 'Linked artifact' # 'Linked artifact' | 'URL of the file'. Required when action = Create Or Update Resource Group. Template location. Default: Linked artifact.
    #csmFileLink: # string. Required when templateLocation = URL of the file && action = Create Or Update Resource Group. Template link. 
    #csmParametersFileLink: # string. Optional. Use when templateLocation = URL of the file && action = Create Or Update Resource Group. Template parameters link. 
    #csmFile: # string. Required when templateLocation = Linked artifact && action = Create Or Update Resource Group. Template. 
    #csmParametersFile: # string. Optional. Use when templateLocation = Linked artifact && action = Create Or Update Resource Group. Template parameters. 
    #overrideParameters: # string. Optional. Use when action = Create Or Update Resource Group. Override template parameters. 
    #deploymentMode: 'Incremental' # 'Incremental' | 'Complete' | 'Validation'. Required when action = Create Or Update Resource Group. Deployment mode. Default: Incremental.
  # Advanced deployment options for virtual machines
    #enableDeploymentPrerequisites: 'None' # 'None' | 'ConfigureVMwithWinRM' | 'ConfigureVMWithDGAgent'. Optional. Use when action = Create Or Update Resource Group || action = Select Resource Group. Enable prerequisites. Default: None.
    #teamServicesConnection: # string. Alias: deploymentGroupEndpoint. Required when (action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Azure Pipelines service connection. 
    #teamProject: # string. Alias: project. Required when (action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Team project. 
    #deploymentGroupName: # string. Required when (action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Deployment Group. 
    #copyAzureVMTags: true # boolean. Optional. Use when (action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Copy Azure VM tags to agents. Default: true.
    #runAgentServiceAsUser: false # boolean. Optional. Use when (action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Run agent service as a user. Default: false.
    #userName: # string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent && runAgentServiceAsUser = true. User name. 
    #password: # string. Optional. Use when enableDeploymentPrerequisites = ConfigureVMWithDGAgent && runAgentServiceAsUser = true. Password. 
    #outputVariable: # string. Optional. Use when (action = Create Or Update Resource Group || action = Select Resource Group) && (enableDeploymentPrerequisites = ConfigureVMwithWinRM || enableDeploymentPrerequisites = None). VM details for WinRM. 
  # Advanced
    #deploymentName: # string. Optional. Use when action = Create Or Update Resource Group. Deployment name. 
    #deploymentOutputs: # string. Optional. Use when action = Create Or Update Resource Group. Deployment outputs. 
    #addSpnToEnvironment: false # boolean. Optional. Use when action = Create Or Update Resource Group. Access service principal details in override parameters. Default: false.
    #useWithoutJSON: false # boolean. Optional. Use when action = Create Or Update Resource Group. Use individual output values without JSON.Stringify applied. Default: false.
```

:::moniker-end

:::moniker range="<=azure-pipelines-2022"

```yaml
# Azure resource group deployment v2
# Deploy an Azure Resource Manager (ARM) template to a resource group and manage virtual machines.
- task: AzureResourceGroupDeployment@2
  inputs:
  # Azure Details
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    action: 'Create Or Update Resource Group' # 'Create Or Update Resource Group' | 'Select Resource Group' | 'Start' | 'Stop' | 'StopWithDeallocate' | 'Restart' | 'Delete' | 'DeleteRG'. Required. Action. Default: Create Or Update Resource Group.
    resourceGroupName: # string. Required. Resource group. 
    #location: # string. Required when action = Create Or Update Resource Group. Location. 
  # Template
    #templateLocation: 'Linked artifact' # 'Linked artifact' | 'URL of the file'. Required when action = Create Or Update Resource Group. Template location. Default: Linked artifact.
    #csmFileLink: # string. Required when templateLocation = URL of the file && action = Create Or Update Resource Group. Template link. 
    #csmParametersFileLink: # string. Optional. Use when templateLocation = URL of the file && action = Create Or Update Resource Group. Template parameters link. 
    #csmFile: # string. Required when templateLocation = Linked artifact && action = Create Or Update Resource Group. Template. 
    #csmParametersFile: # string. Optional. Use when templateLocation = Linked artifact && action = Create Or Update Resource Group. Template parameters. 
    #overrideParameters: # string. Optional. Use when action = Create Or Update Resource Group. Override template parameters. 
    #deploymentMode: 'Incremental' # 'Incremental' | 'Complete' | 'Validation'. Required when action = Create Or Update Resource Group. Deployment mode. Default: Incremental.
  # Advanced deployment options for virtual machines
    #enableDeploymentPrerequisites: 'None' # 'None' | 'ConfigureVMwithWinRM' | 'ConfigureVMWithDGAgent'. Optional. Use when action = Create Or Update Resource Group || action = Select Resource Group. Enable prerequisites. Default: None.
    #teamServicesConnection: # string. Alias: deploymentGroupEndpoint. Required when (action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Azure Pipelines service connection. 
    #teamProject: # string. Alias: project. Required when (action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Team project. 
    #deploymentGroupName: # string. Required when (action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Deployment Group. 
    #copyAzureVMTags: true # boolean. Optional. Use when (action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Copy Azure VM tags to agents. Default: true.
    #runAgentServiceAsUser: false # boolean. Optional. Use when (action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent. Run agent service as a user. Default: false.
    #userName: # string. Required when enableDeploymentPrerequisites = ConfigureVMWithDGAgent && runAgentServiceAsUser = true. User name. 
    #password: # string. Optional. Use when enableDeploymentPrerequisites = ConfigureVMWithDGAgent && runAgentServiceAsUser = true. Password. 
    #outputVariable: # string. Optional. Use when (action = Create Or Update Resource Group || action = Select Resource Group) && (enableDeploymentPrerequisites = ConfigureVMwithWinRM || enableDeploymentPrerequisites = None). VM details for WinRM. 
  # Advanced
    #deploymentName: # string. Optional. Use when action = Create Or Update Resource Group. Deployment name. 
    #deploymentOutputs: # string. Optional. Use when action = Create Or Update Resource Group. Deployment outputs. 
    #addSpnToEnvironment: false # boolean. Optional. Use when action = Create Or Update Resource Group. Access service principal details in override parameters. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
[Input alias](index.md#what-are-task-input-aliases): `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the service connection that contains an Azure Subscription for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="action"::: -->
:::moniker range="<=azure-pipelines"

**`action`** - **Action**<br>
`string`. Required. Allowed values: `Create Or Update Resource Group`, `Select Resource Group` (Configure virtual machine deployment options), `Start` (Start virtual machines), `Stop` (Stop virtual machines), `StopWithDeallocate` (Stop and deallocate virtual machines), `Restart` (Restart virtual machines), `Delete` (Delete virtual machines), `DeleteRG` (Delete resource group). Default value: `Create Or Update Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The action to be performed on the Azure resources or resource group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroupName"::: -->
:::moniker range="<=azure-pipelines"

**`resourceGroupName`** - **Resource group**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides the name of the resource group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="location"::: -->
:::moniker range="<=azure-pipelines"

**`location`** - **Location**<br>
`string`. Required when `action = Create Or Update Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The location to deploy the resource group. If the resource group already exists in the subscription, then this value will be ignored.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="templateLocation"::: -->
:::moniker range="<=azure-pipelines"

**`templateLocation`** - **Template location**<br>
`string`. Required when `action = Create Or Update Resource Group`. Allowed values: `Linked artifact`, `URL of the file`. Default value: `Linked artifact`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select either **Linked artifact** or **URL of the file**.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmFileLink"::: -->
:::moniker range="<=azure-pipelines"

**`csmFileLink`** - **Template link**<br>
`string`. Required when `templateLocation = URL of the file && action = Create Or Update Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the URL of the template file. An example URL: `https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-vm-simple-windows/azuredeploy.json`

To deploy a template stored in a private storage account, retrieve and include the shared access signature (SAS) token in the URL of the template. Example: `<blob_storage_url>/template.json?<SAStoken>`

To upload a template file (or a linked template) to a storage account and generate a SAS token, use the [Azure file copy](https://github.com/microsoft/azure-pipelines-tasks/blob/master/Tasks/AzureFileCopyV1/README.md) task or follow the steps using [PowerShell](/azure/azure-resource-manager/templates/deploy-powershell#deploy-private-template-with-sas-token) or [Azure CLI](https://go.microsoft.com/fwlink/?linkid=836911).

To view the template parameters in a grid, click on `...` next to the override template parameters text box. This feature requires that CORS rules are enabled at the source. If the templates are in an Azure storage blob, see [Understanding CORS requests](/rest/api/storageservices/fileservices/Cross-Origin-Resource-Sharing--CORS--Support-for-the-Azure-Storage-Services?redirectedfrom=MSDN#understanding-cors-requests) to enable CORS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmParametersFileLink"::: -->
:::moniker range="<=azure-pipelines"

**`csmParametersFileLink`** - **Template parameters link**<br>
`string`. Optional. Use when `templateLocation = URL of the file && action = Create Or Update Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the URL of the parameters file. Example: [https://raw.githubusercontent.com/Azure/...](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/quickstarts/microsoft.compute/vm-simple-windows/azuredeploy.parameters.json)

To use a file stored in a private storage account, retrieve and include the shared access signature (SAS) token in the URL of the template. Example: `<blob_storage_url>/template.json?<SAStoken>` To upload a parameters file to a storage account and generate a SAS token, you could use [Azure file copy](https://aka.ms/azurefilecopyreadme) task or follow the steps using [PowerShell](https://go.microsoft.com/fwlink/?linkid=838080) or [Azure CLI](https://go.microsoft.com/fwlink/?linkid=836911). 

To view the template parameters in a grid, click on `...` next to the override template parameters text box. This feature requires that CORS rules are enabled at the source. If the templates are in an Azure storage blob, see [Understanding CORS requests](/rest/api/storageservices/fileservices/Cross-Origin-Resource-Sharing--CORS--Support-for-the-Azure-Storage-Services?redirectedfrom=MSDN#understanding-cors-requests) to enable CORS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmFile"::: -->
:::moniker range="<=azure-pipelines"

**`csmFile`** - **Template**<br>
`string`. Required when `templateLocation = Linked artifact && action = Create Or Update Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path or a pattern pointing to the Azure Resource Manager template. Learn more about [Azure Resource Manager templates](https://github.com/Azure/azure-quickstart-templates). To get started immediately, use [this sample template](https://github.com/Azure/azure-quickstart-templates/tree/master/demos/vm-winrm-windows).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="csmParametersFile"::: -->
:::moniker range="<=azure-pipelines"

**`csmParametersFile`** - **Template parameters**<br>
`string`. Optional. Use when `templateLocation = Linked artifact && action = Create Or Update Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the URL of the parameters file. An example URL: `https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/101-vm-simple-windows/azuredeploy.parameters.json`

To use a file stored in a private storage account, retrieve and include the shared access signature (SAS) token in the URL of the template. Example: `<blob_storage_url>/template.json?<SAStoken>` To upload a parameters file to a storage account and generate a SAS token, use the [Azure file copy](https://aka.ms/azurefilecopyreadme) task or follow the steps using [PowerShell](https://go.microsoft.com/fwlink/?linkid=838080) or [Azure CLI](https://go.microsoft.com/fwlink/?linkid=836911).

To view the template parameters in a grid, click on `...` next to the override template parameters text box. This feature requires that CORS rules are enabled at the source. If the templates are in an Azure storage blob, see [Understanding CORS requests](/rest/api/storageservices/fileservices/Cross-Origin-Resource-Sharing--CORS--Support-for-the-Azure-Storage-Services?redirectedfrom=MSDN#understanding-cors-requests) to enable CORS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideParameters"::: -->
:::moniker range="<=azure-pipelines"

**`overrideParameters`** - **Override template parameters**<br>
`string`. Optional. Use when `action = Create Or Update Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the template parameters to override.

To view the template parameters in a grid, click on `...` next to the override parameters textbox. This feature requires that CORS rules are enabled at the source. If the templates are in the Azure storage blob, reference this string to enable CORS, or type the template parameters to override in the textbox.

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

**`deploymentMode`** - **Deployment mode**<br>
`string`. Required when `action = Create Or Update Resource Group`. Allowed values: `Incremental`, `Complete`, `Validation` (Validation only). Default value: `Incremental`.<br>
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
<!-- :::item name="enableDeploymentPrerequisites"::: -->
:::moniker range="<=azure-pipelines"

**`enableDeploymentPrerequisites`** - **Enable prerequisites**<br>
`string`. Optional. Use when `action = Create Or Update Resource Group || action = Select Resource Group`. Allowed values: `None`, `ConfigureVMwithWinRM` (Configure with WinRM agent), `ConfigureVMWithDGAgent` (Configure with Deployment Group agent). Default value: `None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Applicable only when the resource group contains virtual machines.

Choosing the Deployment Group option configures the Deployment Group agent on each of the virtual machines.

Selecting the WinRM option configures the Windows Remote Management (WinRM) listener over HTTPS protocol on port 5986 using a self-signed certificate. This configuration is required for performing deployment operation on Azure machines. If the target virtual machines are backed by a load balancer, ensure the Inbound NAT rules are configured for target port (5986).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="teamServicesConnection"::: -->
:::moniker range="<=azure-pipelines"

**`teamServicesConnection`** - **Azure Pipelines service connection**<br>
[Input alias](index.md#what-are-task-input-aliases): `deploymentGroupEndpoint`. `string`. Required when `(action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the service connection to connect to an Azure DevOps organization or collection for agent registration.

You can create a service connection using `+New` and then selecting `Token-based authentication`. You need a [personal access token(PAT)](/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate) to setup a service connection. ​Click `Manage` to update the service connection details.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="teamProject"::: -->
:::moniker range="<=azure-pipelines"

**`teamProject`** - **Team project**<br>
[Input alias](index.md#what-are-task-input-aliases): `project`. `string`. Required when `(action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Team Project which defines the deployment group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentGroupName"::: -->
:::moniker range="<=azure-pipelines"

**`deploymentGroupName`** - **Deployment Group**<br>
`string`. Required when `(action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the deployment group against which the agent(s) will be registered. Learn more about [deployment groups](/azure/devops/pipelines/release/deployment-groups/).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="copyAzureVMTags"::: -->
:::moniker range="<=azure-pipelines"

**`copyAzureVMTags`** - **Copy Azure VM tags to agents**<br>
`boolean`. Optional. Use when `(action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Chooses if the configured tags on the Azure VM need to be copied to the corresponding deployment group agent.

​By default, all Azure tags are copied following the format: `Key: Value`. Example: A `Role : Web` Azure tag would be copied as-is to the agent machine.

Learn more about [using tags for Azure resources](/azure/azure-resource-manager/management/tag-resources).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runAgentServiceAsUser"::: -->
:::moniker range="<=azure-pipelines"

**`runAgentServiceAsUser`** - **Run agent service as a user**<br>
`boolean`. Optional. Use when `(action = Create Or Update Resource Group || action = Select Resource Group) && enableDeploymentPrerequisites = ConfigureVMWithDGAgent`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs the agent service as a user other than the default user if the value is set to `true`.

The default user is `NT AUTHORITY\\SYSTEM` in Windows and `root` in Linux.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="userName"::: -->
:::moniker range="<=azure-pipelines"

**`userName`** - **User name**<br>
`string`. Required when `enableDeploymentPrerequisites = ConfigureVMWithDGAgent && runAgentServiceAsUser = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The username to run the agent service on the virtual machines.

For domain users, specify values as `domain\username` or `username@domain.com`. For local users, specify `username`.

It is assumed that the same domain user or a local user with the same name, respectively, is present on all the virtual machines in the resource group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="password"::: -->
:::moniker range="<=azure-pipelines"

**`password`** - **Password**<br>
`string`. Optional. Use when `enableDeploymentPrerequisites = ConfigureVMWithDGAgent && runAgentServiceAsUser = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The password for the user to run the agent service on the Windows VMs.

It is assumed that the password is the same for the specified user on all the VMs.

It can accept variables defined in build or release pipelines as `$(passwordVariable)`. You may mark the variable as `secret` to secure it.

For Linux VMs, a password is not required and will be ignored.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputVariable"::: -->
:::moniker range="<=azure-pipelines"

**`outputVariable`** - **VM details for WinRM**<br>
`string`. Optional. Use when `(action = Create Or Update Resource Group || action = Select Resource Group) && (enableDeploymentPrerequisites = ConfigureVMwithWinRM || enableDeploymentPrerequisites = None)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Required when an existing resource group is selected. Provides a name for the resource group variable. The variable can be used as `$(variableName)` to refer to the resource group in subsequent tasks, such as in PowerShell on Target Machines task for deploying applications.

Valid only when the selected action is `Create`, `Update`, or `Select`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentName"::: -->
:::moniker range="<=azure-pipelines"

**`deploymentName`** - **Deployment name**<br>
`string`. Optional. Use when `action = Create Or Update Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the resource group deployment to create.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentOutputs"::: -->
:::moniker range="<=azure-pipelines"

**`deploymentOutputs`** - **Deployment outputs**<br>
`string`. Optional. Use when `action = Create Or Update Resource Group`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a name for the output variable, which contains the outputs section of the current deployment object in string format. Use the `ConvertFrom-Json` PowerShell cmdlet to parse the JSON object and access the individual output values.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addSpnToEnvironment"::: -->
:::moniker range="<=azure-pipelines"

**`addSpnToEnvironment`** - **Access service principal details in override parameters**<br>
`boolean`. Optional. Use when `action = Create Or Update Resource Group`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Adds the service principal ID and key of the Azure endpoint chosen to be the script's execution environment. The variables `$servicePrincipalId` and `$servicePrincipalKey` can be in override parameters, such as `-key $servicePrincipalKey`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useWithoutJSON"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`useWithoutJSON`** - **Use individual output values without JSON.Stringify applied**<br>
`boolean`. Optional. Use when `action = Create Or Update Resource Group`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Individual output values are being converted via JSON.Stringify by default. If you want to use the output values as it is without converting them via JSON.Stringify, enable this option. For more details refer to [this](https://github.com/microsoft/azure-pipelines-tasks/tree/master/Tasks/AzureResourceGroupDeploymentV2#deployment-outputs).
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
## Remarks

There is a new version of this task available at [AzureResourceManagerTemplateDeployment@3 - ARM template deployment v3 task](azure-resource-manager-template-deployment-v3.md).

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
