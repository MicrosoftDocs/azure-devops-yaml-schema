---
title: Notation@0 - Notation v0 task
description: Azure Pipepine Task for setting up Notation CLI, sign and verify with Notation.
ms.date: 12/08/2023
monikerRange: "=azure-pipelines"
---

# Notation@0 - Notation v0 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Azure Pipepine Task for setting up Notation CLI, sign and verify with Notation.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Notation v0
# Azure Pipepine Task for setting up Notation CLI, sign and verify with Notation.
- task: Notation@0
  inputs:
    command: 'install' # 'install' | 'sign' | 'verify'. Required. Command to run. Default: install.
  # Command Configuration
    #isCustomVersion: false # boolean. Optional. Use when command = install. Custom Version. Default: false.
    #version: '1.0.1' # string. Required when command = install && isCustomVersion = false. Version. Default: 1.0.1.
    #url: # string. Required when command = install && isCustomVersion = true. Download URL. 
    #checksum: # string. Required when command = install && isCustomVersion = true. Checksum. 
    #artifactRefs: # string. Optional. Use when command = verify || command = sign. Artifact references. 
    #trustPolicy: # string. Required when command = verify. Trust Policy File Path. 
    #trustStore: # string. Required when command = verify. Trust Store Folder Path. 
  # Advanced Configuration
    #signatureFormat: 'cose' # 'cose' | 'jws'. Optional. Use when command = sign && command = sign || command = verify. Signature Format. Default: cose.
    #allowReferrersAPI: false # boolean. Optional. Use when command = sign || command = verify. [Experimental] Allow Referrers API. Default: false.
  # Plugin Configuration
    #plugin: 'azureKeyVault' # 'azureKeyVault'. Required when command = sign. Plugin. Default: azureKeyVault.
    #akvPluginVersion: '1.0.1' # string. Required when plugin = azureKeyVault && command = sign. Plugin Version. Default: 1.0.1.
    #azurekvServiceConection: # string. Optional. Use when plugin = azureKeyVault && command = sign. Azure Key Vault service connection. 
    #keyid: # string. Required when plugin = azureKeyVault && command = sign. Key ID. 
    #caCertBundle: # string. Optional. Use when plugin = azureKeyVault && command = sign. Certificate Bundle File Path. 
    #selfSigned: false # boolean. Optional. Use when plugin = azureKeyVault && command = sign. Self-signed Certificate. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="command"::: -->
:::moniker range="=azure-pipelines"

**`command`** - **Command to run**<br>
`string`. Required. Allowed values: `install`, `sign`, `verify`. Default value: `install`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the command mode of the task.

* **install** - The `install` command detects the current operating system and architecture to download the corresponding Notation CLI from GitHub releases. It also verifies the checksum of the downloaded file against the golden file in the `./data` folder and adds Notation to the PATH.
* **sign** - The `sign` command downloads the selected Notation plugin, validates its checksum, and then calls on the Notation CLI to sign.
* **verify** - The `verify` command transfers the trust store and trust policy from the user's code repository to the Notation configuration folder, as required by Notation CLI. It then invokes the Notation CLI to perform verification.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isCustomVersion"::: -->
:::moniker range="=azure-pipelines"

**`isCustomVersion`** - **Custom Version**<br>
`boolean`. Optional. Use when `command = install`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify `true` to provide a custom version of Notation for the task by specifying a download URL to the custom version in the `url` property.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range="=azure-pipelines"

**`version`** - **Version**<br>
`string`. Required when `command = install && isCustomVersion = false`. Default value: `1.0.1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of Notation to install. Example: 1.0.0, 1, 1.0, 1.0.0.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="url"::: -->
:::moniker range="=azure-pipelines"

**`url`** - **Download URL**<br>
`string`. Required when `command = install && isCustomVersion = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The URL to a custom version of Notation to use, for example: `https://github.com/notaryproject/notation/releases/download/v1.0.0/notation_1.0.0_linux_amd64.tar.gz`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checksum"::: -->
:::moniker range="=azure-pipelines"

