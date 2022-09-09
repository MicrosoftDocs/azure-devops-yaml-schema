---
title: AzureFileCopy@3 - Azure file copy v3 task
description: Copy files to Azure Blob Storage or virtual machines (task version 3).
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# AzureFileCopy@3 - Azure file copy v3 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Copy files to Azure Blob Storage or virtual machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Azure file copy v3
# Copy files to Azure Blob Storage or virtual machines.
- task: AzureFileCopy@3
  inputs:
    SourcePath: # string. Required. Source. 
    azureSubscription: # string. Required. Azure Subscription. 
    Destination: # 'AzureBlob' | 'AzureVMs'. Required. Destination Type. 
    storage: # string. Required. RM Storage Account. 
    #ContainerName: # string. Required when Destination = AzureBlob. Container Name. 
    #BlobPrefix: # string. Optional. Use when Destination = AzureBlob. Blob Prefix. 
    #resourceGroup: # string. Required when Destination = AzureVMs. Resource Group. 
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Optional. Use when Destination = AzureVMs. Select Machines By. Default: 'machineNames'.
    #MachineNames: # string. Optional. Use when Destination = AzureVMs. Filter Criteria. 
    #vmsAdminUserName: # string. Required when Destination = AzureVMs. Admin Login. 
    #vmsAdminPassword: # string. Required when Destination = AzureVMs. Password. 
    #TargetPath: # string. Required when Destination = AzureVMs. Destination Folder. 
    #AdditionalArgumentsForBlobCopy: # string. Optional Arguments (for uploading files to blob). 
    #AdditionalArgumentsForVMCopy: # string. Optional. Use when Destination = AzureVMs. Optional Arguments (for downloading files to VM). 
    #enableCopyPrerequisites: false # boolean. Optional. Use when Destination = AzureVMs. Enable Copy Prerequisites. Default: false.
    #CopyFilesInParallel: true # boolean. Optional. Use when Destination = AzureVMs. Copy in Parallel. Default: true.
    #CleanTargetBeforeCopy: false # boolean. Optional. Use when Destination = AzureVMs. Clean Target. Default: false.
    #skipCACheck: true # boolean. Optional. Use when Destination = AzureVMs. Test Certificate. Default: true.
  # Output
    #outputStorageUri: # string. Storage Container URI. 
    #outputStorageContainerSasToken: # string. Storage Container SAS Token. 
    #sasTokenTimeOutInMinutes: # string. SAS Token Expiration Period In Minutes.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="SourcePath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`SourcePath`** - **Source**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The source of the files to copy. Pre-defined system variables such as `$(Build.Repository.LocalPath)` can be used. Names containing wildcards such as `*.zip` are not supported.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azureSubscription`** - **Azure Classic Subscription**<br>
