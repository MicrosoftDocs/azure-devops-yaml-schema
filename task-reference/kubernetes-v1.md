---
title: Kubernetes@1 - Kubectl v1 task
description: Deploy, configure, update a Kubernetes cluster in Azure Container Service by running kubectl commands.
ms.date: 08/10/2022
monikerRange: ">=azure-pipelines-2019"
---

# Kubernetes@1 - Kubectl v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Deploy, configure, update a Kubernetes cluster in Azure Container Service by running kubectl commands.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Deploy, configure, update your Kubernetes cluster in Azure Container Service by running kubectl commands.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020.1"

```yaml
# Kubectl v1
# Deploy, configure, update a Kubernetes cluster in Azure Container Service by running kubectl commands.
- task: Kubernetes@1
  inputs:
  # Kubernetes Cluster
    connectionType: 'Kubernetes Service Connection' # 'Azure Resource Manager' | 'Kubernetes Service Connection' | 'None'. Required. Service connection type. Default: 'Kubernetes Service Connection'.
    #kubernetesServiceEndpoint: # string. Required when connectionType = Kubernetes Service Connection. Kubernetes service connection. 
    #azureSubscriptionEndpoint: # string. Required when connectionType = Azure Resource Manager. Azure subscription. 
    #azureResourceGroup: # string. Required when connectionType = Azure Resource Manager. Resource group. 
    #kubernetesCluster: # string. Required when connectionType = Azure Resource Manager. Kubernetes cluster. 
    #useClusterAdmin: false # boolean. Optional. Use when connectionType = Azure Resource Manager. Use cluster admin credentials. Default: false.
    #namespace: # string. Namespace. 
  # Commands
    #command: # 'apply' | 'create' | 'delete' | 'exec' | 'expose' | 'get' | 'login' | 'logout' | 'logs' | 'run' | 'set' | 'top'. Command. 
    #useConfigurationFile: false # boolean. Optional. Use when command != login && command != logout. Use configuration. Default: false.
    #configurationType: 'configuration' # 'configuration' | 'inline'. Optional. Use when useConfigurationFile = true. Configuration type. Default: 'configuration'.
    configuration: # string. Required when configurationType = configuration. File path. 
    #inline: # string. Required when configurationType = inline. Inline configuration. 
    #arguments: # string. Optional. Use when command != login && command != logout. Arguments. 
  # Secrets
    secretType: 'dockerRegistry' # 'dockerRegistry' | 'generic'. Required. Type of secret. Default: 'dockerRegistry'.
    #secretArguments: # string. Optional. Use when secretType = generic. Arguments. 
    containerRegistryType: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required when secretType = dockerRegistry. Container registry type. Default: 'Azure Container Registry'.
    #dockerRegistryEndpoint: # string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Container Registry. Docker registry service connection. 
    #azureSubscriptionEndpointForSecrets: # string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Azure Container Registry. Azure container registry. 
    #secretName: # string. Secret name. 
    #forceUpdate: true # boolean. Force update secret. Default: true.
  # ConfigMaps
    #configMapName: # string. ConfigMap name. 
    #forceUpdateConfigMap: false # boolean. Force update configmap. Default: false.
    #useConfigMapFile: false # boolean. Use file. Default: false.
    #configMapFile: # string. Required when useConfigMapFile = true. ConfigMap file. 
    #configMapArguments: # string. Optional. Use when useConfigMapFile = false. Arguments. 
  # Advanced
    #versionOrLocation: 'version' # 'version' | 'location'. Kubectl. Default: 'version'.
    #versionSpec: '1.13.2' # string. Optional. Use when versionOrLocation = version. Version spec. Default: '1.13.2'.
    #checkLatest: false # boolean. Optional. Use when versionOrLocation = version. Check for latest version. Default: false.
    #specifyLocation: # string. Required when versionOrLocation = location. Path to kubectl. 
    #workingDirectory: '$(System.DefaultWorkingDirectory)' # string. Working directory. Default: '$(System.DefaultWorkingDirectory)'.
    #outputFormat: 'json' # 'json' | 'yaml' | 'none'. Output format. Default: 'json'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Kubectl v1
# Deploy, configure, update a Kubernetes cluster in Azure Container Service by running kubectl commands.
- task: Kubernetes@1
  inputs:
  # Kubernetes Cluster
    connectionType: 'Kubernetes Service Connection' # 'Azure Resource Manager' | 'Kubernetes Service Connection' | 'None'. Required. Service connection type. Default: 'Kubernetes Service Connection'.
    #kubernetesServiceEndpoint: # string. Required when connectionType = Kubernetes Service Connection. Kubernetes service connection. 
    #azureSubscriptionEndpoint: # string. Required when connectionType = Azure Resource Manager. Azure subscription. 
    #azureResourceGroup: # string. Required when connectionType = Azure Resource Manager. Resource group. 
    #kubernetesCluster: # string. Required when connectionType = Azure Resource Manager. Kubernetes cluster. 
    #useClusterAdmin: false # boolean. Optional. Use when connectionType = Azure Resource Manager. Use cluster admin credentials. Default: false.
    #namespace: # string. Namespace. 
  # Commands
    #command: # 'apply' | 'create' | 'delete' | 'exec' | 'expose' | 'get' | 'login' | 'logout' | 'logs' | 'run' | 'set' | 'top'. Command. 
    #useConfigurationFile: false # boolean. Optional. Use when command != login && command != logout. Use configuration. Default: false.
    #configurationType: 'configuration' # 'configuration' | 'inline'. Optional. Use when useConfigurationFile = true. Configuration type. Default: 'configuration'.
    configuration: # string. Required when configurationType = configuration. File path. 
    #inline: # string. Required when configurationType = inline. Inline configuration. 
    #arguments: # string. Optional. Use when command != login && command != logout. Arguments. 
  # Secrets
    secretType: 'dockerRegistry' # 'dockerRegistry' | 'generic'. Required. Type of secret. Default: 'dockerRegistry'.
    #secretArguments: # string. Optional. Use when secretType = generic. Arguments. 
    containerRegistryType: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required when secretType = dockerRegistry. Container registry type. Default: 'Azure Container Registry'.
    #dockerRegistryEndpoint: # string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Container Registry. Docker registry service connection. 
    #azureSubscriptionEndpointForSecrets: # string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Azure Container Registry. Azure container registry. 
    #secretName: # string. Secret name. 
    #forceUpdate: true # boolean. Force update secret. Default: true.
  # ConfigMaps
    #configMapName: # string. ConfigMap name. 
    #forceUpdateConfigMap: false # boolean. Force update configmap. Default: false.
    #useConfigMapFile: false # boolean. Use file. Default: false.
    #configMapFile: # string. Required when useConfigMapFile = true. ConfigMap file. 
    #configMapArguments: # string. Optional. Use when useConfigMapFile = false. Arguments. 
  # Advanced
    #versionOrLocation: 'version' # 'version' | 'location'. Kubectl. Default: 'version'.
    #versionSpec: '1.13.2' # string. Optional. Use when versionOrLocation = version. Version spec. Default: '1.13.2'.
    #checkLatest: false # boolean. Optional. Use when versionOrLocation = version. Check for latest version. Default: false.
    #specifyLocation: # string. Required when versionOrLocation = location. Path to kubectl. 
    #workingDirectory: '$(System.DefaultWorkingDirectory)' # string. Working directory. Default: '$(System.DefaultWorkingDirectory)'.
    #outputFormat: 'json' # 'json' | 'yaml'. Output format. Default: 'json'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Deploy to Kubernetes v1
# Deploy, configure, update a Kubernetes cluster in Azure Container Service by running kubectl commands.
- task: Kubernetes@1
  inputs:
  # Kubernetes Cluster
    connectionType: 'Kubernetes Service Connection' # 'Azure Resource Manager' | 'Kubernetes Service Connection' | 'None'. Required. Service connection type. Default: 'Kubernetes Service Connection'.
    #kubernetesServiceEndpoint: # string. Required when connectionType = Kubernetes Service Connection. Kubernetes service connection. 
    #azureSubscriptionEndpoint: # string. Required when connectionType = Azure Resource Manager. Azure subscription. 
    #azureResourceGroup: # string. Required when connectionType = Azure Resource Manager. Resource group. 
    #kubernetesCluster: # string. Required when connectionType = Azure Resource Manager. Kubernetes cluster. 
    #useClusterAdmin: false # boolean. Optional. Use when connectionType = Azure Resource Manager. Use cluster admin credentials. Default: false.
    #namespace: # string. Namespace. 
  # Commands
    #command: # 'apply' | 'create' | 'delete' | 'exec' | 'expose' | 'get' | 'login' | 'logout' | 'logs' | 'run' | 'set' | 'top'. Command. 
    #useConfigurationFile: false # boolean. Optional. Use when command != login && command != logout. Use configuration. Default: false.
    #configurationType: 'configuration' # 'configuration' | 'inline'. Optional. Use when useConfigurationFile = true. Configuration type. Default: 'configuration'.
    configuration: # string. Required when configurationType = configuration. File path. 
    #inline: # string. Required when configurationType = inline. Inline configuration. 
    #arguments: # string. Optional. Use when command != login && command != logout. Arguments. 
  # Secrets
    secretType: 'dockerRegistry' # 'dockerRegistry' | 'generic'. Required. Type of secret. Default: 'dockerRegistry'.
    #secretArguments: # string. Optional. Use when secretType = generic. Arguments. 
    containerRegistryType: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required when secretType = dockerRegistry. Container registry type. Default: 'Azure Container Registry'.
    #dockerRegistryEndpoint: # string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Container Registry. Docker registry service connection. 
    #azureSubscriptionEndpointForSecrets: # string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Azure Container Registry. Azure container registry. 
    #secretName: # string. Secret name. 
    #forceUpdate: true # boolean. Force update secret. Default: true.
  # ConfigMaps
    #configMapName: # string. ConfigMap name. 
    #forceUpdateConfigMap: false # boolean. Force update configmap. Default: false.
    #useConfigMapFile: false # boolean. Use file. Default: false.
    #configMapFile: # string. Required when useConfigMapFile = true. ConfigMap file. 
    #configMapArguments: # string. Optional. Use when useConfigMapFile = false. Arguments. 
  # Advanced
    #versionOrLocation: 'version' # 'version' | 'location'. Kubectl. Default: 'version'.
    #versionSpec: '1.13.2' # string. Optional. Use when versionOrLocation = version. Version spec. Default: '1.13.2'.
    #checkLatest: false # boolean. Optional. Use when versionOrLocation = version. Check for latest version. Default: false.
    #specifyLocation: # string. Required when versionOrLocation = location. Path to kubectl. 
    #workingDirectory: '$(System.DefaultWorkingDirectory)' # string. Working directory. Default: '$(System.DefaultWorkingDirectory)'.
    #outputFormat: 'json' # 'json' | 'yaml'. Output format. Default: 'json'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Deploy to Kubernetes v1
# Deploy, configure, update your Kubernetes cluster in Azure Container Service by running kubectl commands.
- task: Kubernetes@1
  inputs:
  # Kubernetes Cluster
    connectionType: 'Azure Resource Manager' # 'Azure Resource Manager' | 'Kubernetes Service Connection' | 'None'. Required. Service connection type. Default: 'Azure Resource Manager'.
    #kubernetesServiceEndpoint: # string. Required when connectionType = Kubernetes Service Connection. Kubernetes service connection. 
    #azureSubscriptionEndpoint: # string. Required when connectionType = Azure Resource Manager. Azure subscription. 
    #azureResourceGroup: # string. Required when connectionType = Azure Resource Manager. Resource group. 
    #kubernetesCluster: # string. Required when connectionType = Azure Resource Manager. Kubernetes cluster. 
    #namespace: # string. Namespace. 
  # Commands
    command: 'apply' # 'apply' | 'create' | 'delete' | 'exec' | 'expose' | 'get' | 'login' | 'logout' | 'logs' | 'run' | 'set' | 'top'. Required. Command. Default: 'apply'.
    #useConfigurationFile: false # boolean. Optional. Use when command != login && command != logout. Use configuration files. Default: false.
    #configuration: # string. Required when useConfigurationFile = true. Configuration file. 
    #arguments: # string. Optional. Use when command != login && command != logout. Arguments. 
  # Secrets
    secretType: 'dockerRegistry' # 'dockerRegistry' | 'generic'. Required. Type of secret. Default: 'dockerRegistry'.
    #secretArguments: # string. Optional. Use when secretType = generic. Arguments. 
    containerRegistryType: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required when secretType = dockerRegistry. Container registry type. Default: 'Azure Container Registry'.
    #dockerRegistryEndpoint: # string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Container Registry. Docker registry service connection. 
    #azureSubscriptionEndpointForSecrets: # string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Azure Container Registry. Azure container registry. 
    #secretName: # string. Secret name. 
    #forceUpdate: true # boolean. Force update secret. Default: true.
  # ConfigMaps
    #configMapName: # string. ConfigMap name. 
    #forceUpdateConfigMap: false # boolean. Force update configmap. Default: false.
    #useConfigMapFile: false # boolean. Use file. Default: false.
    #configMapFile: # string. Required when useConfigMapFile = true. ConfigMap file. 
    #configMapArguments: # string. Optional. Use when useConfigMapFile = false. Arguments. 
  # Advanced
    #versionOrLocation: 'version' # 'version' | 'location'. Kubectl. Default: 'version'.
    #versionSpec: '1.7.0' # string. Optional. Use when versionOrLocation = version. Version spec. Default: '1.7.0'.
    #checkLatest: false # boolean. Optional. Use when versionOrLocation = version. Check for latest version. Default: false.
    #specifyLocation: # string. Required when versionOrLocation = location. Path to kubectl. 
    #workingDirectory: '$(System.DefaultWorkingDirectory)' # string. Working directory. Default: '$(System.DefaultWorkingDirectory)'.
    #outputFormat: 'json' # 'json' | 'yaml'. Output format. Default: 'json'.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="connectionType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`connectionType`** - **Service connection type**<br>
Type: string. Required. Allowed values: 'Azure Resource Manager', 'Kubernetes Service Connection', 'None'. Default value: 'Kubernetes Service Connection'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a service connection type.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`connectionType`** - **Service connection type**<br>
Type: string. Required. Allowed values: 'Azure Resource Manager', 'Kubernetes Service Connection', 'None'. Default value: 'Azure Resource Manager'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a service connection type.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kubernetesServiceEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`kubernetesServiceEndpoint`** - **Kubernetes service connection**<br>
Type: string. Required when connectionType = Kubernetes Service Connection.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Kubernetes service connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscriptionEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureSubscriptionEndpoint`** - **Azure subscription**<br>
Type: string. Required when connectionType = Azure Resource Manager.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription, which contains Azure Container Registry.Note: To configure new service connection, select the Azure subscription from the list and click 'Authorize'. If your subscription is not listed or if you want to use an existing Service Principal, you can setup an Azure service connection using 'Add' or 'Manage' button.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureResourceGroup"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureResourceGroup`** - **Resource group**<br>
Type: string. Required when connectionType = Azure Resource Manager.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure resource group.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kubernetesCluster"::: -->
:::moniker range=">=azure-pipelines-2019"

