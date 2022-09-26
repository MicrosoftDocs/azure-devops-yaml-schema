---
title: AzureCloudPowerShellDeployment@1 - Azure Cloud Service deployment v1 task
description: Deploy an Azure Cloud Service.
ms.date: 09/26/2022
monikerRange: "<=azure-pipelines"
---

# AzureCloudPowerShellDeployment@1 - Azure Cloud Service deployment v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Deploy an Azure Cloud Service.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Azure Cloud Service deployment v1
# Deploy an Azure Cloud Service.
- task: AzureCloudPowerShellDeployment@1
  inputs:
    azureClassicSubscription: # string. Required. Azure subscription (Classic). 
    EnableAdvancedStorageOptions: false # boolean. Required. Enable ARM storage support. Default: false.
    StorageAccount: # string. Required when EnableAdvancedStorageOptions = false. Storage account (Classic). 
    #ARMConnectedServiceName: # string. Required when EnableAdvancedStorageOptions = true. Azure subscription (ARM). 
    #ARMStorageAccount: # string. Required when EnableAdvancedStorageOptions = true. Storage account (ARM). 
    ServiceName: # string. Required. Service name. 
    ServiceLocation: # string. Required. Service location. 
    CsPkg: # string. Required. CsPkg. 
    CsCfg: # string. Required. CsCfg. 
    slotName: 'Production' # string. Required. Environment (Slot). Default: Production.
    #DeploymentLabel: '$(Build.BuildNumber)' # string. Deployment label. Default: $(Build.BuildNumber).
    #AppendDateTimeToLabel: false # boolean. Append current date and time. Default: false.
    AllowUpgrade: true # boolean. Required. Allow upgrade. Default: true.
    #SimultaneousUpgrade: false # boolean. Optional. Use when AllowUpgrade == true. Simultaneous upgrade. Default: false.
    #ForceUpgrade: false # boolean. Optional. Use when AllowUpgrade == true. Force upgrade. Default: false.
    #VerifyRoleInstanceStatus: false # boolean. Verify role instance status. Default: false.
  # Advanced Options For Creating New Service
    #DiagnosticStorageAccountKeys: # string. Diagnostic storage account keys. 
    #NewServiceCustomCertificates: # string. Custom certificates to import. 
    #NewServiceAdditionalArguments: # string. Additional arguments. 
    #NewServiceAffinityGroup: # string. Affinity group.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Azure Cloud Service deployment v1
# Deploy an Azure Cloud Service.
- task: AzureCloudPowerShellDeployment@1
  inputs:
    azureClassicSubscription: # string. Required. Azure subscription (Classic). 
    StorageAccount: # string. Required. Storage account. 
    ServiceName: # string. Required. Service name. 
    ServiceLocation: # string. Required. Service location. 
    CsPkg: # string. Required. CsPkg. 
    CsCfg: # string. Required. CsCfg. 
    slotName: 'Production' # string. Required. Environment (Slot). Default: Production.
    #DeploymentLabel: '$(Build.BuildNumber)' # string. Deployment label. Default: $(Build.BuildNumber).
    #AppendDateTimeToLabel: false # boolean. Append current date and time. Default: false.
    AllowUpgrade: true # boolean. Required. Allow upgrade. Default: true.
    #SimultaneousUpgrade: false # boolean. Optional. Use when AllowUpgrade == true. Simultaneous upgrade. Default: false.
    #ForceUpgrade: false # boolean. Optional. Use when AllowUpgrade == true. Force upgrade. Default: false.
    #VerifyRoleInstanceStatus: false # boolean. Verify role instance status. Default: false.
  # Advanced Options For Creating New Service
    #DiagnosticStorageAccountKeys: # string. Diagnostic storage account keys. 
    #NewServiceCustomCertificates: # string. Custom certificates to import. 
    #NewServiceAdditionalArguments: # string. Additional arguments. 
    #NewServiceAffinityGroup: # string. Affinity group.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Azure Cloud Service Deployment v1
# Deploy an Azure Cloud Service.
- task: AzureCloudPowerShellDeployment@1
  inputs:
    azureClassicSubscription: # string. Required. Azure subscription (Classic). 
    StorageAccount: # string. Required. Storage account. 
    ServiceName: # string. Required. Service name. 
    ServiceLocation: # string. Required. Service location. 
    CsPkg: # string. Required. CsPkg. 
    CsCfg: # string. Required. CsCfg. 
    slotName: 'Production' # string. Required. Environment (Slot). Default: Production.
    #DeploymentLabel: '$(Build.BuildNumber)' # string. Deployment label. Default: $(Build.BuildNumber).
    #AppendDateTimeToLabel: false # boolean. Append current date and time. Default: false.
    AllowUpgrade: true # boolean. Required. Allow upgrade. Default: true.
    #SimultaneousUpgrade: false # boolean. Optional. Use when AllowUpgrade == true. Simultaneous upgrade. Default: false.
    #ForceUpgrade: false # boolean. Optional. Use when AllowUpgrade == true. Force upgrade. Default: false.
    #VerifyRoleInstanceStatus: false # boolean. Verify role instance status. Default: false.
  # Advanced Options For Creating New Service
    #DiagnosticStorageAccountKeys: # string. Diagnostic storage account keys. 
    #NewServiceCustomCertificates: # string. Custom certificates to import. 
    #NewServiceAdditionalArguments: # string. Additional arguments. 
    #NewServiceAffinityGroup: # string. Affinity group.
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

