---
title: AzureFileCopy@4 - Azure file copy v4 task
description: Copy files to Azure Blob Storage or virtual machines.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2020"
---

# AzureFileCopy@4 - Azure file copy v4 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Copy files to Azure Blob Storage or virtual machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Azure file copy v4
# Copy files to Azure Blob Storage or virtual machines.
- task: AzureFileCopy@4
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
    #sasTokenTimeOutInMinutes: '240' # string. Optional. Use when Destination = AzureBlob. SAS Token Expiration Period In Minutes. Default: '240'.
    #enableCopyPrerequisites: false # boolean. Optional. Use when Destination = AzureVMs. Enable Copy Prerequisites. Default: false.
    #CopyFilesInParallel: true # boolean. Optional. Use when Destination = AzureVMs. Copy in Parallel. Default: true.
    #CleanTargetBeforeCopy: false # boolean. Optional. Use when Destination = AzureVMs. Clean Target. Default: false.
    #skipCACheck: true # boolean. Optional. Use when Destination = AzureVMs. Test Certificate. Default: true.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="SourcePath"::: -->
:::moniker range=">=azure-pipelines-2020"

**`SourcePath`** - **Source**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Absolute path of the source folder, or file on the local machine, or a UNC share. Expression should return a single folder or a file. Wild card symbol (*) is supported anywhere in the file path or file name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2020"

**`azureSubscription`** - **Azure Subscription**<br>
Input alias: `ConnectedServiceNameARM`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Resource Manager subscription to target for copying the files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Destination"::: -->
:::moniker range=">=azure-pipelines-2020"

**`Destination`** - **Destination Type**<br>
Type: string. Required. Allowed values: 'AzureBlob', 'AzureVMs'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the destination, either Azure Blob or Azure VMs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="storage"::: -->
:::moniker range=">=azure-pipelines-2020"

**`storage`** - **RM Storage Account**<br>
Input alias: `StorageAccountRM`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a pre-existing ARM storage account. It is also used as an intermediary for copying files to Azure VMs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ContainerName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`ContainerName`** - **Container Name**<br>
Type: string. Required when Destination = AzureBlob.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the Container for uploading the files. If a container with the given name does not exist in the specified storage account, it will automatically be created. <br> If you need to create a virtual directory inside the container, use the blob prefix input below. <br> Example: If your target location is <i>https://myaccount.blob.core.windows.net/mycontainer/vd1/vd2/</i>, then specify <i>mycontainer</i> as container name and <i>vd1/vd2</i> as blob prefix.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="BlobPrefix"::: -->
:::moniker range=">=azure-pipelines-2020"

**`BlobPrefix`** - **Blob Prefix**<br>
Type: string. Optional. Use when Destination = AzureBlob.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Useful for filtering files, for example, append build number to all the blobs to download files from that build only. Example: If you specify blob prefix as <i>myvd1</i>, a virtual directory with this name will be created inside the container. The source files will be copied to <i>https://myaccount.blob.core.windows.net/mycontainer/myvd1/</i>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroup"::: -->
:::moniker range=">=azure-pipelines-2020"

**`resourceGroup`** - **Resource Group**<br>
Input alias: `EnvironmentNameRM`. Type: string. Required when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the target Resource Group for copying files to.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceFilteringMethod"::: -->
:::moniker range=">=azure-pipelines-2020"

**`ResourceFilteringMethod`** - **Select Machines By**<br>
Type: string. Optional. Use when Destination = AzureVMs. Allowed values: 'machineNames', 'tags'. Default value: 'machineNames'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally, select a subset of VMs in resource group either by providing VMs host name or tags. [Tags](/azure/virtual-machines/tag-template) are supported for resources created via the Azure Resource Manager only.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MachineNames"::: -->
:::moniker range=">=azure-pipelines-2020"

**`MachineNames`** - **Filter Criteria**<br>
Type: string. Optional. Use when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a list of VMs host name like ffweb, ffdb, or tags like Role:DB, Web; OS:Win8.1. Note the delimiters used for tags are &#44;(comma), &#58;(colon) and &#59;(semicolon). If multiple tags are provided, then the task will run in all the VMs with the specified tags. The default is to run the task in all the VMs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmsAdminUserName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`vmsAdminUserName`** - **Admin Login**<br>
Type: string. Required when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator Username of the VMs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmsAdminPassword"::: -->
:::moniker range=">=azure-pipelines-2020"

