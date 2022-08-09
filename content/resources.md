---
title: resources definition
description: resources definition reference.
ms.date: 08/08/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"
---

# resources definition


Resources specifies builds, repositories, pipelines, and other resources used by the pipeline.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="resources{builds,containers,pipelines,repositories}" version="azure-pipelines-2019"::: -->

```yaml
resources:
  builds: [ build ]
  containers: [ container ]
  pipelines: [ pipeline ]
  repositories: [ repository ]
```


Properties that use this definition: [pipeline.resources](pipeline.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `builds`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.builds](resources-builds.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of build resources referenced by the pipeline. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `containers`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.containers](resources-containers.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of container images. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pipelines`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.pipelines](resources-pipelines.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of pipeline resources. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repositories`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.repositories](resources-repositories.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of external repositories. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="resources{builds,containers,pipelines,repositories}" version="azure-pipelines-2019.1"::: -->

```yaml
resources:
  builds: [ build ]
  containers: [ container ]
  pipelines: [ pipeline ]
  repositories: [ repository ]
```


Properties that use this definition: [pipeline.resources](pipeline.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `builds`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.builds](resources-builds.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of build resources referenced by the pipeline. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `containers`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.containers](resources-containers.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of container images. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pipelines`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.pipelines](resources-pipelines.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of pipeline resources. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repositories`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.repositories](resources-repositories.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of external repositories. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="resources{builds,containers,pipelines,repositories,packages}" version="azure-pipelines-2020"::: -->

```yaml
resources:
  builds: [ build ]
  containers: [ container ]
  pipelines: [ pipeline ]
  repositories: [ repository ]
  packages: [ package ]
```


Properties that use this definition: [pipeline.resources](pipeline.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `builds`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.builds](resources-builds.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of build resources referenced by the pipeline. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `containers`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.containers](resources-containers.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of container images. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pipelines`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.pipelines](resources-pipelines.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of pipeline resources. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repositories`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.repositories](resources-repositories.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of external repositories. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `packages`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.packages](resources-packages.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of external packages. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="resources{builds,containers,pipelines,repositories,webhooks,packages}" version="azure-pipelines-2020.1"::: -->

```yaml
resources:
  builds: [ build ]
  containers: [ container ]
  pipelines: [ pipeline ]
  repositories: [ repository ]
  webhooks: [ webhook ]
  packages: [ package ]
```


Properties that use this definition: [pipeline.resources](pipeline.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `builds`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.builds](resources-builds.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of build resources referenced by the pipeline. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `containers`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.containers](resources-containers.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of container images. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pipelines`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.pipelines](resources-pipelines.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of pipeline resources. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repositories`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.repositories](resources-repositories.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of external repositories. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `webhooks`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.webhooks](resources-webhooks.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of webhooks. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `packages`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.packages](resources-packages.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of external packages. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="resources{builds,containers,pipelines,repositories,webhooks,packages}" version="azure-pipelines-2022"::: -->

```yaml
resources:
  builds: [ build ]
  containers: [ container ]
  pipelines: [ pipeline ]
  repositories: [ repository ]
  webhooks: [ webhook ]
  packages: [ package ]
```


Properties that use this definition: [pipeline.resources](pipeline.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `builds`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.builds](resources-builds.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of build resources referenced by the pipeline. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `containers`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.containers](resources-containers.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of container images. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pipelines`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.pipelines](resources-pipelines.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of pipeline resources. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repositories`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.repositories](resources-repositories.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of external repositories. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `webhooks`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.webhooks](resources-webhooks.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of webhooks. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `packages`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.packages](resources-packages.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of external packages. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="resources{builds,containers,pipelines,repositories,webhooks,packages}" version="azure-pipelines"::: -->

```yaml
resources:
  builds: [ build ]
  containers: [ container ]
  pipelines: [ pipeline ]
  repositories: [ repository ]
  webhooks: [ webhook ]
  packages: [ package ]
```


Properties that use this definition: [pipeline.resources](pipeline.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `builds`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.builds](resources-builds.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of build resources referenced by the pipeline. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `containers`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.containers](resources-containers.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of container images. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pipelines`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.pipelines](resources-pipelines.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of pipeline resources. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repositories`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.repositories](resources-repositories.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of external repositories. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `webhooks`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.webhooks](resources-webhooks.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of webhooks. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `packages`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.packages](resources-packages.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of external packages. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


<!-- Examples -->


## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)
