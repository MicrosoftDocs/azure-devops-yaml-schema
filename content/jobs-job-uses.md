---
title: jobs.job.uses definition
description: Any resources required by this job that are not already referenced.
ms.date: 02/27/2024
monikerRange: ">=azure-pipelines-2020.1"
---

# jobs.job.uses definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020.1"

<!-- :::editable-content name="description"::: -->
Any resources required by this job that are not already referenced.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020.1"

```yaml
uses:
  repositories: [ string ] # Repository references.
  pools: [ string ] # Pool references.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020.1"

Definitions that reference this definition: [jobs.job](jobs-job.md), [jobs.deployment](jobs-deployment.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="repositories"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`repositories`** string list.<br><!-- :::editable-content name="propDescription"::: -->
Repository references.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pools"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`pools`** string list.<br><!-- :::editable-content name="propDescription"::: -->
Pool references.
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