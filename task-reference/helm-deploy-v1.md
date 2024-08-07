---
title: HelmDeploy@1 - Package and deploy Helm charts v1 task
description: Deploy, configure, update a Kubernetes cluster in Azure Container Service by running helm commands.
ms.date: 07/15/2024
monikerRange: "=azure-pipelines"
---

# HelmDeploy@1 - Package and deploy Helm charts v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Deploy, configure, update a Kubernetes cluster in Azure Container Service by running helm commands.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Package and deploy Helm charts v1
# Deploy, configure, update a Kubernetes cluster in Azure Container Service by running helm commands.
- task: HelmDeploy@1
  inputs:
  # Kubernetes Cluster
    #connectionType: 'Azure Resource Manager' # 'Azure Resource Manager' | 'Kubernetes Service Connection' | 'None'. Required when command != logout && command != package. Connection Type. Default: Azure Resource Manager.
    #azureSubscription: # string. Alias: azureSubscriptionEndpoint. Required when connectionType = Azure Resource Manager && command != logout && command != package. Azure subscription. 
    #azureResourceGroup: # string. Required when connectionType = Azure Resource Manager && command != logout && command != package. Resource group. 
    #kubernetesCluster: # string. Required when connectionType = Azure Resource Manager && command != logout && command != package. Kubernetes cluster. 
    #useClusterAdmin: false # boolean. Optional. Use when connectionType = Azure Resource Manager && command != logout && command != package. Use cluster admin credentials. Default: false.
    #kubernetesServiceConnection: # string. Alias: kubernetesServiceEndpoint. Required when connectionType = Kubernetes Service Connection && command != logout && command != package. Kubernetes Service Connection. 
    #namespace: # string. Optional. Use when command != logout && command != package. Namespace. 
  # Azure Container Registry
    #azureSubscriptionForACR: # string. Alias: azureSubscriptionEndpointForACR. Required when command == login || command == package || command == push. Azure subscription for Container Registry. 
    #azureResourceGroupForACR: # string. Required when command == login || command == package || command == push. Resource group. 
    #azureContainerRegistry: # string. Required when command == login || command == package || command == push. Azure Container Registry. 
  # Commands
    command: 'ls' # 'create' | 'delete' | 'expose' | 'get' | 'init' | 'install' | 'login' | 'logout' | 'ls' | 'package' | 'push' | 'rollback' | 'upgrade' | 'uninstall'. Required. Command. Default: ls.
    #chartType: 'Name' # 'Name' | 'FilePath'. Required when command == install || command == upgrade. Chart Type. Default: Name.
    chartName: # string. Required when chartType == Name. Chart Name. 
    #chartPath: # string. Required when chartType == FilePath || command == package. Chart Path. 
    #chartVersion: # string. Alias: version. Optional. Use when command == package || command == install || command == upgrade. Version. 
    #releaseName: # string. Optional. Use when command == install || command == upgrade. Release Name. 
    #overrideValues: # string. Optional. Use when command == install || command == upgrade. Set Values. 
    #valueFile: # string. Optional. Use when command == install || command == upgrade. Value File. 
    #destination: '$(Build.ArtifactStagingDirectory)' # string. Optional. Use when command == package. Destination. Default: $(Build.ArtifactStagingDirectory).
    #canaryimage: false # boolean. Optional. Use when command == init. Use canary image version. Default: false.
    #upgradetiller: true # boolean. Optional. Use when command == init. Upgrade Tiller. Default: true.
    #updatedependency: false # boolean. Optional. Use when command == install || command == package. Update Dependency. Default: false.
    #save: true # boolean. Optional. Use when command == package. Save. Default: true.
    #install: true # boolean. Optional. Use when command == upgrade. Install if release not present. Default: true.
    #recreate: false # boolean. Optional. Use when command == upgrade. Recreate Pods. Default: false.
    #resetValues: false # boolean. Optional. Use when command == upgrade. Reset Values. Default: false.
    #force: false # boolean. Optional. Use when command == upgrade. Force. Default: false.
    #waitForExecution: true # boolean. Optional. Use when command == init || command == install || command == upgrade. Wait. Default: true.
    #arguments: # string. Optional. Use when command != login && command != logout. Arguments. 
    #chartNameForACR: # string. Required when command == package || command == push. Chart Name For Azure Container Registry. 
    #chartPathForACR: # string. Required when command == package || command == push. Chart Path for Azure Container Registry. 
  # TLS
    #enableTls: false # boolean. Optional. Use when command != login && command != logout && command != package. Enable TLS. Default: false.
    #caCert: # string. Required when enableTls == true && command != login && command != logout && command != package. CA certificate. 
    #certificate: # string. Required when enableTls == true && command != login && command != logout && command != package. Certificate. 
    #privatekey: # string. Required when enableTls == true && command != login && command != logout && command != package. Key. 
  # Advanced
    #tillernamespace: # string. Optional. Use when command != login && command != logout && command != package. Tiller namespace. 
    #failOnStderr: false # boolean. Optional. Use when command != login && command != logout && command != package. Fail on Standard Error. Default: false.
    #publishPipelineMetadata: true # boolean. Optional. Use when command != login && command != logout && command != package. Publish pipeline metadata. Default: true.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="connectionType"::: -->