**`kubernetesCluster`** - **Kubernetes cluster**<br>
Type: string. Required when connectionType = Azure Resource Manager.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure managed cluster.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useClusterAdmin"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`useClusterAdmin`** - **Use cluster admin credentials**<br>
Type: boolean. Optional. Use when connectionType = Azure Resource Manager. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use cluster administrator credentials instead of default cluster user credentials.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="namespace"::: -->
:::moniker range=">=azure-pipelines-2019"

**`namespace`** - **Namespace**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set the namespace for the kubectl command by using the –namespace flag. If the namespace is not provided, the commands will run in the default namespace.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="command"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`command`** - **Command**<br>
Type: string. Allowed values: 'apply', 'create', 'delete', 'exec', 'expose', 'get', 'login', 'logout', 'logs', 'run', 'set', 'top'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select or specify a kubectl command to run.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`command`** - **Command**<br>
Type: string. Required. Allowed values: 'apply', 'create', 'delete', 'exec', 'expose', 'get', 'login', 'logout', 'logs', 'run', 'set', 'top'. Default value: 'apply'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select or specify a kubectl command to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useConfigurationFile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`useConfigurationFile`** - **Use configuration**<br>
Type: boolean. Optional. Use when command != login && command != logout. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use Kubernetes configuration with the kubectl command. An inline script, filename, directory, or URL to Kubernetes configuration files can be provided.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`useConfigurationFile`** - **Use configuration files**<br>
Type: boolean. Optional. Use when command != login && command != logout. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use Kubernetes configuration with the kubectl command. An inline script, filename, directory, or URL to Kubernetes configuration files can be provided.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configurationType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`configurationType`** - **Configuration type**<br>
Type: string. Optional. Use when useConfigurationFile = true. Allowed values: 'configuration', 'inline'. Default value: 'configuration'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Type of Kubernetes configuration for kubectl command. It can be a file path or an inline script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`configuration`** - **File path**<br>
Type: string. Required when configurationType = configuration.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Filename, directory, or URL to kubernetes configuration files that will be used with the commands.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`configuration`** - **Configuration file**<br>
Type: string. Required when useConfigurationFile = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Filename, directory, or URL to kubernetes configuration files that will be used with the commands.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="inline"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`inline`** - **Inline configuration**<br>
Type: string. Required when configurationType = inline.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Inline deployment configuration for kubectl command.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range=">=azure-pipelines-2019"