**`vmsAdminPassword`** - **Password**<br>
Type: string. Required when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The administrator password of the VMs. <br>It can accept variable defined in build or release pipelines as '$(passwordVariable)'. <br>You may mark variable as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetPath"::: -->
:::moniker range=">=azure-pipelines-2020"

**`TargetPath`** - **Destination Folder**<br>
Type: string. Required when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Local path on the target machines for copying the files from the source. Environment variable can be used like $env:windir\BudgetIT\Web.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsForBlobCopy"::: -->
:::moniker range=">=azure-pipelines-2020"

**`AdditionalArgumentsForBlobCopy`** - **Optional Arguments (for uploading files to blob)**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional AzCopy.exe arguments that will be applied when uploading to blob like, --check-length=true. If no optional arguments are specified here, the following optional arguments will be added by default.<br> --log-level=INFO (if the pipeline is running in debug mode set --log-level=DEBUG),<br> --recursive (only if container name is not $root),<br> --blob-type=PageBlob (only if specified storage account is a premium account).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsForVMCopy"::: -->
:::moniker range=">=azure-pipelines-2020"

**`AdditionalArgumentsForVMCopy`** - **Optional Arguments (for downloading files to VM)**<br>
Type: string. Optional. Use when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional AzCopy.exe arguments that will be applied when downloading to VM like,  --check-length=true. If no optional arguments are specified here, the following optional arguments will be added by default.<br> --log-level=INFO (if the pipeline is running in debug mode set --log-level=DEBUG),<br> --recursive.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sasTokenTimeOutInMinutes"::: -->
:::moniker range=">=azure-pipelines-2020"

**`sasTokenTimeOutInMinutes`** - **SAS Token Expiration Period In Minutes**<br>
Type: string. Optional. Use when Destination = AzureBlob. Default value: '240'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the time in minutes after which SAS token for the container will expire. By default, this token expires after 4 hours.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableCopyPrerequisites"::: -->
:::moniker range=">=azure-pipelines-2020"

**`enableCopyPrerequisites`** - **Enable Copy Prerequisites**<br>
Type: boolean. Optional. Use when Destination = AzureVMs. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enabling this option configures Windows Remote Management (WinRM) listener over HTTPS protocol on port 5986, using a self-signed certificate. This configuration is required for performing copy operation on Azure machines. If the target Virtual Machines are backed by a Load balancer, ensure Inbound NAT rules are configured for target port (5986). Applicable only for ARM VMs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CopyFilesInParallel"::: -->
:::moniker range=">=azure-pipelines-2020"

**`CopyFilesInParallel`** - **Copy in Parallel**<br>
Type: boolean. Optional. Use when Destination = AzureVMs. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Setting it to true will copy files in parallel to the target machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CleanTargetBeforeCopy"::: -->
:::moniker range=">=azure-pipelines-2020"

**`CleanTargetBeforeCopy`** - **Clean Target**<br>
Type: boolean. Optional. Use when Destination = AzureVMs. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Setting it to true will clean-up the destination folder before copying the files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipCACheck"::: -->
:::moniker range=">=azure-pipelines-2020"

**`skipCACheck`** - **Test Certificate**<br>
Type: boolean. Optional. Use when Destination = AzureVMs. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this option is selected, client skips the validation that the server certificate is signed by a trusted certificate authority (CA) when connecting over Hypertext Transfer Protocol over Secure Socket Layer (HTTPS).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="StorageContainerUri"::: -->
**`StorageContainerUri`**<br><!-- :::editable-content name="Value"::: -->
Uri of the container where the files were copied to. Valid only when the selected destination is Azure Blob.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="StorageContainerSasToken"::: -->
**`StorageContainerSasToken`**<br><!-- :::editable-content name="Value"::: -->
SasToken for the container where the files were copied to. Valid only when the selected destination is Azure Blob.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

AzureFileCopy@4 supports AzCopy.exe version 10.8.0.

> [!NOTE]
> This task is written in PowerShell and thus works **only** when run on Windows agents. If your pipelines require Linux agents and need to copy files to an Azure Storage Account, consider running `az storage blob` commands in the [Azure CLI task](azure-cli-v2.md) as an alternative.

The task is used to copy application files and other artifacts that are required in order to install the app; such as PowerShell scripts, PowerShell-DSC modules, and more.

