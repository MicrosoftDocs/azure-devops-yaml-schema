---
title: AzureFileCopy@3 - Azure file copy v3 task
description: Copy files to Azure Blob Storage or virtual machines (task version 3).
ms.date: 05/14/2024
monikerRange: ">=azure-pipelines-2019.1"
---

# AzureFileCopy@3 - Azure file copy v3 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Copy files to Azure Blob Storage or virtual machines.

[!INCLUDE [workload-identity](./includes/workload-identity-not-supported.md)]
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
    azureSubscription: # string. Alias: ConnectedServiceNameARM. Required. Azure Subscription. 
    Destination: # 'AzureBlob' | 'AzureVMs'. Required. Destination Type. 
    storage: # string. Alias: StorageAccountRM. Required. RM Storage Account. 
    #ContainerName: # string. Required when Destination = AzureBlob. Container Name. 
    #BlobPrefix: # string. Optional. Use when Destination = AzureBlob. Blob Prefix. 
    #resourceGroup: # string. Alias: EnvironmentNameRM. Required when Destination = AzureVMs. Resource Group. 
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Optional. Use when Destination = AzureVMs. Select Machines By. Default: machineNames.
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
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the absolute path of the source folder, or file on the local machine, or a UNC share.  You can use pre-defined system variables such as `$(Build.Repository.LocalPath)`. Names containing wildcards such as `*.zip` are not supported. The value or expression you specify should return a single folder or a file name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azureSubscription`** - **Azure Subscription**<br>
Input alias: `ConnectedServiceNameARM`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of an [Azure Resource Manager service connection](/azure/devops/pipelines/library/connect-to-azure) configured for the subscription where the target Azure service, virtual machine, or storage account is located. See [Azure Resource Manager overview](/azure/azure-resource-manager/management/overview) for more details.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Destination"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`Destination`** - **Destination Type**<br>
`string`. Required. Allowed values: `AzureBlob` (Azure Blob), `AzureVMs` (Azure VMs).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the destination type.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="storage"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`storage`** - **RM Storage Account**<br>
Input alias: `StorageAccountRM`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a pre-existing ARM storage account. This is the storage account used as an intermediary for copying files to Azure VMs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ContainerName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ContainerName`** - **Container Name**<br>
`string`. Required when `Destination = AzureBlob`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the container into which files are copied. If the specified container does not exist in the storage account, it will be created.

To create a virtual directory inside the container, use the blob prefix input. For example, for the target location `https://myaccount.blob.core.windows.net/mycontainer/vd1/vd2/`, specify container name `mycontainer` and blob prefix: `vd1/vd2`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="BlobPrefix"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`BlobPrefix`** - **Blob Prefix**<br>
`string`. Optional. Use when `Destination = AzureBlob`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a prefix that can be used to filter files.

Example: You can append a build number to filter the files from all blobs with the same build number.

Example: If you specify a blob prefix `myvd1`, a virtual directory is created inside the container. Files are copied from the source to `https://myaccount.blob.core.windows.net/mycontainer/myvd1/`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroup"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`resourceGroup`** - **Resource Group**<br>
Input alias: `EnvironmentNameRM`. `string`. Required when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the target Resource Group into which files will be copied.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceFilteringMethod"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ResourceFilteringMethod`** - **Select Machines By**<br>
`string`. Optional. Use when `Destination = AzureVMs`. Allowed values: `machineNames` (Machine Names), `tags`. Default value: `machineNames`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a VM host name or tag that identifies a subset of VMs in a resource group. [Tags](/azure/virtual-machines/tag-template) are supported for resources created via the Azure Resource Manager only.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MachineNames"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`MachineNames`** - **Filter Criteria**<br>
`string`. Optional. Use when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a list of VM names or tag names that identify the VMs the task will target. Valid filter criteria includes:

- The name of an [Azure Resource Group](/azure/azure-resource-manager/management/overview).
- An output variable from a previous task.
- A comma-delimited list of tag names or VM names.
- Format VM names using a comma-separated list of FQDNs or IP addresses.
- Format tag names for a filter as `{TagName}:{Value}`. Example: `Role:DB;OS:Win8.1`, `ffweb`, `ffdb`, or tags like `Role:DB`, `Web`, `OS:Win8.1`.

Note: Valid delimiters for tags include &#44;(comma), &#58;(colon) and &#59;(semicolon). When providing multiple tags, the task will run only in the VMs that contain the specified tags. By default, the task runs in all VMs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmsAdminUserName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`vmsAdminUserName`** - **Admin Login**<br>
`string`. Required when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the user name of an account with administrative permissions on all of the target VMs.