**`arguments`** - **Arguments**<br>
Type: string. Optional. Use when command != login && command != logout.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Arguments to the specified kubectl command.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secretType"::: -->
:::moniker range=">=azure-pipelines-2019"

**`secretType`** - **Type of secret**<br>
Type: string. Required. Allowed values: 'dockerRegistry', 'generic'. Default value: 'dockerRegistry'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Create/update a generic or docker imagepullsecret. Select dockerRegistry to create/update the imagepullsecret of the selected registry. An imagePullSecret is a way to pass a secret that contains a container registry password to the Kubelet so it can pull a private image on behalf of your Pod.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secretArguments"::: -->
:::moniker range=">=azure-pipelines-2019"

**`secretArguments`** - **Arguments**<br>
Type: string. Optional. Use when secretType = generic.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify keys and literal values to insert in secret.For example, --from-literal=key1=value1 --from-literal=key2="top secret".
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerRegistryType"::: -->
:::moniker range=">=azure-pipelines-2019"

**`containerRegistryType`** - **Container registry type**<br>
Type: string. Required when secretType = dockerRegistry. Allowed values: 'Azure Container Registry', 'Container Registry'. Default value: 'Azure Container Registry'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Container registry type. The task can use Azure Subscription details to work with an Azure Container registry. Other standard Container registries are also supported.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerRegistryEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`dockerRegistryEndpoint`** - **Docker registry service connection**<br>
Type: string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Container Registry.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker registry service connection. Required for commands that need to authenticate with a registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscriptionEndpointForSecrets"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureSubscriptionEndpointForSecrets`** - **Azure subscription**<br>
Type: string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Azure Container Registry.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription, which contains Azure Container Registry. Note: To configure new service connection, select the Azure subscription from the list and click 'Authorize'. If your subscription is not listed or if you want to use an existing Service Principal, you can setup an Azure service connection using 'Add' or 'Manage' button.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureContainerRegistry"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureContainerRegistry`** - **Azure container registry**<br>
Type: string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Azure Container Registry.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure Container Registry which will be used for pulling container images and deploying applications to the Kubernetes cluster. Required for commands that need to authenticate with a registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secretName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`secretName`** - **Secret name**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the secret. You can use this secret name in the Kubernetes YAML configuration file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="forceUpdate"::: -->
:::moniker range=">=azure-pipelines-2019"

