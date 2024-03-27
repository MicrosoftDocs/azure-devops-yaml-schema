---
title: AzureFileCopy@6 - Azure file copy v6 task
description: Copy files to Azure Blob Storage or virtual machines.
ms.date: 03/27/2024
monikerRange: "=azure-pipelines"
---

# AzureFileCopy@6 - Azure file copy v6 task

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
# Azure file copy v6
# Copy files to Azure Blob Storage or virtual machines.
- task: AzureFileCopy@6
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
Absolute path of the source folder, or file on the local machine, or a UNC share. Expression should return a single folder or a file. Wild card symbol (*) is supported anywhere in the file path or file name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscription`** - **Azure Subscription**<br>
Input alias: `ConnectedServiceNameARM`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Resource Manager subscription to target for copying the files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Destination"::: -->
:::moniker range="=azure-pipelines"

**`Destination`** - **Destination Type**<br>
`string`. Required. Allowed values: `AzureBlob` (Azure Blob), `AzureVMs` (Azure VMs).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the destination, either Azure Blob or Azure VMs.
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
Name of the Container for uploading the files. If a container with the given name does not exist in the specified storage account, it will automatically be created. <br> If you need to create a virtual directory inside the container, use the blob prefix input below. <br> Example: If your target location is <i>https://myaccount.blob.core.windows.net/mycontainer/vd1/vd2/</i>, then specify <i>mycontainer</i> as container name and <i>vd1/vd2/</i> as blob prefix.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="BlobPrefix"::: -->
:::moniker range="=azure-pipelines"

**`BlobPrefix`** - **Blob Prefix**<br>
`string`. Optional. Use when `Destination = AzureBlob`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Useful for filtering files, for example, append build number to all the blobs to download files from that build only. Example: If you specify blob prefix as <i>myvd1/</i>, a virtual directory with this name will be created inside the container. Blob prefix with a trailing '/' will be considered a virtual directory. Otherwise, it will be treated as a file, unless the item being copied is itself a folder. The source files will be copied to <i>https://myaccount.blob.core.windows.net/mycontainer/myvd1/</i>.
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
Optionally, select a subset of VMs in resource group either by providing VMs host name or tags. [Tags](https://learn.microsoft.com/en-us/azure/virtual-machines/tag-template/) are supported for resources created via the Azure Resource Manager only.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MachineNames"::: -->
:::moniker range="=azure-pipelines"

**`MachineNames`** - **Filter Criteria**<br>
`string`. Optional. Use when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a list of VMs host name like ffweb, ffdb, or tags like Role:DB, Web; OS:Win8.1. Note the delimiters used for tags are &#44;(comma), &#58;(colon) and &#59;(semicolon). If multiple tags are provided, then the task will run in all the VMs with the specified tags. The default is to run the task in all the VMs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmsAdminUserName"::: -->
:::moniker range="=azure-pipelines"

**`vmsAdminUserName`** - **Admin Login**<br>
`string`. Required when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator Username of the VMs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmsAdminPassword"::: -->
:::moniker range="=azure-pipelines"

**`vmsAdminPassword`** - **Password**<br>
`string`. Required when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The administrator password of the VMs. <br>It can accept variable defined in build or release pipelines as '$(passwordVariable)'. <br>You may mark variable as 'secret' to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetPath"::: -->
:::moniker range="=azure-pipelines"

**`TargetPath`** - **Destination Folder**<br>
`string`. Required when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Local path on the target machines for copying the files from the source. Environment variable can be used like $env:windir\BudgetIT\Web.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsForBlobCopy"::: -->
:::moniker range="=azure-pipelines"

**`AdditionalArgumentsForBlobCopy`** - **Optional Arguments (for uploading files to blob)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional AzCopy.exe arguments that will be applied when uploading to blob like, --check-length=true. If no optional arguments are specified here, the following optional arguments will be added by default.<br> --log-level=INFO (if the pipeline is running in debug mode set --log-level=DEBUG),<br> --recursive (only if container name is not $root),<br> --blob-type=PageBlob (only if specified storage account is a premium account).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArgumentsForVMCopy"::: -->
:::moniker range="=azure-pipelines"

**`AdditionalArgumentsForVMCopy`** - **Optional Arguments (for downloading files to VM)**<br>
`string`. Optional. Use when `Destination = AzureVMs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional AzCopy.exe arguments that will be applied when downloading to VM like,  --check-length=true. If no optional arguments are specified here, the following optional arguments will be added by default.<br> --log-level=INFO (if the pipeline is running in debug mode set --log-level=DEBUG),<br> --recursive.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableCopyPrerequisites"::: -->
:::moniker range="=azure-pipelines"

**`enableCopyPrerequisites`** - **Enable Copy Prerequisites**<br>
`boolean`. Optional. Use when `Destination = AzureVMs`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enabling this option configures Windows Remote Management (WinRM) listener over HTTPS protocol on port 5986, using a self-signed certificate. This configuration is required for performing copy operation on Azure machines. If the target Virtual Machines are backed by a Load balancer, ensure Inbound NAT rules are configured for target port (5986). Applicable only for ARM VMs.
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
If this option is selected, client skips the validation that the server certificate is signed by a trusted certificate authority (CA) when connecting over Hypertext Transfer Protocol over Secure Socket Layer (HTTPS).
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