- Supported formats include: `username`, `domain\username`, `machine-name\username`, and `.\username`.
- UPN formats including `username@domain.com` and built-in system accounts such as `NT Authority\System` are not supported.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmsAdminPassword"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`vmsAdminPassword`** - **Password**<br>
`string`. Required when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the administrator password of the VMs. 

Valid input includes variables defined in build or release pipelines such as `$(passwordVariable)`. To secure a password, mark it as `secret`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`TargetPath`** - **Destination Folder**<br>
`string`. Required when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path to the folder in the Azure VMs into which files will be copied.

Environment variables such as `$env:windir` and `$env:systemroot` are supported. Examples: `$env:windir\FabrikamFiber\Web` and `c:\FabrikamFiber`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsForBlobCopy"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`AdditionalArgumentsForBlobCopy`** - **Optional Arguments (for uploading files to blob)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide additional arguments to `AzCopy.exe` that can be applied when uploading to Blobs such as `/NC:10`. 

If no optional arguments are specified, the following arguments are added by default.

- `/Y`
- `/SetContentType`
- `/Z`
- `/V`
- `/S` - Added when the container name is not `$root`.
- `/BlobType:page` -Added when the specified storage account is a premium account.
- `/Pattern` - Added when the source path is a file. Included with any other specified optional arguments.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsForVMCopy"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`AdditionalArgumentsForVMCopy`** - **Optional Arguments (for downloading files to VM)**<br>
`string`. Optional. Use when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide additional arguments to `AzCopy.exe` that can be applied when downloading to VMs such as `/NC:10`. 

If no optional arguments are specified, the following are added by default.

- `/Y`
- `/S`
- `/Z`
- `/V`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableCopyPrerequisites"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`enableCopyPrerequisites`** - **Enable Copy Prerequisites**<br>
`boolean`. Optional. Use when `Destination = AzureVMs`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When enabled, uses a self-signed certificate to configure a Windows Remote Management (WinRM) listener on port 5986 instead of the HTTPS protocol. Required for performing copy operation on Azure VMs. If the target VMs use a load balancer, configure inbound NAT rules for the target port (5986). Applies only for ARM VMs. On target VMs associated with a Network Security Group (NSG), configure an inbound security rule to allow access on port 5986.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CopyFilesInParallel"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`CopyFilesInParallel`** - **Copy in Parallel**<br>
`boolean`. Optional. Use when `Destination = AzureVMs`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify `true` to copy files in parallel to the target VMs. Using this value can reduce the overall time taken to perform the action.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CleanTargetBeforeCopy"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`CleanTargetBeforeCopy`** - **Clean Target**<br>
`boolean`. Optional. Use when `Destination = AzureVMs`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Setting this value to `true` cleans the destination folder before performing the copy action.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipCACheck"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`skipCACheck`** - **Test Certificate**<br>
`boolean`. Optional. Use when `Destination = AzureVMs`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The default value will not validate if the server certificate was signed by a trusted CA before connecting over HTTPS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputStorageUri"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`outputStorageUri`** - **Storage Container URI**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the variable used for the storage container URI to which files were copied.  Valid only when the selected destination is an Azure Blob.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputStorageContainerSasToken"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`outputStorageContainerSasToken`** - **Storage Container SAS Token**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the variable used for the storage container SAS token that accesses the files that were copied. Use this variable as an input to subsequent tasks. By default, the SAS token expires after 4 hours.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sasTokenTimeOutInMinutes"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`sasTokenTimeOutInMinutes`** - **SAS Token Expiration Period In Minutes**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the time in minutes after which the SAS token will expire. Valid only when the selected destination is Azure Blob.
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

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

What's new in Version AzureFileCopy@3

- AzureFileCopy@3 supports Az Module and stopped supporting the Azure classic service endpoint.

- The task is used to copy application files and other artifacts that are required to install the app such as PowerShell scripts, PowerShell-DSC modules, and more.

- When the target is Azure VMs, the files are first copied to an automatically generated Azure Blob container and then downloaded into the VMs. The container is deleted after the files are successfully copied to the VMs.

- The task uses **AzCopy**, the command-line utility built to quickly copy of data from and into Azure storage accounts. The task version 3 or below uses AzCopy V7.

- To dynamically deploy Azure Resource Groups that contain virtual machines, use the [Azure Resource Group Deployment](azure-resource-group-deployment-v2.md) task. This task has a sample template that can perform the required operations to set up the WinRM HTTPS
protocol on VMs, open port 5986 in the firewall, and install the test certificate.

> [!NOTE]
> If you're deploying to Azure Static Websites as a container in Blob storage,
  use **Version 2** or higher in order to preserve the **$web**
  container name.

### FAQ
#### What are the Azure PowerShell prerequisites for using this task?

