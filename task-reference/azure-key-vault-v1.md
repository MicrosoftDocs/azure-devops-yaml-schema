---
title: AzureKeyVault@1 - Azure Key Vault v1 task
description: Download Azure Key Vault secrets (task version 1).
ms.date: 06/24/2025
monikerRange: "<=azure-pipelines"
author: ramiMSFT
ms.author: rabououn
---

# AzureKeyVault@1 - Azure Key Vault v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to download secrets, such as authentication keys, storage account keys, data encryption keys, .PFX files, and passwords from an [Azure Key Vault](/rest/api/keyvault/about-keys--secrets-and-certificates) instance. The task can be used to fetch the latest values of all or a subset of secrets from the vault and set them as variables that can be used in subsequent tasks of a pipeline. The task is Node-based and works with agents on Linux, macOS, and Windows.

This version of the task is deprecated; use [AzureKeyVault@2](./azure-key-vault-v2.md).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Use this task to download secrets, such as authentication keys, storage account keys, data encryption keys, .PFX files, and passwords from an [Azure Key Vault](/rest/api/keyvault/about-keys--secrets-and-certificates) instance. The task can be used to fetch the latest values of all or a subset of secrets from the vault and set them as variables that can be used in subsequent tasks of a pipeline. The task is Node-based and works with agents on Linux, macOS, and Windows.
<!-- :::editable-content-end::: -->

:::moniker-end

<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Azure Key Vault v1
# Download Azure Key Vault secrets.
- task: AzureKeyVault@1
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    KeyVaultName: # string. Required. Key vault. 
    SecretsFilter: '*' # string. Required. Secrets filter. Default: *.
    #RunAsPreJob: false # boolean. Make secrets available to whole job. Default: false.
```

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

```yaml
# Azure Key Vault v1
# Download Azure Key Vault secrets.
- task: AzureKeyVault@1
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    KeyVaultName: # string. Required. Key vault. 
    SecretsFilter: '*' # 'EditableOptions'. Required. Secrets filter. Default: *.
    #RunAsPreJob: false # 'EditableOptions'. Make secrets available to whole job. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
[Input alias](index.md#what-are-task-input-aliases): `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The service connection for the Azure subscription that either contains the Azure Key Vault instance or creates a new connection. Learn more about [connecting to Azure](/azure/devops/pipelines/library/connect-to-azure).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="KeyVaultName"::: -->
:::moniker range="<=azure-pipelines"

**`KeyVaultName`** - **Key vault**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Azure Key Vault that contains the secrets to download.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SecretsFilter"::: -->
:::moniker range=">=azure-pipelines-2022"

**`SecretsFilter`** - **Secrets filter**<br>
`string`. Required. Default value: `*`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Downloads secret names according to the entered value. The value can be the default value to download all secrets from the selected key vault, or a comma-separated list of secret names.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

**`SecretsFilter`** - **Secrets filter**<br>
`string`. Required. Allowed values: `EditableOptions` (True). Default value: `*`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Downloads secret names according to the entered value. The value can be the default value to download all secrets from the selected key vault, or a comma-separated list of secret names.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RunAsPreJob"::: -->
:::moniker range=">=azure-pipelines-2022"

**`RunAsPreJob`** - **Make secrets available to whole job**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs the task before the job execution begins. Exposes secrets to all tasks in the job, not just tasks that follow this one.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

**`RunAsPreJob`** - **Make secrets available to whole job**<br>
`boolean`. Allowed values: `EditableOptions` (True). Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs the task before the job execution begins. Exposes secrets to all tasks in the job, not just tasks that follow this one.
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

Works with cross-platform agents (Linux, macOS, or Windows).

There is a newer version of the Azure Key Vault task available.

* [Azure Key Vault v2](azure-key-vault-v2.md)

### I get a `forbidden` error on pipelines at the point of getting credentials from Azure Key Vault

This occurs if the required permissions are missing in the Azure key vault. To resolve the issue, [add an access policy with the correct permissions](/azure/key-vault/general/assign-access-policy-portal).
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
## See also

* [Azure Key Vault v2](azure-key-vault-v2.md)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
