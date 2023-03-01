---
title: jobs.job.uses definition
description: Any resources required by this job that are not already referenced.
ms.date: 03/01/2023
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

Definitions that that reference this definition: [jobs.job](jobs-job.md), [jobs.deployment](jobs-deployment.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
:::moniker range=">=azure-pipelines-2020.1"

<!-- :::item name="repositories"::: -->
**`repositories`** string list.<br>
<!-- :::editable-content name="propDescription"::: -->
Repository references.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pools"::: -->
**`pools`** string list.<br>
<!-- :::editable-content name="propDescription"::: -->
Pool references.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
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