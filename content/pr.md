---
title: pr definition
description: Pull request trigger.
ms.date: 12/21/2023
monikerRange: ">=azure-pipelines-2019"
---

# pr definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
A pull request trigger specifies which branches cause a pull request build to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2019"

Definitions that reference this definition: [pipeline](pipeline.md)

:::moniker-end
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range=">=azure-pipelines-2022"

| Implementation | Description |
|---|---|
| [pr: none](#prstring) | Disable pull request triggers. |
| [pr: string list](#prstringlist) | List of branches that trigger a run. |
| [pr: autoCancel, branches, paths, drafts](#probjectproperties) | Full syntax for complete control. |

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

| Implementation | Description |
|---|---|
| [pr: none](#prstring) | Disable pull request triggers. |
| [pr: string list](#prstringlist) | List of branches that trigger a run. |
| [pr: autoCancel, branches, paths](#probjectproperties) | Full syntax for complete control. |

:::moniker-end

:::moniker range="=azure-pipelines-2019"

| Implementation | Description |
|---|---|
| [pr: none](#prstring) | Disable pull request triggers. |
| [pr: string list](#prstringlist) | List of branches that trigger a run. |
| [pr: branches, paths](#probjectproperties) | Full syntax for complete control. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

If you specify no pull request trigger, pull requests to any branch trigger a build.


There are three distinct syntax options for the `pr` keyword: a list of branches to include, a way to disable PR triggers, and the full syntax for complete control.


::: moniker range="azure-pipelines"

> [!IMPORTANT]
> YAML PR triggers are supported only in GitHub and Bitbucket Cloud.
> If you use Azure Repos Git, you can configure a [branch policy for build validation](/azure/devops/repos/git/branch-policies#build-validation) to trigger your build pipeline for validation.

::: moniker-end

::: moniker range=">= azure-pipelines-2019 <= azure-pipelines-2019.1"

> [!IMPORTANT]
> YAML PR triggers are supported only in GitHub.
> If you use Azure Repos Git, you can configure a [branch policy for build validation](/azure/devops/repos/git/branch-policies#build-validation) to trigger your build pipeline for validation.

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
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="pr: string"::: -->
<a name="prstring"></a>
<!-- :::stringAnyOf::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::implementation-signature::: -->
## pr: none
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Disable pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
pr: none # Disable pull request triggers.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-string-item::: -->
**`pr`** string. Allowed values: none.<br>
<!-- :::editable-content name="description"::: -->
Disable pull request triggers.
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

Disablement syntax:

```yaml
pr: none # will disable PR builds (but not CI builds)
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="pr: string list"::: -->
<a name="prstringlist"></a>
<!-- :::arrayAnyOf::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::implementation-signature::: -->
## pr: string list
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
List of branches that trigger a run.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
pr: [ string ] # List of branches that trigger a run.
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

The list syntax specifies a list of branches which trigger a run when a pull request is raised or a push is made to the source branch of a raised pull request.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

List syntax:

```yaml
pr:
- main
- develop
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="pr: object properties"::: -->
<a name="probjectproperties"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::implementation-signature::: -->
## pr: autoCancel, branches, paths, drafts
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Use the full syntax when you need full control of the pull request trigger.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
pr:
  autoCancel: boolean # Whether to cancel running PR builds when a new commit lands in the branch. Default: true.
  branches: # Branch names to include or exclude for triggering a run.
    include: [ string ] # List of items to include.
    exclude: [ string ] # List of items to exclude.
  paths: # File paths to include or exclude for triggering a run.
    include: [ string ] # List of items to include.
    exclude: [ string ] # List of items to exclude.
  drafts: boolean # Whether to start a run when a draft PR is created. Default: true.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="autoCancel"::: -->
**`autoCancel`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Whether to cancel running PR builds when a new commit lands in the branch. Default: true.
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
<!-- :::item name="drafts"::: -->
**`drafts`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Whether to start a run when a draft PR is created. Default: true.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

<!-- :::implementation-signature::: -->
## pr: autoCancel, branches, paths
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Full syntax for complete control.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
pr:
  autoCancel: boolean # Whether to cancel running PR builds when a new commit lands in the branch. Default: true.
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

<!-- :::item name="autoCancel"::: -->
**`autoCancel`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Whether to cancel running PR builds when a new commit lands in the branch. Default: true.
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

:::moniker range="=azure-pipelines-2019"

<!-- :::implementation-signature::: -->
## pr: branches, paths
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Full syntax for complete control.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
pr:
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
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
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
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

Learn more about [pull request triggers](/azure/devops/pipelines/build/triggers#pr-triggers) and how to specify them.
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
