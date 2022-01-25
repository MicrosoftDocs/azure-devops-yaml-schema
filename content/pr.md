---
title: pr definition
description: pr definition reference.
ms.date: 01/25/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# pr definition



A pull request trigger specifies which branches cause a pull request build to run.


:::moniker range="= azure-pipelines-2019"

Properties that use this definition: [pipeline.pr](pipeline.md)

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

Properties that use this definition: [pipeline.pr](pipeline.md)

:::moniker-end

:::moniker range="= azure-pipelines-2020"

Properties that use this definition: [pipeline.pr](pipeline.md)

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

Properties that use this definition: [pipeline.pr](pipeline.md)

:::moniker-end

:::moniker range="= azure-pipelines"

Properties that use this definition: [pipeline.pr](pipeline.md)

:::moniker-end

## Overloads

:::moniker range="= azure-pipelines-2019" 

| Overload | Description |
|----------|-------------|
| [pr: none](#pr-none) | Disable pull request triggers. |
| [pr: branchFilter list](#pr-branchfilter-list) | List of branches that trigger a run. |
| [pr: branches, paths](#pr-branches-paths) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines-2019.1" 

| Overload | Description |
|----------|-------------|
| [pr: none](#pr-none) | Disable pull request triggers. |
| [pr: branchFilter list](#pr-branchfilter-list) | List of branches that trigger a run. |
| [pr: autoCancel, branches, paths](#pr-autocancel-branches-paths) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines-2020" 

| Overload | Description |
|----------|-------------|
| [pr: none](#pr-none) | Disable pull request triggers. |
| [pr: branchFilter list](#pr-branchfilter-list) | List of branches that trigger a run. |
| [pr: autoCancel, branches, paths](#pr-autocancel-branches-paths) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines-2020.1" 

| Overload | Description |
|----------|-------------|
| [pr: none](#pr-none) | Disable pull request triggers. |
| [pr: branchFilter list](#pr-branchfilter-list) | List of branches that trigger a run. |
| [pr: autoCancel, branches, paths](#pr-autocancel-branches-paths) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [pr: none](#pr-none) | Disable pull request triggers. |
| [pr: branchFilter list](#pr-branchfilter-list) | List of branches that trigger a run. |
| [pr: autoCancel, branches, paths, drafts](#pr-autocancel-branches-paths-drafts) | Full syntax for complete control. |

:::moniker-end


## Remarks

If you specify no pull request trigger, pull requests to any branch trigger a build.


There are three distinct syntax options for the `pr` keyword: a list of branches to include, a way to disable PR triggers, and the full syntax for complete control.


::: moniker range="azure-pipelines"

> [!IMPORTANT]
> YAML PR triggers are supported only in GitHub and Bitbucket Cloud.
> If you use Azure Repos Git, you can configure a [branch policy for build validation](/azure/devops/repos/git/branch-policies.md#build-validation) to trigger your build pipeline for validation.

::: moniker-end

::: moniker range=">= azure-pipelines-2019 <= azure-pipelines-2019.1"

> [!IMPORTANT]
> YAML PR triggers are supported only in GitHub.
> If you use Azure Repos Git, you can configure a [branch policy for build validation](/azure/devops/repos/git/branch-policies.md#build-validation) to trigger your build pipeline for validation.

::: moniker-end

::: moniker range=">= azure-pipelines-2020"

If you specify an `exclude` clause without an `include` clause for `branches` or `paths`, it is equivalent to specifying `*` in the `include` clause.

::: moniker-end

::: moniker range="<= azure-pipelines-2019.1"

> [!IMPORTANT]
> When you specify a pull request trigger, only branches that you explicitly configure for inclusion trigger a pipeline.
> Inclusions are processed first, and then exclusions are removed from that list.
> If you specify an exclusion but no inclusions, nothing triggers.

::: moniker-end







:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## pr: none

:::moniker-end

Disable pull request triggers.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="pr(none)" version="azure-pipelines-2019"::: -->


```yaml
pr: none # 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pr`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Acceptable values: none
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="pr(none)" version="azure-pipelines-2019.1"::: -->


```yaml
pr: none # 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pr`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Acceptable values: none
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="pr(none)" version="azure-pipelines-2020"::: -->


```yaml
pr: none # 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pr`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Acceptable values: none
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="pr(none)" version="azure-pipelines-2020.1"::: -->


```yaml
pr: none # 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pr`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Acceptable values: none
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="pr(none)" version="azure-pipelines"::: -->


```yaml
pr: none # 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pr`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Acceptable values: none
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


### Examples

Disablement syntax:

```yaml
pr: none # will disable PR builds (but not CI builds)
```

:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## pr: branchFilter list

:::moniker-end

The list syntax specifies a list of branches which trigger a run when a pull request is raised or a push is made to the source branch of a raised pull request.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="pr[branchFilter]" version="azure-pipelines-2019"::: -->


```yaml
pr: [ branchFilter ] # List of branches that trigger a run. [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="pr[branchFilter]" version="azure-pipelines-2019.1"::: -->


```yaml
pr: [ branchFilter ] # List of branches that trigger a run. [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="pr[branchFilter]" version="azure-pipelines-2020"::: -->


```yaml
pr: [ branchFilter ] # List of branches that trigger a run. [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="pr[branchFilter]" version="azure-pipelines-2020.1"::: -->


```yaml
pr: [ branchFilter ] # List of branches that trigger a run. [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="pr[branchFilter]" version="azure-pipelines"::: -->


```yaml
pr: [ branchFilter ] # List of branches that trigger a run. [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


### Examples

List syntax:

```yaml
pr:
- main
- develop
```
:::moniker range="= azure-pipelines-2019"

## pr: branches, paths

:::moniker-end

Full syntax for complete control.

:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="pr{branches,paths}" version="azure-pipelines-2019"::: -->


```yaml
pr:
  branches:  # Branch names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  paths:  # File paths to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
```

### Properties


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
   `paths`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
include/exclude string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->File paths to include or exclude for triggering a run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


### Examples

List syntax:

```yaml
pr:
- main
- develop
```
:::moniker range="= azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## pr: autoCancel, branches, paths

:::moniker-end

Full syntax for complete control.

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="pr{autoCancel,branches,paths}" version="azure-pipelines-2019.1"::: -->


```yaml
pr:
  autoCancel: boolean # Whether to cancel running PR builds when a new commit lands in the branch.  (false,n,no,off,on,true,y,yes)
  branches:  # Branch names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  paths:  # File paths to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `autoCancel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Whether to cancel running PR builds when a new commit lands in the branch. 
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
   `paths`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
include/exclude string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->File paths to include or exclude for triggering a run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="pr{autoCancel,branches,paths}" version="azure-pipelines-2020"::: -->


```yaml
pr:
  autoCancel: boolean # Whether to cancel running PR builds when a new commit lands in the branch.  (false,n,no,off,on,true,y,yes)
  branches:  # Branch names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  paths:  # File paths to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `autoCancel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Whether to cancel running PR builds when a new commit lands in the branch. 
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
   `paths`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
include/exclude string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->File paths to include or exclude for triggering a run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="pr{autoCancel,branches,paths}" version="azure-pipelines-2020.1"::: -->


```yaml
pr:
  autoCancel: boolean # Whether to cancel running PR builds when a new commit lands in the branch.  (false,n,no,off,on,true,y,yes)
  branches:  # Branch names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  paths:  # File paths to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `autoCancel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Whether to cancel running PR builds when a new commit lands in the branch. 
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
   `paths`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
include/exclude string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->File paths to include or exclude for triggering a run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


### Examples

List syntax:

```yaml
pr:
- main
- develop
```
:::moniker range="= azure-pipelines"

## pr: autoCancel, branches, paths, drafts

:::moniker-end

Use the full syntax when you need full control of the pull request trigger.


:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="pr{autoCancel,branches,paths,drafts}" version="azure-pipelines"::: -->


```yaml
pr:
  autoCancel: boolean # Whether to cancel running PR builds when a new commit lands in the branch.  (false,n,no,off,on,true,y,yes)
  branches:  # Branch names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  paths:  # File paths to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  drafts: boolean # Whether to start a run when a draft PR is created.  (false,n,no,off,on,true,y,yes)
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `autoCancel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Whether to cancel running PR builds when a new commit lands in the branch. 
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
   `paths`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
include/exclude string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->File paths to include or exclude for triggering a run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `drafts`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Whether to start a run when a draft PR is created. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


### Examples
Full syntax:

```yaml
pr:
  branches:
    include:
    - features/*
    exclude:
    - features/experimental/*
  paths:
    exclude:
    - README.md
```

## See also

Learn more about [pull request triggers](/azure/devops/pipelines/build/triggers#pr-triggers) and how to specify them.

