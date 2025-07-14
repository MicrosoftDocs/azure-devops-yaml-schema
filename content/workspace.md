---
title: workspace definition
description: Workspace options on the agent.
ms.date: 07/14/2025
monikerRange: "<=azure-pipelines"
author: steved0x
ms.author: sdanie
---

# workspace definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Workspace options on the agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
workspace:
  clean: outputs | resources | all # What to clean up before the job runs.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information and examples for using this supporting type, see the following **Definitions that reference this definition** articles.

Definitions that reference this definition: [pipeline](pipeline.md), [jobs.job](jobs-job.md), [jobs.deployment](jobs-deployment.md)

:::moniker-end

<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="clean"::: -->
:::moniker range="<=azure-pipelines"

**`clean`** string.<br><!-- :::editable-content name="propDescription"::: -->
Which parts of the workspace should be cleaned before the run. Valid values are `outputs`, `resources`, or `all`.

For more information about workspaces, including clean options, see the [workspace](/azure/devops/pipelines/process/phases#workspace) topic in [Jobs](/azure/devops/pipelines/process/phases).
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