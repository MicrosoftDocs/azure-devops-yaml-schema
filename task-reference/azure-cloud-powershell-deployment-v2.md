---
title: AzureCloudPowerShellDeployment@2 - Azure Cloud Service deployment v2 task
description: Deploy an Azure Cloud Service.
ms.date: 06/22/2023
monikerRange: "=azure-pipelines"
---

# AzureCloudPowerShellDeployment@2 - Azure Cloud Service deployment v2 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Deploy an Azure Cloud Service.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure Cloud Service deployment v2
# Deploy an Azure Cloud Service.
- task: AzureCloudPowerShellDeployment@2
  inputs:
    ARMConnectedServiceName: # string. Required. Azure subscription (ARM). 
    ResourceGroupName: # string. Required. Resource group. 
    ARMStorageAccount: # string. Required. Storage account (ARM). 
    ServiceName: # string. Required. Service name. 
    ServiceLocation: # string. Required. Service location. 
    CsCfg: # string. Required. CsCfg. 
    CsDef: # string. Required. CsDef. 
    CsPkg: # string. Required. CsPkg. 
    #KeyVault: # string. Azure KeyVault. 
    #DeploymentLabel: '$(Build.BuildNumber)' # string. Deployment label. Default: $(Build.BuildNumber).
    #AppendDateTimeToLabel: false # boolean. Append current date and time. Default: false.
    #UpgradeMode: 'Auto' # string. Update mode for the cloud service. Default: Auto.
    #AllowUpgrade: true # boolean. Allow upgrade. Default: true.
    #VerifyRoleInstanceStatus: false # boolean. Verify role instance status. Default: false.
  # Advanced Options For Creating New Service
    #DiagnosticStorageAccountKeys: # string. Diagnostic storage account keys.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="ARMConnectedServiceName"::: -->
:::moniker range="=azure-pipelines"

**`ARMConnectedServiceName`** - **Azure subscription (ARM)**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Resource Manager subscription.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceGroupName"::: -->
:::moniker range="=azure-pipelines"

**`ResourceGroupName`** - **Resource group**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter or Select the Azure Resource Group that contains the Azure App Service specified above.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ARMStorageAccount"::: -->
:::moniker range="=azure-pipelines"

**`ARMStorageAccount`** - **Storage account (ARM)**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose a pre-existing ARM storage account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServiceName"::: -->
:::moniker range="=azure-pipelines"

**`ServiceName`** - **Service name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select or enter an existing cloud service name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServiceLocation"::: -->
:::moniker range="=azure-pipelines"

**`ServiceLocation`** - **Service location**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a region for new service deployment.Possible options are **East US**, **East US 2**, **Central US**, **South Central US**, **West US**, **North Europe**, **West Europe** and others.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CsCfg"::: -->
:::moniker range="=azure-pipelines"

**`CsCfg`** - **CsCfg**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path of CsCfg under the default artifact directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CsDef"::: -->
:::moniker range="=azure-pipelines"

**`CsDef`** - **CsDef**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path of CsDef under the default artifact directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CsPkg"::: -->
:::moniker range="=azure-pipelines"

**`CsPkg`** - **CsPkg**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path of CsPkg under the default artifact directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="KeyVault"::: -->
:::moniker range="=azure-pipelines"

**`KeyVault`** - **Azure KeyVault**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose a pre-existing Azure KeyVault with certificates.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeploymentLabel"::: -->
:::moniker range="=azure-pipelines"

**`DeploymentLabel`** - **Deployment label**<br>
`string`. Default value: `$(Build.BuildNumber)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the label name for the new deployment. If not specified, a Globally Unique Identifier (GUID) is used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppendDateTimeToLabel"::: -->
:::moniker range="=azure-pipelines"

**`AppendDateTimeToLabel`** - **Append current date and time**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Appends current date and time to deployment label.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="UpgradeMode"::: -->
:::moniker range="=azure-pipelines"

**`UpgradeMode`** - **Update mode for the cloud service**<br>
`string`. Default value: `Auto`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
**Auto**, **Manual** or **Simultaneous**.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AllowUpgrade"::: -->
:::moniker range="=azure-pipelines"

**`AllowUpgrade`** - **Allow upgrade**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When selected allows an upgrade to the Microsoft Azure cloud service.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VerifyRoleInstanceStatus"::: -->
:::moniker range="=azure-pipelines"

**`VerifyRoleInstanceStatus`** - **Verify role instance status**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When selected then the task will wait until role instances are in ready state.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DiagnosticStorageAccountKeys"::: -->
:::moniker range="=azure-pipelines"

**`DiagnosticStorageAccountKeys`** - **Diagnostic storage account keys**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide storage keys for diagnostics storage account in Role:Storagekey format. The diagnostics storage account name for each role will be obtained from diagnostics config file (.wadcfgx). If the .wadcfgx file for a role is not found, diagnostics extensions won’t be set for the role. If the storage account name is missing in the .wadcfgx file, the default storage account will be used for storing diagnostics results and the storage key parameters from deployment task will be ignored. It’s recommended to save <storage_account_key> as a secret variable unless there is no sensitive information in the diagnostics result for your environment. <br/><br/>For example,<br/> WebRole: &lt;WebRole_storage_account_key&gt;<br/>WorkerRole: &lt;WorkerRole_stoarge_account_key&gt;.
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
| Runs on | Agent |
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