:::moniker range="=azure-pipelines"

**`connectionType`** - **Connection Type**<br>
`string`. Required when `command != logout && command != package`. Allowed values: `Azure Resource Manager`, `Kubernetes Service Connection`, `None`. Default value: `Azure Resource Manager`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select 'Azure Resource Manager' to connect to an Azure Kubernetes Service by using Azure Service Connection. Select 'Kubernetes Service Connection' to connect to any Kubernetes cluster by using kubeconfig or Service Account.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `azureSubscriptionEndpoint`. `string`. Required when `connectionType = Azure Resource Manager && command != logout && command != package`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure subscription, which has your Azure Container Registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureResourceGroup"::: -->
:::moniker range="=azure-pipelines"

**`azureResourceGroup`** - **Resource group**<br>
`string`. Required when `connectionType = Azure Resource Manager && command != logout && command != package`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure Resource Group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kubernetesCluster"::: -->
:::moniker range="=azure-pipelines"

**`kubernetesCluster`** - **Kubernetes cluster**<br>
`string`. Required when `connectionType = Azure Resource Manager && command != logout && command != package`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure Managed Cluster.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useClusterAdmin"::: -->
:::moniker range="=azure-pipelines"

**`useClusterAdmin`** - **Use cluster admin credentials**<br>
`boolean`. Optional. Use when `connectionType = Azure Resource Manager && command != logout && command != package`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use cluster administrator credentials instead of default cluster user credentials.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kubernetesServiceConnection"::: -->
:::moniker range="=azure-pipelines"

**`kubernetesServiceConnection`** - **Kubernetes Service Connection**<br>
Input alias: `kubernetesServiceEndpoint`. `string`. Required when `connectionType = Kubernetes Service Connection && command != logout && command != package`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Kubernetes service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="namespace"::: -->
:::moniker range="=azure-pipelines"

**`namespace`** - **Namespace**<br>
`string`. Optional. Use when `command != logout && command != package`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify K8 namespace to use. Use Tiller namespace can be specified in the advanced section of the task or by passing the --tiller-namespace option as argument.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscriptionForACR"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscriptionForACR`** - **Azure subscription for Container Registry**<br>
Input alias: `azureSubscriptionEndpointForACR`. `string`. Required when `command == login || command == package || command == push`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure subscription, which has your Azure Container Registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureResourceGroupForACR"::: -->
:::moniker range="=azure-pipelines"

**`azureResourceGroupForACR`** - **Resource group**<br>
`string`. Required when `command == login || command == package || command == push`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure Resource Group, which has your Container Registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureContainerRegistry"::: -->
:::moniker range="=azure-pipelines"

