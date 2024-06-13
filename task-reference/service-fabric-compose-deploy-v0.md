---
title: ServiceFabricComposeDeploy@0 - Service Fabric Compose deploy v0 task
description: Deploy a Docker Compose application to an Azure Service Fabric cluster.
ms.date: 06/11/2024
monikerRange: "<=azure-pipelines"
---

# ServiceFabricComposeDeploy@0 - Service Fabric Compose deploy v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to deploy a Docker Compose application to a Service Fabric cluster. This task deploys an Azure Service Fabric application to a cluster according to the settings defined in the Compose file.

[!INCLUDE [workload-identity](./includes/workload-identity-not-supported.md)]
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Service Fabric Compose deploy v0
# Deploy a Docker Compose application to an Azure Service Fabric cluster.
- task: ServiceFabricComposeDeploy@0
  inputs:
    clusterConnection: # string. Alias: serviceConnectionName. Required. Cluster Service Connection. 
    composeFilePath: '**/docker-compose.yml' # string. Required. Compose File Path. Default: **/docker-compose.yml.
    applicationName: 'fabric:/Application1' # string. Required. Application Name. Default: fabric:/Application1.
  # Registry Settings
    registryCredentials: 'AzureResourceManagerEndpoint' # 'AzureResourceManagerEndpoint' | 'ContainerRegistryEndpoint' | 'UsernamePassword' | 'None'. Required. Registry Credentials Source. Default: AzureResourceManagerEndpoint.
    #dockerRegistryConnection: # string. Alias: dockerRegistryEndpointName. Optional. Use when registryCredentials = ContainerRegistryEndpoint. Docker Registry Service Connection. 
    azureSubscription: # string. Alias: azureSubscriptionEndpoint. Required when registryCredentials = AzureResourceManagerEndpoint. Azure subscription. 
    #registryUserName: # string. Optional. Use when registryCredentials = UsernamePassword. Registry User Name. 
    #registryPassword: # string. Optional. Use when registryCredentials = UsernamePassword. Registry Password. 
    #passwordEncrypted: true # boolean. Optional. Use when registryCredentials = UsernamePassword. Password Encrypted. Default: true.
  # Advanced Settings
    #upgrade: false # boolean. Upgrade. Default: false.
    #deployTimeoutSec: # string. Deploy Timeout (s). 
    #removeTimeoutSec: # string. Remove Timeout (s). 
    #getStatusTimeoutSec: # string. Get Status Timeout (s).
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Service Fabric Compose Deploy v0
# Deploy a docker-compose application to a Service Fabric cluster.
- task: ServiceFabricComposeDeploy@0
  inputs:
    clusterConnection: # string. Alias: serviceConnectionName. Required. Cluster Service Connection. 
    composeFilePath: '**/docker-compose.yml' # string. Required. Compose File Path. Default: **/docker-compose.yml.
    applicationName: 'fabric:/Application1' # string. Required. Application Name. Default: fabric:/Application1.
  # Registry Settings
    registryCredentials: 'AzureResourceManagerEndpoint' # 'AzureResourceManagerEndpoint' | 'ContainerRegistryEndpoint' | 'UsernamePassword' | 'None'. Required. Registry Credentials Source. Default: AzureResourceManagerEndpoint.
    #dockerRegistryConnection: # string. Alias: dockerRegistryEndpointName. Optional. Use when registryCredentials = ContainerRegistryEndpoint. Docker Registry Service Connection. 
    azureSubscription: # string. Alias: azureSubscriptionEndpoint. Required when registryCredentials = AzureResourceManagerEndpoint. Azure subscription. 
    #registryUserName: # string. Optional. Use when registryCredentials = UsernamePassword. Registry User Name. 
    #registryPassword: # string. Optional. Use when registryCredentials = UsernamePassword. Registry Password. 
    #passwordEncrypted: true # boolean. Optional. Use when registryCredentials = UsernamePassword. Password Encrypted. Default: true.
  # Advanced Settings
    #upgrade: false # boolean. Upgrade. Default: false.
    #deployTimeoutSec: # string. Deploy Timeout (s). 
    #removeTimeoutSec: # string. Remove Timeout (s). 
    #getStatusTimeoutSec: # string. Get Status Timeout (s).
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="clusterConnection"::: -->
:::moniker range=">=azure-pipelines-2019"

**`clusterConnection`** - **Cluster Service Connection**<br>
Input alias: `serviceConnectionName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an Azure Service Fabric service connection to be used to connect to the cluster. Choose `Manage` to register a new service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="composeFilePath"::: -->
:::moniker range="<=azure-pipelines"

**`composeFilePath`** - **Compose File Path**<br>
`string`. Required. Default value: `**/docker-compose.yml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the compose file that is to be deployed. [Variables](/azure/devops/pipelines/build/variables) and wildcards can be used in the path. Example: `$(System.DefaultWorkingDirectory)/**/drop/projectartifacts/**/docker-compose.yml`. 
> [!NOTE]
> Combining compose files is not supported as part of this task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="applicationName"::: -->
:::moniker range="<=azure-pipelines"

