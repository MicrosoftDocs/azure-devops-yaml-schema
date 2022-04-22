---
title: stages.stage definition
description: stages.stage definition reference.
ms.date: 04/22/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# stages.stage definition


Stages are a collection of related jobs. By default, stages run sequentially. Each stage starts only after the preceding stage is complete unless otherwise specified via the `dependsOn` property.


:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="stage{stage}" version="azure-pipelines-2020"::: -->

```yaml
stages:
- stage: string # Required as first property. ID of the stage. 
  displayName: string # Human-readable name for the stage. 
  pool: pool # Pool where jobs in this stage will run unless otherwise specified
  dependsOn: string | [ string ]  # Any stages which must complete before this one
  condition: string # Evaluate this condition expression to determine whether to run this stage. 
  variables: variables # Stage-specific variables
  jobs: [ job | deployment | template ]
```


Properties that use this definition: [stages](stages.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `stage`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the stage. 
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
<!-- :::api-desc type="property"::: -->Human-readable name for the stage. 
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
<!-- :::api-desc type="property"::: -->Pool where jobs in this stage will run unless otherwise specified. 
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
<!-- :::api-desc type="property"::: -->Any stages which must complete before this one. 
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
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this stage. 
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
<!-- :::api-desc type="property"::: -->Stage-specific variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `jobs`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs](jobs.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Jobs which make up the stage. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="stage{stage}" version="azure-pipelines-2020.1"::: -->

```yaml
stages:
- stage: string # Required as first property. ID of the stage. 
  displayName: string # Human-readable name for the stage. 
  pool: pool # Pool where jobs in this stage will run unless otherwise specified
  dependsOn: string | [ string ]  # Any stages which must complete before this one
  condition: string # Evaluate this condition expression to determine whether to run this stage. 
  variables: variables # Stage-specific variables
  jobs: [ job | deployment | template ]
```


Properties that use this definition: [stages](stages.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `stage`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the stage. 
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
<!-- :::api-desc type="property"::: -->Human-readable name for the stage. 
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
<!-- :::api-desc type="property"::: -->Pool where jobs in this stage will run unless otherwise specified. 
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
<!-- :::api-desc type="property"::: -->Any stages which must complete before this one. 
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
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this stage. 
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
<!-- :::api-desc type="property"::: -->Stage-specific variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `jobs`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs](jobs.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Jobs which make up the stage. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="stage{stage}" version="azure-pipelines"::: -->

```yaml
stages:
- stage: string # Required as first property. ID of the stage. 
  displayName: string # Human-readable name for the stage. 
  pool: pool # Pool where jobs in this stage will run unless otherwise specified
  dependsOn: string | [ string ]  # Any stages which must complete before this one
  condition: string # Evaluate this condition expression to determine whether to run this stage. 
  variables: variables # Stage-specific variables
  jobs: [ job | deployment | template ]
  lockBehavior: string # Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests.  (runLatest,sequential)
  templateContext:  # Stage related information passed from a pipeline when extending a template.
     # Job, stage, or deployment related information passed from a pipeline when extending a template.```


Properties that use this definition: [stages](stages.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `stage`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the stage. 
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
<!-- :::api-desc type="property"::: -->Human-readable name for the stage. 
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
<!-- :::api-desc type="property"::: -->Pool where jobs in this stage will run unless otherwise specified. 
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
<!-- :::api-desc type="property"::: -->Any stages which must complete before this one. 
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
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this stage. 
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
<!-- :::api-desc type="property"::: -->Stage-specific variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `jobs`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs](jobs.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Jobs which make up the stage. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `lockBehavior`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `templateContext`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
templateContext
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Stage related information passed from a pipeline when extending a template. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

Use [approval checks](/azure/devops/pipelines/process/approvals) to manually control when a stage should run.
These checks are commonly used to control deployments to production environments.

Checks are a mechanism available to the *resource owner*.
They control when a stage in a pipeline consumes a resource.
As an owner of a resource like an environment, you can define checks that are required before a stage that consumes the resource can start.

Currently, manual approval checks are supported on [environments](/azure/devops/pipelines/process/environments).
For more information, see [Approvals](/azure/devops/pipelines/process/approvals).

:::moniker range="> azure-pipelines-2020.1"

### Exclusive lock

In YAML pipelines, checks are used to control the execution of stages on [protected resources](/azure/devops/pipelines/security/resources). One of the common checks that you can use is an [exclusive lock check](/azure/devops/pipelines/process/approvals). This check lets only a single run from the pipeline proceed. When multiple runs attempt to deploy to an environment at the same time, the check cancels all the old runs and permits the latest run to be deployed.

You can configure the behavior of the exclusive lock check using the `lockBehavior` property, which has two values:

- `runLatest` - Only the latest run acquires the lock to the resource. This is the default value if no `lockBehavior` is specified.
- `sequential` - All runs acquire the lock sequentially to the protected resource.

Canceling old runs is a good approach when your releases are cumulative and contain all the code changes from previous runs. However, there are some pipelines in which code changes are not cumulative. By configuring the `lockBehavior` property, you can choose to allow all runs to proceed and deploy sequentially to an environment, or preserve the previous behavior of canceling old runs and allowing just the latest. A value of `sequential` implies that all runs acquire the lock sequentially to the protected resource. A value of `runLatest` implies that only the latest run acquires the lock to the resource.

To use exclusive lock check with `sequential` deployments or `runLatest`, follow these steps:

 1. Enable the exclusive lock check on the environment (or another protected resource).
 2. In the YAML file for the pipeline, specify a new property called `lockBehavior`. This can be specified for the whole pipeline or for a given stage:

Set on a stage:

```yaml
stages:
- stage: A
  lockBehavior: sequential
  jobs:
  - job: Job
    steps:
    - script: Hey!
```
Set on the pipeline:

```yaml
lockBehavior: runLatest
stages:
- stage: A
  jobs:
  - job: Job
    steps:
    - script: Hey!
```

:::moniker-end


## Examples

This example runs three stages, one after another.
The middle stage runs two jobs in parallel.

```yaml
stages:
- stage: Build
  jobs:
  - job: BuildJob
    steps:
    - script: echo Building!
- stage: Test
  jobs:
  - job: TestOnWindows
    steps:
    - script: echo Testing on Windows!
  - job: TestOnLinux
    steps:
    - script: echo Testing on Linux!
- stage: Deploy
  jobs:
  - job: Deploy
    steps:
    - script: echo Deploying the code!
```

This example runs two stages in parallel.
For brevity, the jobs and steps are omitted.

```yaml
stages:
- stage: BuildWin
  displayName: Build for Windows
- stage: BuildMac
  displayName: Build for Mac
  dependsOn: [] # by specifying an empty array, this stage doesn't depend on the stage before it
```


## See also

Learn more about [stages](/azure/devops/pipelines/process/stages), [conditions](/azure/devops/pipelines/process/conditions), and [variables](/azure/devops/pipelines/process/variables).



