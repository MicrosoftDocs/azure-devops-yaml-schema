---
title: postRouteTrafficHook definition
description: Used to run the steps after the traffic is routed.
ms.date: 01/27/2026
monikerRange: "<=azure-pipelines"
author: steved0x
ms.author: sdanie
---

# postRouteTrafficHook definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Used to run the steps after the traffic is routed. Typically, these tasks monitor the health of the updated version for defined interval.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
postRouteTrafficHook:
  steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
  pool: string | pool # Pool where post route traffic steps will run.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information and examples for using this supporting type, see the following **Definitions that reference this definition** articles.

Definitions that reference this definition: [jobs.deployment.strategy.runOnce](jobs-deployment-strategy-run-once.md), [jobs.deployment.strategy.rolling](jobs-deployment-strategy-rolling.md), [jobs.deployment.strategy.canary](jobs-deployment-strategy-canary.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="steps"::: -->
:::moniker range="<=azure-pipelines"

**`steps`** [steps](steps.md).<br><!-- :::editable-content name="propDescription"::: -->
A list of steps to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
:::moniker range="<=azure-pipelines"

**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where post route traffic steps will run.
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