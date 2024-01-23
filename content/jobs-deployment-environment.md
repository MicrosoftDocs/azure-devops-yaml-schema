---
title: jobs.deployment.environment definition
description: Target environment name and optionally a resource name to record the deployment history.
ms.date: 01/23/2024
monikerRange: ">=azure-pipelines-2020"
---

# jobs.deployment.environment definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
The `environment` keyword specifies the [environment](/azure/devops/pipelines/process/environments) or its resource that is targeted by a deployment job of the pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [jobs.deployment](jobs-deployment.md)

:::moniker-end
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range=">=azure-pipelines-2020"

| Implementation | Description |
|---|---|
| [environment: string](#environmentstring) | Deployment job with environment name. |
| [environment: name, resourceName, resourceId, resourceType, tags](#environmentobjectproperties) | Full syntax for complete control. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

An environment also holds information about the deployment strategy for running the steps defined inside the job.

You can reduce the deployment target's scope to a particular resource within the environment as shown here:

```yaml
environment: 'smarthotel-dev.bookings'
strategy:
  runOnce:
    deploy:
      steps:
      - task: KubernetesManifest@0
        displayName: Deploy to Kubernetes cluster
        inputs:
          action: deploy
          namespace: $(k8sNamespace)
          manifests: $(System.ArtifactsDirectory)/manifests/*
          imagePullSecrets: $(imagePullSecret)
          containers: $(containerRegistry)/$(imageRepository):$(tag)
          # value for kubernetesServiceConnection input automatically passed down to task by environment.resource input
```
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="environment: string"::: -->
<a name="environmentstring"></a>
<!-- :::stringAnyOf::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## environment: string
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
To specify an environment by name without using any additional properties, use the following syntax.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
environment: string # Deployment job with environment name.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-string-item::: -->
**`environment`** string.<br>
<!-- :::editable-content name="description"::: -->
Deployment job with environment name.
<!-- :::editable-content-end::: -->
<!-- :::implementation-string-item-end::: -->

:::moniker-end
<!-- :::stringAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

```yaml
environment: environmentName.resourceName
strategy:                 # deployment strategy
  runOnce:              # default strategy
    deploy:
      steps:
      - script: echo Hello world
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="environment: object properties"::: -->
<a name="environmentobjectproperties"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## environment: name, resourceName, resourceId, resourceType, tags
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
To configure environment properties in addition to the name, use the full syntax.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
environment:
  name: string # Name of environment.
  resourceName: string # Name of resource.
  resourceId: string # Id of resource.
  resourceType: string # Type of environment resource.
  tags: string # List of tag filters.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Name of environment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resourceName"::: -->
**`resourceName`** string.<br><!-- :::editable-content name="propDescription"::: -->
Name of resource.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resourceId"::: -->
**`resourceId`** string.<br><!-- :::editable-content name="propDescription"::: -->
Id of resource.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resourceType"::: -->
**`resourceType`** string.<br><!-- :::editable-content name="propDescription"::: -->
Type of environment resource.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
**`tags`** string.<br><!-- :::editable-content name="propDescription"::: -->
List of tag filters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end
<!-- :::objectAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

The full syntax is:

```yaml
environment:            # create environment and/or record deployments
  name: string          # name of the environment to run this job on.
  resourceName: string  # name of the resource in the environment to record the deployments against
  resourceId: number    # resource identifier
  resourceType: string  # type of the resource you want to target. Supported types - virtualMachine, Kubernetes
  tags: string          # comma separated tag names to filter the resources in the environment
strategy:               # deployment strategy
  runOnce:              # default strategy
    deploy:
      steps:
      - script: echo Hello world
```

If you specify an environment or one of its resources but don't need to specify other properties, you can shorten the syntax to:

```yaml
environment: environmentName.resourceName
strategy:         # deployment strategy
  runOnce:        # default strategy
    deploy:
      steps:
      - script: echo Hello world
```

You can reduce the deployment target's scope to a particular resource within the environment as shown here:

```yaml
environment: 'smarthotel-dev.bookings'
strategy:
  runOnce:
    deploy:
      steps:
      - task: KubernetesManifest@0
        displayName: Deploy to Kubernetes cluster
        inputs:
          action: deploy
          namespace: $(k8sNamespace)
          manifests: $(System.ArtifactsDirectory)/manifests/*
          imagePullSecrets: $(imagePullSecret)
          containers: $(containerRegistry)/$(imageRepository):$(tag)
          # value for kubernetesServiceConnection input automatically passed down to task by environment.resource input
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Create and target an environment](/azure/devops/pipelines/process/environments)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