Input alias: `ConnectedServiceNameARM`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Required if you select **Azure Classic** for the **Azure Connection Type** parameter. The name of an [Azure Classic service connection](/azure/devops/pipelines/library/service-endpoints) configured for the subscription where the target Azure service, virtual machine, or storage account is located.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azureSubscription`** - **Azure RM Subscription**<br>
Input alias: `ConnectedServiceNameARM`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Required if you select **Azure Resource Manager** for the **Azure Connection Type** parameter. The name of an [Azure Resource Manager service](/azure/devops/pipelines/library/connect-to-azure) connection configured for the subscription where the target Azure service, virtual machine, or storage account is located. See [Azure Resource Manager overview](/azure/azure-resource-manager/management/overview) for more details.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Destination"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`Destination`** - **Destination Type**<br>
Type: string. Required. Allowed values: 'AzureBlob', 'AzureVMs'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the destination, either **Azure Blob** or **Azure VMs**.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="storage"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`storage`** - **RM Storage Account**<br>
Input alias: `StorageAccountRM`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a pre-existing ARM storage account. It is also used as an intermediary for copying files to Azure VMs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ContainerName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ContainerName`** - **Container Name**<br>
Type: string. Required when Destination = AzureBlob.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the Container for uploading the files. If a container with the given name does not exist in the specified storage account, it will automatically be created. <br> If you need to create a virtual directory inside the container, use the blob prefix input below. <br> Example: If your target location is <i>https://myaccount.blob.core.windows.net/mycontainer/vd1/vd2/</i>, then specify <i>mycontainer</i> as container name and <i>vd1/vd2</i> as blob prefix.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="BlobPrefix"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`BlobPrefix`** - **Blob Prefix**<br>
Type: string. Optional. Use when Destination = AzureBlob.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Useful for filtering files, for example, append build number to all the blobs to download files from that build only. Example: If you specify blob prefix as <i>myvd1</i>, a virtual directory with this name will be created inside the container. The source files will be copied to <i>https://myaccount.blob.core.windows.net/mycontainer/myvd1/</i>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroup"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`resourceGroup`** - **Resource Group**<br>
Input alias: `EnvironmentNameRM`. Type: string. Required when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the target Resource Group for copying files to.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceFilteringMethod"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ResourceFilteringMethod`** - **Select Machines By**<br>
Type: string. Optional. Use when Destination = AzureVMs. Allowed values: 'machineNames', 'tags'. Default value: 'machineNames'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally, select a subset of VMs in resource group either by providing VMs host name or tags. [Tags](/azure/virtual-machines/tag-template) are supported for resources created via the Azure Resource Manager only.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MachineNames"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`MachineNames`** - **Filter Criteria**<br>
Type: string. Optional. Use when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A list of machine names or tag names that identifies the machines that the task will target. The filter criteria can be:
- The name of an [Azure Resource Group](/azure/azure-resource-manager/management/overview).
- An output variable from a previous task.
- A comma-delimited list of tag names or machine names.
Format when using machine names is a comma-separated list of the machine FQDNs or IP addresses.
Specify tag names for a filter as {TagName}:{Value} Example: `Role:DB;OS:Win8.1`
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmsAdminUserName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`vmsAdminUserName`** - **Admin Login**<br>
Type: string. Required when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The user name of an account that has administrative permissions for all the target VMs.
- Formats such as **username**, **domain\username**, **machine-name\username**, and **.\username** are supported.
- UPN formats such as **username@domain.com** and built-in system accounts such as **NT Authority\System** are not supported.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmsAdminPassword"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`vmsAdminPassword`** - **Password**<br>
Type: string. Required when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The administrator password of the VMs. <br>It can accept variable defined in build or release pipelines as '$(passwordVariable)'. <br>You may mark variable as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`TargetPath`** - **Destination Folder**<br>
Type: string. Required when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The folder in the Azure VMs to which the files will be copied. Environment variables such as `$env:windir` and `$env:systemroot` are supported. Examples: `$env:windir\FabrikamFiber\Web` and `c:\FabrikamFiber`
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsForBlobCopy"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`AdditionalArgumentsForBlobCopy`** - **Optional Arguments (for uploading files to blob)**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional AzCopy.exe arguments that will be applied when uploading to blob like, /NC:10. If no optional arguments are specified here, the following optional arguments will be added by default.<br> /Y, /SetContentType, /Z, /V,<br> /S (only if container name is not $root),<br> /BlobType:page (only if specified storage account is a premium account).<br> If source path is a file, /Pattern will always be added irrespective of whether or not you have specified optional arguments.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsForVMCopy"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`AdditionalArgumentsForVMCopy`** - **Optional Arguments (for downloading files to VM)**<br>
Type: string. Optional. Use when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional AzCopy.exe arguments that will be applied when downloading to VM like, /NC:10. If no optional arguments are specified here, the following optional arguments will be added by default.<br> /Y, /S, /Z, /V.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableCopyPrerequisites"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`enableCopyPrerequisites`** - **Enable Copy Prerequisites**<br>
Type: boolean. Optional. Use when Destination = AzureVMs. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enabling this option configures Windows Remote Management (WinRM) listener over HTTPS protocol on port 5986, using a self-signed certificate. This configuration is required for performing copy operation on Azure machines. If the target Virtual Machines are backed by a Load balancer, ensure Inbound NAT rules are configured for target port (5986). Applicable only for ARM VMs. If the target virtual machines are associated with a Network Security Group (NSG), configure an inbound security rule to allow access on port 5986.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CopyFilesInParallel"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`CopyFilesInParallel`** - **Copy in Parallel**<br>
Type: boolean. Optional. Use when Destination = AzureVMs. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Setting this option causes the process to execute in parallel for the copied files. This can considerably reduce the overall time taken.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CleanTargetBeforeCopy"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`CleanTargetBeforeCopy`** - **Clean Target**<br>
Type: boolean. Optional. Use when Destination = AzureVMs. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Setting it to true will clean-up the destination folder before copying the files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipCACheck"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`skipCACheck`** - **Test Certificate**<br>
Type: boolean. Optional. Use when Destination = AzureVMs. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this option is selected, client skips the validation that the server certificate is signed by a trusted certificate authority (CA) when connecting over Hypertext Transfer Protocol over Secure Socket Layer (HTTPS).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputStorageUri"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`outputStorageUri`** - **Storage Container URI**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the variable for the storage container URI that the files were copied to with this task.  Valid only when the selected destination is Azure Blob.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputStorageContainerSasToken"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`outputStorageContainerSasToken`** - **Storage Container SAS Token**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of a variable that will be updated with the Storage Access Security (SAS) token of the storage container into which the files were copied. Use this variable as an input to subsequent tasks. By default, the SAS token expires after 4 hours.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sasTokenTimeOutInMinutes"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`sasTokenTimeOutInMinutes`** - **SAS Token Expiration Period In Minutes**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the time in minutes after which SAS token will expire. Valid only when the selected destination is Azure Blob.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019.1"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

What's new in Version AzureFileCopy@3
* AzureFileCopy@3 supports Az Module and stopped supporting the Azure classic service endpoint.

The task is used to copy application files and other
artifacts that are required in order to install the 
app; such as PowerShell scripts, PowerShell-DSC modules,
and more.
 
When the target is Azure VMs, the files are first copied
to an automatically generated Azure blob container 
and then downloaded into the VMs. The container is deleted 
after the files have been successfully copied to the VMs.

