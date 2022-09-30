---
title: AzureVmssDeployment@0 - Azure VM scale set deployment v0 task
description: Deploy a virtual machine scale set image.
ms.date: 09/26/2022
monikerRange: "<=azure-pipelines"
---

# AzureVmssDeployment@0 - Azure VM scale set deployment v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Deploy a virtual machine scale set image.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Deploy Virtual Machine scale set image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Azure VM scale set deployment v0
# Deploy a virtual machine scale set image.
- task: AzureVmssDeployment@0
  inputs:
  # Azure Details
    azureSubscription: # string. Required. Azure subscription. 
    action: 'Update image' # 'Update image' | 'Configure application startup'. Required. Action. Default: Update image.
    vmssName: # string. Required. Virtual Machine scale set name. 
    vmssOsType: # 'Windows' | 'Linux'. Required. OS type. 
  # Image Details
    imageUrl: # string. Required. Image URL. 
  # Configure start-up
    #customScriptsDirectory: # string. Custom script directory. 
    #customScript: # string. Command. 
    #customScriptArguments: # string. Arguments. 
    #customScriptsStorageAccount: # string. Azure storage account where custom scripts will be uploaded. 
  # Advanced
    #skipArchivingCustomScripts: false # boolean. Skip Archiving custom scripts. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Azure VM scale set Deployment v0
# Deploy Virtual Machine scale set image.
- task: AzureVmssDeployment@0
  inputs:
  # Azure Details
    azureSubscription: # string. Required. Azure subscription. 
    action: 'Update image' # 'Update image' | 'Configure application startup'. Required. Action. Default: Update image.
    vmssName: # string. Required. Virtual Machine scale set name. 
    vmssOsType: # 'Windows' | 'Linux'. Required. OS type. 
  # Image Details
    imageUrl: # string. Required. Image URL. 
  # Configure start-up
    #customScriptsDirectory: # string. Custom script directory. 
    #customScript: # string. Command. 
    #customScriptArguments: # string. Arguments. 
    #customScriptsStorageAccount: # string. Azure storage account where custom scripts will be uploaded. 
  # Advanced
    #skipArchivingCustomScripts: false # boolean. Skip Archiving custom scripts. Default: false.
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
Input alias: `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription for the scale set.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="action"::: -->
:::moniker range="<=azure-pipelines"

**`action`** - **Action**<br>
`string`. Required. Allowed values: `Update image` (Update VM Scale set by using an image), `Configure application startup` (Run Custom Script VM extension on VM scale set). Default value: `Update image`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose between updating a VM scale set by using a VHD image and/or by running deployment/install scripts using Custom Script VM Extension.<br/>The VHD image approach is better for scaling quickly and doing rollback. The extension approach is useful for post deployment configuration, software installation, or any other configuration/management task.<br/>You can use a VHD image to update a VM scale set only when it was created by using a custom image. The update will fail if the VM scale set was created by using a platform/gallery image available in Azure.<br/>The Custom Script VM Extension approach can be used for VM scale set created by using either custom image or platform/gallery image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmssName"::: -->
:::moniker range="<=azure-pipelines"

**`vmssName`** - **Virtual Machine scale set name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the VM scale set which you want to update by using either a VHD image or by using a Custom Script VM Extension.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vmssOsType"::: -->
:::moniker range="<=azure-pipelines"

**`vmssOsType`** - **OS type**<br>
`string`. Required. Allowed values: `Windows`, `Linux`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the operating system type of the VM scale set.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageUrl"::: -->
:::moniker range=">=azure-pipelines-2019"

**`imageUrl`** - **Image URL**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the URL of the VHD image. If it is an Azure storage blob URL, the storage account location should be the same as the scale set location.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`imageUrl`** - **Image url**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the URL of the VHD image. If it is an Azure storage blob URL, the storage account location should be the same as the scale set location.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customScriptsDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`customScriptsDirectory`** - **Custom script directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. The path to the directory containing the custom script(s) that will be run by using the Custom Script VM Extension. The extension approach is useful for post deployment configuration, application/software installation, or any other application configuration/management task. For example, the script can set a machine level environment variable which the application uses, like database connection string.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customScript"::: -->
:::moniker range="<=azure-pipelines"

**`customScript`** - **Command**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. The script that will be run by using the Custom Script VM Extension. This script can invoke other scripts in the directory. The script will be invoked with arguments passed below.<br/>This script in conjugation with such arguments can be used to execute commands.

For example:
1. `Update-DatabaseConnectionStrings.ps1 -clusterType dev -user $(dbUser) -password $(dbUserPwd)` will update the connection string in `web.config` of the web application.
2. `install-secrets.sh --key-vault-type prod -key serviceprincipalkey` will create an encrypted file containing a service principal key.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customScriptArguments"::: -->
:::moniker range="<=azure-pipelines"

**`customScriptArguments`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. The custom script will be invoked with arguments passed. Build/Release variables can be used, which makes it easy to use secrets.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customScriptsStorageAccount"::: -->
:::moniker range="<=azure-pipelines"

**`customScriptsStorageAccount`** - **Azure storage account where custom scripts will be uploaded**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. The Custom Script Extension downloads and executes scripts provided by you on each virtual machine in the VM scale set. These scripts will be stored in the pre-existing ARM storage account specified here.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skipArchivingCustomScripts"::: -->
:::moniker range="<=azure-pipelines"

**`skipArchivingCustomScripts`** - **Skip Archiving custom scripts**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. By default, this task creates a compressed archive of the directory containing the custom scripts. This improves performance and reliability while uploading to Azure storage. If not selected, archiving will not be done and all files will be individually uploaded.
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

Use this task to deploy a virtual machine scale set image.

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
| Agent version |  2.0.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->