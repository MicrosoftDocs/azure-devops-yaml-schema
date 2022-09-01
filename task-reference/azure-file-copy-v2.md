---
title: AzureFileCopy@2 - Azure file copy v2 task
description: Copy files to Azure Blob Storage or virtual machines (task version 2).
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019"
---

# AzureFileCopy@2 - Azure file copy v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Copy files to Azure Blob Storage or virtual machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Azure file copy v2
# Copy files to Azure Blob Storage or virtual machines.
- task: AzureFileCopy@2
  inputs:
    SourcePath: # string. Required. Source. 
    #azureConnectionType: 'ConnectedServiceNameARM' # 'ConnectedServiceName' | 'ConnectedServiceNameARM'. Azure Connection Type. Default: 'ConnectedServiceNameARM'.
    #azureClassicSubscription: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Classic Subscription. 
    azureSubscription: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. Azure Subscription. 
    Destination: # 'AzureBlob' | 'AzureVMs'. Required. Destination Type. 
    #classicStorage: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName. Classic Storage Account. 
    storage: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. RM Storage Account. 
    #ContainerName: # string. Required when Destination = AzureBlob. Container Name. 
    #BlobPrefix: # string. Optional. Use when Destination = AzureBlob. Blob Prefix. 
    #cloudService: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName && Destination = AzureVMs. Cloud Service. 
    #resourceGroup: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM && Destination = AzureVMs. Resource Group. 
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Optional. Use when Destination = AzureVMs. Select Machines By. Default: 'machineNames'.
    #MachineNames: # string. Optional. Use when Destination = AzureVMs. Filter Criteria. 
    #vmsAdminUserName: # string. Required when Destination = AzureVMs. Admin Login. 
    #vmsAdminPassword: # string. Required when Destination = AzureVMs. Password. 
    #TargetPath: # string. Required when Destination = AzureVMs. Destination Folder. 
    #AdditionalArgumentsForBlobCopy: # string. Optional Arguments (for uploading files to blob). 
    #AdditionalArgumentsForVMCopy: # string. Optional. Use when Destination = AzureVMs. Optional Arguments (for downloading files to VM). 
    #enableCopyPrerequisites: false # boolean. Optional. Use when ConnectedServiceNameSelector = ConnectedServiceNameARM && Destination = AzureVMs. Enable Copy Prerequisites. Default: false.
    #CopyFilesInParallel: true # boolean. Optional. Use when Destination = AzureVMs. Copy in Parallel. Default: true.
    #CleanTargetBeforeCopy: false # boolean. Optional. Use when Destination = AzureVMs. Clean Target. Default: false.
    #skipCACheck: true # boolean. Optional. Use when Destination = AzureVMs. Test Certificate. Default: true.
  # Output
    #outputStorageUri: # string. Storage Container URI. 
    #outputStorageContainerSasToken: # string. Storage Container SAS Token.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Azure File Copy v2
# Copy files to Azure blob or VM(s).
- task: AzureFileCopy@2
  inputs:
    SourcePath: # string. Required. Source. 
    #azureConnectionType: 'ConnectedServiceNameARM' # 'ConnectedServiceName' | 'ConnectedServiceNameARM'. Azure Connection Type. Default: 'ConnectedServiceNameARM'.
    #azureClassicSubscription: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Classic Subscription. 
    azureSubscription: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. Azure Subscription. 
    Destination: # 'AzureBlob' | 'AzureVMs'. Required. Destination Type. 
    #classicStorage: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName. Classic Storage Account. 
    storage: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. RM Storage Account. 
    #ContainerName: # string. Required when Destination = AzureBlob. Container Name. 
    #BlobPrefix: # string. Optional. Use when Destination = AzureBlob. Blob Prefix. 
    #cloudService: # string. Required when ConnectedServiceNameSelector = ConnectedServiceName && Destination = AzureVMs. Cloud Service. 
    #resourceGroup: # string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM && Destination = AzureVMs. Resource Group. 
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Optional. Use when Destination = AzureVMs. Select Machines By. Default: 'machineNames'.
    #MachineNames: # string. Optional. Use when Destination = AzureVMs. Filter Criteria. 
    #vmsAdminUserName: # string. Required when Destination = AzureVMs. Admin Login. 
    #vmsAdminPassword: # string. Required when Destination = AzureVMs. Password. 
    #TargetPath: # string. Required when Destination = AzureVMs. Destination Folder. 
    #AdditionalArgumentsForBlobCopy: # string. Optional Arguments (for uploading files to blob). 
    #AdditionalArgumentsForVMCopy: # string. Optional. Use when Destination = AzureVMs. Optional Arguments (for downloading files to VM). 
    #enableCopyPrerequisites: false # boolean. Optional. Use when ConnectedServiceNameSelector = ConnectedServiceNameARM && Destination = AzureVMs. Enable Copy Prerequisites. Default: false.
    #CopyFilesInParallel: true # boolean. Optional. Use when Destination = AzureVMs. Copy in Parallel. Default: true.
    #CleanTargetBeforeCopy: false # boolean. Optional. Use when Destination = AzureVMs. Clean Target. Default: false.
    #skipCACheck: true # boolean. Optional. Use when Destination = AzureVMs. Test Certificate. Default: true.
  # Output
    #outputStorageUri: # string. Storage Container URI. 
    #outputStorageContainerSasToken: # string. Storage Container SAS Token.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="SourcePath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`SourcePath`** - **Source**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Absolute path of the source folder, or file on the local machine, or a UNC share. Expression should return a single folder or a file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureConnectionType"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureConnectionType`** - **Azure Connection Type**<br>
