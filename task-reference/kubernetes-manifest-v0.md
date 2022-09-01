---
title: KubernetesManifest@0 - Deploy to Kubernetes v0 task
description: Use Kubernetes manifest files to deploy to clusters or even bake the manifest files to be used for deployments using Helm charts.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# KubernetesManifest@0 - Deploy to Kubernetes v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use Kubernetes manifest files to deploy to clusters or even bake the manifest files to be used for deployments using Helm charts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Deploy to Kubernetes v0
# Use Kubernetes manifest files to deploy to clusters or even bake the manifest files to be used for deployments using Helm charts.
- task: KubernetesManifest@0
  inputs:
    #action: 'deploy' # 'bake' | 'createSecret' | 'delete' | 'deploy' | 'patch' | 'promote' | 'scale' | 'reject'. Action. Default: 'deploy'.
    #kubernetesServiceConnection: # string. Required when action != bake. Kubernetes service connection. 
    #namespace: # string. Namespace. 
    #strategy: 'none' # 'canary' | 'none'. Optional. Use when action = deploy || action = promote || action = reject. Strategy. Default: 'none'.
    #trafficSplitMethod: 'pod' # 'pod' | 'smi'. Optional. Use when strategy = canary. Traffic split method. Default: 'pod'.
    #percentage: '0' # string. Required when strategy = Canary && action = deploy. Percentage. Default: '0'.
    #baselineAndCanaryReplicas: '1' # string. Required when strategy = Canary && action = deploy && trafficSplitMethod = SMI. Baseline and canary replicas. Default: '1'.
    #manifests: # string. Required when action = deploy || action = promote || action = reject. Manifests. 
    #containers: # string. Optional. Use when action = deploy || action = promote || action = bake. Containers. 
    #imagePullSecrets: # string. Optional. Use when action = deploy || action = promote. ImagePullSecrets. 
    #renderType: 'helm' # 'helm' | 'kompose' | 'kustomize'. Optional. Use when action = bake. Render Engine. Default: 'helm'.
    #dockerComposeFile: # string. Required when action = bake && renderType = kompose. Path to docker compose file. 
    #helmChart: # string. Required when action = bake && renderType = helm. Helm Chart. 
    #releaseName: # string. Optional. Use when action = bake && renderType = helm. Helm Release Name. 
    #overrideFiles: # string. Optional. Use when action = bake && renderType = helm. Override Files. 
    #overrides: # string. Optional. Use when action = bake && renderType = helm. Overrides. 
    #kustomizationPath: # string. Optional. Use when action = bake && renderType = kustomize. Kustomization Path. 
    #resourceToPatch: 'file' # 'file' | 'name'. Required when action = patch. Resource to patch. Default: 'file'.
    #resourceFileToPatch: # string. Required when action = patch && resourceToPatch = file. File path. 
    #kind: # 'deployment' | 'replicaset' | 'statefulset'. Required when action = scale || resourceToPatch = name. Kind. 
    #name: # string. Required when action = scale || resourceToPatch = name. Name. 
    #replicas: # string. Required when action = scale. Replica count. 
    #mergeStrategy: 'strategic' # 'json' | 'merge' | 'strategic'. Required when action = patch. Merge Strategy. Default: 'strategic'.
    #arguments: # string. Optional. Use when action = delete. Arguments. 
    #patch: # string. Required when action = patch. Patch. 
    #secretType: 'dockerRegistry' # 'dockerRegistry' | 'generic'. Required when action = createSecret. Type of secret. Default: 'dockerRegistry'.
    #secretName: # string. Optional. Use when action = createSecret. Secret name. 
    #secretArguments: # string. Optional. Use when action = createSecret && secretType = generic. Arguments. 
    #dockerRegistryEndpoint: # string. Optional. Use when action = createSecret && secretType = dockerRegistry. Docker registry service connection. 
    #rolloutStatusTimeout: '0' # string. Optional. Use when action = deploy || action = patch || action = scale || action = promote. Timeout for rollout status. Default: '0'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Deploy Kubernetes manifests v0
