---
title: trigger definition
description: Continuous integration (push) trigger.
ms.date: 01/23/2026
monikerRange: "<=azure-pipelines"
author: steved0x
ms.author: sdanie
---

# trigger definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
A push trigger specifies which branches cause a continuous integration build to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [pipeline](pipeline.md), [resources.repositories.repository](resources-repositories-repository.md)

:::moniker-end

<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range="<=azure-pipelines"

| Implementation | Description |
|---|---|
| [trigger: none](#triggerstring) | Disable CI triggers. |
| [trigger: string list](#triggerstringlist) | List of branches that trigger a run. |
| [trigger: batch, branches, paths, tags](#triggerobjectproperties) | Full syntax for complete control. |

:::moniker-end

<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

For more information about using triggers with a specific repository type, see [Supported source repositories](/azure/devops/pipelines/repos).

:::moniker range="<= azure-pipelines-2022.1"

If you specify no push trigger, pushes to any branch trigger a build.

:::moniker-end

:::moniker range="> azure-pipelines-2022.1"

YAML pipelines are configured by default with a CI trigger on all branches, unless the [Disable implied YAML CI trigger](/azure/devops/release-notes/2023/sprint-227-update#prevent-unintended-pipeline-runs) setting is enabled. The **Disable implied YAML CI trigger** setting can be configured at the organization level or at the project level. When the **Disable implied YAML CI trigger** setting is enabled, CI triggers for YAML pipelines are not enabled if the YAML pipeline doesn't have a `trigger` section. The default value for **Disable implied YAML CI trigger** is `false`.

:::moniker-end

There are three distinct syntax options for the `trigger` keyword: a list of branches to include, a way to disable CI triggers, and the full syntax for complete control.

::: moniker range="<=azure-pipelines"

If you specify an `exclude` clause without an `include` clause for `branches`, `tags`, or `paths`, it is equivalent to specifying `*` in the `include` clause.

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
:::moniker range="<=azure-pipelines"

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
:::moniker range="<=azure-pipelines"

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
### Remarks

Pushing a commit to branches specified in the list trigger a run. In addition to specifying branch names in the `branches` lists, you can also configure triggers when a tag is pushed by using the following format:

```yaml
trigger:
- refs/tags/{tagname}
```

For more information on tags, choose your repository type in [Supported repositories](/azure/devops/pipelines/repos/), and go to the CI triggers section.
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
:::moniker range="<=azure-pipelines"

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

<!-- :::objectAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
### Remarks

If you have many team members uploading changes often, you may want to reduce the number of runs you start. If you set `batch` to `true`, when a pipeline is running, the system waits until the run is completed, then starts another run with all changes that have not yet been built. By default, `batch` is `false`.

When specifying a branch, tag, or path, you may use an exact name or a wildcard. For more information, see [wildcards](/azure/devops/pipelines/repos/github#wildcards).

::: moniker range="<=azure-pipelines"

> [!IMPORTANT]
> `batch` is not supported in [repository resource](./resources-repositories-repository.md) triggers.

::: moniker-end

For more information, see [Triggers - CI triggers](/azure/devops/pipelines/build/triggers#ci-triggers) and choose your repository type.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

```yaml
# Build every branch except for main
trigger:
  branches:
    include:
    - '*' # Must enclose in '' since * is a reserved YAML character
    exclude:
    - main
```

```yaml
# specific branch build with batching
trigger:
  batch: true
  branches:
    include:
    - main
```

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
