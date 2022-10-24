---
title: AzureKeyVault@2 - Azure Key Vault v2 task
description: Download Azure Key Vault secrets.
ms.date: 10/21/2022
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
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    KeyVaultName: # string. Required. Key vault. 
    SecretsFilter: '*' # string. Required. Secrets filter. Default: *.
    RunAsPreJob: false # boolean. Required. Make secrets available to whole job. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2022"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the service connection for the Azure subscription containing the Azure Key Vault instance, or create a new connection. [Learn more](/azure/devops/pipelines/library/connect-to-azure).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="KeyVaultName"::: -->
:::moniker range=">=azure-pipelines-2022"

**`KeyVaultName`** - **Key vault**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the name of the Azure Key Vault from which the secrets will be downloaded.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SecretsFilter"::: -->
:::moniker range=">=azure-pipelines-2022"

**`SecretsFilter`** - **Secrets filter**<br>
`string`. Required. Default value: `*`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma separated list of secret names or leave * to download all secrets from the selected key vault.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RunAsPreJob"::: -->
:::moniker range=">=azure-pipelines-2022"

**`RunAsPreJob`** - **Make secrets available to whole job**<br>
`boolean`. Required. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run the task before job execution begins. Exposes secrets to all tasks in the job, not just tasks that follow this one.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
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

Use this task to download secrets such as authentication keys, storage account keys, data encryption keys, .PFX files, and passwords
from an [Azure Key Vault](/rest/api/keyvault/about-keys--secrets-and-certificates) instance.
The task can be used to fetch the latest values of all or a subset of secrets from the vault, and set them as variables that can be used in subsequent tasks of a pipeline.
The task is Node-based, and works with agents on Linux, macOS, and Windows.

### Prerequisites

The task has the following Prerequisites:

* An Azure subscription linked to Azure Pipelines or Team Foundation Server using the [Azure Resource Manager service connection](/azure/devops/pipelines/library/connect-to-azure).
* An [Azure Key Vault](https://azure.microsoft.com/services/key-vault/) containing the secrets.

You can create a key vault:

* In the [Azure portal](https://ms.portal.azure.com/#create/Microsoft.KeyVault)
* By using [Azure PowerShell](/azure/key-vault/key-vault-get-started)
* By using the [Azure CLI](/azure/key-vault/key-vault-manage-with-cli2)

Add secrets to a key vault:

* By using the PowerShell cmdlet [Set-AzureKeyVaultSecret](/powershell/module/azurerm.keyvault/set-azurekeyvaultsecret).
  If the secret does not exist, this cmdlet creates it. If the secret already exists, this cmdlet creates a new version of that secret.
* By using the Azure CLI. To add a secret to a key vault, for example a secret named **SQLPassword** with the value **PlaceholderPassword**, type:

  ```azurecli
  az keyvault secret set --vault-name 'ContosoKeyVault' --name 'SQLPassword' --value 'PlaceholderPassword'
  ```

When you want to access secrets:

* Ensure the Azure service connection has at least **Get** and **List** permissions
  on the vault. You can set these permissions in the [Azure portal](https://portal.azure.com):

  - Open the **Settings** blade for the vault, choose **Access policies**, then **Add new**.
  - In the **Add access policy** blade, choose **Select principal** and select the service principal for your client account.
  - In the **Add access policy** blade, choose **Secret permissions** and ensure that **Get** and **List** are checked (ticked).
  - Choose **OK** to save the changes.<p />
  
> [!NOTE]
> If you're using a Microsoft-hosted agent, you must add the IP range of the Microsoft-hosted agent to your firewall. Get the weekly list of IP ranges from the [weekly JSON file](https://www.microsoft.com/download/details.aspx?id=56519), which is published every Wednesday. The new IP ranges become effective the following Monday. For more information, see [Microsoft-hosted agents](/azure/devops/pipelines/agents/hosted#networking).
> To find the IP ranges that are required for your Azure DevOps organization, learn how to [identify the possible IP ranges for Microsoft-hosted agents](/azure/devops/pipelines/agents/hosted#to-identify-the-possible-ip-ranges-for-microsoft-hosted-agents).

> [!NOTE]
> Values are retrieved as strings. For example, if there is a secret named **connectionString**,
> a task variable `connectionString` is created with the latest value of the respective secret
> fetched from Azure key vault. This variable is then available in subsequent tasks.

If the value fetched from the vault is a certificate (for example, a PFX file), the task variable
will contain the contents of the PFX in string format. You can use the following PowerShell code
to retrieve the PFX file from the task variable:
 
```powershell
$kvSecretBytes = [System.Convert]::FromBase64String($(PfxSecret))
$certCollection = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2Collection
$certCollection.Import($kvSecretBytes,$null,[System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::Exportable)
```

If the certificate file will be stored locally on the machine, it is good practice
to encrypt it with a password: 

```powershell
 #Get the file created
$password = 'your password'
$protectedCertificateBytes = $certCollection.Export([System.Security.Cryptography.X509Certificates.X509ContentType]::Pkcs12, $password)
$pfxPath = [Environment]::GetFolderPath("Desktop") + "\MyCert.pfx"
[System.IO.File]::WriteAllBytes($pfxPath, $protectedCertificateBytes)
```

For more information, see [Get started with Azure Key Vault certificates](/archive/blogs/kv/get-started-with-azure-key-vault-certificates).
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