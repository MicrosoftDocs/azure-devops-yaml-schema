---
title: AzureFileCopy@5 - Azure file copy v5 task
description: Copy files to Azure Blob Storage or virtual machines.
ms.date: 10/13/2022
monikerRange: "=azure-pipelines"
---

# AzureFileCopy@5 - Azure file copy v5 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Copy files to Azure Blob Storage or virtual machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure file copy v5
# Copy files to Azure Blob Storage or virtual machines.
- task: AzureFileCopy@5
  inputs:
    SourcePath: # string. Required. Source. 
    azureSubscription: # string. Required. Azure Subscription. 
    Destination: # 'AzureBlob' | 'AzureVMs'. Required. Destination Type. 
    storage: # string. Required. RM Storage Account. 
    #ContainerName: # string. Required when Destination = AzureBlob. Container Name. 
    #BlobPrefix: # string. Optional. Use when Destination = AzureBlob. Blob Prefix. 
    #resourceGroup: # string. Required when Destination = AzureVMs. Resource Group. 
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Optional. Use when Destination = AzureVMs. Select Machines By. Default: machineNames.
    #MachineNames: # string. Optional. Use when Destination = AzureVMs. Filter Criteria. 
    #vmsAdminUserName: # string. Required when Destination = AzureVMs. Admin Login. 
    #vmsAdminPassword: # string. Required when Destination = AzureVMs. Password. 
    #TargetPath: # string. Required when Destination = AzureVMs. Destination Folder. 
    #AdditionalArgumentsForBlobCopy: # string. Optional Arguments (for uploading files to blob). 
    #AdditionalArgumentsForVMCopy: # string. Optional. Use when Destination = AzureVMs. Optional Arguments (for downloading files to VM). 
    #sasTokenTimeOutInMinutes: '240' # string. Optional. Use when Destination = AzureBlob. SAS Token Expiration Period In Minutes. Default: 240.
    #enableCopyPrerequisites: false # boolean. Optional. Use when Destination = AzureVMs. Enable Copy Prerequisites. Default: false.
    #CopyFilesInParallel: true # boolean. Optional. Use when Destination = AzureVMs. Copy in Parallel. Default: true.
    #CleanTargetBeforeCopy: false # boolean. Clean Target. Default: false.
    #skipCACheck: true # boolean. Optional. Use when Destination = AzureVMs. Test Certificate. Default: true.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="SourcePath"::: -->
:::moniker range="=azure-pipelines"