**`azureContainerRegistry`** - **Azure Container Registry**<br>
`string`. Required when `command == login || command == package || command == push`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure Container Registry which will be used for pushing helm charts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="command"::: -->
:::moniker range="=azure-pipelines"

**`command`** - **Command**<br>
`string`. Required. Allowed values: `create`, `delete`, `expose`, `get`, `init`, `install`, `login`, `logout`, `ls`, `package`, `push`, `rollback`, `upgrade`, `uninstall`. Default value: `ls`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a helm command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="chartType"::: -->
:::moniker range="=azure-pipelines"

**`chartType`** - **Chart Type**<br>
`string`. Required when `command == install || command == upgrade`. Allowed values: `Name`, `FilePath` (File Path). Default value: `Name`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select how you want to enter chart info. You can either provide name of the chart or folder/file path to the chart.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="chartName"::: -->
:::moniker range="=azure-pipelines"

**`chartName`** - **Chart Name**<br>
`string`. Required when `chartType == Name`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Chart reference to install, this can be a url or a chart name. For example, if chart name is 'stable/mysql', the task will run 'helm install stable/mysql'.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="chartPath"::: -->
:::moniker range="=azure-pipelines"

**`chartPath`** - **Chart Path**<br>
`string`. Required when `chartType == FilePath || command == package`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the chart to install. This can be a path to a packaged chart or a path to an unpacked chart directory. For example, if './redis' is specified the task will run 'helm install ./redis'.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="chartVersion"::: -->
:::moniker range="=azure-pipelines"

**`chartVersion`** - **Version**<br>
Input alias: `version`. `string`. Optional. Use when `command == package || command == install || command == upgrade`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the exact chart version to install. If this is not specified, the latest version is installed. Set the version on the chart to this semver version​.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseName"::: -->
:::moniker range="=azure-pipelines"

**`releaseName`** - **Release Name**<br>
`string`. Optional. Use when `command == install || command == upgrade`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Release name. If unspecified, it will autogenerate one for you.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideValues"::: -->
:::moniker range="=azure-pipelines"

**`overrideValues`** - **Set Values**<br>
`string`. Optional. Use when `command == install || command == upgrade`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set values on the command line (can specify multiple or separate values with commas or newlines: key1=val1,key2=val2 or <br>key1=val1<br>key2=val2<br>). The task will construct the helm command by using these set values. For example, helm install --set key1=val1 ./redis.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="valueFile"::: -->
:::moniker range="=azure-pipelines"

**`valueFile`** - **Value File**<br>
`string`. Optional. Use when `command == install || command == upgrade`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify values in a YAML file or a URL. For example, specifying myvalues.yaml will result in 'helm install --values=myvals.yaml'.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="destination"::: -->
:::moniker range="=azure-pipelines"