<!-- :::item name="azureClassicSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureClassicSubscription`** - **Azure subscription (Classic)**<br>
Input alias: `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Classic subscription to target for deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="EnableAdvancedStorageOptions"::: -->
:::moniker range=">=azure-pipelines-2020"

**`EnableAdvancedStorageOptions`** - **Enable ARM storage support**<br>
`boolean`. Required. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select to enable ARM storage support for this task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="StorageAccount"::: -->
:::moniker range=">=azure-pipelines-2020"

**`StorageAccount`** - **Storage account (Classic)**<br>
`string`. Required when `EnableAdvancedStorageOptions = false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Storage account must exist prior to deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`StorageAccount`** - **Storage account**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Storage account must exist prior to deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ARMConnectedServiceName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`ARMConnectedServiceName`** - **Azure subscription (ARM)**<br>
`string`. Required when `EnableAdvancedStorageOptions = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Resource Manager subscription.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ARMStorageAccount"::: -->
:::moniker range=">=azure-pipelines-2020"

**`ARMStorageAccount`** - **Storage account (ARM)**<br>
`string`. Required when `EnableAdvancedStorageOptions = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose a pre-existing ARM storage account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServiceName"::: -->
:::moniker range="<=azure-pipelines"

**`ServiceName`** - **Service name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select or enter an existing cloud service name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServiceLocation"::: -->
:::moniker range="<=azure-pipelines"

**`ServiceLocation`** - **Service location**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a region for new service deployment.Possible options are **East US**, **East US 2**, **Central US**, **South Central US**, **West US**, **North Europe**, **West Europe** and others.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CsPkg"::: -->
:::moniker range="<=azure-pipelines"

**`CsPkg`** - **CsPkg**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path of CsPkg under the default artifact directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CsCfg"::: -->
:::moniker range="<=azure-pipelines"

**`CsCfg`** - **CsCfg**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path of CsCfg under the default artifact directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="slotName"::: -->
:::moniker range="<=azure-pipelines"

**`slotName`** - **Environment (Slot)**<br>
Input alias: `Slot`. `string`. Required. Default value: `Production`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
**Production** or **Staging**.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeploymentLabel"::: -->
:::moniker range="<=azure-pipelines"

**`DeploymentLabel`** - **Deployment label**<br>
`string`. Default value: `$(Build.BuildNumber)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the label name for the new deployment. If not specified, a Globally Unique Identifier (GUID) is used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppendDateTimeToLabel"::: -->
:::moniker range="<=azure-pipelines"

**`AppendDateTimeToLabel`** - **Append current date and time**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Appends current date and time to deployment label.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AllowUpgrade"::: -->
:::moniker range="<=azure-pipelines"

**`AllowUpgrade`** - **Allow upgrade**<br>
`boolean`. Required. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When selected allows an upgrade to the Microsoft Azure deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SimultaneousUpgrade"::: -->
:::moniker range=">=azure-pipelines-2019"

**`SimultaneousUpgrade`** - **Simultaneous upgrade**<br>
`boolean`. Optional. Use when `AllowUpgrade == true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Updates all instances at once. Your cloud service will be unavailable during update.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ForceUpgrade"::: -->
:::moniker range="<=azure-pipelines"

**`ForceUpgrade`** - **Force upgrade**<br>
`boolean`. Optional. Use when `AllowUpgrade == true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When selected sets the upgrade to a forced upgrade, which could potentially cause loss of local data.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VerifyRoleInstanceStatus"::: -->
:::moniker range=">=azure-pipelines-2019"

**`VerifyRoleInstanceStatus`** - **Verify role instance status**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When selected then the task will wait until role instances are in ready state.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DiagnosticStorageAccountKeys"::: -->
:::moniker range="<=azure-pipelines"

**`DiagnosticStorageAccountKeys`** - **Diagnostic storage account keys**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide storage keys for diagnostics storage account in Role:Storagekey format. The diagnostics storage account name for each role will be obtained from diagnostics config file (.wadcfgx). If the .wadcfgx file for a role is not found, diagnostics extensions won’t be set for the role. If the storage account name is missing in the .wadcfgx file, the default storage account will be used for storing diagnostics results and the storage key parameters from deployment task will be ignored. It’s recommended to save <storage_account_key> as a secret variable unless there is no sensitive information in the diagnostics result for your environment. <br/><br/>For example,<br/> WebRole: &lt;WebRole_storage_account_key&gt;<br/>WorkerRole: &lt;WorkerRole_stoarge_account_key&gt;.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="NewServiceCustomCertificates"::: -->
:::moniker range=">=azure-pipelines-2019"

**`NewServiceCustomCertificates`** - **Custom certificates to import**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide custom certificates in CertificatePfxBase64:CertificatePassword format. It’s recommended to save <certificate_password> as a secret variable. <br/><br/>For example,<br/> Certificate1: &lt;Certificate1_password&gt;<br/>Certificate2: &lt;Certificate2_password&gt;.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="NewServiceAdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`NewServiceAdditionalArguments`** - **Additional arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Pass in additional arguments while creating a brand new service. These will be passed on to `New-AzureService` cmdlet. Eg: `-Label 'MyTestService'`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="NewServiceAffinityGroup"::: -->
:::moniker range="<=azure-pipelines"

**`NewServiceAffinityGroup`** - **Affinity group**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
While creating new service, this affinity group will be considered instead of using service location.
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

Use this task to deploy an Azure Cloud Service.
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