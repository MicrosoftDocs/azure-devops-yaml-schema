---
title: pool definition
description: pool definition reference.
ms.date: 01/18/2023
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"
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

:::moniker range="= azure-pipelines-2022"

Properties that use this definition: [pipeline.pool](pipeline.md), [stages.stage.pool](stages-stage.md), [jobs.job.pool](jobs-job.md), [jobs.deployment.pool](jobs-deployment.md)

:::moniker-end

:::moniker range="= azure-pipelines"

Properties that use this definition: [pipeline.pool](pipeline.md), [stages.stage.pool](stages-stage.md), [jobs.job.pool](jobs-job.md), [jobs.deployment.pool](jobs-deployment.md)

:::moniker-end

## Overloads

:::moniker range="= azure-pipelines-2019" 

| Overload | Description |
|----------|-------------|
| [pool: string](#pool-string) | Specify a private pool by name. |
| [pool: name, demands, vmImage](#pool-name-demands-vmimage) | Full syntax for using demands and Microsoft-hosted pools. |

:::moniker-end

:::moniker range="= azure-pipelines-2019.1" 

| Overload | Description |
|----------|-------------|
| [pool: string](#pool-string) | Specify a private pool by name. |
| [pool: name, demands, vmImage](#pool-name-demands-vmimage) | Full syntax for using demands and Microsoft-hosted pools. |

:::moniker-end

:::moniker range="= azure-pipelines-2020" 

| Overload | Description |
|----------|-------------|
| [pool: string](#pool-string) | Specify a private pool by name. |
| [pool: name, demands, vmImage](#pool-name-demands-vmimage) | Full syntax for using demands and Microsoft-hosted pools. |

:::moniker-end

:::moniker range="= azure-pipelines-2020.1" 

| Overload | Description |
|----------|-------------|
| [pool: string](#pool-string) | Specify a private pool by name. |
| [pool: name, demands, vmImage](#pool-name-demands-vmimage) | Full syntax for using demands and Microsoft-hosted pools. |

:::moniker-end

:::moniker range="= azure-pipelines-2022" 

| Overload | Description |
|----------|-------------|
| [pool: string](#pool-string) | Specify a private pool by name. |
| [pool: name, demands, vmImage](#pool-name-demands-vmimage) | Full syntax for using demands and Microsoft-hosted pools. |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [pool: string](#pool-string) | Specify a private pool by name. |
| [pool: name, demands, vmImage](#pool-name-demands-vmimage) | Full syntax for using demands and Microsoft-hosted pools. |

:::moniker-end


## Remarks

::: moniker range=">= azure-pipelines-2019 <= azure-pipelines-2019.1"

In Azure DevOps Server 2019 you can specify a pool at the job level in YAML, and at the pipeline level in the pipeline settings UI. In Azure DevOps Server 2019.1 you can also specify a pool at the pipeline level in YAML if you have a single implicit job.
:::moniker-end

::: moniker range=">= azure-pipelines-2020"
You can specify a pool at the pipeline, stage, or job level.
:::moniker-end

The pool specified at the lowest level of the hierarchy is used to run the job.

:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"

## pool: string

Specify a pool by name to use for a job of the pipeline.



:::moniker-end

:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="pool{string}" version="azure-pipelines-2019"::: -->


```yaml
pool: string # Specify a private pool by name.
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
<!-- :::api-desc type="property"::: -->Specify a private pool by name. 
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
pool: string # Specify a private pool by name.
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
<!-- :::api-desc type="property"::: -->Specify a private pool by name. 
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
pool: string # Specify a private pool by name.
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
<!-- :::api-desc type="property"::: -->Specify a private pool by name. 
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
pool: string # Specify a private pool by name.
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
<!-- :::api-desc type="property"::: -->Specify a private pool by name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="pool{string}" version="azure-pipelines-2022"::: -->


```yaml
pool: string # Specify a private pool by name.
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
<!-- :::api-desc type="property"::: -->Specify a private pool by name. 
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
pool: string # Specify a private pool by name.
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
<!-- :::api-desc type="property"::: -->Specify a private pool by name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


### Remarks

Use this syntax to specify a private pool by name.

> [!NOTE]
> If your pool name has a space in it, enclose the pool name in single quotes, like `pool: 'My pool'`.


### Examples

To use a private pool with no demands:

```yaml
pool: MyPool
```


:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"

## pool: name, demands, vmImage

Specify a pool to use for a job of the pipeline using the full syntax.



:::moniker-end

:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="pool{name,demands,vmImage}" version="azure-pipelines-2019"::: -->


```yaml
pool:
  name: string # Name of a pool. 
  demands: string | [ string ] # List of demands (for a private pool)
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
string or string list
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
  demands: string | [ string ] # List of demands (for a private pool)
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
string or string list
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
  demands: string | [ string ] # List of demands (for a private pool)
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
string or string list
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
  demands: string | [ string ] # List of demands (for a private pool)
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
string or string list
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

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="pool{name,demands,vmImage}" version="azure-pipelines-2022"::: -->


```yaml
pool:
  name: string # Name of a pool. 
  demands: string | [ string ] # List of demands (for a private pool)
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
string or string list
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
  demands: string | [ string ] # List of demands (for a private pool)
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
string or string list
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


### Remarks

Specify a Microsoft-hosted pool using the `vmImage` property.

If your self-hosted agent pool name has a space in it, enclose the pool name in single quotes, like `name: 'My pool'`.


### Examples

:::moniker range="= azure-pipelines"

To use a Microsoft-hosted pool, omit the name and specify one of the available [hosted images](/azure/devops/pipelines/agents/hosted#use-a-microsoft-hosted-agent):

```yaml
pool:
  vmImage: ubuntu-latest
```

::: moniker-end

You can specify demands for a private pool using the full syntax.

To add a single demand to your YAML build pipeline, add the `demands:` line to the `pool` section.
```yaml
pool:
  name: Default
  demands: SpecialSoftware # exists check for SpecialSoftware
```

Or if you need to add multiple demands, add one per line.

```yaml
pool:
  name: MyPool
  demands:
  - myCustomCapability   # exists check for myCustomCapability
  - Agent.Version -equals 2.144.0 # equals check for Agent.Version 2.144.0
```

> [!NOTE]
> Checking for the existence of a capability (exists) and checking for a specific string in a capability (equals) are the only two supported operations for demands.

For more information and examples, see [Specify demands](/azure/devops/pipelines/process/demands).

## See also

Learn more about [conditions](/azure/devops/pipelines/process/conditions) and [timeouts](/azure/devops/pipelines/process/phases#timeouts).


