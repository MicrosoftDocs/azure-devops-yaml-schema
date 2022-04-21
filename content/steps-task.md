---
title: steps.task definition
description: steps.task definition reference.
ms.date: 04/21/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# steps.task definition


A `task` step runs a task.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="step{task}" version="azure-pipelines-2019"::: -->

```yaml
steps:
- task
```


Properties that use this definition: [steps](steps.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `step`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
task
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="step{task}" version="azure-pipelines-2019.1"::: -->

```yaml
steps:
- task
```


Properties that use this definition: [steps](steps.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `step`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
task
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="step{task}" version="azure-pipelines-2020"::: -->

```yaml
steps:
- task
```


Properties that use this definition: [steps](steps.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `step`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
task
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

<!-- :::api-definition signature="step{task}" version="azure-pipelines-2020.1"::: -->

```yaml
steps:
- task
```


Properties that use this definition: [steps](steps.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `step`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
task
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

<!-- :::api-definition signature="step{task}" version="azure-pipelines"::: -->

```yaml
steps:
- task
```


Properties that use this definition: [steps](steps.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `step`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
task
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

[Tasks](/azure/devops/pipelines/process/tasks) are the building blocks of a pipeline.
There's a [catalog of tasks](/azure/devops/pipelines/tasks/index) available to choose from.

If you don't specify a command mode, you can shorten the `target` structure to:

```yaml
- task:
  target: string  # container name or the word 'host'
```

All steps and tasks support the following properties in addition to their task or step specific properties.

:::moniker range=">azure-pipelines-2020.1"

```YAML
  condition: string # Evaluate this condition expression to determine whether to run this task. 
  continueOnError: boolean # Continue running even on failure?.  (false,n,no,off,on,true,y,yes)
  displayName: string # Human-readable name for the task. 
  target: # Environment in which to run this task
  enabled: boolean # Run this task when the job runs? (false,n,no,off,on,true,y,yes)
  env:  # Variables to map into the process's environment
    string: string # Name/value pairs.
  name: string # ID of the step.
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it. 
  retryCountOnTaskFailure: string # Number of retries if the task fails. 
```


:::moniker-end

:::moniker range=">= azure-pipelines-2020 <= azure-pipelines-2020.1"

```YAML
  condition: string # Evaluate this condition expression to determine whether to run this task. 
  continueOnError: boolean # Continue running even on failure?.  (false,n,no,off,on,true,y,yes)
  displayName: string # Human-readable name for the task. 
  target: # Environment in which to run this task
  enabled: boolean # Run this task when the job runs? (false,n,no,off,on,true,y,yes)
  env:  # Variables to map into the process's environment
    string: string # Name/value pairs.
  name: string # ID of the step.
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it. 
```

:::moniker-end

:::moniker range=">= azure-pipelines-2019 <= azure-pipelines-2019.1"

```YAML
  condition: string # Evaluate this condition expression to determine whether to run this task. 
  continueOnError: boolean # Continue running even on failure?.  (false,n,no,off,on,true,y,yes)
  displayName: string # Human-readable name for the step. 
  enabled: boolean # Run this task when the job runs? (false,n,no,off,on,true,y,yes)
  env:  # Variables to map into the process's environment
    string: string # Name/value pairs.
  name: string # ID of the step.
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it. 
```

:::moniker-end

Learn more about [conditions](/azure/devops/pipelines/process/conditions),
[timeouts](/azure/devops/pipelines/process/phases#timeouts), and [step targets](/azure/devops/pipelines/process/tasks#step-target).


## Examples

```yaml
steps:
- task: VSBuild@1
  displayName: Build
  timeoutInMinutes: 120
  inputs:
    solution: '**\*.sln'
```


## See also

- [Tasks](/azure/devops/pipelines/process/tasks)
- [Catalog of tasks](/azure/devops/pipelines/tasks/index)

