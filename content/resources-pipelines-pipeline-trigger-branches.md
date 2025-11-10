---
title: resources.pipelines.pipeline.trigger.branches definition
description: Branches to include or exclude for triggering a run using a pipeline resource.
ms.date: 11/10/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# resources.pipelines.pipeline.trigger.branches definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Branches to include or exclude for triggering a run using a pipeline resource.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [resources.pipelines.pipeline.trigger](resources-pipelines-pipeline-trigger.md)

:::moniker-end
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range="<=azure-pipelines"

| Implementation | Description |
|---|---|
| [branches: include, exclude](#branchesobjectproperties) | Lists of branches to include and exclude. |
| [branches: string list](#branchesstringlist) | List of branches to include. |

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
<!-- :::implementation-item name="branches: object properties"::: -->
<a name="branchesobjectproperties"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-server"

<!-- :::implementation-signature::: -->
## branches: include, exclude
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Lists of branches to include and exclude.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
branches:
  include: [ string ] # List of branches to include.
  exclude: [ string ] # List of branches to exclude.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="include"::: -->
**`include`** string list.<br><!-- :::editable-content name="propDescription"::: -->
List of branches to include.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="exclude"::: -->
**`exclude`** string list.<br><!-- :::editable-content name="propDescription"::: -->
List of branches to exclude.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

<!-- :::implementation-signature::: -->
## branches: include, exclude
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Lists of branches to include and exclude.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
branches:
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
<!-- :::implementation-item name="branches: string list"::: -->
<a name="branchesstringlist"></a>
<!-- :::arrayAnyOf::: -->
:::moniker range="<=azure-pipelines"

<!-- :::implementation-signature::: -->
## branches: string list
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
List of branches to include.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
branches: [ string ] # List of branches to include.
```
<!-- :::implementation-syntax-end::: -->

### List types

<!-- :::implementation-list-types::: -->
| Type | Description |
|---|---|
| string | List of branches to include. |
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
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