Input alias: `ConnectedServiceNameSelector`. Type: string. Allowed values: 'ConnectedServiceName', 'ConnectedServiceNameARM'. Default value: 'ConnectedServiceNameARM'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureClassicSubscription"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureClassicSubscription`** - **Azure Classic Subscription**<br>
Input alias: `ConnectedServiceName`. Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceName.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Classic subscription to target for copying the files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureSubscription`** - **Azure Subscription**<br>
Input alias: `ConnectedServiceNameARM`. Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Resource Manager subscription to target for copying the files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Destination"::: -->
:::moniker range=">=azure-pipelines-2019"

**`Destination`** - **Destination Type**<br>
Type: string. Required. Allowed values: 'AzureBlob', 'AzureVMs'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the destination, either Azure Blob or Azure VMs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="classicStorage"::: -->
:::moniker range=">=azure-pipelines-2019"

**`classicStorage`** - **Classic Storage Account**<br>
Input alias: `StorageAccount`. Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceName.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a pre-existing classic storage account. It is also used as an intermediary for copying files to Azure VMs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="storage"::: -->
:::moniker range=">=azure-pipelines-2019"

**`storage`** - **RM Storage Account**<br>
Input alias: `StorageAccountRM`. Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a pre-existing ARM storage account. It is also used as an intermediary for copying files to Azure VMs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ContainerName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ContainerName`** - **Container Name**<br>
Type: string. Required when Destination = AzureBlob.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the Container for uploading the files. If a container with the given name does not exist in the specified storage account, it will automatically be created. <br> If you need to create a virtual directory inside the container, use the blob prefix input below. <br> Example: If your target location is <i>https://myaccount.blob.core.windows.net/mycontainer/vd1/vd2/</i>, then specify <i>mycontainer</i> as container name and <i>vd1/vd2</i> as blob prefix.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="BlobPrefix"::: -->
:::moniker range=">=azure-pipelines-2019"

**`BlobPrefix`** - **Blob Prefix**<br>
Type: string. Optional. Use when Destination = AzureBlob.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Useful for filtering files, for example, append build number to all the blobs to download files from that build only. Example: If you specify blob prefix as <i>myvd1</i>, a virtual directory with this name will be created inside the container. The source files will be copied to <i>https://myaccount.blob.core.windows.net/mycontainer/myvd1/</i>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cloudService"::: -->
:::moniker range=">=azure-pipelines-2019"

**`cloudService`** - **Cloud Service**<br>
Input alias: `EnvironmentName`. Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceName && Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the target Cloud Service for copying files to.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroup"::: -->
:::moniker range=">=azure-pipelines-2019"

**`resourceGroup`** - **Resource Group**<br>
Input alias: `EnvironmentNameRM`. Type: string. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM && Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the target Resource Group for copying files to.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceFilteringMethod"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ResourceFilteringMethod`** - **Select Machines By**<br>
Type: string. Optional. Use when Destination = AzureVMs. Allowed values: 'machineNames', 'tags'. Default value: 'machineNames'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally, select a subset of VMs in resource group either by providing VMs host name or tags. [Tags](/azure/virtual-machines/tag-template) are supported for resources created via the Azure Resource Manager only.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MachineNames"::: -->
:::moniker range=">=azure-pipelines-2019"