The task uses **AzCopy**, the command-line utility 
built for fast copying of data from and into Azure storage accounts. The task version 3 or below uses AzCopy V7.

To dynamically deploy Azure Resource Groups that 
contain virtual machines, use the 
[Azure Resource Group Deployment](azure-resource-group-deployment-v2.md) task. This task
has a sample template that can perform the required
operations to set up the WinRM HTTPS
protocol on the virtual machines, open the 5986 port 
in the firewall, and install the test certificate.

> [!NOTE]
> If you are deploying to Azure Static Websites as a container in blob storage,
  you must use **Version 2** or higher of the task in order to preserve the **$web**
  container name.

### FAQ
#### What are the Azure PowerShell prerequisites for using this task?

The task requires Azure PowerShell to be installed 
on the machine running the automation agent. The 
recommended version is 1.0.2, but the task will work
with version 0.9.8 and higher. You can use the
[Azure PowerShell Installer v1.0.2](https://github.com/Azure/azure-powershell/releases/tag/v1.0.2-December2015)
to obtain this.

#### What are the WinRM prerequisites for this task?

The task uses Windows Remote Management (WinRM) HTTPS protocol to
copy the files from the storage blob container to the Azure VMs.
This requires the WinRM HTTPS service to be configured on the VMs,
and a suitable certificate installed.

If the VMs have been created without opening the 
WinRM HTTPS ports, follow these steps:

1. Configure an inbound access rule to allow HTTPS on port 5986 of each VM.
1. Disable [UAC remote restrictions](https://support.microsoft.com/kb/951016).
1. Specify the credentials for the task to access the VMs using an administrator-level login in the simple form **username** without any domain part.
1. Install a certificate on the machine that runs the automation agent.
1. Set the **Test Certificate** parameter of the task if you are using a self-signed certificate.

#### What type of service connection should I choose?

The following table lists the storage accounts and 
the service connections that work with them.
To identify whether a storage account is based on 
the classic APIs or the Resource Manager APIs, log 
into the [Azure portal](https://portal.azure.com/)
and browse for **Storage accounts (Classic)** or 
**Storage accounts**.

| Storage account type | Azure Service Connections in TFS/TS |
| --- | --- |
| Resource Manager | Azure Resource Manager service connection | 
| Classic | Azure service connection with certificate-based or credentials-based authentication using a school or work account | 


* For Azure classic resources, use an **Azure** service connection
  type with certificate or credentials-based authentication.
  If you are using credentials-based authentication, 
  ensure that the credentials are for a 
  [school or work account](https://azure.microsoft.com/pricing/member-offers/msdn-benefits-details/work-accounts-faq/).
  Microsoft accounts such as **joe@live.com** and 
  **joe@hotmail.com** are not supported.
  
* For Azure Resource Manager VMs, use an **Azure Resource Manager** service connection type. See more details at [Automating Azure Resource Group deployment using a Service Principal](https://devblogs.microsoft.com/devops/automating-azure-resource-group-deployment-using-a-service-principal-in-visual-studio-online-buildrelease-management/).
  
* If you are using an **Azure Resource Manager** 
  service connection type, or an **Azure** service connection 
  type with certificate-based authentication, the task
  automatically filters appropriate classic storage 
  accounts, the newer Azure Resource Manager storage 
  accounts, and other fields. For example, the Resource
  Group or cloud service, and the virtual machines.

* **Note**: Currently an **Azure** service connection type with 
  credentials-based authentication does not filter 
  the storage, Resource Group or cloud service, and 
  virtual machine fields.

#### How do I fix failure '403: This request is not authorized to perform this operation using this permission'?

When Azure DevOps creates and authorizes the service connection 
to Azure, it creates an App Registration in your subscription's 
Active Directory. This identity is automatically added with a 
`Contributor` role to all resources in the Resource Group you 
chose to authorize. In order to upload blobs to a storage account, 
being a `Contributor` is *not enough*. You must manually assign the 
[`Storage Blob Data Contributor` role to the app registration identity](/azure/storage/common/storage-auth-aad-rbac-portal).

You can copy the app identity from the existing inherited entry as 
`Contributor` that you will see in the IAM pane and search explicitly 
for it in the `Add role assignment` UI. Note that the identity will 
*not* be listed in the dropdown and you will need to search for its 
identifier.

#### What happens if my Resource Group contains both Classic and Resource Manager VMs?

If the specified Resource Group contains both 
Azure Resource Manager and Classic VMs, the set of VMs that 
will be targeted depends on the connection type.
For certificate-based connections and credentials-based
connections, the copy operation will be performed 
only on Classic VMs. For Service Principal Name 
based connections, the copy operation will be 
performed on only Resource Manager VMs.

#### How do I create a school or work account for use with this task?

A suitable account can be easily created for use in a service connection:

1. Use the Azure portal to create a new user account in Azure Active Directory.
1. Add the Azure Active Directory user account to the co-administrators group in your Azure subscription.
1. Sign into the Azure portal with this user account and change the password.
1. Use the username and password of this account in the service connection. Deployments will be processed using this account.
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