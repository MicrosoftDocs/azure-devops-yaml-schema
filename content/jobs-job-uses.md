---
title: jobs.job.uses definition
description: Any resources required by this job that are not already referenced.
ms.date: 02/24/2025
monikerRange: ">=azure-pipelines-2020.1"
author: juliakm
ms.author: jukullam
---

# jobs.job.uses definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020.1"

<!-- :::editable-content name="description"::: -->
Specifies resources required by a job that are not already referenced elsewhere in the pipeline, for example by a [checkout](./steps-checkout.md) step or a [repository resource](./resources-repositories-repository.md). For more information about `uses`, see [Limit job authorization scope](/azure/devops/pipelines/repos/azure-repos-git#limit-job-authorization-scope) and ["uses" statement for pre-declaring resources](/azure/devops/release-notes/2021/sprint-181-update#uses-statement-for-pre-declaring-resources).
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
Specifies Azure Repos repositories required by a job that are not already referenced elsewhere in the pipeline, for example by a [checkout](./steps-checkout.md) step or a [repository resource](./resources-repositories-repository.md). For more information, see [Limit job authorization scope](/azure/devops/pipelines/repos/azure-repos-gi#limit-job-authorization-scope) and ["uses" statement for pre-declaring resources](/azure/devops/release-notes/2021/sprint-181-update#uses-statement-for-pre-declaring-resources).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pools"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`pools`** string list.<br><!-- :::editable-content name="propDescription"::: -->
Specifies pools required by this job, typically when using a [matrix](./jobs-job-strategy.md#strategy-matrix-maxparallel) job strategy. For more information, see ["uses" statement for pre-declaring resources](/azure/devops/release-notes/2021/sprint-181-update#uses-statement-for-pre-declaring-resources).
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