# Use Kubernetes manifest files to deploy to clusters or even bake the manifest files to be used for deployments using Helm charts.
- task: KubernetesManifest@0
  inputs:
    #action: 'deploy' # 'bake' | 'createSecret' | 'delete' | 'deploy' | 'patch' | 'promote' | 'scale' | 'reject'. Action. Default: 'deploy'.
    #kubernetesServiceConnection: # string. Required when action != bake. Kubernetes service connection. 
    #namespace: 'default' # string. Required when action != bake. Namespace. Default: 'default'.
    #strategy: 'none' # 'canary' | 'none'. Optional. Use when action = deploy || action = promote || action = reject. Strategy. Default: 'none'.
    #percentage: '0' # string. Required when strategy = Canary && action = deploy. Percentage. Default: '0'.
    #manifests: # string. Required when action = deploy || action = promote || action = reject. Manifests. 
    #containers: # string. Optional. Use when action = deploy || action = promote. Containers. 
    #imagePullSecrets: # string. Optional. Use when action = deploy || action = promote. ImagePullSecrets. 
    #renderType: 'helm2' # 'helm2'. Optional. Use when action = bake. Render Engine. Default: 'helm2'.
    #helmChart: # string. Required when action = bake && renderType = helm2. Helm Chart. 
    #releaseName: # string. Optional. Use when action = bake && renderType = helm2. Helm Release Name. 
    #overrideFiles: # string. Optional. Use when action = bake && renderType = helm2. Override Files. 
    #overrides: # string. Optional. Use when action = bake && renderType = helm2. Overrides. 
    #resourceToPatch: 'file' # 'file' | 'name'. Required when action = patch. Resource to patch. Default: 'file'.
    #resourceFileToPatch: # string. Required when action = patch && resourceToPatch = file. File path. 
    #kind: # 'deployment' | 'replicaset' | 'statefulset'. Required when action = scale || resourceToPatch = name. Kind. 
    #name: # string. Required when action = scale || resourceToPatch = name. Name. 
    #replicas: # string. Required when action = scale. Replica count. 
    #mergeStrategy: 'strategic' # 'json' | 'merge' | 'strategic'. Required when action = patch. Merge Strategy. Default: 'strategic'.
    #arguments: # string. Optional. Use when action = delete. Arguments. 
    #patch: # string. Required when action = patch. Patch. 
    #secretType: 'dockerRegistry' # 'dockerRegistry' | 'generic'. Required when action = createSecret. Type of secret. Default: 'dockerRegistry'.
    #secretName: # string. Optional. Use when action = createSecret. Secret name. 
    #secretArguments: # string. Optional. Use when action = createSecret && secretType = generic. Arguments. 
    #dockerRegistryEndpoint: # string. Optional. Use when action = createSecret && secretType = dockerRegistry. Docker registry service connection.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="action"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`action`** - **Action**<br>
Type: string. Allowed values: 'bake', 'createSecret', 'delete', 'deploy', 'patch', 'promote', 'scale', 'reject'. Default value: 'deploy'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose the action to be performed.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kubernetesServiceConnection"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`kubernetesServiceConnection`** - **Kubernetes service connection**<br>
Type: string. Required when action != bake.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Kubernetes service connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="namespace"::: -->
:::moniker range=">=azure-pipelines-2020"

**`namespace`** - **Namespace**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets the namespace for the commands by using the –namespace flag. If the namespace is not provided, the commands will run in the default namespace.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`namespace`** - **Namespace**<br>
Type: string. Required when action != bake. Default value: 'default'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets the namespace for the commands by using the –namespace flag. If the namespace is not provided, the commands will run in the default namespace.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`strategy`** - **Strategy**<br>
Type: string. Optional. Use when action = deploy || action = promote || action = reject. Allowed values: 'canary', 'none'. Default value: 'none'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Deployment strategy to be used.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="trafficSplitMethod"::: -->
:::moniker range=">=azure-pipelines-2020"

**`trafficSplitMethod`** - **Traffic split method**<br>
Type: string. Optional. Use when strategy = canary. Allowed values: 'pod', 'smi'. Default value: 'pod'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Traffic split method to be used.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="percentage"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`percentage`** - **Percentage**<br>
Type: string. Required when strategy = Canary && action = deploy. Default value: '0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Percentage of traffic redirect to canary deployment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="baselineAndCanaryReplicas"::: -->
:::moniker range=">=azure-pipelines-2020"

**`baselineAndCanaryReplicas`** - **Baseline and canary replicas**<br>
Type: string. Required when strategy = Canary && action = deploy && trafficSplitMethod = SMI. Default value: '1'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Baseline and canary replicas count.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="manifests"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`manifests`** - **Manifests**<br>
Type: string. Required when action = deploy || action = promote || action = reject.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Manifests to deploy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containers"::: -->
:::moniker range=">=azure-pipelines-2020"

**`containers`** - **Containers**<br>
Type: string. Optional. Use when action = deploy || action = promote || action = bake.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Containers.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`containers`** - **Containers**<br>
Type: string. Optional. Use when action = deploy || action = promote.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Containers.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imagePullSecrets"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`imagePullSecrets`** - **ImagePullSecrets**<br>
Type: string. Optional. Use when action = deploy || action = promote.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
ImagePullSecret to pull image from private registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="renderType"::: -->
:::moniker range=">=azure-pipelines-2020"