**`checksum`** - **Checksum**<br>
`string`. Required when `command = install && isCustomVersion = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The SHA-256 checksum of the downloaded file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="artifactRefs"::: -->
:::moniker range="=azure-pipelines"

**`artifactRefs`** - **Artifact references**<br>
`string`. Optional. Use when `command = verify || command = sign`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Container artifact references for signing. If not specified, the task uses the artifact reference from the previous Docker push task. Example: `<registry name>/<repository name>@<digest>`. Multiple artifact references must be comma separated.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signatureFormat"::: -->
:::moniker range="=azure-pipelines"

**`signatureFormat`** - **Signature Format**<br>
`string`. Optional. Use when `command = sign && command = sign || command = verify`. Allowed values: `cose`, `jws`. Default value: `cose`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Signature envelope format.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowReferrersAPI"::: -->
:::moniker range="=azure-pipelines"

**`allowReferrersAPI`** - **[Experimental] Allow Referrers API**<br>
`boolean`. Optional. Use when `command = sign || command = verify`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use the Referrers API to sign signatures, if not supported (returns 404), fallback to the Referrers tag schema.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="plugin"::: -->
:::moniker range="=azure-pipelines"

**`plugin`** - **Plugin**<br>
`string`. Required when `command = sign`. Allowed values: `azureKeyVault` (Azure Key Vault Plugin). Default value: `azureKeyVault`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="akvPluginVersion"::: -->
:::moniker range="=azure-pipelines"

**`akvPluginVersion`** - **Plugin Version**<br>
`string`. Required when `plugin = azureKeyVault && command = sign`. Default value: `1.0.1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of the Azure Key Vault plugin to be installed. See the [notation-azure-kv releases page](https://github.com/Azure/notation-azure-kv/releases) for the available versions.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azurekvServiceConection"::: -->
:::moniker range="=azure-pipelines"

**`azurekvServiceConection`** - **Azure Key Vault service connection**<br>
`string`. Optional. Use when `plugin = azureKeyVault && command = sign`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure subscription for the key vault if prefer to use service connection for authentication.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="keyid"::: -->
:::moniker range="=azure-pipelines"

**`keyid`** - **Key ID**<br>
`string`. Required when `plugin = azureKeyVault && command = sign`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Key ID is the key or certificate identifier for Azure Key Vault.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="caCertBundle"::: -->
:::moniker range="=azure-pipelines"

**`caCertBundle`** - **Certificate Bundle File Path**<br>
`string`. Optional. Use when `plugin = azureKeyVault && command = sign`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The certificate bundle file with root and all intermediate certificates, starting from the root certificate, following the order in the certificate chain.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="selfSigned"::: -->
:::moniker range="=azure-pipelines"

**`selfSigned`** - **Self-signed Certificate**<br>
`boolean`. Optional. Use when `plugin = azureKeyVault && command = sign`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Whether the certificate is a self-signed certificate.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="trustPolicy"::: -->
:::moniker range="=azure-pipelines"

**`trustPolicy`** - **Trust Policy File Path**<br>
`string`. Required when `command = verify`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the [trust policy](https://github.com/notaryproject/specifications/blob/v1.0.0/specs/trust-store-trust-policy.md#trust-policy) file relative to the repository. Example: `./path/to/trust-policy.json`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="trustStore"::: -->
:::moniker range="=azure-pipelines"

**`trustStore`** - **Trust Store Folder Path**<br>
`string`. Required when `command = verify`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the directory containing the [trust store](https://github.com/notaryproject/specifications/blob/v1.0.0/specs/trust-store-trust-policy.md#trust-store) relative to the repository. Example: `./path/to/truststore/`.
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

The Notation task calls upon the Notation CLI to execute signing and verification operations. Notation CLI is a tool used to sign and verify Docker container artifacts or images. When signing an artifact, Notation signs the artifact's unique manifest descriptor and attaches the signature to the same repository. When verifying an artifact, Notation retrieves the signature from the repository and validates it against the certificate in the trust store.

### Prerequisites

* This task requires public network access for downloading Notation CLI and Notation Azure Key Vault plugin from Github releases.
* Supported Agent OS: Linux x64/ARM64, Windows x64, macOS x64/ARM64

### Notation install command

The `install` command detects the current operating system and architecture to download the corresponding Notation CLI from GitHub releases. It also verifies the checksum of the downloaded file against the golden file in the `./data` folder and adds Notation to the PATH.

### Notation sign command

The `sign` command downloads the selected Notation plugin, validates its checksum, and then calls on the Notation CLI to sign.

### Notation verfy command

The `verify` command transfers the trust store and trust policy from the user's code repository to the Notation configuration folder, as required by Notation CLI. It then invokes the Notation CLI to perform verification.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

The following example shows you to create a pipeline to achieve the following goals:

1. Build a container image and push it to Azure Container Registry (ACR).
2. Install Notation CLI, sign the image with Notation and Notation AKV plugin. The generated signature will be automatically pushed to ACR.

### Example prerequisites

* You have created a Key Vault in Azure Key Vault and created a self-signed signing key and certificate. See [Sign container images with Notation and Azure Key Vault using a self-signed certificate](/azure/container-registry/container-registry-tutorial-sign-build-push#create-a-self-signed-certificate-azure-cli) to create self-signed key and certificate for testing purposes. If you have a CA issued certificate, see [Sign container images with Notation and Azure Key Vault using a CA-issued certificate](/azure/container-registry/container-registry-tutorial-sign-trusted-ca).
* You have created a registry in ACR.
* You have an Azure DevOps Git repository or GitHub repository.

### Create Service Connection

Signing an image stored in ACR registry requires the ACR credential. Use the [Docker task](./docker-v2.md#build-and-push) to log in to the ACR registry.

#### Create a Docker service connection

Create a [Docker Registry service connection](/azure/devops/pipelines/library/service-endpoints#docker-registry-service-connection) in Azure DevOps pipeline to grant the access permission to your ACR registry for the Notation tasks in your pipeline.

1. Sign in to your organization (`https://dev.azure.com/{yourorganization}`) and select your project.
1. Select the **Settings** button in the bottom-left corner.
1. Go to **Pipelines**, and then select **Service connection**.
1. Choose **New service connection** and select **Docker Registry**.
1. Next choose **Azure Container Registry**.
1. Choose **Service Principle** in the **Authentication Type** and enter the Service Principal details including your Azure Subscription and ACR registry.
1. Enter a user-friendly **Connection name** to use when referring to this service connection.

#### Create am Azure Resource Manager service connection

Similarly, Create a service connection with the connection type of [Azure Resource Manager](/azure/devops/pipelines/library/service-endpoints#azure-resource-manager-service-connection). This will grant the access to your Azure Key Vault:

1. Choose **Service principal (automatic)**.
1. Next, choose **Subscription** and find your Azure subscription from the drop-down list.
1. Choose an available Resource group from the drop-down list.
1. Enter a user-friendly **Service connection name** to use when referring to this service connection.
1. Save it to finish the creation.

#### Grant the access policy to your service principal

1. Open the created Azure Resource Manager service connection and click **Manage Service Principal** to enter the Azure service principal portal.
1. Copy the `Application (client) ID`. It will be used to grant the permission for the service principal.
1. Open the Azure Key Vault portal and enter **Access Policies** page.
1. Create a new access policy with `key sign`, `secret get` and `certificate get` permission.
1. Grant this new access policy to a service principle using the `Application (client) ID` paste from the previous step.
1. Save it to finish the creation.

See [Create a service connection](/azure/devops/pipelines/library/service-endpoints#create-a-service-connection) for more details.

### Create a pipeline and use the Notation task

Create an Azure pipeline for your git repository as follows:

1. Navigate to the project in your Azure DevOps organization.
1. Go to **Pipelines** from the left menu and then select **New pipeline**. 
1. Choose your git repository. We use the Azure DevOps repository for demonstration convenience.
1. Configure the pipeline with a **Starter Pipeline** if you are new to Azure DevOps. Review and create the pipeline by clicking on **Save and run**.

> [!NOTE]
> The example use a default branch name of `main`. If it's not, please follow the [guide](/azure/devops/repos/git/change-default-branch#temporary-mirroring) to update the default branch.

Edit the pipeline created in the previous step. There are two ways to use Notation tasks to sign images in your Azure pipeline: use the [task assistant](/azure/devops/pipelines/get-started/yaml-pipeline-editor#use-task-assistant) to add Notation tasks to your pipeline, or copy from the sample Azure Pipeline file.

### Option 1: Use the task assitant

#### Add a Docker task with login command

1. Search for the `Docker` task from the [task assistant](/azure/devops/pipelines/get-started/yaml-pipeline-editor#use-task-assistant) on the right side. We use its `login` command with the Docker Registry service connection to authenticate with ACR.
1. Choose the Docker Registry service connection created in the previous step from the **Container registry** drop-down list. Click **Add** to add the `notation install` task to the pipeline. 
1. Choose `login` from the **Command** drop-down list.
1. Click **Add** to add the `notation sign` to the pipeline file left.

#### Add a Docker task with buildAndPush command

1. Search the `Docker` task from the task assistant. We use its `buildAndPush` command to automatically build the source code to an image and push it to the target ACR repository. It will generate an image digest that will be used for signing in the next step.
1. Input the repository name to **Container repository**.
1. Choose **buildAndPush** from the the **Command** drop-down list.
1. Specify the file path of Dockerfile. For example, use `./Dockerfile` if your Dockerfile is stored in the root folder.
1. Click **Add** to add the `notation sign` to the pipeline file left.

#### Add a Notation task with install command

1. Search the `Notation` task from the task assistant on the right side.
1. Choose **Install** from the drop-down list **command to run**. Click **Add** to add the `notation install` task to the pipeline.

#### Add a Notation task with sign command

1. Similarly, search the `Notation` task from the task assistantagain and choose **Sign**. 
1. You can skip **Artifact references** since we sign an image using its latest digest that is built and pushed to the registry by a [Docker task](./docker-v2.md). Instead, you can manually specify a digest using `<registry_host>/<repository>@<digest>`.
1. Fill out the plugin configuration in the form. We will use the default AKV plugin and the service connection created in the previous step. Copy your Key ID from your AKV into the **Key ID**.
1. Check the **Self-signed Certificate** box since we use a self-signed certificate for demonstration convenience. Instead, you can input your certificate file path in **Certificate Bundle File Path** if you want to use a CA issued certificate.
1. Click **Add** to add the `notation sign` to the pipeline.

### Option 2: Editing the pipeline YAML file

If you are familiar with Azure Pipeline and Notation, start with a template pipeline file will be efficient to use Notation tasks.

Copy the following pipeline template to your pipeline file. Then fill out the required values according to the references and comments below.

```yaml
trigger:
 - main
pool: 
  vmImage: 'ubuntu-latest'

steps:
# log in to registry
- task: Docker@2
  inputs:
    containerRegistry: <your_docker_registry_service_connection>
    command: 'login'
# build and push artifact to registry
- task: Docker@2
  inputs:
    repository: <your_repository_name>
    command: 'buildAndPush'
    Dockerfile: './Dockerfile'
# install notation
- task: Notation@0
  inputs:
    command: 'install'
    version: '1.0.0'
# automatically detect the artifact pushed by Docker task and sign the artifact.
- task: Notation@0
  inputs:
    command: 'sign'
    plugin: 'azureKeyVault'
    akvPluginVersion: <azure_key_vault_plugin_version>
    azurekvServiceConection: <your_akv_service_connection>
    keyid: <your_key_id>
    selfSigned: true
```

In addition to using the Docker task, you can sign a specified image digest by manually specifying an artifact reference in `artifactRefs` as follows.

```yaml
# sign the artifact
- task: Notation@0
  inputs:
    artifactRefs: '<registry_host>/<repository>@<digest>'
    command: 'sign'
    plugin: 'azureKeyVault'
    akvPluginVersion: <azure_key_vault_plugin_version>
    azurekvServiceConection: <akv_service_connection>
    keyid: <key_id>
    selfSigned: true
```

### Run the pipeline

After filled out the inputs in the pipeline, you can save and run it to trigger the pipeline.

Go to **Job** page of the running pipeline, you will be able to see the execution result in each step. This pipeline will build and sign the latest build or the specified digest, then will push the signed image with its associated signature to the registry. On success, you will be able to see the image pushed to your ACR with a COSE format signature attached.
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
| Agent version |  2.144.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->