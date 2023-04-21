---
title: KubernetesManifest@1 - Deploy to Kubernetes v1 task
description: Use Kubernetes manifest files to deploy to clusters or even bake the manifest files to be used for deployments using Helm charts.
ms.date: 04/12/2023
monikerRange: "=azure-pipelines"
---

# KubernetesManifest@1 - Deploy to Kubernetes v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use Kubernetes manifest files to deploy to clusters or even bake the manifest files to be used for deployments using Helm charts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Deploy to Kubernetes v1
# Use Kubernetes manifest files to deploy to clusters or even bake the manifest files to be used for deployments using Helm charts.
- task: KubernetesManifest@1
  inputs:
    #action: 'deploy' # 'bake' | 'createSecret' | 'delete' | 'deploy' | 'patch' | 'promote' | 'scale' | 'reject'. Action. Default: deploy.
    #connectionType: 'kubernetesServiceConnection' # 'azureResourceManager' | 'kubernetesServiceConnection'. Required when action != bake. Service connection type. Default: kubernetesServiceConnection.
    #kubernetesServiceConnection: # string. Alias: kubernetesServiceEndpoint. Required when action != bake && connectionType = kubernetesServiceConnection. Kubernetes service connection. 
    #azureSubscriptionConnection: # string. Alias: azureSubscriptionEndpoint. Required when action != bake && connectionType = azureResourceManager. Azure subscription. 
    #azureResourceGroup: # string. Required when action != bake && connectionType = azureResourceManager. Resource group. 
    #kubernetesCluster: # string. Required when action != bake && connectionType = azureResourceManager. Kubernetes cluster. 
    #namespace: # string. Namespace. 
    #strategy: 'none' # 'canary' | 'none'. Optional. Use when action = deploy || action = promote || action = reject. Strategy. Default: none.
    #trafficSplitMethod: 'pod' # 'pod' | 'smi'. Optional. Use when strategy = canary. Traffic split method. Default: pod.
    #percentage: '0' # string. Required when strategy = Canary && action = deploy. Percentage. Default: 0.
    #baselineAndCanaryReplicas: '1' # string. Required when strategy = Canary && action = deploy && trafficSplitMethod = SMI. Baseline and canary replicas. Default: 1.
    #manifests: # string. Required when action = deploy || action = promote || action = reject. Manifests. 
    #containers: # string. Optional. Use when action = deploy || action = promote || action = bake. Containers. 
    #imagePullSecrets: # string. Optional. Use when action = deploy || action = promote. ImagePullSecrets. 
    #renderType: 'helm' # 'helm' | 'kompose' | 'kustomize'. Optional. Use when action = bake. Render Engine. Default: helm.
    #dockerComposeFile: # string. Required when action = bake && renderType = kompose. Path to docker compose file. 
    #helmChart: # string. Required when action = bake && renderType = helm. Helm Chart. 
    #releaseName: # string. Optional. Use when action = bake && renderType = helm. Helm Release Name. 
    #overrideFiles: # string. Optional. Use when action = bake && renderType = helm. Override Files. 
    #overrides: # string. Optional. Use when action = bake && renderType = helm. Overrides. 
    #kustomizationPath: # string. Optional. Use when action = bake && renderType = kustomize. Kustomization Path. 
    #resourceToPatch: 'file' # 'file' | 'name'. Required when action = patch. Resource to patch. Default: file.
    #resourceFileToPatch: # string. Required when action = patch && resourceToPatch = file. File path. 
    #kind: # 'deployment' | 'replicaset' | 'statefulset'. Required when action = scale || resourceToPatch = name. Kind. 
    #name: # string. Required when action = scale || resourceToPatch = name. Name. 
    #replicas: # string. Required when action = scale. Replica count. 
    #mergeStrategy: 'strategic' # 'json' | 'merge' | 'strategic'. Required when action = patch. Merge Strategy. Default: strategic.
    #arguments: # string. Optional. Use when action = delete. Arguments. 
    #patch: # string. Required when action = patch. Patch. 
    #secretType: 'dockerRegistry' # 'dockerRegistry' | 'generic'. Required when action = createSecret. Type of secret. Default: dockerRegistry.
    #secretName: # string. Optional. Use when action = createSecret. Secret name. 
    #secretArguments: # string. Optional. Use when action = createSecret && secretType = generic. Arguments. 
    #dockerRegistryEndpoint: # string. Optional. Use when action = createSecret && secretType = dockerRegistry. Docker registry service connection. 
    #rolloutStatusTimeout: '0' # string. Optional. Use when action = deploy || action = patch || action = scale || action = promote. Timeout for rollout status. Default: 0.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="action"::: -->
