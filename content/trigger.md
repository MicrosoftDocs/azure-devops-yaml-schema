---
title: trigger definition
description: Continuous integration (push) trigger.
ms.date: 10/19/2023
monikerRange: ">=azure-pipelines-2019"
---

# trigger definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
A push trigger specifies which branches cause a continuous integration build to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [pipeline](pipeline.md), [resources.repositories.repository](resources-repositories-repository.md)

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

Definitions that reference this definition: [pipeline](pipeline.md)

:::moniker-end
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range=">=azure-pipelines-2019.1"

| Implementation | Description |
|---|---|
| [trigger: none](#triggerstring) | Disable CI triggers. |
| [trigger: string list](#triggerstringlist) | List of branches that trigger a run. |
| [trigger: batch, branches, paths, tags](#triggerobjectproperties) | Full syntax for complete control. |

:::moniker-end

:::moniker range="=azure-pipelines-2019"

| Implementation | Description |
|---|---|
| [trigger: none](#triggerstring) | Disable CI triggers. |
| [trigger: string list](#triggerstringlist) | List of branches that trigger a run. |
| [trigger: batch, branches, paths](#triggerobjectproperties) | Full syntax for complete control. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
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
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="trigger: string"::: -->
<a name="triggerstring"></a>
<!-- :::stringAnyOf::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::implementation-signature::: -->
## trigger: none
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Disable CI triggers.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
trigger: none # Disable CI triggers.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-string-item::: -->
**`trigger`** string. Allowed values: none.<br>
<!-- :::editable-content name="description"::: -->
Disable CI triggers.
<!-- :::editable-content-end::: -->
<!-- :::implementation-string-item-end::: -->

:::moniker-end
<!-- :::stringAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

```yaml
trigger: none # will disable CI builds entirely
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="trigger: string list"::: -->
<a name="triggerstringlist"></a>
<!-- :::arrayAnyOf::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::implementation-signature::: -->
## trigger: string list
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
List of branches that trigger a run.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
trigger: [ string ] # List of branches that trigger a run.
```
<!-- :::implementation-syntax-end::: -->

### List types

<!-- :::implementation-list-types::: -->
| Type | Description |
|---|---|
| string | List of branches that trigger a run. |
<!-- :::implementation-list-types-end::: -->

:::moniker-end
<!-- :::arrayAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

```yaml
trigger:
- main
- develop
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="trigger: object properties"::: -->
<a name="triggerobjectproperties"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::implementation-signature::: -->
## trigger: batch, branches, paths, tags
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Use the full syntax control for full control over the CI trigger.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
trigger:
  batch: boolean # Whether to batch changes per branch.
  branches: # Branch names to include or exclude for triggering a run.
    include: [ string ] # List of items to include.
    exclude: [ string ] # List of items to exclude.
  paths: # File paths to include or exclude for triggering a run.
    include: [ string ] # List of items to include.
    exclude: [ string ] # List of items to exclude.
  tags: # Tag names to include or exclude for triggering a run.
    include: [ string ] # List of items to include.
    exclude: [ string ] # List of items to exclude.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="batch"::: -->
**`batch`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Whether to batch changes per branch.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="branches"::: -->
**`branches`** [includeExcludeFilters](include-exclude-filters.md).<br><!-- :::editable-content name="propDescription"::: -->
Branch names to include or exclude for triggering a run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="paths"::: -->
**`paths`** [includeExcludeFilters](include-exclude-filters.md).<br><!-- :::editable-content name="propDescription"::: -->
File paths to include or exclude for triggering a run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
**`tags`** [includeExcludeFilters](include-exclude-filters.md).<br><!-- :::editable-content name="propDescription"::: -->
Tag names to include or exclude for triggering a run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::implementation-signature::: -->
## trigger: batch, branches, paths
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Use the full syntax control for full control over the CI trigger.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
trigger:
  batch: boolean # Whether to batch changes per branch.
  branches: # Branch names to include or exclude for triggering a run.
    include: [ string ] # List of items to include.
    exclude: [ string ] # List of items to exclude.
  paths: # File paths to include or exclude for triggering a run.
    include: [ string ] # List of items to include.
    exclude: [ string ] # List of items to exclude.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="batch"::: -->
**`batch`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Whether to batch changes per branch.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="branches"::: -->
**`branches`** [includeExcludeFilters](include-exclude-filters.md).<br><!-- :::editable-content name="propDescription"::: -->
Branch names to include or exclude for triggering a run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="paths"::: -->
**`paths`** [includeExcludeFilters](include-exclude-filters.md).<br><!-- :::editable-content name="propDescription"::: -->
File paths to include or exclude for triggering a run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end
<!-- :::objectAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
### Remarks

If you have many team members uploading changes often, you may want to reduce the number of runs you start. If you set `batch` to `true`, when a pipeline is running, the system waits until the run is completed, then starts another run with all changes that have not yet been built. By default, `batch` is `false`.

::: moniker range=">= azure-pipelines-2020"

> [!NOTE]
> `batch` is not supported in repository resource triggers.

::: moniker-end

For more information, see [Triggers - CI triggers](/azure/devops/pipelines/build/triggers#ci-triggers) and choose your repository type.

```yaml
# specific branch build with batching
trigger:
  batch: true
  branches:
    include:
    - main
```
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
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
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

Learn more about [triggers](/azure/devops/pipelines/build/triggers#ci-triggers) and how to specify them.
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
