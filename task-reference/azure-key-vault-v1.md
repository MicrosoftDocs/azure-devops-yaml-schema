---
title: AzureKeyVault@1 - Azure Key Vault v1 task
description: Download Azure Key Vault secrets (task version 1).
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# AzureKeyVault@1 - Azure Key Vault v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Download Azure Key Vault secrets.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Download Azure Key Vault Secrets.
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
    azureSubscription: # string. Required. Azure subscription. 
    KeyVaultName: # string. Required. Key vault. 
    SecretsFilter: '*' # string. Required. Secrets filter. Default: '*'.
    RunAsPreJob: false # boolean. Required. Make secrets available to whole job. Default: false.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

```yaml
# Azure Key Vault v1
# Download Azure Key Vault secrets.
- task: AzureKeyVault@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    KeyVaultName: # string. Required. Key vault. 
    SecretsFilter: '*' # 'EditableOptions'. Required. Secrets filter. Default: '*'.
    RunAsPreJob: false # 'EditableOptions'. Required. Make secrets available to whole job. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Azure Key Vault v1
# Download Azure Key Vault secrets.
- task: AzureKeyVault@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    KeyVaultName: # string. Required. Key vault. 
    SecretsFilter: '*' # 'EditableOptions'. Required. Secrets filter. Default: '*'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Azure Key Vault v1
# Download Azure Key Vault Secrets.
- task: AzureKeyVault@1
  inputs:
    azureSubscription: # string. Required. Azure subscription. 
    KeyVaultName: # string. Required. Key vault. 
    SecretsFilter: '*' # 'EditableOptions'. Required. Secrets filter. Default: '*'.
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
Input alias: `ConnectedServiceName`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure subscription for the key vault.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="KeyVaultName"::: -->
:::moniker range="<=azure-pipelines"

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

:::moniker range="<=azure-pipelines-2020.1"

**`SecretsFilter`** - **Secrets filter**<br>
Type: string. Required. Allowed values: 'EditableOptions'. Default value: '*'.<br>
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

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

**`RunAsPreJob`** - **Make secrets available to whole job**<br>
Type: boolean. Required. Allowed values: 'EditableOptions'. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run the task before job execution begins. Exposes secrets to all tasks in the job, not just tasks that follow this one.
<!-- :::editable-content-end::: -->

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

There is a newer version of the Archive Files task available.

* [Azure Key Vault v2](azure-key-vault-v2.md)
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