**`forceUpdate`** - **Force update secret**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Delete the secret if it exists and create a new one with updated values.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configMapName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`configMapName`** - **ConfigMap name**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
ConfigMaps allow you to decouple configuration artifacts from image content to keep containerized applications portable.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="forceUpdateConfigMap"::: -->
:::moniker range=">=azure-pipelines-2019"

**`forceUpdateConfigMap`** - **Force update configmap**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Delete the configmap if it exists and create a new one with updated values.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useConfigMapFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`useConfigMapFile`** - **Use file**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Create a ConfigMap from an individual file, or from multiple files by specifying a directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configMapFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`configMapFile`** - **ConfigMap file**<br>
Type: string. Required when useConfigMapFile = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a file or directory that contains the configMaps.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configMapArguments"::: -->
:::moniker range=">=azure-pipelines-2019"

**`configMapArguments`** - **Arguments**<br>
Type: string. Optional. Use when useConfigMapFile = false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify keys and literal values to insert in configMap.For example, --from-literal=key1=value1 --from-literal=key2="top secret".
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionOrLocation"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionOrLocation`** - **Kubectl**<br>
Type: string. Allowed values: 'version', 'location'. Default value: 'version'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
kubectl is a command line interface for running commands against Kubernetes clusters.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionSpec"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`versionSpec`** - **Version spec**<br>
Type: string. Optional. Use when versionOrLocation = version. Default value: '1.13.2'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Version Spec of version to get.  Examples: 1.7.0, 1.x.0, 4.x.0, 6.10.0, >=6.10.0.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`versionSpec`** - **Version spec**<br>
Type: string. Optional. Use when versionOrLocation = version. Default value: '1.7.0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Version Spec of version to get.  Examples: 1.7.0, 1.x.0, 4.x.0, 6.10.0, >=6.10.0.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkLatest"::: -->
:::moniker range=">=azure-pipelines-2019"