**`MachineNames`** - **Filter Criteria**<br>
Type: string. Optional. Use when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a list of VMs host name like ffweb, ffdb, or tags like Role:DB, Web; OS:Win8.1. Note the delimiters used for tags are &#44;(comma), &#58;(colon) and &#59;(semicolon). If multiple tags are provided, then the task will run in all the VMs with the specified tags. The default is to run the task in all the VMs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmsAdminUserName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`vmsAdminUserName`** - **Admin Login**<br>
Type: string. Required when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator Username of the VMs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmsAdminPassword"::: -->
:::moniker range=">=azure-pipelines-2019"

**`vmsAdminPassword`** - **Password**<br>
Type: string. Required when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The administrator password of the VMs. <br>It can accept variable defined in build or release pipelines as '$(passwordVariable)'. <br>You may mark variable as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`TargetPath`** - **Destination Folder**<br>
Type: string. Required when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Local path on the target machines for copying the files from the source. Environment variable can be used like $env:windir\BudgetIT\Web.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsForBlobCopy"::: -->
:::moniker range=">=azure-pipelines-2019"

**`AdditionalArgumentsForBlobCopy`** - **Optional Arguments (for uploading files to blob)**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional AzCopy.exe arguments that will be applied when uploading to blob like, /NC:10. If no optional arguments are specified here, the following optional arguments will be added by default.<br> /Y, /SetContentType, /Z, /V,<br> /S (only if container name is not $root),<br> /BlobType:page (only if specified storage account is a premium account).<br> If source path is a file, /Pattern will always be added irrespective of whether or not you have specified optional arguments.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsForVMCopy"::: -->
:::moniker range=">=azure-pipelines-2019"

**`AdditionalArgumentsForVMCopy`** - **Optional Arguments (for downloading files to VM)**<br>
Type: string. Optional. Use when Destination = AzureVMs.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional AzCopy.exe arguments that will be applied when downloading to VM like, /NC:10. If no optional arguments are specified here, the following optional arguments will be added by default.<br> /Y, /S, /Z, /V.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableCopyPrerequisites"::: -->
:::moniker range=">=azure-pipelines-2019"

**`enableCopyPrerequisites`** - **Enable Copy Prerequisites**<br>
Type: boolean. Optional. Use when ConnectedServiceNameSelector = ConnectedServiceNameARM && Destination = AzureVMs. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enabling this option configures Windows Remote Management (WinRM) listener over HTTPS protocol on port 5986, using a self-signed certificate. This configuration is required for performing copy operation on Azure machines. If the target Virtual Machines are backed by a Load balancer, ensure Inbound NAT rules are configured for target port (5986). Applicable only for ARM VMs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CopyFilesInParallel"::: -->
:::moniker range=">=azure-pipelines-2019"

**`CopyFilesInParallel`** - **Copy in Parallel**<br>
Type: boolean. Optional. Use when Destination = AzureVMs. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Setting it to true will copy files in parallel to the target machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CleanTargetBeforeCopy"::: -->
:::moniker range=">=azure-pipelines-2019"

**`CleanTargetBeforeCopy`** - **Clean Target**<br>
Type: boolean. Optional. Use when Destination = AzureVMs. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Setting it to true will clean-up the destination folder before copying the files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipCACheck"::: -->
:::moniker range=">=azure-pipelines-2019"

**`skipCACheck`** - **Test Certificate**<br>
Type: boolean. Optional. Use when Destination = AzureVMs. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this option is selected, client skips the validation that the server certificate is signed by a trusted certificate authority (CA) when connecting over Hypertext Transfer Protocol over Secure Socket Layer (HTTPS).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputStorageUri"::: -->
:::moniker range=">=azure-pipelines-2019"

**`outputStorageUri`** - **Storage Container URI**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the variable for the storage container URI that the files were copied to with this task.  Valid only when the selected destination is Azure Blob.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputStorageContainerSasToken"::: -->
:::moniker range=">=azure-pipelines-2019"

**`outputStorageContainerSasToken`** - **Storage Container SAS Token**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the variable for the storage container SAS Token used to access the files copied to with this task.  Valid only when the selected destination is Azure Blob.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

What's new in Version 2.0: 
    Using newer version of AzCopy.
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