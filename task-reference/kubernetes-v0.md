---
title: Kubernetes@0 - Kubectl v0 task
description: Deploy, configure, update a Kubernetes cluster in Azure Container Service by running kubectl commands (task version 0).
ms.date: 11/11/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
---

# Kubernetes@0 - Kubectl v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Use this task to deploy, configure, or update a Kubernetes cluster in Azure Container Service by running `kubectl` commands.

This version of the task is deprecated; use [Kubernetes@1](./kubernetes-v1.md) to take advantage of the latest features like [Workload identity federation](/azure/devops/pipelines/release/troubleshoot-workload-identity#review-pipeline-tasks).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Use this task to deploy, configure, or update a Kubernetes cluster in Azure Container Service by running `kubectl` commands.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Kubectl v0
# Deploy, configure, update a Kubernetes cluster in Azure Container Service by running kubectl commands.
- task: Kubernetes@0
  inputs:
    #kubernetesServiceConnection: # string. Alias: kubernetesServiceEndpoint. Kubernetes service connection. 
    #namespace: # string. Namespace. 
  # Commands
    #command: # 'apply' | 'create' | 'delete' | 'exec' | 'expose' | 'get' | 'logs' | 'run' | 'set' | 'top'. Command. 
    #useConfigurationFile: false # boolean. Use Configuration files. Default: false.
    #configuration: # string. Required when useConfigurationFile = true. Configuration file. 
    #arguments: # string. Arguments. 
  # Secrets
    secretType: 'dockerRegistry' # 'dockerRegistry' | 'generic'. Required. Type of secret. Default: dockerRegistry.
    #secretArguments: # string. Optional. Use when secretType = generic. Arguments. 
    containerRegistryType: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required when secretType = dockerRegistry. Container Registry type. Default: Azure Container Registry.
    #dockerRegistryConnection: # string. Alias: dockerRegistryEndpoint. Optional. Use when secretType = dockerRegistry && containerRegistryType = Container Registry. Docker Registry service connection. 
    #azureSubscription: # string. Alias: azureSubscriptionEndpoint. Optional. Use when secretType = dockerRegistry && containerRegistryType = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when secretType = dockerRegistry && containerRegistryType = Azure Container Registry. Azure Container Registry. 
    #secretName: # string. Secret name. 
    #forceUpdate: true # boolean. Force update secret. Default: true.
  # ConfigMaps
    #configMapName: # string. ConfigMap name. 
    #forceUpdateConfigMap: false # boolean. Force update configmap. Default: false.
    #useConfigMapFile: false # boolean. Use file. Default: false.
    #configMapFile: # string. Required when useConfigMapFile = true. ConfigMap file. 
    #configMapArguments: # string. Optional. Use when useConfigMapFile = false. Arguments. 
  # Advanced
    #versionOrLocation: 'version' # 'version' | 'location'. Kubectl. Default: version.
    #versionSpec: '1.7.0' # string. Optional. Use when versionOrLocation = version. Version spec. Default: 1.7.0.
    #checkLatest: false # boolean. Optional. Use when versionOrLocation = version. Check for latest version. Default: false.
    #specifyLocation: # string. Required when versionOrLocation = location. Path to Kubectl. 
    #workingDirectory: '$(System.DefaultWorkingDirectory)' # string. Alias: cwd. Working directory. Default: $(System.DefaultWorkingDirectory).
  # Output
    #outputFormat: 'json' # 'json' | 'yaml'. Output format. Default: json.
    #kubectlOutput: # string. Output variable name.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="kubernetesServiceConnection"::: -->
:::moniker range="<=azure-pipelines"

**`kubernetesServiceConnection`** - **Kubernetes service connection**<br>
[Input alias](index.md#what-are-task-input-aliases): `kubernetesServiceEndpoint`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Kubernetes service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="namespace"::: -->
:::moniker range="<=azure-pipelines"

**`namespace`** - **Namespace**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the namespace for the `kubectl` command by using the `–namespace` flag. If the namespace is not provided, the commands will run in the default namespace.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="command"::: -->
:::moniker range="<=azure-pipelines"

**`command`** - **Command**<br>
`string`. Allowed values: `apply`, `create`, `delete`, `exec`, `expose`, `get`, `logs`, `run`, `set`, `top`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a `kubectl` command to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useConfigurationFile"::: -->
:::moniker range="<=azure-pipelines"

**`useConfigurationFile`** - **Use Configuration files**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use Kubernetes configuration file with the kubectl command. Filename, directory, or URL to Kubernetes configuration files can also be provided.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration file**<br>
`string`. Required when `useConfigurationFile = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the filename, directory, or URL to kubernetes configuration files that is used with the commands.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the arguments to the specified `kubectl` command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secretType"::: -->
:::moniker range="<=azure-pipelines"

**`secretType`** - **Type of secret**<br>
`string`. Required. Allowed values: `dockerRegistry`, `generic`. Default value: `dockerRegistry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Creates or updates a generic or docker `imagepullsecret`. Specify `dockerRegistry` to create or update the `imagepullsecret` of the selected registry. An `imagePullSecret` is a way to pass a secret that contains a container registry password to the Kubelet, so it can pull a private image on behalf of your Pod.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secretArguments"::: -->
:::moniker range="<=azure-pipelines"

**`secretArguments`** - **Arguments**<br>
`string`. Optional. Use when `secretType = generic`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies keys and literal values to insert in secret. For example, `--from-literal=key1=value1` or `--from-literal=key2="top secret"`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerRegistryType"::: -->
:::moniker range="<=azure-pipelines"

**`containerRegistryType`** - **Container Registry type**<br>
`string`. Required when `secretType = dockerRegistry`. Allowed values: `Azure Container Registry`, `Container Registry`. Default value: `Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Container registry type. The task can use Azure Subscription details to work with an Azure Container registry. Other standard Container registries are also supported.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerRegistryConnection"::: -->
:::moniker range="<=azure-pipelines"

**`dockerRegistryConnection`** - **Docker Registry service connection**<br>
[Input alias](index.md#what-are-task-input-aliases): `dockerRegistryEndpoint`. `string`. Optional. Use when `secretType = dockerRegistry && containerRegistryType = Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker registry service connection. Required for commands that need to authenticate with a registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
[Input alias](index.md#what-are-task-input-aliases): `azureSubscriptionEndpoint`. `string`. Optional. Use when `secretType = dockerRegistry && containerRegistryType = Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Azure Resource Manager subscription, which contains Azure Container Registry.
>[!NOTE]
>To configure a new service connection, select the Azure subscription from the list and click `Authorize`. If your subscription is not listed or if you want to use an existing Service Principal, you can setup an Azure service connection using the `Add` or `Manage` buttons.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureContainerRegistry"::: -->
:::moniker range="<=azure-pipelines"

**`azureContainerRegistry`** - **Azure Container Registry**<br>
`string`. Optional. Use when `secretType = dockerRegistry && containerRegistryType = Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an Azure Container Registry which is used for pulling container images and deploying applications to the Kubernetes cluster. Required for commands that need to authenticate with a registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secretName"::: -->
:::moniker range="<=azure-pipelines"

**`secretName`** - **Secret name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the secret. You can use this secret name in the Kubernetes YAML configuration file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="forceUpdate"::: -->
:::moniker range="<=azure-pipelines"

**`forceUpdate`** - **Force update secret**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Delete the secret if it exists and create a new one with updated values.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configMapName"::: -->
:::moniker range="<=azure-pipelines"

**`configMapName`** - **ConfigMap name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
ConfigMaps allow you to decouple configuration artifacts from image content to keep containerized applications portable.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="forceUpdateConfigMap"::: -->
:::moniker range="<=azure-pipelines"

**`forceUpdateConfigMap`** - **Force update configmap**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Delete the configmap if it exists and create a new one with updated values.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useConfigMapFile"::: -->
:::moniker range="<=azure-pipelines"

**`useConfigMapFile`** - **Use file**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Create a ConfigMap from an individual file, or from multiple files by specifying a directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configMapFile"::: -->
:::moniker range="<=azure-pipelines"

**`configMapFile`** - **ConfigMap file**<br>
`string`. Required when `useConfigMapFile = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a file or directory that contains the configMaps.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configMapArguments"::: -->
:::moniker range="<=azure-pipelines"

**`configMapArguments`** - **Arguments**<br>
`string`. Optional. Use when `useConfigMapFile = false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies keys and literal values to insert in `configMap` .For example, `--from-literal=key1=value1` or `--from-literal=key2="top secret"`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionOrLocation"::: -->
:::moniker range="<=azure-pipelines"

**`versionOrLocation`** - **Kubectl**<br>
`string`. Allowed values: `version`, `location` (Specify location). Default value: `version`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
kubectl is a command line interface for running commands against Kubernetes clusters.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionSpec"::: -->
:::moniker range="<=azure-pipelines"

**`versionSpec`** - **Version spec**<br>
`string`. Optional. Use when `versionOrLocation = version`. Default value: `1.7.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Version Spec of the version to get. Examples: `1.7.0`, `1.x.0`, `4.x.0`, `6.10.0`, `>=6.10.0`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkLatest"::: -->
:::moniker range="<=azure-pipelines"

**`checkLatest`** - **Check for latest version**<br>
`boolean`. Optional. Use when `versionOrLocation = version`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Always checks online for the latest available version (stable.txt) that satisfies the version spec. This is typically false unless you have a specific scenario to always get latest. This will cause it to incur download costs when potentially not necessary, especially with the hosted build pool.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="specifyLocation"::: -->
:::moniker range="<=azure-pipelines"

**`specifyLocation`** - **Path to Kubectl**<br>
`string`. Required when `versionOrLocation = location`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the full path to the `kubectl.exe` file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `cwd`. `string`. Default value: `$(System.DefaultWorkingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Working directory for the Kubectl command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputFormat"::: -->
:::moniker range="<=azure-pipelines"

**`outputFormat`** - **Output format**<br>
`string`. Allowed values: `json`, `yaml`. Default value: `json`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Output format.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kubectlOutput"::: -->
:::moniker range="<=azure-pipelines"

**`kubectlOutput`** - **Output variable name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the variable in which output of the command should be saved.
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
| Agent version | All supported agent versions. |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->