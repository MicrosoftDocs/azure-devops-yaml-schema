---
title: resources.containers.container definition
description: resources.containers.container definition reference.
ms.date: 01/25/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# resources.containers.container definition


A container resource references a container image.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="containerResource{container}" version="azure-pipelines-2019"::: -->

```yaml
containerResources:
- container: string # Required as first property. ID for the container.  ([-_A-Za-z0-9]*)
  endpoint: string # ID of the service endpoint connecting to a private container registry. 
  azureSubscription: string # Azure subscription (ARM service connection) for container registry. 
  resourceGroup: string # Resource group for your ACR. 
  registry: string # Registry for container images. 
  repository: string # Name of the container image repository in ACR. 
```


Properties that use this definition: [resources.containers.containerResources](resources-containers.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID for the container. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `endpoint`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ID of the service endpoint connecting to a private container registry. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `azureSubscription`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Azure subscription (ARM service connection) for container registry. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `resourceGroup`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Resource group for your ACR. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `registry`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Registry for container images. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repository`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the container image repository in ACR. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="containerResource{container}" version="azure-pipelines-2019.1"::: -->

```yaml
containerResources:
- container: string # Required as first property. ID for the container.  ([-_A-Za-z0-9]*)
  endpoint: string # ID of the service endpoint connecting to a private container registry. 
  azureSubscription: string # Azure subscription (ARM service connection) for container registry. 
  resourceGroup: string # Resource group for your ACR. 
  registry: string # Registry for container images. 
  repository: string # Name of the container image repository in ACR. 
```


Properties that use this definition: [resources.containers.containerResources](resources-containers.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID for the container. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `endpoint`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ID of the service endpoint connecting to a private container registry. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `azureSubscription`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Azure subscription (ARM service connection) for container registry. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `resourceGroup`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Resource group for your ACR. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `registry`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Registry for container images. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repository`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the container image repository in ACR. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="containerResource{container}" version="azure-pipelines-2020"::: -->

```yaml
containerResources:
- container: string # Required as first property. ID for the container.  ([-_A-Za-z0-9]*)
  type: string # Type of the registry like ACR or GCR.
  endpoint: string # ID of the service endpoint connecting to a private container registry. 
  trigger: # none to disable, true to trigger on all image tags, or full syntax (see the following examples).
  azureSubscription: string # Azure subscription (ARM service connection) for container registry. 
  resourceGroup: string # Resource group for your ACR. 
  registry: string # Registry for container images. 
  repository: string # Name of the container image repository in ACR. 
```


Properties that use this definition: [resources.containers.containerResources](resources-containers.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID for the container. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `type`
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



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `endpoint`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ID of the service endpoint connecting to a private container registry. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string or trigger
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `azureSubscription`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Azure subscription (ARM service connection) for container registry. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `resourceGroup`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Resource group for your ACR. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `registry`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Registry for container images. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repository`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the container image repository in ACR. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="containerResource{container,image}" version="azure-pipelines-2020.1"::: -->

```yaml
containerResources:
- container: string # Required as first property. ID for the container.  ([-_A-Za-z0-9]*)
  image: string # Required. Container image tag. 
  type: string # Type of the registry like ACR or GCR.
  trigger: # none to disable, true to trigger on all image tags, or full syntax (see the following examples).
  endpoint: string # ID of the service endpoint connecting to a private container registry. 
  env:  # Variables to map into the container's environment
    string: string # Name/value pairs.
  mapDockerSocket: boolean # Set this flag to false to force the agent not to setup the /var/run/docker.sock volume on container jobs.  (false,n,no,off,on,true,y,yes)
  options: string # Options to pass into container host. 
  ports: [ string ] # Ports to expose on the container. 
  volumes: [ string ] # Volumes to mount on the container. 
  mountReadOnly:  # Volumes to mount read-only, the default is all false.
    work: boolean # Mount the work directory as readonly.  (false,n,no,off,on,true,y,yes)
    externals: boolean # Mount the externals directory as readonly.  (false,n,no,off,on,true,y,yes)
    tools: boolean # Mount the tools directory as readonly.  (false,n,no,off,on,true,y,yes)
    tasks: boolean # Mount the tasks directory as readonly.  (false,n,no,off,on,true,y,yes)
  azureSubscription: string # Azure subscription (ARM service connection) for container registry. 
  resourceGroup: string # Resource group for your ACR. 
  registry: string # Registry for container images. 
  repository: string # Name of the container image repository in ACR. 
```


Properties that use this definition: [resources.containers.containerResources](resources-containers.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID for the container. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `type`
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



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string or trigger
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `endpoint`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ID of the service endpoint connecting to a private container registry. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `env`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Variables to map into the container's environment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `image`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required. Container image tag. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `mapDockerSocket`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Set this flag to false to force the agent not to setup the /var/run/docker.sock volume on container jobs. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `options`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Options to pass into container host. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `ports`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Ports to expose on the container. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `volumes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Volumes to mount on the container. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `mountReadOnly`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string/boolean pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Volumes to mount read-only, the default is all false. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `azureSubscription`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Azure subscription (ARM service connection) for container registry. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `resourceGroup`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Resource group for your ACR. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `registry`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Registry for container images. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repository`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the container image repository in ACR. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="containerResource{container,image}" version="azure-pipelines"::: -->

```yaml
containerResources:
- container: string # Required as first property. ID for the container.  ([-_A-Za-z0-9]*)
  image: string # Required. Container image tag. 
  type: string # Type of the registry like ACR or GCR.
  trigger: # none to disable, true to trigger on all image tags, or full syntax (see the following examples).
  endpoint: string # ID of the service endpoint connecting to a private container registry. 
  env:  # Variables to map into the container's environment
    string: string # Name/value pairs.
  mapDockerSocket: boolean # Set this flag to false to force the agent not to setup the /var/run/docker.sock volume on container jobs.  (false,n,no,off,on,true,y,yes)
  options: string # Options to pass into container host. 
  ports: [ string ] # Ports to expose on the container. 
  volumes: [ string ] # Volumes to mount on the container. 
  mountReadOnly:  # Volumes to mount read-only, the default is all false.
    work: boolean # Mount the work directory as readonly.  (false,n,no,off,on,true,y,yes)
    externals: boolean # Mount the externals directory as readonly.  (false,n,no,off,on,true,y,yes)
    tools: boolean # Mount the tools directory as readonly.  (false,n,no,off,on,true,y,yes)
    tasks: boolean # Mount the tasks directory as readonly.  (false,n,no,off,on,true,y,yes)
  azureSubscription: string # Azure subscription (ARM service connection) for container registry. 
  resourceGroup: string # Resource group for your ACR. 
  registry: string # Registry for container images. 
  repository: string # Name of the container image repository in ACR. 
```


Properties that use this definition: [resources.containers.containerResources](resources-containers.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID for the container. Acceptable values: [-_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `type`
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



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string or trigger
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `endpoint`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ID of the service endpoint connecting to a private container registry. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `env`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Variables to map into the container's environment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `image`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required. Container image tag. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `mapDockerSocket`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Set this flag to false to force the agent not to setup the /var/run/docker.sock volume on container jobs. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `options`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Options to pass into container host. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `ports`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Ports to expose on the container. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `volumes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Volumes to mount on the container. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `mountReadOnly`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string/boolean pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Volumes to mount read-only, the default is all false. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `azureSubscription`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Azure subscription (ARM service connection) for container registry. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `resourceGroup`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Resource group for your ACR. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `registry`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Registry for container images. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repository`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the container image repository in ACR. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

[Container jobs](/azure/devops/pipelines/process/container-phases) let you isolate your tools and dependencies inside a container.

The agent launches an instance of your specified container then runs steps inside it.
The `container` keyword lets you specify your container images.

[Service containers](/azure/devops/pipelines/process/service-containers) run alongside a job to provide various dependencies like databases.


## Examples

::: moniker range="azure-pipelines"

```yaml
resources:
  containers:
  - container: string  # identifier (A-Z, a-z, 0-9, and underscore)
    image: string  # container image name
    options: string  # arguments to pass to container at startup
    endpoint: string  # reference to a service connection for the private registry
    env: { string: string }  # list of environment variables to add
    ports: [ string ] # ports to expose on the container
    volumes: [ string ] # volumes to mount on the container
    mapDockerSocket: bool # whether to map in the Docker daemon socket; defaults to true
    mountReadOnly:  # volumes to mount read-only - all default to false
      externals: boolean  # components required to talk to the agent
      tasks: boolean  # tasks required by the job
      tools: boolean  # installable tools like Python and Ruby
      work: boolean # the work directory
```

::: moniker-end

::: moniker range=">= azure-pipelines-2020 <= azure-pipelines-2020.1"

```yaml
resources:
  containers:
  - container: string  # identifier (A-Z, a-z, 0-9, and underscore)
    image: string  # container image name
    options: string  # arguments to pass to container at startup
    endpoint: string  # reference to a service connection for the private registry
    env: { string: string }  # list of environment variables to add
    ports: [ string ] # ports to expose on the container
    volumes: [ string ] # volumes to mount on the container
    mapDockerSocket: bool # whether to map in the Docker daemon socket; defaults to true
```

::: moniker-end

::: moniker range=">= azure-pipelines-2019 <= azure-pipelines-2019.1"

```yaml
resources:
  containers:
  - container: string  # identifier (A-Z, a-z, 0-9, and underscore)
    image: string  # container image name
    options: string  # arguments to pass to container at startup
    endpoint: string  # reference to a service connection for the private registry
    env: { string: string }  # list of environment variables to add
    ports: [ string ] # ports to expose on the container
    volumes: [ string ] # volumes to mount on the container
```

::: moniker-end

```yaml
resources:
  containers:
  - container: linux
    image: ubuntu:16.04
  - container: windows
    image: myprivate.azurecr.io/windowsservercore:1803
    endpoint: my_acr_connection
  - container: my_service
    image: my_service:tag
    ports:
    - 8080:80 # bind container port 80 to 8080 on the host machine
    - 6379 # bind container port 6379 to a random available port on the host machine
    volumes:
    - /src/dir:/dst/dir # mount /src/dir on the host into /dst/dir in the container
```


## See also

[Define resources in YAML](/azure/devops/pipelines/process/resources)