**`SourcePath`** - **Source**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The source of the files to copy. YAML Pipelines and Classic Release support [predefined system variables](/azure/devops/pipelines/build/variables?tabs=yaml) like *Build.Repository.LocalPath* as well. [Release variables](/azure/devops/pipelines/release/variables?tabs=batch) are supported only in classic releases. Wild card symbol (*) is supported anywhere in the file path or file name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscription`** - **Azure Subscription**<br>
Input alias: `ConnectedServiceNameARM`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of an [Azure Resource Manager service connection](/azure/devops/pipelines/library/connect-to-azure) configured for the subscription where the target Azure service, virtual machine, or storage account is located. See [Azure Resource Manager overview](/azure/azure-resource-manager/management/overview) for more details.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Destination"::: -->
:::moniker range="=azure-pipelines"

**`Destination`** - **Destination Type**<br>
`string`. Required. Allowed values: `AzureBlob` (Azure Blob), `AzureVMs` (Azure VMs).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the destination, either **Azure Blob** or **Azure VMs**.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="storage"::: -->
:::moniker range="=azure-pipelines"

**`storage`** - **RM Storage Account**<br>
Input alias: `StorageAccountRM`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a pre-existing ARM storage account. It is also used as an intermediary for copying files to Azure VMs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ContainerName"::: -->
:::moniker range="=azure-pipelines"

**`ContainerName`** - **Container Name**<br>
`string`. Required when `Destination = AzureBlob`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the Container for uploading the files. If a container with the given name does not exist in the specified storage account, it will automatically be created. <br> If you need to create a virtual directory inside the container, use the blob prefix input below. <br> Example: If your target location is <i>https://myaccount.blob.core.windows.net/mycontainer/vd1/vd2/</i>, then specify <i>mycontainer</i> as container name and <i>vd1/vd2</i> as blob prefix.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="BlobPrefix"::: -->
:::moniker range="=azure-pipelines"

**`BlobPrefix`** - **Blob Prefix**<br>
`string`. Optional. Use when `Destination = AzureBlob`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Useful for filtering files, for example, append build number to all the blobs to download files from that build only. Example: If you specify blob prefix as <i>myvd1</i>, a virtual directory with this name will be created inside the container. The source files will be copied to <i>https://myaccount.blob.core.windows.net/mycontainer/myvd1/</i>.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroup"::: -->
:::moniker range="=azure-pipelines"

**`resourceGroup`** - **Resource Group**<br>
Input alias: `EnvironmentNameRM`. `string`. Required when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the target Resource Group for copying files to.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceFilteringMethod"::: -->
:::moniker range="=azure-pipelines"

**`ResourceFilteringMethod`** - **Select Machines By**<br>
`string`. Optional. Use when `Destination = AzureVMs`. Allowed values: `machineNames` (Machine Names), `tags`. Default value: `machineNames`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally, select a subset of VMs in resource group either by providing VMs host name or tags. [Tags](/azure/virtual-machines/tag-template) are supported for resources created via the Azure Resource Manager only.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MachineNames"::: -->
:::moniker range="=azure-pipelines"

**`MachineNames`** - **Filter Criteria**<br>
`string`. Optional. Use when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A list of machine names or tag names that identifies the machines that the task will target. The filter criteria can be:

- The name of an [Azure Resource Group](/azure-resource-manager/management/overview).
- An output variable from a previous task.
- A comma-delimited list of tag names or machine names.
Format when using machine names is a comma-separated list of the machine FQDNs or IP addresses.
Specify tag names for a filter as {TagName}:{Value} Example: `Role:DB;OS:Win8.1`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmsAdminUserName"::: -->
:::moniker range="=azure-pipelines"

**`vmsAdminUserName`** - **Admin Login**<br>
`string`. Required when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The user name of an account that has administrative permissions for all the target VMs.

- Formats such as **username**, **domain\username**, **machine-name\username**, and **.\username** are supported.
- UPN formats such as **username@domain.com** and built-in system accounts such as **NT Authority\System** are not supported.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmsAdminPassword"::: -->
:::moniker range="=azure-pipelines"

**`vmsAdminPassword`** - **Password**<br>
`string`. Required when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The password for the account specified as the **Admin Login** parameter. Use the padlock icon for a variable defined in the **Variables** tab to protect the value, and insert the variable name here.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetPath"::: -->
:::moniker range="=azure-pipelines"

**`TargetPath`** - **Destination Folder**<br>
`string`. Required when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The folder in the Azure VMs to which the files will be copied. Environment variables such as `$env:windir` and `$env:systemroot` are supported. Examples: `$env:windir\FabrikamFiber\Web` and `c:\FabrikamFiber`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsForBlobCopy"::: -->
:::moniker range="=azure-pipelines"

**`AdditionalArgumentsForBlobCopy`** - **Optional Arguments (for uploading files to blob)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Any arguments you want to pass to the **AzCopy.exe** program for use when uploading to the blob and downloading to the VMs. See [Transfer data with the AzCopy Command-Line Utility](/azure/storage/common/storage-use-azcopy-v10) for more details. If you are using a Premium storage account, which supports only Azure page blobs, then pass '--blob-type=PageBlob' as an additional argument. The default arguments are --log-level=INFO (default) and --recursive (only if container name is not $root).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsForVMCopy"::: -->
:::moniker range="=azure-pipelines"

**`AdditionalArgumentsForVMCopy`** - **Optional Arguments (for downloading files to VM)**<br>
`string`. Optional. Use when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional AzCopy.exe arguments that will be applied when downloading to VM like,  `--check-length=true`. If no optional arguments are specified here, the following optional arguments will be added by default.<br> `--log-level=INFO` (if the pipeline is running in debug mode set `--log-level=DEBUG`),<br> `--recursive`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sasTokenTimeOutInMinutes"::: -->
:::moniker range="=azure-pipelines"

**`sasTokenTimeOutInMinutes`** - **SAS Token Expiration Period In Minutes**<br>
`string`. Optional. Use when `Destination = AzureBlob`. Default value: `240`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the time in minutes after which SAS token for the container will expire. By default, this token expires after 4 hours.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableCopyPrerequisites"::: -->
:::moniker range="=azure-pipelines"

**`enableCopyPrerequisites`** - **Enable Copy Prerequisites**<br>
`boolean`. Optional. Use when `Destination = AzureVMs`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Setting this option configures the Windows Remote Management (WinRM) listener over HTTPS protocol on port 5986, using a self-signed certificate. This configuration is required for performing copy operation on Azure virtual machines.

- If the target virtual machines are accessed through a load balancer, ensure an inbound NAT rule is configured to allow access on port 5986.
- If the target virtual machines are associated with a Network Security Group (NSG), configure an inbound security rule to allow access on port 5986.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CopyFilesInParallel"::: -->
:::moniker range="=azure-pipelines"

**`CopyFilesInParallel`** - **Copy in Parallel**<br>
`boolean`. Optional. Use when `Destination = AzureVMs`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Setting it to true will copy files in parallel to the target machines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CleanTargetBeforeCopy"::: -->
:::moniker range="=azure-pipelines"

**`CleanTargetBeforeCopy`** - **Clean Target**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Setting it to true will clean-up the destination folder before copying the files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipCACheck"::: -->
:::moniker range="=azure-pipelines"

**`skipCACheck`** - **Test Certificate**<br>
`boolean`. Optional. Use when `Destination = AzureVMs`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
WinRM requires a certificate for the HTTPS transfer when copying files from the intermediate storage blob into the Azure VMs. If you set use a self-signed certificate, set this option to prevent the process from validating the certificate with a trusted certificate authority (CA).
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

AzureFileCopy@5 supports AzCopy.exe version 10.12.2.

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
## Examples

```yml
- task: AzureFileCopy@5
  inputs:
    SourcePath: 'Readme.md'
    azureSubscription: 'Azure'
    Destination: 'AzureBlob'
    storage: 'storageAccount'
    ContainerName: 'containerName'
    BlobPrefix: ''
  name: AzureFileCopy
  
- script: | 
    echo $(AzureFileCopy.StorageContainerUri)
    echo $(AzureFileCopy.StorageContainerSasToken)
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="=azure-pipelines"

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