**`applicationName`** - **Application Name**<br>
`string`. Required. Default value: `fabric:/Application1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Service Fabric application name of the deployed application. Use `fabric:/` as a prefix. Application names within a Service Fabric cluster must be unique.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registryCredentials"::: -->
:::moniker range=">=azure-pipelines-2019"

**`registryCredentials`** - **Registry Credentials Source**<br>
`string`. Required. Allowed values: `AzureResourceManagerEndpoint` (Azure Resource Manager service connection), `ContainerRegistryEndpoint` (Container Registry service connection), `UsernamePassword` (Username and Password), `None`. Default value: `AzureResourceManagerEndpoint`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies how credentials for the Docker container registry will be provided to the deployment task. The allowed values are:

* `AzureResourceManagerEndpoint` (Azure Resource Manager service connection): uses `azureSubscription` to obtain a service principal ID and key for an Azure Container Registry.
* `ContainerRegistryEndpoint` (Container Registry service connection): uses `dockerRegistryConnection` to select a Docker registry service connection. If a certificate matching the Server Certificate Thumbprint in the Cluster Service Connection is installed on the build agent, it will be used to encrypt the password; otherwise, the password will not be encrypted.
* `UsernamePassword` (Username and Password): uses `registryUsername` and `registryPassword` to store the username and password for the Docker registry. Passwords should be encrypted using [Invoke-ServiceFabricEncryptText](/azure/service-fabric/service-fabric-application-secret-management#encrypt-application-secrets) with the `Password Encrypted` option. If passwords are not encrypted with `Invoke-ServiceFabricEncryptText`, and a certificate matching the Server Certificate Thumbprint in the Cluster Connection is installed on the build agent, the certificate will be used to encrypt the password. Otherwise, the password will not be encrypted and will be sent in clear text.
* `None`: No registry credentials are provided. This is used for accessing public container registries.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerRegistryConnection"::: -->
:::moniker range=">=azure-pipelines-2019"

**`dockerRegistryConnection`** - **Docker Registry Service Connection**<br>
Input alias: `dockerRegistryEndpointName`. `string`. Optional. Use when `registryCredentials = ContainerRegistryEndpoint`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a Docker registry service connection. If a certificate matching the Server Certificate Thumbprint in the Cluster Service Connection is installed on the build agent, it will be used to encrypt the password; otherwise, the password will not be encrypted.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `azureSubscriptionEndpoint`. `string`. Required when `registryCredentials = AzureResourceManagerEndpoint`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an Azure subscription.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registryUserName"::: -->
:::moniker range="<=azure-pipelines"

**`registryUserName`** - **Registry User Name**<br>
`string`. Optional. Use when `registryCredentials = UsernamePassword`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the username for the Docker registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registryPassword"::: -->
:::moniker range="<=azure-pipelines"

**`registryPassword`** - **Registry Password**<br>
`string`. Optional. Use when `registryCredentials = UsernamePassword`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the Docker registry. If the password is not encrypted, it is recommended that you use a custom release pipeline secret variable to store it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="passwordEncrypted"::: -->
:::moniker range="<=azure-pipelines"

**`passwordEncrypted`** - **Password Encrypted**<br>
`boolean`. Optional. Use when `registryCredentials = UsernamePassword`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Encrypts your password using [Invoke-ServiceFabricEncryptText](/azure/service-fabric/service-fabric-application-secret-management#encrypt-application-secrets). If you do not encrypt your password, and a certificate matching the Server Certificate Thumbprint in the Cluster Service Connection is installed on the build agent, it will be used to encrypt the password; otherwise, an error will occur.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="upgrade"::: -->
:::moniker range=">=azure-pipelines-2019"

**`upgrade`** - **Upgrade**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Upgrades an existing deployment rather than removing it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`deployTimeoutSec`** - **Deploy Timeout (s)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the timeout, in seconds,for deploying the application.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="removeTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`removeTimeoutSec`** - **Remove Timeout (s)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the timeout, in seconds,for removing an existing application.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="getStatusTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`getStatusTimeoutSec`** - **Get Status Timeout (s)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the timeout, in seconds,for getting the status of an existing application.
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

Use this task to deploy a Docker-compose application to a Service Fabric cluster.
This task deploys an Azure Service Fabric application to a cluster according to the settings defined in the compose file.

> [!NOTE]
> This task is currently in preview and requires a preview version of Service Fabric that supports compose deploy.
See [Docker Compose deployment support in Azure Service Fabric](/azure/service-fabric/service-fabric-docker-compose).

### Service Fabric

* This task uses a Service Fabric installation to connect and deploy to a Service Fabric cluster.
* Download and install [Azure Service Fabric Core SDK](https://www.microsoft.com/web/handlers/webpi.ashx?command=getinstallerredirect&appid=MicrosoftAzure-ServiceFabric-CoreSDK) on the build agent.
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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: Cmd |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.95.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->