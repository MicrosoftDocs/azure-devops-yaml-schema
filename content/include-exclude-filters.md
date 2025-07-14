---
title: includeExcludeFilters definition
description: Lists of items to include or exclude.
ms.date: 07/14/2025
monikerRange: "<=azure-pipelines"
author: steved0x
ms.author: sdanie
---

# includeExcludeFilters definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Lists of items to include or exclude for trigger events.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
includeExcludeFilters:
  include: [ string ] # List of items to include.
  exclude: [ string ] # List of items to exclude.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information and examples for using this supporting type, see the following **Definitions that reference this definition** articles.

Definitions that reference this definition: [trigger](trigger.md), [pr](pr.md), [schedules.cron](schedules-cron.md)

:::moniker-end

<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="include"::: -->
:::moniker range="<=azure-pipelines"

**`include`** string list.<br><!-- :::editable-content name="propDescription"::: -->
List of items to include.

```yml
include:
- item1
- item2
```

You can also specify the `include` list on a single line using the following format.

```yml
include: [ item1, item2 ]
```

For example, to specify a list of branches to match in a `pr` trigger, use the following syntax.

```yml
pr:
  branches:
    include:
    - main
    - features/*
```

You can also specify the `includes` list on a single line using the following format.

```yml
pr:
  branches:
    include: [ main, features/* ]
```
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exclude"::: -->
:::moniker range="<=azure-pipelines"

**`exclude`** string list.<br><!-- :::editable-content name="propDescription"::: -->
List of items to exclude.

```yml
exclude:
- item1
- item2
```

You can also specify the `exclude` list on a single line using the following format.

```yml
exclude: [ item1, item2 ]
```
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

The `includeExcludeFilters` definition is a supporting definition and is not intended for use directly in a pipeline; instead it is used to provide the structure of different properties in the definitions listed at the top of the article.

For example, `includeExcludeFilters` is the type that defines how the `pr.branches` section is structured. See the [pr implementations](pr.md#implementations) **Full syntax for complete control** section for the `pr` properties that use `includeExcludeFilters`.

```yaml
pr:
  branches: # Branch names to include or exclude for triggering a run.
    include: [ string ] # List of items to include.
    exclude: [ string ] # List of items to exclude.
```
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->