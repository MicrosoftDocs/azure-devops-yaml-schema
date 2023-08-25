---
title: includeExcludeStringFilters definition
description: Items to include or exclude.
ms.date: 08/25/2023
monikerRange: ">=azure-pipelines-2020"
---

# includeExcludeStringFilters definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Items to include or exclude.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information on using the definitions that this type supports, see the following definition links.

Definitions that reference this definition: [resources.containers.container.trigger](resources-containers-container-trigger.md)

:::moniker-end
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range=">=azure-pipelines-2020"

| Implementation | Description |
|---|---|
| [includeExcludeStringFilters: string list](#includeexcludestringfiltersstringlist) | List of items to include. |
| [includeExcludeStringFilters: include, exclude](#includeexcludestringfiltersobjectproperties) | Lists of items to include and exclude. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="includeExcludeStringFilters: string list"::: -->
<a name="includeexcludestringfiltersstringlist"></a>
<!-- :::arrayAnyOf::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## includeExcludeStringFilters: string list
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
List of items to include.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
includeExcludeStringFilters: [ string ] # List of items to include.
```
<!-- :::implementation-syntax-end::: -->

### List types

<!-- :::implementation-list-types::: -->
| Type | Description |
|---|---|
| string | List of items to include. |
<!-- :::implementation-list-types-end::: -->

:::moniker-end
<!-- :::arrayAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="includeExcludeStringFilters: object properties"::: -->
<a name="includeexcludestringfiltersobjectproperties"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## includeExcludeStringFilters: include, exclude
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Lists of items to include and exclude.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
includeExcludeStringFilters:
  include: [ string ]
  exclude: [ string ]
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="include"::: -->
**`include`** string list.<br><!-- :::editable-content name="propDescription"::: -->
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="exclude"::: -->
**`exclude`** string list.<br><!-- :::editable-content name="propDescription"::: -->
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
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