:::moniker range="=azure-pipelines"

**`action`** - **Action**<br>
`string`. Allowed values: `bake`, `createSecret` (create secret), `delete`, `deploy`, `patch`, `promote`, `scale`, `reject`. Default value: `deploy`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the action to be performed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="connectionType"::: -->
:::moniker range="=azure-pipelines"

**`connectionType`** - **Service connection type**<br>
`string`. Required when `action != bake`. Allowed values: `azureResourceManager` (Azure Resource Manager), `kubernetesServiceConnection` (Kubernetes Service Connection). Default value: `kubernetesServiceConnection`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Kubernetes service connection type. For more information, see [Remarks](#remarks).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kubernetesServiceConnection"::: -->
:::moniker range="=azure-pipelines"

**`kubernetesServiceConnection`** - **Kubernetes service connection**<br>
Input alias: `kubernetesServiceEndpoint`. `string`. Required when `action != bake && connectionType = kubernetesServiceConnection`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a [Kubernetes service connection](/azure/devops/pipelines/library/service-endpoints).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscriptionConnection"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscriptionConnection`** - **Azure subscription**<br>
Input alias: `azureSubscriptionEndpoint`. `string`. Required when `action != bake && connectionType = azureResourceManager`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the Azure Resource Manager subscription, which contains Azure Container Registry.Note: To configure new service connection, select the Azure subscription from the list and click 'Authorize'. If your subscription is not listed or if you want to use an existing Service Principal, you can setup an Azure service connection using 'Add' or 'Manage' button.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureResourceGroup"::: -->
:::moniker range="=azure-pipelines"

**`azureResourceGroup`** - **Resource group**<br>
`string`. Required when `action != bake && connectionType = azureResourceManager`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure resource group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kubernetesCluster"::: -->
:::moniker range="=azure-pipelines"

**`kubernetesCluster`** - **Kubernetes cluster**<br>
`string`. Required when `action != bake && connectionType = azureResourceManager`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure managed cluster.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="namespace"::: -->
:::moniker range="=azure-pipelines"

**`namespace`** - **Namespace**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the namespace for the commands by using the `–namespace` flag. If the namespace is not provided, the commands will run in the default namespace.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
:::moniker range="=azure-pipelines"

**`strategy`** - **Strategy**<br>
`string`. Optional. Use when `action = deploy || action = promote || action = reject`. Allowed values: `canary`, `none`. Default value: `none`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the deployment strategy used in the `deploy` action before a `promote` action or `reject` action. Currently, `canary` is the only acceptable deployment strategy.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="trafficSplitMethod"::: -->
:::moniker range="=azure-pipelines"

**`trafficSplitMethod`** - **Traffic split method**<br>
`string`. Optional. Use when `strategy = canary`. Allowed values: `pod`, `smi`. Default value: `pod`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
For the value `smi`, the percentage traffic split is done at the request level by using a service mesh. A service mesh must be set up by a cluster admin. This task handles orchestration of SMI [TrafficSplit](https://github.com/servicemeshinterface/smi-spec/tree/main/apis/traffic-split) objects.

For the value `pod`, the percentage split isn't possible at the request level in the absence of a service mesh. Instead, the percentage input is used to calculate the replicas for baseline and canary. The calculation is a percentage of replicas that are specified in the input manifests for the stable variant.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="percentage"::: -->
:::moniker range="=azure-pipelines"

**`percentage`** - **Percentage**<br>
`string`. Required when `strategy = Canary && action = deploy`. Default value: `0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The percentage that is used to compute the number of baseline-variant and canary-variant replicas of the workloads that are contained in manifest files.

For the specified percentage input, calculate:

(*percentage* × *number of replicas*) / 100

If the result isn't an integer, the mathematical floor of the result is used when baseline and canary variants are created.

For example, assume the deployment `hello-world` is in the input manifest file and that the following lines are in the task input:

```
replicas: 4
strategy: canary
percentage: 25
```

In this case, the deployments `hello-world-baseline` and `hello-world-canary` are created with one replica each. The baseline variant is created with the same image and tag as the stable version, which is the four-replica variant before deployment. The canary variant is created with the image and tag corresponding to the newly deployed changes.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="baselineAndCanaryReplicas"::: -->
:::moniker range="=azure-pipelines"

**`baselineAndCanaryReplicas`** - **Baseline and canary replicas**<br>
`string`. Required when `strategy = Canary && action = deploy && trafficSplitMethod = SMI`. Default value: `1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When you set `trafficSplitMethod` to `smi`, the percentage traffic split is controlled in the service mesh plane. You can control the actual number of replicas for canary and baseline variants independently of the traffic split.

For example, assume that the input deployment manifest specifies 30 replicas for the stable variant. Also assume that you specify the following input for the task:

```
strategy: canary
trafficSplitMethod: smi
percentage: 20
baselineAndCanaryReplicas: 1
```

In this case, the stable variant receives 80% of the traffic, while the baseline and canary variants each receive half of the specified 20%. Baseline and canary variants don't receive three replicas each. They instead receive the specified number of replicas, which means they each receive one replica.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="manifests"::: -->
:::moniker range="=azure-pipelines"

**`manifests`** - **Manifests**<br>
`string`. Required when `action = deploy || action = promote || action = reject`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the manifest files to be used for deployment. Each line represents a single path. A [file-matching pattern](/azure/devops/pipelines/tasks/file-matching-patterns) is an acceptable value for each line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containers"::: -->
:::moniker range="=azure-pipelines"

**`containers`** - **Containers**<br>
`string`. Optional. Use when `action = deploy || action = promote || action = bake`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the fully qualified resource URL of the image to be used for substitutions on the manifest files. The URL `contosodemo.azurecr.io/helloworld:test` is an example.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imagePullSecrets"::: -->
:::moniker range="=azure-pipelines"

**`imagePullSecrets`** - **ImagePullSecrets**<br>
`string`. Optional. Use when `action = deploy || action = promote`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a multiline input where each line contains the name of a Docker registry secret that has already been set up within the cluster. Each secret name is added under `imagePullSecrets` for the workloads that are found in the input manifest files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="renderType"::: -->
:::moniker range="=azure-pipelines"

**`renderType`** - **Render Engine**<br>
`string`. Optional. Use when `action = bake`. Allowed values: `helm`, `kompose`, `kustomize`. Default value: `helm`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the render type used to produce the manifest files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerComposeFile"::: -->
:::moniker range="=azure-pipelines"

**`dockerComposeFile`** - **Path to docker compose file**<br>
`string`. Required when `action = bake && renderType = kompose`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a docker-compose file path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="helmChart"::: -->
:::moniker range="=azure-pipelines"

**`helmChart`** - **Helm Chart**<br>
`string`. Required when `action = bake && renderType = helm`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Helm chart path to bake.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseName"::: -->
:::moniker range="=azure-pipelines"

**`releaseName`** - **Helm Release Name**<br>
`string`. Optional. Use when `action = bake && renderType = helm`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Helm release name to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideFiles"::: -->
:::moniker range="=azure-pipelines"

**`overrideFiles`** - **Override Files**<br>
`string`. Optional. Use when `action = bake && renderType = helm`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a multiline input that accepts the path to the override files. The files are used when manifest files from Helm charts are baked.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrides"::: -->
:::moniker range="=azure-pipelines"

**`overrides`** - **Overrides**<br>
`string`. Optional. Use when `action = bake && renderType = helm`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the override values to set.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kustomizationPath"::: -->
:::moniker range="=azure-pipelines"

**`kustomizationPath`** - **Kustomization Path**<br>
`string`. Optional. Use when `action = bake && renderType = kustomize`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the argument that must be the path to the directory containing the file, or a git repository URL with a path suffix specifying `same` with respect to the repository root.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceToPatch"::: -->
:::moniker range="=azure-pipelines"

**`resourceToPatch`** - **Resource to patch**<br>
`string`. Required when `action = patch`. Allowed values: `file`, `name`. Default value: `file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Indicates one of the following patch methods:

- A manifest file identifies the objects to be patched.
- An individual object is identified by kind and name as the patch target.

Acceptable values are **file** and **name**.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceFileToPatch"::: -->
:::moniker range="=azure-pipelines"

**`resourceFileToPatch`** - **File path**<br>
`string`. Required when `action = patch && resourceToPatch = file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the file used for a patch.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kind"::: -->
:::moniker range="=azure-pipelines"

**`kind`** - **Kind**<br>
`string`. Required when `action = scale || resourceToPatch = name`. Allowed values: `deployment`, `replicaset`, `statefulset`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the kind of K8s object, such as `deployment`, `replicaSet` and more.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
:::moniker range="=azure-pipelines"

**`name`** - **Name**<br>
`string`. Required when `action = scale || resourceToPatch = name`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the K8s object.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="replicas"::: -->
:::moniker range="=azure-pipelines"

**`replicas`** - **Replica count**<br>
`string`. Required when `action = scale`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the number of replicas to scale to.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mergeStrategy"::: -->
:::moniker range="=azure-pipelines"

**`mergeStrategy`** - **Merge Strategy**<br>
`string`. Required when `action = patch`. Allowed values: `json`, `merge`, `strategic`. Default value: `strategic`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the type of patch being provided.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="=azure-pipelines"

**`arguments`** - **Arguments**<br>
`string`. Optional. Use when `action = delete`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the arguments for the `kubectl delete` command. An example is:
`arguments: deployment hello-world foo-bar`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="patch"::: -->
:::moniker range="=azure-pipelines"

**`patch`** - **Patch**<br>
`string`. Required when `action = patch`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the contents of the patch.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secretType"::: -->
:::moniker range="=azure-pipelines"

**`secretType`** - **Type of secret**<br>
`string`. Required when `action = createSecret`. Allowed values: `dockerRegistry`, `generic`. Default value: `dockerRegistry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Creates or updates a generic or docker `imagepullsecret`. Specify `dockerRegistry` to create or update the `imagepullsecret` of the selected registry. An `imagePullSecret` is a way to pass a secret that contains a container registry password to the Kubelet, so it can pull a private image on behalf of your Pod.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secretName"::: -->
:::moniker range="=azure-pipelines"

**`secretName`** - **Secret name**<br>
`string`. Optional. Use when `action = createSecret`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the secret. You can use this secret name in the Kubernetes YAML configuration file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secretArguments"::: -->
:::moniker range="=azure-pipelines"

**`secretArguments`** - **Arguments**<br>
`string`. Optional. Use when `action = createSecret && secretType = generic`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies keys and literal values to insert in secret. For example, `--from-literal=key1=value1` `--from-literal=key2="top secret"`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerRegistryEndpoint"::: -->
:::moniker range="=azure-pipelines"

**`dockerRegistryEndpoint`** - **Docker registry service connection**<br>
`string`. Optional. Use when `action = createSecret && secretType = dockerRegistry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the credentials of the specified service connection that are used to create a Docker registry secret within the cluster. Manifest files under the `imagePullSecrets` field can then refer to this secret's name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="rolloutStatusTimeout"::: -->
:::moniker range="=azure-pipelines"

**`rolloutStatusTimeout`** - **Timeout for rollout status**<br>
`string`. Optional. Use when `action = deploy || action = patch || action = scale || action = promote`. Default value: `0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the length of time (in seconds) to wait before ending `watch on rollout` status.
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

<!-- :::item name="manifestsBundle"::: -->
**`manifestsBundle`**<br><!-- :::editable-content name="Value"::: -->
The location of the manifest bundles created by bake action
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
::: moniker range="> azure-pipelines-2022"

## Remarks

[!INCLUDE [kubernetes-service-connection](./includes/kubernetes-service-connection.md)]

::: moniker-end
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