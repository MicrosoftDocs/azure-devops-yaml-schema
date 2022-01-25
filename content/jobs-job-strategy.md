---
title: jobs.job.strategy definition
description: jobs.job.strategy definition reference.
ms.date: 01/24/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# jobs.job.strategy definition



The `matrix` and `parallel` keywords specify mutually exclusive strategies for duplicating a job.



:::moniker range="= azure-pipelines-2019"

Properties that use this definition: [pipeline.strategy](pipeline.md), [jobs.job.strategy](jobs-job.md)

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

Properties that use this definition: [pipeline.strategy](pipeline.md), [jobs.job.strategy](jobs-job.md)

:::moniker-end

:::moniker range="= azure-pipelines-2020"

Properties that use this definition: [pipeline.strategy](pipeline.md), [jobs.job.strategy](jobs-job.md)

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

Properties that use this definition: [pipeline.strategy](pipeline.md), [jobs.job.strategy](jobs-job.md)

:::moniker-end

:::moniker range="= azure-pipelines"

Properties that use this definition: [pipeline.strategy](pipeline.md), [jobs.job.strategy](jobs-job.md)

:::moniker-end

## Overloads

:::moniker range="= azure-pipelines-2019" 

| Overload | Description |
|----------|-------------|
| [jobStrategy: matrix, maxParallel](#jobstrategy-matrix-maxparallel) | Matrix job strategy. |
| [jobStrategy: parallel](#jobstrategy-parallel) | Parallel job strategy. |

:::moniker-end

:::moniker range="= azure-pipelines-2019.1" 

| Overload | Description |
|----------|-------------|
| [jobStrategy: matrix, maxParallel](#jobstrategy-matrix-maxparallel) | Matrix job strategy. |
| [jobStrategy: parallel](#jobstrategy-parallel) | Parallel job strategy. |

:::moniker-end

:::moniker range="= azure-pipelines-2020" 

| Overload | Description |
|----------|-------------|
| [jobStrategy: matrix, maxParallel](#jobstrategy-matrix-maxparallel) | Matrix job strategy. |
| [jobStrategy: parallel](#jobstrategy-parallel) | Parallel job strategy. |

:::moniker-end

:::moniker range="= azure-pipelines-2020.1" 

| Overload | Description |
|----------|-------------|
| [jobStrategy: matrix, maxParallel](#jobstrategy-matrix-maxparallel) | Matrix job strategy. |
| [jobStrategy: parallel](#jobstrategy-parallel) | Parallel job strategy. |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [jobStrategy: matrix, maxParallel](#jobstrategy-matrix-maxparallel) | Matrix job strategy. |
| [jobStrategy: parallel](#jobstrategy-parallel) | Parallel job strategy. |

:::moniker-end

<!-- Remarks -->

:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## jobStrategy: matrix, maxParallel

:::moniker-end


Use of a matrix generates copies of a job, each with different input.
These copies are useful for testing against different configurations or platform versions.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="jobStrategy{matrix,maxParallel}" version="azure-pipelines-2019"::: -->


```yaml
strategy:
  matrix: { string1: { string2: string3 } } # Job matrix, see the following examples. # Matrix defining the job strategy; see the following examples.
  maxParallel: string # Maximum number of jobs running in parallel. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `matrix`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
jobMatrix
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Matrix defining the job strategy; see the following examples. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `maxParallel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Maximum number of jobs running in parallel. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="jobStrategy{matrix,maxParallel}" version="azure-pipelines-2019.1"::: -->


```yaml
strategy:
  matrix: { string1: { string2: string3 } } # Job matrix, see the following examples. # Matrix defining the job strategy; see the following examples.
  maxParallel: string # Maximum number of jobs running in parallel. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `matrix`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
jobMatrix
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Matrix defining the job strategy; see the following examples. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `maxParallel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Maximum number of jobs running in parallel. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="jobStrategy{matrix,maxParallel}" version="azure-pipelines-2020"::: -->


```yaml
strategy:
  matrix: { string1: { string2: string3 } } # Job matrix, see the following examples. # Matrix defining the job strategy; see the following examples.
  maxParallel: string # Maximum number of jobs running in parallel. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `matrix`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
jobMatrix
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Matrix defining the job strategy; see the following examples. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `maxParallel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Maximum number of jobs running in parallel. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="jobStrategy{matrix,maxParallel}" version="azure-pipelines-2020.1"::: -->


```yaml
strategy:
  matrix: { string1: { string2: string3 } } # Job matrix, see the following examples. # Matrix defining the job strategy; see the following examples.
  maxParallel: string # Maximum number of jobs running in parallel. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `matrix`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
jobMatrix
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Matrix defining the job strategy; see the following examples. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `maxParallel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Maximum number of jobs running in parallel. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="jobStrategy{matrix,maxParallel}" version="azure-pipelines"::: -->


```yaml
strategy:
  matrix: { string1: { string2: string3 } } # Job matrix, see the following examples. # Matrix defining the job strategy; see the following examples.
  maxParallel: string # Maximum number of jobs running in parallel. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `matrix`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
jobMatrix
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Matrix defining the job strategy; see the following examples. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `maxParallel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Maximum number of jobs running in parallel. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


<!-- Examples -->

:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## jobStrategy: parallel

:::moniker-end


This strategy specifies how many duplicates of a job should run.
It's useful for slicing up a large test matrix.
The [Visual Studio Test task](/azure/devops/pipelines/tasks/test/vstest) understands how to divide the test load across the number of scheduled jobs.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="jobStrategy{parallel}" version="azure-pipelines-2019"::: -->


```yaml
strategy:
  parallel: string # Run the job this many times. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `parallel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Run the job this many times. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="jobStrategy{parallel}" version="azure-pipelines-2019.1"::: -->


```yaml
strategy:
  parallel: string # Run the job this many times. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `parallel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Run the job this many times. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="jobStrategy{parallel}" version="azure-pipelines-2020"::: -->


```yaml
strategy:
  parallel: string # Run the job this many times. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `parallel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Run the job this many times. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="jobStrategy{parallel}" version="azure-pipelines-2020.1"::: -->


```yaml
strategy:
  parallel: string # Run the job this many times. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `parallel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Run the job this many times. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="jobStrategy{parallel}" version="azure-pipelines"::: -->


```yaml
strategy:
  parallel: string # Run the job this many times. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `parallel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Run the job this many times. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


<!-- Examples -->

<!-- See also -->