**`destination`** - **Destination**<br>
`string`. Optional. Use when `command == package`. Default value: `$(Build.ArtifactStagingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify values in a YAML file or a URL.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="canaryimage"::: -->
:::moniker range="=azure-pipelines"

**`canaryimage`** - **Use canary image version.**<br>
`boolean`. Optional. Use when `command == init`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use the canary Tiller image, the latest pre-release version of Tiller.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="upgradetiller"::: -->
:::moniker range="=azure-pipelines"

**`upgradetiller`** - **Upgrade Tiller**<br>
`boolean`. Optional. Use when `command == init`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Upgrade if Tiller is already installed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="updatedependency"::: -->
:::moniker range="=azure-pipelines"

**`updatedependency`** - **Update Dependency**<br>
`boolean`. Optional. Use when `command == install || command == package`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run helm dependency update before installing the chart. Update dependencies from 'requirements.yaml' to dir 'charts/' before packaging.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="save"::: -->
:::moniker range="=azure-pipelines"

**`save`** - **Save**<br>
`boolean`. Optional. Use when `command == package`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Save packaged chart to local chart repository (default true)​.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="install"::: -->
:::moniker range="=azure-pipelines"

**`install`** - **Install if release not present.**<br>
`boolean`. Optional. Use when `command == upgrade`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If a release by this name doesn't already exist, run an install​.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="recreate"::: -->
:::moniker range="=azure-pipelines"

**`recreate`** - **Recreate Pods.**<br>
`boolean`. Optional. Use when `command == upgrade`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Performs pods restart for the resource if applicable.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resetValues"::: -->
:::moniker range="=azure-pipelines"

**`resetValues`** - **Reset Values.**<br>
`boolean`. Optional. Use when `command == upgrade`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Reset the values to the ones built into the chart.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="force"::: -->
:::moniker range="=azure-pipelines"

**`force`** - **Force**<br>
`boolean`. Optional. Use when `command == upgrade`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Force resource update through delete/recreate if needed​.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="waitForExecution"::: -->
:::moniker range="=azure-pipelines"

**`waitForExecution`** - **Wait**<br>
`boolean`. Optional. Use when `command == init || command == install || command == upgrade`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Block till command execution completes.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="=azure-pipelines"

**`arguments`** - **Arguments**<br>
`string`. Optional. Use when `command != login && command != logout`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Helm command options.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableTls"::: -->
:::moniker range="=azure-pipelines"

**`enableTls`** - **Enable TLS**<br>
`boolean`. Optional. Use when `command != login && command != logout && command != package`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enables using SSL between Helm and Tiller.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="caCert"::: -->
:::moniker range="=azure-pipelines"

**`caCert`** - **CA certificate**<br>
`string`. Required when `enableTls == true && command != login && command != logout && command != package`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
CA cert used to issue certificate for tiller and helm client.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="certificate"::: -->
:::moniker range="=azure-pipelines"

**`certificate`** - **Certificate**<br>
`string`. Required when `enableTls == true && command != login && command != logout && command != package`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify Tiller certificate or Helm client certificate.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="privatekey"::: -->
:::moniker range="=azure-pipelines"

**`privatekey`** - **Key**<br>
`string`. Required when `enableTls == true && command != login && command != logout && command != package`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify Tiller Key or Helm client key.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tillernamespace"::: -->
:::moniker range="=azure-pipelines"

**`tillernamespace`** - **Tiller namespace**<br>
`string`. Optional. Use when `command != login && command != logout && command != package`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify K8 namespace of tiller.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStderr"::: -->
:::moniker range="=azure-pipelines"

**`failOnStderr`** - **Fail on Standard Error**<br>
`boolean`. Optional. Use when `command != login && command != logout && command != package`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, this task will fail if any errors are written to the error pipeline, or if any data is written to the Standard Error stream. Otherwise the task will rely on the exit code to determine failure.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishPipelineMetadata"::: -->
:::moniker range="=azure-pipelines"

**`publishPipelineMetadata`** - **Publish pipeline metadata**<br>
`boolean`. Optional. Use when `command != login && command != logout && command != package`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, the task will collect and publish deployment metadata.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="chartNameForACR"::: -->
:::moniker range="=azure-pipelines"

**`chartNameForACR`** - **Chart Name For Azure Container Registry**<br>
`string`. Required when `command == package || command == push`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Chart name with which the chart will be stored in Azure Container Registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="chartPathForACR"::: -->
:::moniker range="=azure-pipelines"

**`chartPathForACR`** - **Chart Path for Azure Container Registry**<br>
`string`. Required when `command == package || command == push`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the chart directory.
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

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="helmExitCode"::: -->
**`helmExitCode`**<br><!-- :::editable-content name="Value"::: -->
Exit code emitted from the execution of specified Helm command
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="helmOutput"::: -->
**`helmOutput`**<br><!-- :::editable-content name="Value"::: -->
Output emitted from the execution of specified Helm command
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

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

:::moniker range="=azure-pipelines"

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