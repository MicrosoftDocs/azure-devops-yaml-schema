---
title: AzureVmssDeployment@1 - Azure VM scale set deployment v1 task
description: Deploy a virtual machine scale set image.
ms.date: 06/24/2025
monikerRange: "=azure-pipelines"
---

# AzureVmssDeployment@1 - Azure VM scale set deployment v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Deploy a virtual machine scale set image.

> [!NOTE]
> This version of the task uses Azure RBAC to connect to Azure storage. For more information, see [Configure Azure RBAC to access Azure storage](#configure-azure-rbac-to-access-azure-storage).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure VM scale set deployment v1
# Deploy a virtual machine scale set image.
- task: AzureVmssDeployment@1
  inputs:
  # Azure Details
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    action: 'Update image' # 'Update image' | 'Configure application startup'. Required. Action. Default: Update image.
    vmssName: # string. Required. Virtual Machine scale set name. 
    vmssOsType: # 'Windows' | 'Linux'. Required. OS type. 
  # Image Details
    #imageUrl: # string. Required when action = Update image || action = UpdateImage. Image URL. 
  # Configure start-up
    #customScriptsDirectory: # string. Optional. Use when action = Configure application startup || action = Update image || action = UpdateImage. Custom script directory. 
    #customScript: # string. Optional. Use when action = Configure application startup || action = Update image || action = UpdateImage. Command. 
    #customScriptArguments: # string. Optional. Use when action = Configure application startup || action = Update image || action = UpdateImage. Arguments. 
    #customScriptsStorageAccount: # string. Optional. Use when action = Configure application startup || action = Update image || action = UpdateImage. Azure storage account where custom scripts will be uploaded. 
  # Advanced
    #skipArchivingCustomScripts: false # boolean. Skip Archiving custom scripts. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
[Input alias](index.md#what-are-task-input-aliases): `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription for the scale set.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="action"::: -->
:::moniker range="=azure-pipelines"

**`action`** - **Action**<br>
`string`. Required. Allowed values: `Update image` (Update VM Scale set by using an image), `Configure application startup` (Run Custom Script VM extension on VM scale set). Default value: `Update image`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose between updating a VM scale set by using a VHD image and/or by running deployment/install scripts using Custom Script VM extension.<br/>The VHD image approach is better for scaling quickly and doing rollback. The extension approach is useful for post deployment configuration, software installation, or any other configuration / management task.<br/>You can use a VHD image to update a VM scale set only when it was created by using a custom image, the update will fail if the VM Scale set was created by using a platform/gallery image available in Azure.<br/>The Custom script VM extension approach can be used for VM scale set created by using either custom image or platform/gallery image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmssName"::: -->
:::moniker range="=azure-pipelines"

**`vmssName`** - **Virtual Machine scale set name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of VM scale set which you want to update by using either a VHD image or by using Custom script VM extension.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmssOsType"::: -->
:::moniker range="=azure-pipelines"

**`vmssOsType`** - **OS type**<br>
`string`. Required. Allowed values: `Windows`, `Linux`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the operating system type of VM scale set.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageUrl"::: -->
:::moniker range="=azure-pipelines"

**`imageUrl`** - **Image URL**<br>
`string`. Required when `action = Update image || action = UpdateImage`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the URL of VHD image. If it is an Azure storage blob URL, the storage account location should be same as scale set location.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customScriptsDirectory"::: -->
:::moniker range="=azure-pipelines"

**`customScriptsDirectory`** - **Custom script directory**<br>
`string`. Optional. Use when `action = Configure application startup || action = Update image || action = UpdateImage`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to directory containing custom script(s) that will be run by using Custom Script VM extension. The extension approach is useful for post deployment configuration, application/software installation, or any other application configuration/management task. For example: the script can set a machine level environment variable which the application uses, like database connection string.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customScript"::: -->
:::moniker range="=azure-pipelines"

**`customScript`** - **Command**<br>
`string`. Optional. Use when `action = Configure application startup || action = Update image || action = UpdateImage`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The script that will be run by using Custom Script VM extension. This script can invoke other scripts in the directory. The script will be invoked with arguments passed below.<br/>This script in conjugation with such arguments can be used to execute commands. For example:<br/>1. Update-DatabaseConnectionStrings.ps1 -clusterType dev -user $(dbUser) -password $(dbUserPwd) will update connection string in web.config of web application.<br/>2. install-secrets.sh --key-vault-type prod -key serviceprincipalkey will create an encrypted file containing service principal key.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customScriptArguments"::: -->
:::moniker range="=azure-pipelines"

**`customScriptArguments`** - **Arguments**<br>
`string`. Optional. Use when `action = Configure application startup || action = Update image || action = UpdateImage`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The custom script will be invoked with arguments passed. Build/Release variables can be used which makes it easy to use secrets.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customScriptsStorageAccount"::: -->
:::moniker range="=azure-pipelines"

**`customScriptsStorageAccount`** - **Azure storage account where custom scripts will be uploaded**<br>
`string`. Optional. Use when `action = Configure application startup || action = Update image || action = UpdateImage`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Custom Script Extension downloads and executes scripts provided by you on each virtual machines in the VM scale set. These scripts will be stored in the storage account specified here. Specify a pre-existing ARM storage account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipArchivingCustomScripts"::: -->
:::moniker range="=azure-pipelines"

**`skipArchivingCustomScripts`** - **Skip Archiving custom scripts**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
By default, this task creates a compressed archive of directory containing custom scripts. This improves performance and reliability while uploading to azure storage. If not selected, archiving will not be done and all files will be individually uploaded.
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

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to deploy a Virtual Machine scale set image.

### The script execution is reported as successful, however the VMSS instances are not updated

Scale sets have an upgrade policy that determine how VMs are brought up-to-date with the latest scale set model, and if the upgrade policy is set to manual you must manually upgrade each VM. For more information, see [How to bring VMs up-to-date with the latest scale set model](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-upgrade-scale-set#how-to-bring-vms-up-to-date-with-the-latest-scale-set-model). You can change the update policy or manually upgrade each VM. For example, to upgrade the policy to `Automatic`, use the following Az CLI command: 
```az vmss update --set upgradePolicy.mode=Automatic -g <resource group name> -n <vmss name>```

### Error: 'Permission denied: Script is not executable'

This issue occurs if you try to run a custom script, but the script isn't executable.

To resolve the issue, first make sure that the `customScript` input doesn't have `./` or anything else before the script name `'test.sh'`:

```yml
    customScript: 'test.sh'
```

Next, try adding a command line task before the virtual machine scale set task:

```yml
    - task: CmdLine@2
      inputs:
        script: 'chmod 777 $(System.DefaultWorkingDirectory)/test.sh' 
```

### Configure Azure RBAC to access Azure storage

This version of the task uses an [Azure Resource Manager service connection](/azure/devops/pipelines/library/connect-to-azure) configured using workload identity federation and Azure RBAC to connect to Azure storage instead of storage account keys or shared access signatures (SAS). To connect to Azure storage from this task, you must assign the [Storage Blob Data Contributor](/azure/role-based-access-control/built-in-roles/storage#storage-blob-data-contributor) role on the storage account to the identity of the service connection configured for `azureSubscription`.

For more information, see [Assign an Azure role for access to blob data](/azure/storage/blobs/assign-azure-role-data-access) and [Steps to assign a role](/azure/role-based-access-control/role-assignments-steps).

The `AzureVmssDeployment@1` task requires the following additional RBAC roles configured to access the storage account configured in `customScriptsStorageAccount`.

| Role | Resource | User |
|------|-------|------|
| [Contributor](/azure/role-based-access-control/built-in-roles/privileged#contributor) or [Virtual Machine Contributor](/azure/role-based-access-control/built-in-roles/compute#virtual-machine-contributor) | Virtual Machine Scale Set | The identity of the service connection configured for `azureSubscription` |
| [Storage Blob Data Contributor](/azure/role-based-access-control/built-in-roles/storage#storage-blob-data-contributor) | Azure storage account that holds the custom script | The identity of the service connection configured for `azureSubscription` |
| [Storage Blob Data Reader](/azure/role-based-access-control/built-in-roles/storage#storage-blob-data-reader) | Azure storage account that holds the custom script | The Virtual Machine Scale Set System-assigned Managed Identity |

:::image type="content" source="./media/azure-vmss-deployment/azure-rbac-roles.png" alt-text="Azure RBAC access for custom script access.":::
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
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.209.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->