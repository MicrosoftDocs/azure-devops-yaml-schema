---
title: AzureKeyVault@2 - Azure Key Vault v2 task
description: Download Azure Key Vault secrets.
ms.date: 08/10/2022
monikerRange: ">=azure-pipelines-2022"
---

# AzureKeyVault@2 - Azure Key Vault v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::editable-content name="description"::: -->
Download Azure Key Vault secrets.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Azure Key Vault v2
# Download Azure Key Vault secrets.
- task: AzureKeyVault@2
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    KeyVaultName: # string. Required. Key vault. 
    SecretsFilter: '*' # string. Required. Secrets filter. Default: '*'.
    RunAsPreJob: false # boolean. Required. Make secrets available to whole job. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2022"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `ConnectedServiceName`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure subscription for the key vault.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="KeyVaultName"::: -->
:::moniker range=">=azure-pipelines-2022"

**`KeyVaultName`** - **Key vault**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the name of an existing key vault.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SecretsFilter"::: -->
:::moniker range=">=azure-pipelines-2022"

**`SecretsFilter`** - **Secrets filter**<br>
Type: string. Required. Default value: '*'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma separated list of secret names or leave * to download all secrets from the selected key vault.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RunAsPreJob"::: -->
:::moniker range=">=azure-pipelines-2022"

**`RunAsPreJob`** - **Make secrets available to whole job**<br>
Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run the task before job execution begins. Exposes secrets to all tasks in the job, not just tasks that follow this one.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2022"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

What's new in Version 2.0: 
   Added support for %3B, %5D in secrets.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.182.1 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->