The task requires that Azure PowerShell is installed on the machine running the automation agent. The recommended version is 1.0.2, but the task works with version 0.9.8 and higher. Use [Azure PowerShell Installer v1.0.2](https://github.com/Azure/azure-powershell/releases/tag/v1.0.2-December2015) to get the recommended version.

#### What are the WinRM prerequisites for this task?

The task uses the WinRM HTTPS protocol to copy the files from the storage Blob container to the Azure VMs. The WinRM HTTPS service must be configured on the VMs, and a suitable certificate installed.

If the VMs are created without opening the WinRM HTTPS ports, follow these steps:

1. Configure an inbound access rule to allow HTTPS on port 5986 of each VM.
1. Disable [UAC remote restrictions](https://support.microsoft.com/kb/951016).
1. Specify the credentials for the task to access the VMs using an administrator-level login formatted as **username** without any domain reference.
1. Install a certificate on the machine that runs the automation agent.
1. Set the **Test Certificate** parameter of the task for a self-signed certificate.

#### What type of service connection should I choose?

The following table lists storage account types and the associated service connections. To identify whether a storage account is based on the classic APIs or the Resource Manager APIs, log into the [Azure portal](https://portal.azure.com/) and search for **Storage accounts (Classic)** or **Storage accounts**.

| Storage account type | Azure Service Connections in TFS/TS |
| --- | --- |
| Resource Manager | Azure Resource Manager service connection |
| Classic | Azure service connection with certificate-based or credentials-based authentication using a school or work account |

- For Azure classic resources, use an **Azure** service connection type with certificate or credentials-based authentication. If you're using credentials-based authentication, ensure that the credentials are for a [school or work account](https://azure.microsoft.com/pricing/member-offers/msdn-benefits-details/work-accounts-faq/). Microsoft accounts such as `joe@live.com` and `joe@hotmail.com` are not supported.
  
- For Azure Resource Manager VMs, use an **Azure Resource Manager** service connection type. For more details, see [Automating Azure Resource Group deployment using a Service Principal](https://devblogs.microsoft.com/devops/automating-azure-resource-group-deployment-using-a-service-principal-in-visual-studio-online-buildrelease-management/).
  
- If using an **Azure Resource Manager** service connection type, or an **Azure** service connection type with certificate-based authentication, the task automatically filters the appropriate classic storage accounts, newer Azure Resource Manager storage accounts, and other fields. For example, the Resource Group or cloud service, and the virtual machines.

> [!NOTE]
> Currently an **Azure** service connection type with credentials-based authentication does not filter the storage, Resource Group or cloud service, and virtual machine fields.

#### How do I fix failure '403: This request is not authorized to perform this operation using this permission'?

When Azure DevOps creates and authorizes the service connection to Azure, it creates an App Registration in your subscription's Active Directory. This identity is automatically added with a `Contributor` role to all resources in the Resource Group you chose to authorize. In order to upload Blobs to a storage account, being a `Contributor` is *not enough*. You must manually assign the [`Storage Blob Data Contributor` role to the app registration identity](/azure/storage/common/storage-auth-aad-rbac-portal).

Copy the app identity from the existing inherited entry as `Contributor` that you'll see in the IAM pane and search explicitly for it in the `Add role assignment` UI. The identity is not listed in the dropdown, you must search for its identifier.

#### What happens if my Resource Group contains both Classic and Resource Manager VMs?

If the specified Resource Group contains both Azure Resource Manager and Classic VMs, the set of VMs that are targeted depends on the connection type. 

- For certificate-based connections and credentials-based connections, the copy operation is only performed on Classic VMs.
- For Service Principal Name based connections, the copy operation is performed only on Resource Manager VMs.

#### How do I create a school or work account for use with this task?

A suitable account can be easily created for use in a service connection:

1. Use the Azure portal to create a new user account in Azure Active Directory.
1. Add the Azure Active Directory user account to the co-administrators group in your Azure subscription.
1. Sign into the Azure portal with this user account and change the password.
1. Use the new credentials for this account in the service connection. Deployments will be processed using this account.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yml
# Example: Upload files from Pipeline staging directory to blob storage.
- task: AzureFileCopy@3
  displayName: 'Example Step Name'
  inputs:
    sourcePath: '$(Build.ArtifactStagingDirectory)/BlobsToUpload'
    additionalArgumentsForBlobCopy: |
      '/Y' # Supresses all AZCopy Confirmations. Used here to allow overwrites
      '/Pattern:*' # Pattern of files to copy.
      '/S' # Recursive Copy
    azureSubscription: 'Subscription Name'
    destination: AzureBlob
    storage: storageaccountname
    containerName: storagecontainername
    blobPrefix: targetdirectoryincontainer
```
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
