---
title: AzureCloudPowerShellDeployment@1 - Azure Cloud Service deployment v1 task
description: Deploy an Azure Cloud Service (task version 1).
ms.date: 09/08/2023
monikerRange: "<=azure-pipelines"
---

# AzureCloudPowerShellDeployment@1 - Azure Cloud Service deployment v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Deploy an Azure Cloud Service.

[!INCLUDE [workload-identity](./includes/workload-identity.md)]
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
    azureClassicSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription (Classic). 
    #EnableAdvancedStorageOptions: false # boolean. Enable ARM storage support. Default: false.
    StorageAccount: # string. Required when EnableAdvancedStorageOptions = false. Storage account (Classic). 
    #ARMConnectedServiceName: # string. Required when EnableAdvancedStorageOptions = true. Azure subscription (ARM). 
    #ARMStorageAccount: # string. Required when EnableAdvancedStorageOptions = true. Storage account (ARM). 
    ServiceName: # string. Required. Service name. 
    ServiceLocation: # string. Required. Service location. 
    CsPkg: # string. Required. CsPkg. 
    CsCfg: # string. Required. CsCfg. 
    slotName: 'Production' # string. Alias: Slot. Required. Environment (Slot). Default: Production.
    #DeploymentLabel: '$(Build.BuildNumber)' # string. Deployment label. Default: $(Build.BuildNumber).
    #AppendDateTimeToLabel: false # boolean. Append current date and time. Default: false.
    #AllowUpgrade: true # boolean. Allow upgrade. Default: true.
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
    azureClassicSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription (Classic). 
    StorageAccount: # string. Required. Storage account. 
    ServiceName: # string. Required. Service name. 
    ServiceLocation: # string. Required. Service location. 
    CsPkg: # string. Required. CsPkg. 
    CsCfg: # string. Required. CsCfg. 
    slotName: 'Production' # string. Alias: Slot. Required. Environment (Slot). Default: Production.
    #DeploymentLabel: '$(Build.BuildNumber)' # string. Deployment label. Default: $(Build.BuildNumber).
    #AppendDateTimeToLabel: false # boolean. Append current date and time. Default: false.
    #AllowUpgrade: true # boolean. Allow upgrade. Default: true.
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
    azureClassicSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription (Classic). 
    StorageAccount: # string. Required. Storage account. 
    ServiceName: # string. Required. Service name. 
    ServiceLocation: # string. Required. Service location. 
    CsPkg: # string. Required. CsPkg. 
    CsCfg: # string. Required. CsCfg. 
    slotName: 'Production' # string. Alias: Slot. Required. Environment (Slot). Default: Production.
    #DeploymentLabel: '$(Build.BuildNumber)' # string. Deployment label. Default: $(Build.BuildNumber).
    #AppendDateTimeToLabel: false # boolean. Append current date and time. Default: false.
    #AllowUpgrade: true # boolean. Allow upgrade. Default: true.
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
The Azure subscription to target for deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="EnableAdvancedStorageOptions"::: -->
:::moniker range=">=azure-pipelines-2020"

**`EnableAdvancedStorageOptions`** - **Enable ARM storage support**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enables or disables ARM storage support.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="StorageAccount"::: -->
:::moniker range=">=azure-pipelines-2020"

**`StorageAccount`** - **Storage account (Classic)**<br>
`string`. Required when `EnableAdvancedStorageOptions = false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The storage account must exist prior to deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`StorageAccount`** - **Storage account**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The storage account must exist prior to deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ARMConnectedServiceName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`ARMConnectedServiceName`** - **Azure subscription (ARM)**<br>
`string`. Required when `EnableAdvancedStorageOptions = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The ARM subscription.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ARMStorageAccount"::: -->
:::moniker range=">=azure-pipelines-2020"

