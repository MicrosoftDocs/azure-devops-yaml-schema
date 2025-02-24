---
title: includeExcludeFilters definition
description: Lists of items to include or exclude.
ms.date: 02/24/2025
monikerRange: "<=azure-pipelines"
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
:::moniker range=">=azure-pipelines-2020"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information on using the definitions that this type supports, see the following definition links.

Definitions that reference this definition: [trigger](trigger.md), [pr](pr.md), [schedules.cron](schedules-cron.md)

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information on using the definitions that this type supports, see the following definition links.

Definitions that reference this definition: [trigger](trigger.md), [pr](pr.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="include"::: -->
:::moniker range="<=azure-pipelines"

**`include`** string list.<br><!-- :::editable-content name="propDescription"::: -->
List of items to include.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="exclude"::: -->
:::moniker range="<=azure-pipelines"

**`exclude`** string list.<br><!-- :::editable-content name="propDescription"::: -->
List of items to exclude.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
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