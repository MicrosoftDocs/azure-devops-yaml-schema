---
title: ServiceFabricComposeDeploy@0 - Service Fabric Compose deploy v0 task
description: Deploy a Docker Compose application to an Azure Service Fabric cluster.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# ServiceFabricComposeDeploy@0 - Service Fabric Compose deploy v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Deploy a Docker Compose application to an Azure Service Fabric cluster.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Deploy a docker-compose application to a Service Fabric cluster.
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
    clusterConnection: # string. Required. Cluster Service Connection. 
    composeFilePath: '**/docker-compose.yml' # string. Required. Compose File Path. Default: '**/docker-compose.yml'.
    applicationName: 'fabric:/Application1' # string. Required. Application Name. Default: 'fabric:/Application1'.
  # Registry Settings
    registryCredentials: 'AzureResourceManagerEndpoint' # 'AzureResourceManagerEndpoint' | 'ContainerRegistryEndpoint' | 'UsernamePassword' | 'None'. Required. Registry Credentials Source. Default: 'AzureResourceManagerEndpoint'.
    #dockerRegistryConnection: # string. Optional. Use when registryCredentials = ContainerRegistryEndpoint. Docker Registry Service Connection. 
    azureSubscription: # string. Required when registryCredentials = AzureResourceManagerEndpoint. Azure subscription. 
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
    clusterConnection: # string. Required. Cluster Service Connection. 
    composeFilePath: '**/docker-compose.yml' # string. Required. Compose File Path. Default: '**/docker-compose.yml'.
    applicationName: 'fabric:/Application1' # string. Required. Application Name. Default: 'fabric:/Application1'.
  # Registry Settings
    registryCredentials: 'AzureResourceManagerEndpoint' # 'AzureResourceManagerEndpoint' | 'ContainerRegistryEndpoint' | 'UsernamePassword' | 'None'. Required. Registry Credentials Source. Default: 'AzureResourceManagerEndpoint'.
    #dockerRegistryConnection: # string. Optional. Use when registryCredentials = ContainerRegistryEndpoint. Docker Registry Service Connection. 
    azureSubscription: # string. Required when registryCredentials = AzureResourceManagerEndpoint. Azure subscription. 
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

<!-- :::item name="clusterConnection"::: -->
:::moniker range=">=azure-pipelines-2019"

**`clusterConnection`** - **Cluster Service Connection**<br>
Input alias: `serviceConnectionName`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure Service Fabric service connection to be used to connect to the cluster. Choose 'Manage' to register a new service connection.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`clusterConnection`** - **Cluster Connection**<br>
Input alias: `serviceConnectionName`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure Service Fabric service connection to be used to connect to the cluster. Choose 'Manage' to register a new service connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="composeFilePath"::: -->
:::moniker range="<=azure-pipelines"

**`composeFilePath`** - **Compose File Path**<br>
Type: string. Required. Default value: '**/docker-compose.yml'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the compose file that is to be deployed. [Variables](https://go.microsoft.com/fwlink/?LinkID=550988) and wildcards can be used in the path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="applicationName"::: -->
:::moniker range="<=azure-pipelines"

**`applicationName`** - **Application Name**<br>
Type: string. Required. Default value: 'fabric:/Application1'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the application being deployed.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registryCredentials"::: -->
:::moniker range="<=azure-pipelines"

**`registryCredentials`** - **Registry Credentials Source**<br>
Type: string. Required. Allowed values: 'AzureResourceManagerEndpoint', 'ContainerRegistryEndpoint', 'UsernamePassword', 'None'. Default value: 'AzureResourceManagerEndpoint'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose if/how credentials for the docker registry will be provided.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerRegistryConnection"::: -->
:::moniker range=">=azure-pipelines-2019"

**`dockerRegistryConnection`** - **Docker Registry Service Connection**<br>
Input alias: `dockerRegistryEndpointName`. Type: string. Optional. Use when registryCredentials = ContainerRegistryEndpoint.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker registry service connection. If a certificate matching the Server Certificate Thumbprint in the Cluster Service Connection is installed on the build agent, it will be used to encrypt the password; otherwise the password will not be encrypted.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`dockerRegistryConnection`** - **Docker Registry Connection**<br>
Input alias: `dockerRegistryEndpointName`. Type: string. Optional. Use when registryCredentials = ContainerRegistryEndpoint.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker registry service connection. If a certificate matching the Server Certificate Thumbprint in the Cluster Service Connection is installed on the build agent, it will be used to encrypt the password; otherwise the password will not be encrypted.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `azureSubscriptionEndpoint`. Type: string. Required when registryCredentials = AzureResourceManagerEndpoint.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure subscription.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registryUserName"::: -->
:::moniker range="<=azure-pipelines"

**`registryUserName`** - **Registry User Name**<br>
Type: string. Optional. Use when registryCredentials = UsernamePassword.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Username for the Docker registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registryPassword"::: -->
:::moniker range="<=azure-pipelines"

**`registryPassword`** - **Registry Password**<br>
Type: string. Optional. Use when registryCredentials = UsernamePassword.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password for the Docker registry. If the password is not encrypted, it is recommended that you use a custom release pipeline secret variable to store it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="passwordEncrypted"::: -->
:::moniker range="<=azure-pipelines"

**`passwordEncrypted`** - **Password Encrypted**<br>
Type: boolean. Optional. Use when registryCredentials = UsernamePassword. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
It is recommended to encrypt your password using [Invoke-ServiceFabricEncryptText](/azure/service-fabric/service-fabric-application-secret-management#encrypt-application-secrets). If you do not, and a certificate matching the Server Certificate Thumbprint in the Cluster Service Connection is installed on the build agent, it will be used to encrypt the password; otherwise an error will occur.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="upgrade"::: -->
:::moniker range=">=azure-pipelines-2019"

**`upgrade`** - **Upgrade**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Upgrade an existing deployment rather than removing it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`deployTimeoutSec`** - **Deploy Timeout (s)**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Timeout in seconds for deploying the application.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="removeTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`removeTimeoutSec`** - **Remove Timeout (s)**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Timeout in seconds for removing an existing application.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="getStatusTimeoutSec"::: -->
:::moniker range="<=azure-pipelines"

**`getStatusTimeoutSec`** - **Get Status Timeout (s)**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Timeout in seconds for getting the status of an existing application.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

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