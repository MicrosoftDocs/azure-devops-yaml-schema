---
title: pool definition
description: pool definition reference.
ms.date: 01/24/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# pool definition



The `pool` keyword specifies which [pool](/azure/devops/pipelines/agents/pools-queues) to use for a job of the pipeline.
A `pool` specification also holds information about the job's strategy for running.


:::moniker range="= azure-pipelines-2019"

Properties that use this definition: [pipeline.pool](pipeline.md), [jobs.job.pool](jobs-job.md)

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

Properties that use this definition: [pipeline.pool](pipeline.md), [jobs.job.pool](jobs-job.md)

:::moniker-end

:::moniker range="= azure-pipelines-2020"

Properties that use this definition: [pipeline.pool](pipeline.md), [stages.stage.pool](stages-stage.md), [jobs.job.pool](jobs-job.md), [jobs.deployment.pool](jobs-deployment.md)

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

Properties that use this definition: [pipeline.pool](pipeline.md), [stages.stage.pool](stages-stage.md), [jobs.job.pool](jobs-job.md), [jobs.deployment.pool](jobs-deployment.md)

:::moniker-end

:::moniker range="= azure-pipelines"

Properties that use this definition: [pipeline.pool](pipeline.md), [stages.stage.pool](stages-stage.md), [jobs.job.pool](jobs-job.md), [jobs.deployment.pool](jobs-deployment.md)

:::moniker-end

## Overloads

:::moniker range="= azure-pipelines-2019" 

| Overload | Description |
|----------|-------------|
| [pool: string](#pool-string) | Name of pool. |
| [pool: name, demands, vmImage](#pool-name-demands-vmimage) | Full syntax. |

:::moniker-end

:::moniker range="= azure-pipelines-2019.1" 

| Overload | Description |
|----------|-------------|
| [pool: string](#pool-string) | Name of pool. |
| [pool: name, demands, vmImage](#pool-name-demands-vmimage) | Full syntax. |

:::moniker-end

:::moniker range="= azure-pipelines-2020" 

| Overload | Description |
|----------|-------------|
| [pool: string](#pool-string) | Name of pool. |
| [pool: name, demands, vmImage](#pool-name-demands-vmimage) | Full syntax. |

:::moniker-end

:::moniker range="= azure-pipelines-2020.1" 

| Overload | Description |
|----------|-------------|
| [pool: string](#pool-string) | Name of pool. |
| [pool: name, demands, vmImage](#pool-name-demands-vmimage) | Full syntax. |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [pool: string](#pool-string) | Name of pool. |
| [pool: name, demands, vmImage](#pool-name-demands-vmimage) | Full syntax. |

:::moniker-end


## Remarks

::: moniker range=">= azure-pipelines-2019 <= azure-pipelines-2019.1"

In Azure DevOps Server 2019 you can specify a pool at the job level in YAML, and at the pipeline level in the pipeline settings UI. In Azure DevOps Server 2019.1 you can also specify a pool at the pipeline level in YAML if you have a single implicit job.
:::moniker-end

::: moniker range=">= azure-pipelines-2020"
You can specify a pool at the pipeline, stage, or job level.
:::moniker-end

The pool specified at the lowest level of the hierarchy is used to run the job.

The full syntax is:

```yaml
pool:
  name: string  # name of the pool to run this job in
  demands: string | [ string ]  # see the following "Demands" topic
  vmImage: string # name of the VM image you want to use; valid only in the Microsoft-hosted pool
```

If you use a Microsoft-hosted pool, choose an [available virtual machine image](/azure/devops/pipelines/agents/hosted.md#use-a-microsoft-hosted-agent).

If you use a private pool and don't need to specify demands, you can shorten the syntax to:

```yaml
pool: string # name of the private pool to run this job in
```

Learn more about [conditions](/azure/devops/pipelines/process/conditions) and [timeouts](/azure/devops/pipelines/process/phases#timeouts).


:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## pool: string

:::moniker-end

Which pool to use for a job of the pipeline.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="pool{string}" version="azure-pipelines-2019"::: -->


```yaml
pool: string # Name of the pool.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pool`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="pool{string}" version="azure-pipelines-2019.1"::: -->


```yaml
pool: string # Name of the pool.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pool`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="pool{string}" version="azure-pipelines-2020"::: -->


```yaml
pool: string # Name of the pool.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pool`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="pool{string}" version="azure-pipelines-2020.1"::: -->


```yaml
pool: string # Name of the pool.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pool`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="pool{string}" version="azure-pipelines"::: -->


```yaml
pool: string # Name of the pool.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pool`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


### Examples

To use a private pool with no demands:

```yaml
pool: MyPool
```


:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## pool: name, demands, vmImage

:::moniker-end

Which pool to use for a job of the pipeline.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="pool{name,demands,vmImage}" version="azure-pipelines-2019"::: -->


```yaml
pool:
  name: string # Name of a pool. 
  demands: string | [ string ]  # List of demands (for a private pool)
  vmImage: string # Name of the VM image you want to use; valid only in the Microsoft-hosted pool. 
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
<!-- :::api-desc type="property"::: -->Name of a pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `demands`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[pool.demands](pool-demands.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of demands (for a private pool). 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `vmImage`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the VM image you want to use; valid only in the Microsoft-hosted pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="pool{name,demands,vmImage}" version="azure-pipelines-2019.1"::: -->


```yaml
pool:
  name: string # Name of a pool. 
  demands: string | [ string ]  # List of demands (for a private pool)
  vmImage: string # Name of the VM image you want to use; valid only in the Microsoft-hosted pool. 
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
<!-- :::api-desc type="property"::: -->Name of a pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `demands`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[pool.demands](pool-demands.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of demands (for a private pool). 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `vmImage`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the VM image you want to use; valid only in the Microsoft-hosted pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="pool{name,demands,vmImage}" version="azure-pipelines-2020"::: -->


```yaml
pool:
  name: string # Name of a pool. 
  demands: string | [ string ]  # List of demands (for a private pool)
  vmImage: string # Name of the VM image you want to use; valid only in the Microsoft-hosted pool. 
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
<!-- :::api-desc type="property"::: -->Name of a pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `demands`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[pool.demands](pool-demands.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of demands (for a private pool). 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `vmImage`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the VM image you want to use; valid only in the Microsoft-hosted pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="pool{name,demands,vmImage}" version="azure-pipelines-2020.1"::: -->


```yaml
pool:
  name: string # Name of a pool. 
  demands: string | [ string ]  # List of demands (for a private pool)
  vmImage: string # Name of the VM image you want to use; valid only in the Microsoft-hosted pool. 
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
<!-- :::api-desc type="property"::: -->Name of a pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `demands`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[pool.demands](pool-demands.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of demands (for a private pool). 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `vmImage`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the VM image you want to use; valid only in the Microsoft-hosted pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="pool{name,demands,vmImage}" version="azure-pipelines"::: -->


```yaml
pool:
  name: string # Name of a pool. 
  demands: string | [ string ]  # List of demands (for a private pool)
  vmImage: string # Name of the VM image you want to use; valid only in the Microsoft-hosted pool. 
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
<!-- :::api-desc type="property"::: -->Name of a pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `demands`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[pool.demands](pool-demands.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of demands (for a private pool). 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `vmImage`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the VM image you want to use; valid only in the Microsoft-hosted pool. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


### Examples

To use a Microsoft-hosted pool, omit the name and specify one of the available [hosted images](/azure/devops/pipelines/agents/hosted.md#use-a-microsoft-hosted-agent):

```yaml
pool:
  vmImage: ubuntu-16.04
```


<!-- See also -->