When the target is Azure VMs, the files are first copied
to an automatically generated Azure blob container 
and then downloaded into the VMs. The container is deleted 
after the files have been successfully copied to the VMs.

The task uses **AzCopy**, the command-line utility 
built for fast copying of data from and into Azure storage accounts. Version 4 of the Azure File Copy task uses [AzCopy V10](/azure/storage/common/storage-use-azcopy-v10).

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

The task supports authentication based on Azure Active Directory. Authentication using a service principal and managed identity are available. For managed identities, only system-wide managed identity is supported.
  
> [!NOTE]
> For authorization you will have to provide access to the Security Principal. The level of authorization required can be referred [here](/azure/storage/common/storage-use-azcopy-v10#option-1-use-azure-active-directory).

### What are the Azure PowerShell prerequisites for using this task?

The task requires Azure PowerShell to be installed 
on the machine running the automation agent. The 
recommended version is 1.0.2, but the task will work
with version 0.9.8 and higher. You can use the
[Azure PowerShell Installer v1.0.2](https://github.com/Azure/azure-powershell/releases/tag/v1.0.2-December2015)
to obtain this.

### What are the WinRM prerequisites for this task?

The task uses Windows Remote Management (WinRM) HTTPS protocol to
copy the files from the storage blob container to the Azure VMs.
This requires the WinRM HTTPS service to be configured on the VMs,
and a suitable certificate installed. 

### Configure WinRM after virtual machine creation

If the VMs have been created without opening the 
WinRM HTTPS ports, follow these steps:

1. Configure an inbound access rule to allow HTTPS on port 5986 of each VM.
1. Disable [UAC remote restrictions](https://support.microsoft.com/kb/951016).
1. Specify the credentials for the task to access the VMs using an administrator-level login in the simple form **username** without any domain part.
1. Install a certificate on the machine that runs the automation agent.
1. Set the **Test Certificate** parameter of the task if you are using a self-signed certificate.

### What type of service connection should I choose?
  
* For Azure Resource Manager storage accounts and Azure Resource Manager VMs, use an **Azure Resource Manager** service connection type. See more details at [Automating Azure Resource Group deployment using a Service Principal](https://devblogs.microsoft.com/devops/automating-azure-resource-group-deployment-using-a-service-principal-in-visual-studio-online-buildrelease-management/).
  
* While using an **Azure Resource Manager** 
  service connection type, the task
  automatically filters appropriate newer Azure Resource Manager storage 
  accounts, and other fields. For example, the Resource
  Group or cloud service, and the virtual machines.

### How do I create a school or work account for use with this task?

A suitable account can be easily created for use in a service connection:

1. Use the Azure portal to create a new user account in Azure Active Directory.
1. Add the Azure Active Directory user account to the co-administrators group in your Azure subscription.
1. Sign into the Azure portal with this user account and change the password.
1. Use the username and password of this account in the service connection. Deployments will be processed using this account.

### If the task fails, will the copy resume?

Since AzCopy V10 does not support journal files, the task cannot resume the copy. You will have to run the task again to copy all the files.

### Are the log files and plan files cleaned after the copy?

The log and plan files are not deleted by the task. To explicitly clean up the files you can add a CLI step in the workflow using [this command](/azure/storage/common/storage-ref-azcopy-jobs-clean).

### How do I use the Azure file copy task to copy a file to an Azure virtual machine that doesn't have a public IP address?

Make sure that you're using version 4 of the Azure file copy task. If the task fails, you can add a build step to execute the command `azcopy cp "source-file-path" "destination-file-path"` to substitute the source and destination values.

### Forbidden error: 'AzCopy.exe exited with non-zero exit code while uploading files to blob storage' while using Azure File Copy task

The hosted agents are assigned randomly every time a build is triggered and hence the [agent IP addresses](/azure/devops/pipelines/agents/hosted#networking) will be different on every run. If these IP addresses are not in your allowed list of IPs, the communication between Azure DevOps and the storage account fails. In such scenarios, follow the below steps outlined:

1. Add a build step using Azure CLI, which will identify the IP of the Microsoft Hosted Build agent at runtime and it will add the IP address in the Network rule on the Azure Storage Account.
1. Execute the build step for your Azure Storage Account.
1. Add another build step using Azure CLI, which will remove the IP address of the build agent from the Azure Storage Account network rule which was added earlier.
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