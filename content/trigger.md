---
title: trigger definition
description: trigger definition reference.
ms.date: 09/02/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"
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

:::moniker range="= azure-pipelines-2022"

Properties that use this definition: [pipeline.trigger](pipeline.md), [resources.repositories.repository.trigger](resources-repositories-repository.md)

:::moniker-end

:::moniker range="= azure-pipelines"

Properties that use this definition: [pipeline.trigger](pipeline.md), [resources.repositories.repository.trigger](resources-repositories-repository.md)

:::moniker-end

## Overloads

:::moniker range="= azure-pipelines-2019" 

| Overload | Description |
|----------|-------------|
| [trigger: none](#trigger-none) |  |
| [trigger: branchFilter list](#trigger-branchfilter-list) | List of branches that trigger a run. |
| [trigger: batch, branches, paths](#trigger-batch-branches-paths) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines-2019.1" 

| Overload | Description |
|----------|-------------|
| [trigger: none](#trigger-none) |  |
| [trigger: branchFilter list](#trigger-branchfilter-list) | List of branches that trigger a run. |
| [trigger: batch, branches, paths, tags](#trigger-batch-branches-paths-tags) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines-2020" 

| Overload | Description |
|----------|-------------|
| [trigger: none](#trigger-none) |  |
| [trigger: branchFilter list](#trigger-branchfilter-list) | List of branches that trigger a run. |
| [trigger: batch, branches, paths, tags](#trigger-batch-branches-paths-tags) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines-2020.1" 

| Overload | Description |
|----------|-------------|
| [trigger: none](#trigger-none) |  |
| [trigger: branchFilter list](#trigger-branchfilter-list) | List of branches that trigger a run. |
| [trigger: batch, branches, paths, tags](#trigger-batch-branches-paths-tags) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines-2022" 

| Overload | Description |
|----------|-------------|
| [trigger: none](#trigger-none) |  |
| [trigger: branchFilter list](#trigger-branchfilter-list) | List of branches that trigger a run. |
| [trigger: batch, branches, paths, tags](#trigger-batch-branches-paths-tags) | Full syntax for complete control. |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [trigger: none](#trigger-none) |  |
| [trigger: branchFilter list](#trigger-branchfilter-list) | List of branches that trigger a run. |
| [trigger: batch, branches, paths, tags](#trigger-batch-branches-paths-tags) | Full syntax for complete control. |

:::moniker-end


## Remarks

For more information about using triggers with a specific repository type, see [Supported source repositories](/azure/devops/pipelines/repos).

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


:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"

## trigger: none

Disablement syntax.



:::moniker-end

:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="trigger(none)" version="azure-pipelines-2019"::: -->


```yaml
trigger: none # Disable CI triggers.
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
<!-- :::api-desc type="property"::: -->Disable CI triggers. Acceptable values: none
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
trigger: none # Disable CI triggers.
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
<!-- :::api-desc type="property"::: -->Disable CI triggers. Acceptable values: none
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
trigger: none # Disable CI triggers.
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
<!-- :::api-desc type="property"::: -->Disable CI triggers. Acceptable values: none
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
trigger: none # Disable CI triggers.
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
<!-- :::api-desc type="property"::: -->Disable CI triggers. Acceptable values: none
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="trigger(none)" version="azure-pipelines-2022"::: -->


```yaml
trigger: none # Disable CI triggers.
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
<!-- :::api-desc type="property"::: -->Disable CI triggers. Acceptable values: none
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
trigger: none # Disable CI triggers.
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
<!-- :::api-desc type="property"::: -->Disable CI triggers. Acceptable values: none
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
:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"

## trigger: branchFilter list

List syntax specifies a list of branches for which a push triggers a run.



:::moniker-end

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
<!-- :::api-desc type="property"::: -->Disable CI triggers. Acceptable values: [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
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
<!-- :::api-desc type="property"::: -->Disable CI triggers. Acceptable values: [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
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
<!-- :::api-desc type="property"::: -->Disable CI triggers. Acceptable values: [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
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
<!-- :::api-desc type="property"::: -->Disable CI triggers. Acceptable values: [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="trigger[branchFilter]" version="azure-pipelines-2022"::: -->


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
<!-- :::api-desc type="property"::: -->Disable CI triggers. Acceptable values: [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
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
<!-- :::api-desc type="property"::: -->Disable CI triggers. Acceptable values: [^\/~\^\: \[\]\\]+(\/[^\/~\^\: \[\]\\]+)*
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

Full syntax for complete control.


:::moniker-end

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


<!-- Examples -->

:::moniker range="= azure-pipelines || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"

## trigger: batch, branches, paths, tags

Use the full syntax control for full control over the CI trigger.



:::moniker-end

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

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="trigger{batch,branches,paths,tags}" version="azure-pipelines-2022"::: -->


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


### Remarks

If you have many team members uploading changes often, you may want to reduce the number of runs you start. If you set `batch` to `true`, when a pipeline is running, the system waits until the run is completed, then starts another run with all changes that have not yet been built. By default, `batch` is `false`.

::: moniker range=">= azure-pipelines-2020"

> [!NOTE]
> If you are using repository resource triggers, do not set the `batch` property on any of the repository CI triggers other than the `self` repository. `batch` is only supported for CI triggers defined on the `self` repository.

::: moniker-end

For more information, see [Triggers - CI triggers](/azure/devops/pipelines/build/triggers#ci-triggers) and choose your repository type.

```yaml
## specific branch build with batching
trigger:
  batch: true
  branches:
    include:
    - main
```


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
