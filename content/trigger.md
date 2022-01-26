---
title: trigger definition
description: trigger definition reference.
ms.date: 01/26/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# trigger definition



A push trigger specifies which branches cause a continuous integration build to run.


:::moniker range="= azure-pipelines-2019"

Properties that use this definition: [pipeline.trigger](pipeline.md)

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

Properties that use this definition: [pipeline.trigger](pipeline.md)

:::moniker-end

:::moniker range="= azure-pipelines-2020"

Properties that use this definition: [pipeline.trigger](pipeline.md), [resources.repositories.repository.trigger](resources-repositories-repository.md)

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

Properties that use this definition: [pipeline.trigger](pipeline.md), [resources.repositories.repository.trigger](resources-repositories-repository.md)

:::moniker-end

:::moniker range="= azure-pipelines"

Properties that use this definition: [pipeline.trigger](pipeline.md), [resources.repositories.repository.trigger](resources-repositories-repository.md)

:::moniker-end

## Overloads

:::moniker range="= azure-pipelines-2019" 

| Overload | Description |
|----------|-------------|
| [trigger: none](#trigger-none) | Disable CI triggers. |
| [trigger: branchFilter list](#trigger-branchfilter-list) | List of branches that trigger a run. |
| [trigger: batch, branches, paths](#trigger-batch-branches-paths) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines-2019.1" 

| Overload | Description |
|----------|-------------|
| [trigger: none](#trigger-none) | Disable CI triggers. |
| [trigger: branchFilter list](#trigger-branchfilter-list) | List of branches that trigger a run. |
| [trigger: batch, branches, paths, tags](#trigger-batch-branches-paths-tags) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines-2020" 

| Overload | Description |
|----------|-------------|
| [trigger: none](#trigger-none) | Disable CI triggers. |
| [trigger: branchFilter list](#trigger-branchfilter-list) | List of branches that trigger a run. |
| [trigger: batch, branches, paths, tags](#trigger-batch-branches-paths-tags) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines-2020.1" 

| Overload | Description |
|----------|-------------|
| [trigger: none](#trigger-none) | Disable CI triggers. |
| [trigger: branchFilter list](#trigger-branchfilter-list) | List of branches that trigger a run. |
| [trigger: batch, branches, paths, tags](#trigger-batch-branches-paths-tags) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [trigger: none](#trigger-none) | Disable CI triggers. |
| [trigger: branchFilter list](#trigger-branchfilter-list) | List of branches that trigger a run. |
| [trigger: batch, branches, paths, tags](#trigger-batch-branches-paths-tags) | Full syntax for complete control. |

:::moniker-end


## Remarks

If you specify no push trigger, pushes to any branch trigger a build.

There are three distinct syntax options for the `trigger` keyword: a list of branches to include, a way to disable CI triggers, and the full syntax for complete control. 

::: moniker range=">= azure-pipelines-2020"

If you specify an `exclude` clause without an `include` clause for `branches`, `tags`, or `paths`, it is equivalent to specifying `*` in the `include` clause.

::: moniker-end

::: moniker range="<= azure-pipelines-2019.1"

> [!IMPORTANT]
> When you specify a trigger, only branches that you explicitly configure for inclusion trigger a pipeline.
> Inclusions are processed first, and then exclusions are removed from that list.
> If you specify an exclusion but no inclusions, nothing triggers.

::: moniker-end


:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## trigger: none

:::moniker-end

Disablement syntax.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="trigger(none)" version="azure-pipelines-2019"::: -->


```yaml
trigger: none # List of branches that trigger a run.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of branches that trigger a run. Acceptable values: none
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="trigger(none)" version="azure-pipelines-2019.1"::: -->


```yaml
trigger: none # List of branches that trigger a run.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of branches that trigger a run. Acceptable values: none
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="trigger(none)" version="azure-pipelines-2020"::: -->


```yaml
trigger: none # List of branches that trigger a run.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of branches that trigger a run. Acceptable values: none
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="trigger(none)" version="azure-pipelines-2020.1"::: -->


```yaml
trigger: none # List of branches that trigger a run.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of branches that trigger a run. Acceptable values: none
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="trigger(none)" version="azure-pipelines"::: -->


```yaml
trigger: none # List of branches that trigger a run.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of branches that trigger a run. Acceptable values: none
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
trigger: none # will disable CI builds entirely
```
:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## trigger: branchFilter list

:::moniker-end

List syntax specifies a list of branches for which a push triggers a run.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="trigger[branchFilter]" version="azure-pipelines-2019"::: -->


```yaml
trigger: [ branchFilter ] # List of branches that trigger a run. [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of branches that trigger a run. Acceptable values: [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="trigger[branchFilter]" version="azure-pipelines-2019.1"::: -->


```yaml
trigger: [ branchFilter ] # List of branches that trigger a run. [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of branches that trigger a run. Acceptable values: [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="trigger[branchFilter]" version="azure-pipelines-2020"::: -->


```yaml
trigger: [ branchFilter ] # List of branches that trigger a run. [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of branches that trigger a run. Acceptable values: [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="trigger[branchFilter]" version="azure-pipelines-2020.1"::: -->


```yaml
trigger: [ branchFilter ] # List of branches that trigger a run. [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of branches that trigger a run. Acceptable values: [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="trigger[branchFilter]" version="azure-pipelines"::: -->


```yaml
trigger: [ branchFilter ] # List of branches that trigger a run. [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of branches that trigger a run. Acceptable values: [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
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
trigger:
- main
- develop
```
:::moniker range="= azure-pipelines-2019"

## trigger: batch, branches, paths

:::moniker-end

Full syntax for complete control.

:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="trigger{batch,branches,paths}" version="azure-pipelines-2019"::: -->


```yaml
trigger:
  batch: boolean # Whether to batch changes per branch.  (false,n,no,off,on,true,y,yes)
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
   `batch`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Whether to batch changes per branch. 
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

```yaml
trigger:
- main
- develop
```
:::moniker range="= azure-pipelines || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## trigger: batch, branches, paths, tags

:::moniker-end

Use the full sytax control for full control over the CI trigger.


:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="trigger{batch,branches,paths,tags}" version="azure-pipelines-2019.1"::: -->


```yaml
trigger:
  batch: boolean # Whether to batch changes per branch.  (false,n,no,off,on,true,y,yes)
  branches:  # Branch names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  paths:  # File paths to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  tags:  # Tag names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
```

### Properties


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
<!-- :::api-desc type="property"::: -->Whether to batch changes per branch. 
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
   `tags`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
include/exclude string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Tag names to include or exclude for triggering a run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="trigger{batch,branches,paths,tags}" version="azure-pipelines-2020"::: -->


```yaml
trigger:
  batch: boolean # Whether to batch changes per branch.  (false,n,no,off,on,true,y,yes)
  branches:  # Branch names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  paths:  # File paths to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  tags:  # Tag names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
```

### Properties


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
<!-- :::api-desc type="property"::: -->Whether to batch changes per branch. 
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
   `tags`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
include/exclude string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Tag names to include or exclude for triggering a run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="trigger{batch,branches,paths,tags}" version="azure-pipelines-2020.1"::: -->


```yaml
trigger:
  batch: boolean # Whether to batch changes per branch.  (false,n,no,off,on,true,y,yes)
  branches:  # Branch names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  paths:  # File paths to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  tags:  # Tag names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
```

### Properties


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
<!-- :::api-desc type="property"::: -->Whether to batch changes per branch. 
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
   `tags`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
include/exclude string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Tag names to include or exclude for triggering a run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="trigger{batch,branches,paths,tags}" version="azure-pipelines"::: -->


```yaml
trigger:
  batch: boolean # Whether to batch changes per branch.  (false,n,no,off,on,true,y,yes)
  branches:  # Branch names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  paths:  # File paths to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
  tags:  # Tag names to include or exclude for triggering a run.
    include: [ branchFilter ] # List of items to include. 
    exclude: [ branchFilter ] # List of items to exclude. 
```

### Properties


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
<!-- :::api-desc type="property"::: -->Whether to batch changes per branch. 
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
   `tags`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
include/exclude string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Tag names to include or exclude for triggering a run. 
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
trigger:
  batch: true
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

Learn more about [triggers](/azure/devops/pipelines/build/triggers#ci-triggers) and how to specify them.
