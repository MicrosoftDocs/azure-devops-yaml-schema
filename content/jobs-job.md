---
title: jobs.job definition
description: jobs.job definition reference.
ms.date: 02/28/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# jobs.job definition


A [job](/azure/devops/pipelines/process/phases) is a collection of steps run by an [agent](/azure/devops/pipelines/agents/agents) or on a [server](/azure/devops/pipelines/process/phases#server-jobs).


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="job{job}" version="azure-pipelines-2019"::: -->

```yaml
jobs:
- job: string # Required as first property. ID of the job.  ([-_A-Za-z0-9]*)
  displayName: string # Human-readable name for the job. 
  dependsOn: string | [ string ]  # Any jobs which must complete before this one
  condition: string # Evaluate this condition expression to determine whether to run this job. 
  continueOnError: string # Continue running even on failure?. 
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it. 
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it. 
  variables: variables # Job-specific variables
  strategy: jobStrategy # Execution strategy for this job
  pool: pool # Pool where this job will run
  services:  # Container resources to run as a service container.
    string: string # Name/value pairs.
  workspace:  # Workspace options on the agent.
    clean: string # Scorch the repo before fetching?.  (outputs, resources, all)
  steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | publish | template | restoreCache | saveCache ]
```


Properties that use this definition: [jobs](jobs.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `job`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the job. Acceptable values: [_A-Za-z0-9]*
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
<!-- :::api-desc type="property"::: -->Human-readable name for the job. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `dependsOn`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string or string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Any jobs which must complete before this one. 
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
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this job. 
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
   `timeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for this job to complete before the server kills it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `cancelTimeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for the job to cancel before forcibly terminating it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[variables](variables.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Job-specific variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `strategy`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.job.strategy](jobs-job-strategy.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Execution strategy for this job. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pool`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[pool](pool.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pool where this job will run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `services`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resources to run as a service container. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `workspace`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
workspace options
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Workspace options on the agent. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `steps`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[steps](steps.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->A list of steps to run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="job{job}" version="azure-pipelines-2019.1"::: -->

```yaml
jobs:
- job: string # Required as first property. ID of the job.  ([-_A-Za-z0-9]*)
  displayName: string # Human-readable name for the job. 
  dependsOn: string | [ string ]  # Any jobs which must complete before this one
  condition: string # Evaluate this condition expression to determine whether to run this job. 
  continueOnError: string # Continue running even on failure?. 
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it. 
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it. 
  variables: variables # Job-specific variables
  strategy: jobStrategy # Execution strategy for this job
  pool: pool # Pool where this job will run
  container: jobContainer # Container resource name
  services:  # Container resources to run as a service container.
    string: string # Name/value pairs.
  workspace:  # Workspace options on the agent.
    clean: string # Scorch the repo before fetching?.  (outputs, resources, all)
  steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | publish | template | restoreCache | saveCache ]
```


Properties that use this definition: [jobs](jobs.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `job`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the job. Acceptable values: [_A-Za-z0-9]*
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
<!-- :::api-desc type="property"::: -->Human-readable name for the job. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `dependsOn`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string or string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Any jobs which must complete before this one. 
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
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this job. 
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
   `timeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for this job to complete before the server kills it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `cancelTimeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for the job to cancel before forcibly terminating it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[variables](variables.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Job-specific variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `strategy`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.job.strategy](jobs-job-strategy.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Execution strategy for this job. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pool`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[pool](pool.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pool where this job will run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.job.container](jobs-job-container.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resource name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `services`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resources to run as a service container. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `workspace`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
workspace options
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Workspace options on the agent. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `steps`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[steps](steps.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->A list of steps to run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="job{job}" version="azure-pipelines-2020"::: -->

```yaml
jobs:
- job: string # Required as first property. ID of the job.  ([-_A-Za-z0-9]*)
  displayName: string # Human-readable name for the job. 
  dependsOn: string | [ string ]  # Any jobs which must complete before this one
  condition: string # Evaluate this condition expression to determine whether to run this job. 
  continueOnError: string # Continue running even on failure?. 
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it. 
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it. 
  variables: variables # Job-specific variables
  strategy: jobStrategy # Execution strategy for this job
  pool: pool # Pool where this job will run
  container: jobContainer # Container resource name
  services:  # Container resources to run as a service container.
    string: string # Name/value pairs.
  workspace:  # Workspace options on the agent.
    clean: string # Which parts of the workspace should be scorched before fetching.  (outputs, resources, all)
  steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
```


Properties that use this definition: [jobs](jobs.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `job`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the job. Acceptable values: [_A-Za-z0-9]*
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
<!-- :::api-desc type="property"::: -->Human-readable name for the job. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `dependsOn`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string or string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Any jobs which must complete before this one. 
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
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this job. 
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
   `timeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for this job to complete before the server kills it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `cancelTimeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for the job to cancel before forcibly terminating it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[variables](variables.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Job-specific variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `strategy`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.job.strategy](jobs-job-strategy.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Execution strategy for this job. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pool`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[pool](pool.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pool where this job will run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.job.container](jobs-job-container.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resource name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `services`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resources to run as a service container. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `workspace`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
workspace options
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Workspace options on the agent. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `steps`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[steps](steps.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->A list of steps to run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="job{job}" version="azure-pipelines-2020.1"::: -->

```yaml
jobs:
- job: string # Required as first property. ID of the job.  ([-_A-Za-z0-9]*)
  displayName: string # Human-readable name for the job. 
  dependsOn: string | [ string ]  # Any jobs which must complete before this one
  condition: string # Evaluate this condition expression to determine whether to run this job. 
  continueOnError: string # Continue running even on failure?. 
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it. 
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it. 
  variables: variables # Job-specific variables
  strategy: jobStrategy # Execution strategy for this job
  pool: pool # Pool where this job will run
  container: jobContainer # Container resource name
  services:  # Container resources to run as a service container.
    string: string # Name/value pairs.
  workspace:  # Workspace options on the agent.
    clean: string # Which parts of the workspace should be scorched before fetching.  (outputs, resources, all)
  uses:  # Any resources required by this job that are not already referenced
    repositories: [ string ] # Repository references 
    pools: [ string ] # Pool references 
  steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
```


Properties that use this definition: [jobs](jobs.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `job`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the job. Acceptable values: [_A-Za-z0-9]*
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
<!-- :::api-desc type="property"::: -->Human-readable name for the job. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `dependsOn`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string or string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Any jobs which must complete before this one. 
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
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this job. 
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
   `timeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for this job to complete before the server kills it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `cancelTimeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for the job to cancel before forcibly terminating it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[variables](variables.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Job-specific variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `strategy`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.job.strategy](jobs-job-strategy.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Execution strategy for this job. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pool`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[pool](pool.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pool where this job will run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.job.container](jobs-job-container.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resource name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `services`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resources to run as a service container. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `workspace`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
workspace options
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Workspace options on the agent. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `uses`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
pools and repositories
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Any resources required by this job that are not already referenced. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `steps`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[steps](steps.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->A list of steps to run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="job{job}" version="azure-pipelines"::: -->

```yaml
jobs:
- job: string # Required as first property. ID of the job.  ([-_A-Za-z0-9]*)
  displayName: string # Human-readable name for the job. 
  dependsOn: string | [ string ]  # Any jobs which must complete before this one
  condition: string # Evaluate this condition expression to determine whether to run this job. 
  continueOnError: string # Continue running even on failure?. 
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it. 
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it. 
  variables: variables # Job-specific variables
  strategy: jobStrategy # Execution strategy for this job
  pool: pool # Pool where this job will run
  container: jobContainer # Container resource name
  services:  # Container resources to run as a service container.
    string: string # Name/value pairs.
  workspace:  # Workspace options on the agent.
    clean: string # Which parts of the workspace should be scorched before fetching.  (outputs, resources, all)
  uses:  # Any resources required by this job that are not already referenced
    repositories: [ string ] # Repository references 
    pools: [ string ] # Pool references 
  steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
```


Properties that use this definition: [jobs](jobs.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `job`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the job. Acceptable values: [-_A-Za-z0-9]*
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
<!-- :::api-desc type="property"::: -->Human-readable name for the job. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `dependsOn`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string or string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Any jobs which must complete before this one. 
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
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this job. 
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
   `timeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for this job to complete before the server kills it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `cancelTimeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for the job to cancel before forcibly terminating it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[variables](variables.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Job-specific variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `strategy`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.job.strategy](jobs-job-strategy.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Execution strategy for this job. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pool`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[pool](pool.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pool where this job will run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.job.container](jobs-job-container.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resource name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `services`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resources to run as a service container. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `workspace`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
workspace options
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Workspace options on the agent. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `uses`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
pools and repositories
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Any resources required by this job that are not already referenced. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `steps`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[steps](steps.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->A list of steps to run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

Jobs can run [conditionally](/azure/devops/pipelines/process/phases#conditions) and might [depend on earlier jobs](/azure/devops/pipelines/process/phases#dependencies).

> [!NOTE]
> If you have only one stage and one job, you can use [single-job syntax](/azure/devops/pipelines/process/phases) as a shorter way to describe the steps to run.


## Examples

```yaml
jobs:
- job: MyJob
  displayName: My First Job
  continueOnError: true
  workspace:
    clean: outputs
  steps:
  - script: echo My first job
```


## See also

- For more information about `uses`, see [Limit job authorization scope to referenced Azure DevOps repositories](/azure/devops/pipelines/repos/azure-repos-git#limit-job-authorization-scope-to-referenced-azure-devops-repositories). For more information about workspaces, including clean options, see the [workspace](/azure/devops/pipelines/process/phased#workspace) topic in [Jobs](/azure/devops/pipelines/process/phases).
- Learn more about [variables](/azure/devops/pipelines/process/variables), [steps](steps.md), [pools](pool.md), and [server jobs](/azure/devops/pipelines/process/phases#server).





