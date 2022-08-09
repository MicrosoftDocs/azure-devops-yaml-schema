---
title: jobs.job.strategy definition
description: jobs.job.strategy definition reference.
ms.date: 08/08/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"
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

:::moniker range="= azure-pipelines-2022"

Properties that use this definition: [pipeline.strategy](pipeline.md), [jobs.job.strategy](jobs-job.md)

:::moniker-end

:::moniker range="= azure-pipelines"

Properties that use this definition: [pipeline.strategy](pipeline.md), [jobs.job.strategy](jobs-job.md)

:::moniker-end

## Overloads

:::moniker range="= azure-pipelines-2019" 

| Overload | Description |
|----------|-------------|
| [strategy: matrix, maxParallel](#strategy-matrix-maxparallel) | Matrix job strategy. |
| [strategy: parallel](#strategy-parallel) | Parallel job strategy. |

:::moniker-end

:::moniker range="= azure-pipelines-2019.1" 

| Overload | Description |
|----------|-------------|
| [strategy: matrix, maxParallel](#strategy-matrix-maxparallel) | Matrix job strategy. |
| [strategy: parallel](#strategy-parallel) | Parallel job strategy. |

:::moniker-end

:::moniker range="= azure-pipelines-2020" 

| Overload | Description |
|----------|-------------|
| [strategy: matrix, maxParallel](#strategy-matrix-maxparallel) | Matrix job strategy. |
| [strategy: parallel](#strategy-parallel) | Parallel job strategy. |

:::moniker-end

:::moniker range="= azure-pipelines-2020.1" 

| Overload | Description |
|----------|-------------|
| [strategy: matrix, maxParallel](#strategy-matrix-maxparallel) | Matrix job strategy. |
| [strategy: parallel](#strategy-parallel) | Parallel job strategy. |

:::moniker-end

:::moniker range="= azure-pipelines-2022" 

| Overload | Description |
|----------|-------------|
| [strategy: matrix, maxParallel](#strategy-matrix-maxparallel) | Matrix job strategy. |
| [strategy: parallel](#strategy-parallel) | Parallel job strategy. |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [strategy: matrix, maxParallel](#strategy-matrix-maxparallel) | Matrix job strategy. |
| [strategy: parallel](#strategy-parallel) | Parallel job strategy. |

:::moniker-end

<!-- Remarks -->

:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"

## strategy: matrix, maxParallel


Use of a matrix generates copies of a job, each with different input.
These copies are useful for testing against different configurations or platform versions.



:::moniker-end

:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="jobStrategy{matrix,maxParallel}" version="azure-pipelines-2019"::: -->


```yaml
strategy:
  matrix: { string1: { string2: string3 } } # Matrix defining the job strategy; see the following examples.
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
  matrix: { string1: { string2: string3 } } # Matrix defining the job strategy; see the following examples.
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
  matrix: { string1: { string2: string3 } } # Matrix defining the job strategy; see the following examples.
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
  matrix: { string1: { string2: string3 } } # Matrix defining the job strategy; see the following examples.
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

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="jobStrategy{matrix,maxParallel}" version="azure-pipelines-2022"::: -->


```yaml
strategy:
  matrix: { string1: { string2: string3 } } # Matrix defining the job strategy; see the following examples.
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
  matrix: { string1: { string2: string3 } } # Matrix defining the job strategy; see the following examples.
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


### Remarks

```yaml
strategy:
  matrix: { string1: { string2: string3 } }
  maxParallel: number
```

For each occurrence of *string1* in the matrix, a copy of the job is generated.
The name *string1* is the copy's name and is appended to the name of the job.
For each occurrence of *string2*, a variable called *string2* with the value *string3* is available to the job.

> [!NOTE]
> Matrix configuration names must contain only basic Latin alphabet letters (A-Z and a-z), digits (0-9), and underscores (`_`).
> They must start with a letter.
> Also, their length must be 100 characters or fewer.

The optional `maxParallel` keyword specifies the maximum number of simultaneous matrix legs to run at once.

::: moniker range=">= azure-pipelines-2020"

If `maxParallel` is unspecified or set to 0, no limit is applied.

::: moniker-end

::: moniker range=">= azure-pipelines-2019 <= azure-pipelines-2019.1"

If `maxParallel` is unspecified, no limit is applied.

::: moniker-end

> [!NOTE]
> The `matrix` syntax doesn't support automatic job scaling but you can implement similar
> functionality using the `each` keyword. For an example, see [expressions](/azure/devops/pipelines/process/expressions).


### Examples

```yaml
jobs:
- job: Build
  strategy:
    matrix:
      Python35:
        PYTHON_VERSION: '3.5'
      Python36:
        PYTHON_VERSION: '3.6'
      Python37:
        PYTHON_VERSION: '3.7'
    maxParallel: 2
```

This matrix creates three jobs: "Build Python35," "Build Python36," and "Build Python37."
Within each job, a variable named PYTHON_VERSION is available.
In "Build Python35," the variable is set to "3.5".
It's likewise set to "3.6" in "Build Python36."
Only two jobs run simultaneously.




:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"

## strategy: parallel


This strategy specifies how many duplicates of a job should run.
It's useful for slicing up a large test matrix.
The [Visual Studio Test task](/azure/devops/pipelines/tasks/test/vstest) understands how to divide the test load across the number of scheduled jobs.



:::moniker-end

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

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="jobStrategy{parallel}" version="azure-pipelines-2022"::: -->


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


### Examples

```yaml
jobs:
- job: SliceItFourWays
  strategy:
    parallel: 4
```




<!-- See also -->