**`ARMStorageAccount`** - **Storage account (ARM)**<br>
`string`. Required when `EnableAdvancedStorageOptions = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A pre-existing ARM storage account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServiceName"::: -->
:::moniker range="<=azure-pipelines"

**`ServiceName`** - **Service name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
An existing cloud service name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ServiceLocation"::: -->
:::moniker range="<=azure-pipelines"

**`ServiceLocation`** - **Service location**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A region for new service deployment. Options include: East US, East US 2, Central US, South Central US, West US, North Europe, West Europe, and others.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CsPkg"::: -->
:::moniker range="<=azure-pipelines"

**`CsPkg`** - **CsPkg**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the CsPkg in the default artifact directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CsCfg"::: -->
:::moniker range="<=azure-pipelines"

**`CsCfg`** - **CsCfg**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The CsCfg path in the default artifact directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="slotName"::: -->
:::moniker range="<=azure-pipelines"

**`slotName`** - **Environment (Slot)**<br>
Input alias: `Slot`. `string`. Required. Default value: `Production`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set this value to 'Staging' or use the default.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DeploymentLabel"::: -->
:::moniker range="<=azure-pipelines"

**`DeploymentLabel`** - **Deployment label**<br>
`string`. Default value: `$(Build.BuildNumber)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the label name for the new deployment. If not specified, defaults to a Globally Unique Identifier (GUID).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AppendDateTimeToLabel"::: -->
:::moniker range="<=azure-pipelines"

**`AppendDateTimeToLabel`** - **Append current date and time**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Appends current date and time to the deployment label.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AllowUpgrade"::: -->
:::moniker range="<=azure-pipelines"

**`AllowUpgrade`** - **Allow upgrade**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Allows an upgrade to the Microsoft Azure deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SimultaneousUpgrade"::: -->
:::moniker range=">=azure-pipelines-2019"

**`SimultaneousUpgrade`** - **Simultaneous upgrade**<br>
`boolean`. Optional. Use when `AllowUpgrade == true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Upgrades all instances at once. Your cloud service is unavailable during this time.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ForceUpgrade"::: -->
:::moniker range="<=azure-pipelines"

**`ForceUpgrade`** - **Force upgrade**<br>
`boolean`. Optional. Use when `AllowUpgrade == true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets a forced upgrade.  Forcing an upgrade can cause loss of local data.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="VerifyRoleInstanceStatus"::: -->
:::moniker range=">=azure-pipelines-2019"

**`VerifyRoleInstanceStatus`** - **Verify role instance status**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Causes the task to wait until role instances are in the ready state.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="DiagnosticStorageAccountKeys"::: -->
:::moniker range="<=azure-pipelines"

**`DiagnosticStorageAccountKeys`** - **Diagnostic storage account keys**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Format storage key string as `Role:Storagekey`. The diagnostics storage account name for each role is retrieved from the diagnostic config file (.wadcfgx).

- If the .wadcfgx file for a role is not found: The diagnostic extension isn't set for that role.
- If the storage account name is not found in the .wadcfgx file: The default storage account is used for storing diagnostic results, and storage key parameters from the deployment task is ignored.

NOTE: If there is sensitive information in the diagnostic results for your environment, save the `storage_account_key` as a secret variable. For example:

- WebRole: `WebRole_storage_account_key`
- WorkerRole: `WorkerRole_stoarge_account_key`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="NewServiceCustomCertificates"::: -->
:::moniker range=">=azure-pipelines-2019"

**`NewServiceCustomCertificates`** - **Custom certificates to import**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Format the custom certificate string as `CertificatePfxBase64:CertificatePassword`. Save the `certificate_password` as a secret variable. For example: 

- Certificate1: `Certificate1_password`
- Certificate2: `Certificate2_password`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="NewServiceAdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`NewServiceAdditionalArguments`** - **Additional arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Passes additional arguments when creating a new service. Arguments are passed to the `New-AzureService` cmdlet. For example, `-Label 'MyTestService'`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="NewServiceAffinityGroup"::: -->
:::moniker range="<=azure-pipelines"

**`NewServiceAffinityGroup`** - **Affinity group**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The affinity group used instead of service location when creating a new service.
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
