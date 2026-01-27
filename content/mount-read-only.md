---
title: mountReadOnly definition
description: Volumes to mount read-only.
ms.date: 01/27/2026
monikerRange: "<=azure-pipelines"
author: steved0x
ms.author: sdanie
---

# mountReadOnly definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Volumes to mount read-only, the default is all false.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
mountReadOnly:
  work: boolean # Mount the work directory as readonly.
  externals: boolean # Mount the externals directory as readonly.
  tools: boolean # Mount the tools directory as readonly.
  tasks: boolean # Mount the tasks directory as readonly.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information and examples for using this supporting type, see the following **Definitions that reference this definition** articles.

Definitions that reference this definition: [jobs.job.container](jobs-job-container.md), [resources.containers.container](resources-containers-container.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<a name="work-property"></a>
<!-- :::item name="work"::: -->
:::moniker range="<=azure-pipelines"

**`work`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Mount the work directory as readonly.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="externals-property"></a>
<!-- :::item name="externals"::: -->
:::moniker range="<=azure-pipelines"

**`externals`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Mount the externals directory as readonly.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="tools-property"></a>
<!-- :::item name="tools"::: -->
:::moniker range="<=azure-pipelines"

**`tools`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Mount the tools directory as readonly.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="tasks-property"></a>
<!-- :::item name="tasks"::: -->
:::moniker range="<=azure-pipelines"

**`tasks`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Mount the tasks directory as readonly.
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