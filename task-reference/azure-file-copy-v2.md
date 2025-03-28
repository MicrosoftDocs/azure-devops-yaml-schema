---
title: AzureFileCopy@2 - Azure file copy v2 task
description: Copy files to Azure Blob Storage or virtual machines (task version 2).
ms.date: 03/28/2025
monikerRange: "<=azure-pipelines"
---

# AzureFileCopy@2 - Azure file copy v2 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Copy files to Azure Blob Storage or virtual machines.

This task is deprecated as this version of the AzureFileCopy task uses a retired version of AzCopy. Use the latest version of the AzureFileCopy task. See [AzCopy Migration Guide for v8 to v10](https://github.com/Azure/azure-storage-azcopy/blob/main/MigrationGuideV8toV10.md).

[!INCLUDE [workload-identity](./includes/workload-identity-not-supported.md)]
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Copy files to Azure Blob Storage or virtual machines.

[!INCLUDE [workload-identity](./includes/workload-identity-not-supported.md)]
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Azure file copy v2
# Copy files to Azure Blob Storage or virtual machines.
- task: AzureFileCopy@2
  inputs:
    SourcePath: # string. Required. Source. 
    #azureConnectionType: 'ConnectedServiceNameARM' # 'ConnectedServiceName' | 'ConnectedServiceNameARM'. Alias: ConnectedServiceNameSelector. Azure Connection Type. Default: ConnectedServiceNameARM.
    #azureClassicSubscription: # string. Alias: ConnectedServiceName. Required when ConnectedServiceNameSelector = ConnectedServiceName. Azure Classic Subscription. 
    azureSubscription: # string. Alias: ConnectedServiceNameARM. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. Azure Subscription. 
    Destination: # 'AzureBlob' | 'AzureVMs'. Required. Destination Type. 
    #classicStorage: # string. Alias: StorageAccount. Required when ConnectedServiceNameSelector = ConnectedServiceName. Classic Storage Account. 
    storage: # string. Alias: StorageAccountRM. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM. RM Storage Account. 
    #ContainerName: # string. Required when Destination = AzureBlob. Container Name. 
    #BlobPrefix: # string. Optional. Use when Destination = AzureBlob. Blob Prefix. 
    #cloudService: # string. Alias: EnvironmentName. Required when ConnectedServiceNameSelector = ConnectedServiceName && Destination = AzureVMs. Cloud Service. 
    #resourceGroup: # string. Alias: EnvironmentNameRM. Required when ConnectedServiceNameSelector = ConnectedServiceNameARM && Destination = AzureVMs. Resource Group. 
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Optional. Use when Destination = AzureVMs. Select Machines By. Default: machineNames.
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
:::moniker range="<=azure-pipelines"

**`SourcePath`** - **Source**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the absolute path to the source folder, file on the local machine, or a UNC share. The specified value or expression should return either a single folder name or a file name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureConnectionType"::: -->
:::moniker range="<=azure-pipelines"

**`azureConnectionType`** - **Azure Connection Type**<br>
[Input alias](index.md#what-are-task-input-aliases): `ConnectedServiceNameSelector`. `string`. Allowed values: `ConnectedServiceName` (Azure Classic), `ConnectedServiceNameARM` (Azure Resource Manager). Default value: `ConnectedServiceNameARM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the Azure connection type.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureClassicSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureClassicSubscription`** - **Azure Classic Subscription**<br>
[Input alias](index.md#what-are-task-input-aliases): `ConnectedServiceName`. `string`. Required when `ConnectedServiceNameSelector = ConnectedServiceName`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the target Azure Classic subscription.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure Subscription**<br>
[Input alias](index.md#what-are-task-input-aliases): `ConnectedServiceNameARM`. `string`. Required when `ConnectedServiceNameSelector = ConnectedServiceNameARM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the target Azure Resource Manager subscription.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Destination"::: -->
:::moniker range="<=azure-pipelines"

**`Destination`** - **Destination Type**<br>
`string`. Required. Allowed values: `AzureBlob` (Azure Blob), `AzureVMs` (Azure VMs).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the destination type to use for copying the files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="classicStorage"::: -->
:::moniker range="<=azure-pipelines"

**`classicStorage`** - **Classic Storage Account**<br>
[Input alias](index.md#what-are-task-input-aliases): `StorageAccount`. `string`. Required when `ConnectedServiceNameSelector = ConnectedServiceName`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a pre-existing classic storage account. This is the storage account used as an intermediary for copying files to Azure VMs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="storage"::: -->
:::moniker range="<=azure-pipelines"

**`storage`** - **RM Storage Account**<br>
[Input alias](index.md#what-are-task-input-aliases): `StorageAccountRM`. `string`. Required when `ConnectedServiceNameSelector = ConnectedServiceNameARM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a pre-existing ARM storage account. This is the storage account used as an intermediary for copying files to Azure VMs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ContainerName"::: -->
:::moniker range="<=azure-pipelines"

**`ContainerName`** - **Container Name**<br>
`string`. Required when `Destination = AzureBlob`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the container into which files are copied. If the specified container does not exist in the storage account, it will be created.

To create a virtual directory inside the container, use the Blob prefix input. For example, for target location `https://myaccount.blob.core.windows.net/mycontainer/vd1/vd2/`, specify the container name `mycontainer` and Blob prefix `vd1/vd2`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="BlobPrefix"::: -->
:::moniker range="<=azure-pipelines"

**`BlobPrefix`** - **Blob Prefix**<br>
`string`. Optional. Use when `Destination = AzureBlob`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a prefix that can be used to filter files.

Example: You can append a build number to filter the files from all Blobs with the same build number.

Example: If you specify a Blob prefix `myvd1`, a virtual directory is created inside the container. Files are copied from the source to `https://myaccount.blob.core.windows.net/mycontainer/myvd1/`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cloudService"::: -->
:::moniker range="<=azure-pipelines"

**`cloudService`** - **Cloud Service**<br>
[Input alias](index.md#what-are-task-input-aliases): `EnvironmentName`. `string`. Required when `ConnectedServiceNameSelector = ConnectedServiceName && Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the target Cloud Service.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroup"::: -->
:::moniker range="<=azure-pipelines"

**`resourceGroup`** - **Resource Group**<br>
[Input alias](index.md#what-are-task-input-aliases): `EnvironmentNameRM`. `string`. Required when `ConnectedServiceNameSelector = ConnectedServiceNameARM && Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the target Resource Group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceFilteringMethod"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceFilteringMethod`** - **Select Machines By**<br>
`string`. Optional. Use when `Destination = AzureVMs`. Allowed values: `machineNames` (Machine Names), `tags`. Default value: `machineNames`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the VM host name or tag that identifies a subset of VMs in a resource group. [Tags](/azure/virtual-machines/tag-template) are supported for resources created via the Azure Resource Manager only.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MachineNames"::: -->
:::moniker range="<=azure-pipelines"

**`MachineNames`** - **Filter Criteria**<br>
`string`. Optional. Use when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a list of Azure VM host names such as `ffweb`, `ffdb`, or tags such as `Role:DB`, `Web`, `OS:Win8.1`.

Note: Valid delimiters for tags include &#44;(comma), &#58;(colon) and &#59;(semicolon). When providing multiple tags, the task will run in all the VMs that contains the specified tags. By default, the task runs in all the VMs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmsAdminUserName"::: -->
:::moniker range="<=azure-pipelines"

**`vmsAdminUserName`** - **Admin Login**<br>
`string`. Required when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the user name of the Azure VM administrator account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmsAdminPassword"::: -->
:::moniker range="<=azure-pipelines"

**`vmsAdminPassword`** - **Password**<br>
`string`. Required when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the password for the Azure VM administrator account.

Valid input includes variables defined in build or release pipelines such as `$(passwordVariable)`. To secure a password, mark it as `secret`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetPath"::: -->
:::moniker range="<=azure-pipelines"

**`TargetPath`** - **Destination Folder**<br>
`string`. Required when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the local path on the target VMs.

Valid input includes environment variables such as `$env:windir\BudgetIT\Web`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsForBlobCopy"::: -->
:::moniker range="<=azure-pipelines"

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
- `/BlobType:page` - Added when the specified storage account is a premium account.
- `/Pattern` - Added when the source path is a file. Included with any other specified optional arguments.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsForVMCopy"::: -->
:::moniker range="<=azure-pipelines"

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
:::moniker range="<=azure-pipelines"

**`enableCopyPrerequisites`** - **Enable Copy Prerequisites**<br>
`boolean`. Optional. Use when `ConnectedServiceNameSelector = ConnectedServiceNameARM && Destination = AzureVMs`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When enabled, uses a self-signed certificate to configure a Windows Remote Management (WinRM) listener on port 5986 instead of the HTTPS protocol. Required for performing copy operations on Azure VMs. If the target VMs use a load balancer, configure inbound NAT rules for the target port (5986). Applies only for ARM VMs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CopyFilesInParallel"::: -->
:::moniker range="<=azure-pipelines"

**`CopyFilesInParallel`** - **Copy in Parallel**<br>
`boolean`. Optional. Use when `Destination = AzureVMs`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Accepting the default setting copies files in parallel to the target VMs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CleanTargetBeforeCopy"::: -->
:::moniker range="<=azure-pipelines"

**`CleanTargetBeforeCopy`** - **Clean Target**<br>
`boolean`. Optional. Use when `Destination = AzureVMs`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Setting this value to `true` cleans the destination folder before performing the copy action.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipCACheck"::: -->
:::moniker range="<=azure-pipelines"

**`skipCACheck`** - **Test Certificate**<br>
`boolean`. Optional. Use when `Destination = AzureVMs`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The default value will not validate that the server certificate was signed by a trusted CA before connecting over HTTPS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputStorageUri"::: -->
:::moniker range="<=azure-pipelines"

**`outputStorageUri`** - **Storage Container URI**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the variable used for the storage container URI to which files were copied.  Valid only when the selected destination is an Azure Blob.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputStorageContainerSasToken"::: -->
:::moniker range="<=azure-pipelines"

**`outputStorageContainerSasToken`** - **Storage Container SAS Token**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the variable used for the storage container SAS token that accesses the files that were copied.  Valid only when the selected destination is an Azure Blob.
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

:::moniker range="<=azure-pipelines"

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