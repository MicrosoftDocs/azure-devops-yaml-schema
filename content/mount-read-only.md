---
title: mountReadOnly definition
description: Volumes to mount read-only.
ms.date: 10/19/2023
monikerRange: ">=azure-pipelines-2020.1"
---

# mountReadOnly definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020.1"

<!-- :::editable-content name="description"::: -->
Volumes to mount read-only, the default is all false.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020.1"

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
:::moniker range=">=azure-pipelines-2020.1"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information on using the definitions that this type supports, see the following definition links.

Definitions that reference this definition: [jobs.job.container](jobs-job-container.md), [resources.containers.container](resources-containers-container.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="work"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`work`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Mount the work directory as readonly.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="externals"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`externals`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Mount the externals directory as readonly.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tools"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`tools`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Mount the tools directory as readonly.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tasks"::: -->
:::moniker range=">=azure-pipelines-2020.1"

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