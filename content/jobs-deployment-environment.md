---
title: jobs.deployment.environment definition
description: jobs.deployment.environment definition reference.
ms.date: 01/24/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# jobs.deployment.environment definition


The `environment` keyword specifies the [environment](/azure/devops/pipelines/process/environments) or its resource that is targeted by a deployment job of the pipeline.


:::moniker range="= azure-pipelines-2020"

Properties that use this definition: [jobs.deployment.environment](jobs-deployment.md)

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

Properties that use this definition: [jobs.deployment.environment](jobs-deployment.md)

:::moniker-end

:::moniker range="= azure-pipelines"

Properties that use this definition: [jobs.deployment.environment](jobs-deployment.md)

:::moniker-end

## Overloads

:::moniker range="= azure-pipelines-2020" 

| Overload | Description |
|----------|-------------|
| [deploymentEnvironment: string](#deploymentenvironment-string) | Deployment job with environment name. |
| [deploymentEnvironment: name, resourceName, resourceId, resourceType, tags](#deploymentenvironment-name-resourcename-resourceid-resourcetype-tags) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines-2020.1" 

| Overload | Description |
|----------|-------------|
| [deploymentEnvironment: string](#deploymentenvironment-string) | Deployment job with environment name. |
| [deploymentEnvironment: name, resourceName, resourceId, resourceType, tags](#deploymentenvironment-name-resourcename-resourceid-resourcetype-tags) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [deploymentEnvironment: string](#deploymentenvironment-string) | Deployment job with environment name. |
| [deploymentEnvironment: name, resourceName, resourceId, resourceType, tags](#deploymentenvironment-name-resourcename-resourceid-resourcetype-tags) | Full syntax for complete control. |

:::moniker-end


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

:::moniker range="= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## deploymentEnvironment: string

:::moniker-end

To specify an environment by name without using any additional properties, use the following syntax.


:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="deploymentEnvironment{string}" version="azure-pipelines-2020"::: -->


```yaml
deploymentEnvironment: string # Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `deploymentEnvironment`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="deploymentEnvironment{string}" version="azure-pipelines-2020.1"::: -->


```yaml
deploymentEnvironment: string # Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `deploymentEnvironment`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="deploymentEnvironment{string}" version="azure-pipelines"::: -->


```yaml
deploymentEnvironment: string # Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `deploymentEnvironment`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


### Examples


```yaml
environment: environmentName.resourceName
strategy:                 # deployment strategy
  runOnce:              # default strategy
    deploy:
      steps:
      - script: echo Hello world
```


:::moniker range="= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## deploymentEnvironment: name, resourceName, resourceId, resourceType, tags

:::moniker-end

To configure other properties in addition to the name, use the full syntax.


:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="deploymentEnvironment{name,resourceName,resourceId,resourceType,tags}" version="azure-pipelines-2020"::: -->


```yaml
environment:
  name: string # Name of environment. 
  resourceName: string # Name of resource. 
  resourceId: string # Id of resource. 
  resourceType: string # Type of environment resource. 
  tags: string # List of tag filters. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `name`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of environment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `resourceName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of resource. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `resourceId`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Id of resource. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `resourceType`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Type of environment resource. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `tags`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of tag filters. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="deploymentEnvironment{name,resourceName,resourceId,resourceType,tags}" version="azure-pipelines-2020.1"::: -->


```yaml
environment:
  name: string # Name of environment. 
  resourceName: string # Name of resource. 
  resourceId: string # Id of resource. 
  resourceType: string # Type of environment resource. 
  tags: string # List of tag filters. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `name`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of environment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `resourceName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of resource. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `resourceId`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Id of resource. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `resourceType`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Type of environment resource. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `tags`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of tag filters. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="deploymentEnvironment{name,resourceName,resourceId,resourceType,tags}" version="azure-pipelines"::: -->


```yaml
environment:
  name: string # Name of environment. 
  resourceName: string # Name of resource. 
  resourceId: string # Id of resource. 
  resourceType: string # Type of environment resource. 
  tags: string # List of tag filters. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `name`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of environment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `resourceName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of resource. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `resourceId`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Id of resource. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `resourceType`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Type of environment resource. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `tags`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of tag filters. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


### Examples

The full syntax is:

```yaml
environment:                # create environment and/or record deployments
  name: string              # name of the environment to run this job on.
  resourceName: string      # name of the resource in the environment to record the deployments against
  resourceId: number        # resource identifier
  resourceType: string      # type of the resource you want to target. Supported types - virtualMachine, Kubernetes
  tags: string | [ string ] # tag names to filter the resources in the environment
strategy:                 # deployment strategy
  runOnce:                # default strategy
    deploy:
      steps:
      - script: echo Hello world
```

If you specify an environment or one of its resources but don't need to specify other properties, you can shorten the syntax to:

```yaml
environment: environmentName.resourceName
strategy:                 # deployment strategy
  runOnce:              # default strategy
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

## See also

* [Create and target an environment](/azure/devops/pipelines/process/environments)
