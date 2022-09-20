---
title: steps.download definition
description: steps.download definition reference.
ms.date: 09/01/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"
---

# steps.download definition


The `download` step downloads artifacts associated with the current run or from another Azure Pipeline that is associated as a pipeline resource.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="step{download}" version="azure-pipelines-2019"::: -->

```yaml
steps:
- download: string # Required as first property. Specify current, pipeline resource identifier, or none to disable automatic download. 
  artifact: string # Artifact name.. 
  patterns: string # Pattern to download files from artifact. 
  condition: string # Evaluate this condition expression to determine whether to run this task. 
  continueOnError: boolean # Continue running even on failure?.  (false,n,no,off,on,true,y,yes)
  displayName: string # Human-readable name for the task. 
  enabled: boolean # Run this task when the job runs?.  (false,n,no,off,on,true,y,yes)
  env:  # Variables to map into the process's environment
    string: string # Name/value pairs.
  name: string # ID of the step.  ([-_A-Za-z0-9]*)
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it. 
```


Properties that use this definition: [steps](steps.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `download`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Specify current, pipeline resource identifier, or none to disable automatic download. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `artifact`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Artifact name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `patterns`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pattern to download files from artifact. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `condition`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `continueOnError`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Continue running even on failure? 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `displayName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Human-readable name for the task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `enabled`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Run this task when the job runs? 
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
<!-- :::api-desc type="property"::: -->Variables to map into the process's environment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



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
<!-- :::api-desc type="property"::: -->ID of the step. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `timeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for this task to complete before the server kills it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="step{download}" version="azure-pipelines-2019.1"::: -->

```yaml
steps:
- download: string # Required as first property. Specify current, pipeline resource identifier, or none to disable automatic download. 
  artifact: string # Artifact name.. 
  patterns: string # Pattern to download files from artifact. 
  condition: string # Evaluate this condition expression to determine whether to run this task. 
  continueOnError: boolean # Continue running even on failure?.  (false,n,no,off,on,true,y,yes)
  displayName: string # Human-readable name for the task. 
  enabled: boolean # Run this task when the job runs?.  (false,n,no,off,on,true,y,yes)
  env:  # Variables to map into the process's environment
    string: string # Name/value pairs.
  name: string # ID of the step.  ([-_A-Za-z0-9]*)
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it. 
```


Properties that use this definition: [steps](steps.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `download`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Specify current, pipeline resource identifier, or none to disable automatic download. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `artifact`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Artifact name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `patterns`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pattern to download files from artifact. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `condition`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `continueOnError`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Continue running even on failure? 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `displayName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Human-readable name for the task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `enabled`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Run this task when the job runs? 
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
<!-- :::api-desc type="property"::: -->Variables to map into the process's environment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



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
<!-- :::api-desc type="property"::: -->ID of the step. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `timeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for this task to complete before the server kills it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="step{download}" version="azure-pipelines-2020"::: -->

```yaml
steps:
- download: string # Required as first property. Specify current, pipeline resource identifier, or none to disable automatic download. 
  artifact: string # Artifact name.. 
  patterns: string # Pattern to download files from artifact. 
  condition: string # Evaluate this condition expression to determine whether to run this task. 
  continueOnError: boolean # Continue running even on failure?.  (false,n,no,off,on,true,y,yes)
  displayName: string # Human-readable name for the task. 
  target: stepTarget # Environment in which to run this task
  enabled: boolean # Run this task when the job runs?.  (false,n,no,off,on,true,y,yes)
  env:  # Variables to map into the process's environment
    string: string # Name/value pairs.
  name: string # ID of the step.  ([-_A-Za-z0-9]*)
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it. 
```


Properties that use this definition: [steps](steps.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `download`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Specify current, pipeline resource identifier, or none to disable automatic download. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `artifact`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Artifact name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `patterns`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pattern to download files from artifact. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `condition`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `continueOnError`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Continue running even on failure? 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `displayName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Human-readable name for the task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `target`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[target](target.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Environment in which to run this task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `enabled`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Run this task when the job runs? 
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
<!-- :::api-desc type="property"::: -->Variables to map into the process's environment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



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
<!-- :::api-desc type="property"::: -->ID of the step. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `timeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for this task to complete before the server kills it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="step{download}" version="azure-pipelines-2020.1"::: -->

```yaml
steps:
- download: string # Required as first property. Specify current, pipeline resource identifier, or none to disable automatic download. 
  artifact: string # Artifact name.. 
  patterns: string # Pattern to download files from artifact. 
  condition: string # Evaluate this condition expression to determine whether to run this task. 
  continueOnError: boolean # Continue running even on failure?.  (false,n,no,off,on,true,y,yes)
  displayName: string # Human-readable name for the task. 
  target: stepTarget # Environment in which to run this task
  enabled: boolean # Run this task when the job runs?.  (false,n,no,off,on,true,y,yes)
  env:  # Variables to map into the process's environment
    string: string # Name/value pairs.
  name: string # ID of the step.  ([-_A-Za-z0-9]*)
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it. 
```


Properties that use this definition: [steps](steps.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `download`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Specify current, pipeline resource identifier, or none to disable automatic download. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `artifact`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Artifact name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `patterns`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pattern to download files from artifact. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `condition`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `continueOnError`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Continue running even on failure? 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `displayName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Human-readable name for the task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `target`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[target](target.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Environment in which to run this task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `enabled`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Run this task when the job runs? 
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
<!-- :::api-desc type="property"::: -->Variables to map into the process's environment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



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
<!-- :::api-desc type="property"::: -->ID of the step. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `timeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for this task to complete before the server kills it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="step{download}" version="azure-pipelines-2022"::: -->

```yaml
steps:
- download: string # Required as first property. Specify current, pipeline resource identifier, or none to disable automatic download. 
  artifact: string # Artifact name.. 
  patterns: string # Pattern to download files from artifact. 
  condition: string # Evaluate this condition expression to determine whether to run this task. 
  continueOnError: boolean # Continue running even on failure?.  (false,n,no,off,on,true,y,yes)
  displayName: string # Human-readable name for the task. 
  target: stepTarget # Environment in which to run this task
  enabled: boolean # Run this task when the job runs?.  (false,n,no,off,on,true,y,yes)
  env:  # Variables to map into the process's environment
    string: string # Name/value pairs.
  name: string # ID of the step.  ([-_A-Za-z0-9]*)
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it. 
  retryCountOnTaskFailure: string # Number of retries if the task fails. 
```


Properties that use this definition: [steps](steps.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `download`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Specify current, pipeline resource identifier, or none to disable automatic download. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `artifact`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Artifact name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `patterns`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pattern to download files from artifact. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `condition`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `continueOnError`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Continue running even on failure? 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `displayName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Human-readable name for the task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `target`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[target](target.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Environment in which to run this task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `enabled`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Run this task when the job runs? 
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
<!-- :::api-desc type="property"::: -->Variables to map into the process's environment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



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
<!-- :::api-desc type="property"::: -->ID of the step. Acceptable values: [-_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `timeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for this task to complete before the server kills it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `retryCountOnTaskFailure`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Number of retries if the task fails. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="step{download}" version="azure-pipelines"::: -->

```yaml
steps:
- download: string # Required as first property. Specify current, pipeline resource identifier, or none to disable automatic download. 
  artifact: string # Artifact name.. 
  patterns: string # Pattern to download files from artifact. 
  condition: string # Evaluate this condition expression to determine whether to run this task. 
  continueOnError: boolean # Continue running even on failure?.  (false,n,no,off,on,true,y,yes)
  displayName: string # Human-readable name for the task. 
  target: stepTarget # Environment in which to run this task
  enabled: boolean # Run this task when the job runs?.  (false,n,no,off,on,true,y,yes)
  env:  # Variables to map into the process's environment
    string: string # Name/value pairs.
  name: string # ID of the step.  ([-_A-Za-z0-9]*)
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it. 
  retryCountOnTaskFailure: string # Number of retries if the task fails. 
```


Properties that use this definition: [steps](steps.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `download`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Specify current, pipeline resource identifier, or none to disable automatic download. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `artifact`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Artifact name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `patterns`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pattern to download files from artifact. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `condition`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `continueOnError`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Continue running even on failure? 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `displayName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Human-readable name for the task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `target`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[target](target.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Environment in which to run this task. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `enabled`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Run this task when the job runs? 
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
<!-- :::api-desc type="property"::: -->Variables to map into the process's environment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



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
<!-- :::api-desc type="property"::: -->ID of the step. Acceptable values: [-_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `timeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for this task to complete before the server kills it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `retryCountOnTaskFailure`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Number of retries if the task fails. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

The `download` keyword is a shortcut for the [Download Pipeline Artifacts task](/azure/devops/pipelines/tasks/reference/download-pipeline-artifact-v2).

### Artifact download location

Artifacts from the current pipeline are downloaded to `$(**Pipeline.Workspace**)/<artifact name>`.

Artifacts from the associated pipeline resource are downloaded to `$(**Pipeline.Workspace**)/\<pipeline resource identifier\>/<artifact name>`.

### Automatic download in deployment jobs

All available artifacts from the current pipeline and from the associated pipeline resources are automatically downloaded in deployment jobs and made available for your deployment.

To prevent downloads, specify `download: none`.


## Examples

```yaml
steps:
- download: current  # refers to artifacts published by current pipeline
  artifact: WebApp
  patterns: '**/.js'
  displayName: Download artifact WebApp
- download: MyAppA   # downloads artifacts available as part of the pipeline resource specified as MyAppA
```


## See also

- [Publish and download pipeline Artifacts](/azure/devops/pipelines/artifacts/pipeline-artifacts)
- [Download Pipeline Artifacts task](/azure/devops/pipelines/tasks/reference/download-pipeline-artifact-v2)
