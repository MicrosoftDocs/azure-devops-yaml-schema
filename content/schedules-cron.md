---
title: schedules.cron definition
description: schedules.cron definition reference.
ms.date: 08/08/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"
---

# schedules.cron definition


A scheduled trigger specifies a schedule on which branches are built.


:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="schedule{cron}" version="azure-pipelines-2020"::: -->

```yaml
schedules:
- cron: string # Required as first property. Cron syntax defining a schedule in UTC time.. 
  displayName: string # Optional friendly name given to a specific schedule.. 
  branches:  # Branch names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  batch: boolean # Whether to run the pipeline if the previously scheduled run is in-progress; the default is false..  (false,n,no,off,on,true,y,yes)
  always: boolean # Whether to always run the pipeline or only if there have been source code changes since the last successful scheduled run; the default is false..  (false,n,no,off,on,true,y,yes)
```


Properties that use this definition: [schedules](schedules.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `cron`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Cron syntax defining a schedule in UTC time. 
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
<!-- :::api-desc type="property"::: -->Optional friendly name given to a specific schedule. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `branches`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
include/exclude string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Branch names to include or exclude for triggering a run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `batch`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Whether to run the pipeline if the previously scheduled run is in-progress; the default is false. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `always`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Whether to always run the pipeline or only if there have been source code changes since the last successful scheduled run; the default is false. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="schedule{cron}" version="azure-pipelines-2020.1"::: -->

```yaml
schedules:
- cron: string # Required as first property. Cron syntax defining a schedule in UTC time.. 
  displayName: string # Optional friendly name given to a specific schedule.. 
  branches:  # Branch names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  batch: boolean # Whether to run the pipeline if the previously scheduled run is in-progress; the default is false..  (false,n,no,off,on,true,y,yes)
  always: boolean # Whether to always run the pipeline or only if there have been source code changes since the last successful scheduled run; the default is false..  (false,n,no,off,on,true,y,yes)
```


Properties that use this definition: [schedules](schedules.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `cron`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Cron syntax defining a schedule in UTC time. 
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
<!-- :::api-desc type="property"::: -->Optional friendly name given to a specific schedule. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `branches`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
include/exclude string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Branch names to include or exclude for triggering a run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `batch`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Whether to run the pipeline if the previously scheduled run is in-progress; the default is false. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `always`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Whether to always run the pipeline or only if there have been source code changes since the last successful scheduled run; the default is false. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="schedule{cron}" version="azure-pipelines-2022"::: -->

```yaml
schedules:
- cron: string # Required as first property. Cron syntax defining a schedule in UTC time.. 
  displayName: string # Optional friendly name given to a specific schedule.. 
  branches:  # Branch names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  batch: boolean # Whether to run the pipeline if the previously scheduled run is in-progress; the default is false..  (false,n,no,off,on,true,y,yes)
  always: boolean # Whether to always run the pipeline or only if there have been source code changes since the last successful scheduled run; the default is false..  (false,n,no,off,on,true,y,yes)
```


Properties that use this definition: [schedules](schedules.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `cron`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Cron syntax defining a schedule in UTC time. 
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
<!-- :::api-desc type="property"::: -->Optional friendly name given to a specific schedule. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `branches`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
include/exclude string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Branch names to include or exclude for triggering a run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `batch`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Whether to run the pipeline if the previously scheduled run is in-progress; the default is false. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `always`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Whether to always run the pipeline or only if there have been source code changes since the last successful scheduled run; the default is false. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="schedule{cron}" version="azure-pipelines"::: -->

```yaml
schedules:
- cron: string # Required as first property. Cron syntax defining a schedule in UTC time.. 
  displayName: string # Optional friendly name given to a specific schedule.. 
  branches:  # Branch names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  batch: boolean # Whether to run the pipeline if the previously scheduled run is in-progress; the default is false..  (false,n,no,off,on,true,y,yes)
  always: boolean # Whether to always run the pipeline or only if there have been source code changes since the last successful scheduled run; the default is false..  (false,n,no,off,on,true,y,yes)
```


Properties that use this definition: [schedules](schedules.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `cron`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Cron syntax defining a schedule in UTC time. 
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
<!-- :::api-desc type="property"::: -->Optional friendly name given to a specific schedule. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `branches`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
include/exclude string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Branch names to include or exclude for triggering a run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `batch`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Whether to run the pipeline if the previously scheduled run is in-progress; the default is false. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `always`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Whether to always run the pipeline or only if there have been source code changes since the last successful scheduled run; the default is false. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

If you specify no scheduled trigger, no scheduled builds occur.

> [!NOTE]
> If you specify an `exclude` clause without an `include` clause for `branches`, it is equivalent to specifying `*` in the `include` clause.


## Examples

```yaml
schedules:
- cron: "0 0 * * *"
  displayName: Daily midnight build
  branches:
    include:
    - main
    - releases/*
    exclude:
    - releases/ancient/*
- cron: "0 12 * * 0"
  displayName: Weekly Sunday build
  branches:
    include:
    - releases/*
  always: true
```

In the preceding example, two schedules are defined.

The first schedule, **Daily midnight build**, runs a pipeline at midnight every day only if the code has changed since the last successful scheduled run.
It runs the pipeline for `main` and all `releases/*` branches, except for those branches under `releases/ancient/*`.

The second schedule, **Weekly Sunday build**, runs a pipeline at noon on Sundays for all `releases/*` branches.
It does so regardless of whether the code has changed since the last run.


## See also

- Learn more about [scheduled triggers](/azure/devops/pipelines/process/scheduled-triggers).
- Learn more about [triggers](/azure/devops/pipelines/build/triggers#pr-triggers) in general and how to specify them.