**`checkLatest`** - **Check for latest version**<br>
Type: boolean. Optional. Use when versionOrLocation = version. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Always checks online for the latest available version (stable.txt) that satisfies the version spec. This is typically false unless you have a specific scenario to always get latest. This will cause it to incur download costs when potentially not necessary, especially with the hosted build pool.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="specifyLocation"::: -->
:::moniker range=">=azure-pipelines-2019"

**`specifyLocation`** - **Path to kubectl**<br>
Type: string. Required when versionOrLocation = location.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Full path to the kubectl.exe.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`workingDirectory`** - **Working directory**<br>
Input alias: `cwd`. Type: string. Default value: '$(System.DefaultWorkingDirectory)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Working directory for the Kubectl command.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputFormat"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`outputFormat`** - **Output format**<br>
Type: string. Allowed values: 'json', 'yaml', 'none'. Default value: 'json'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Output format.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020"

**`outputFormat`** - **Output format**<br>
Type: string. Allowed values: 'json', 'yaml'. Default value: 'json'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Output format.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="KubectlOutput"::: -->
**`KubectlOutput`**<br><!-- :::editable-content name="Value"::: -->
Stores the output of the kubectl command
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

What's new in Version 1.0.

* Added new service connection type input for easy selection of Azure AKS cluster.
* Replaced output variable input with output variables section that we had added in all tasks.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->