**`renderType`** - **Render Engine**<br>
Type: string. Optional. Use when action = bake. Allowed values: 'helm', 'kompose', 'kustomize'. Default value: 'helm'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The render type used to produce the manifest files.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`renderType`** - **Render Engine**<br>
Type: string. Optional. Use when action = bake. Allowed values: 'helm2'. Default value: 'helm2'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The render type used to produce the manifest files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerComposeFile"::: -->
:::moniker range=">=azure-pipelines-2020"

**`dockerComposeFile`** - **Path to docker compose file**<br>
Type: string. Required when action = bake && renderType = kompose.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
docker-compose file path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="helmChart"::: -->
:::moniker range=">=azure-pipelines-2020"

**`helmChart`** - **Helm Chart**<br>
Type: string. Required when action = bake && renderType = helm.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Helm chart path to bake.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`helmChart`** - **Helm Chart**<br>
Type: string. Required when action = bake && renderType = helm2.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Helm chart path to bake.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`releaseName`** - **Helm Release Name**<br>
Type: string. Optional. Use when action = bake && renderType = helm.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Helm release name to use.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`releaseName`** - **Helm Release Name**<br>
Type: string. Optional. Use when action = bake && renderType = helm2.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Helm release name to use.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideFiles"::: -->
:::moniker range=">=azure-pipelines-2020"

**`overrideFiles`** - **Override Files**<br>
Type: string. Optional. Use when action = bake && renderType = helm.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Override files to set.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`overrideFiles`** - **Override Files**<br>
Type: string. Optional. Use when action = bake && renderType = helm2.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Override files to set.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrides"::: -->
:::moniker range=">=azure-pipelines-2020"

**`overrides`** - **Overrides**<br>
Type: string. Optional. Use when action = bake && renderType = helm.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Override values to set.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`overrides`** - **Overrides**<br>
Type: string. Optional. Use when action = bake && renderType = helm2.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Override values to set.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kustomizationPath"::: -->
:::moniker range=">=azure-pipelines-2020"

**`kustomizationPath`** - **Kustomization Path**<br>
Type: string. Optional. Use when action = bake && renderType = kustomize.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The argument must be the path to the directory containing the file, or a git repository URL with a path suffix specifying same with respect to the repository root.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceToPatch"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`resourceToPatch`** - **Resource to patch**<br>
Type: string. Required when action = patch. Allowed values: 'file', 'name'. Default value: 'file'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
to identify the resource.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceFileToPatch"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`resourceFileToPatch`** - **File path**<br>
Type: string. Required when action = patch && resourceToPatch = file.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the file used for patch.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kind"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`kind`** - **Kind**<br>
Type: string. Required when action = scale || resourceToPatch = name. Allowed values: 'deployment', 'replicaset', 'statefulset'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Kind of K8s object; deployment, replicaSet etc.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`name`** - **Name**<br>
Type: string. Required when action = scale || resourceToPatch = name.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the k8s object.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="replicas"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`replicas`** - **Replica count**<br>
Type: string. Required when action = scale.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Number of replicas to scale to.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mergeStrategy"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`mergeStrategy`** - **Merge Strategy**<br>
Type: string. Required when action = patch. Allowed values: 'json', 'merge', 'strategic'. Default value: 'strategic'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The type of patch being provided; one of [json merge strategic].
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`arguments`** - **Arguments**<br>
Type: string. Optional. Use when action = delete.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Arguments for `kubectl delete` command.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="patch"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`patch`** - **Patch**<br>
Type: string. Required when action = patch.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Contents of patch.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secretType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`secretType`** - **Type of secret**<br>
Type: string. Required when action = createSecret. Allowed values: 'dockerRegistry', 'generic'. Default value: 'dockerRegistry'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Create/update a generic or docker imagepullsecret. Select dockerRegistry to create/update the imagepullsecret of the selected registry. An imagePullSecret is a way to pass a secret that contains a container registry password to the Kubelet so it can pull a private image on behalf of your Pod.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secretName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`secretName`** - **Secret name**<br>
Type: string. Optional. Use when action = createSecret.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the secret. You can use this secret name in the Kubernetes YAML configuration file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secretArguments"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`secretArguments`** - **Arguments**<br>
Type: string. Optional. Use when action = createSecret && secretType = generic.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify keys and literal values to insert in secret.For example, --from-literal=key1=value1 --from-literal=key2="top secret".
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerRegistryEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`dockerRegistryEndpoint`** - **Docker registry service connection**<br>
Type: string. Optional. Use when action = createSecret && secretType = dockerRegistry.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker registry service connection. Required for commands that need to authenticate with a registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="rolloutStatusTimeout"::: -->
:::moniker range=">=azure-pipelines-2020"

**`rolloutStatusTimeout`** - **Timeout for rollout status**<br>
Type: string. Optional. Use when action = deploy || action = patch || action = scale || action = promote. Default value: '0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The length of time (in seconds) to wait before ending watch on rollout status.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019.1"

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
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019.1"

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