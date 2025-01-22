---
title: preDeployHook definition
description: Used to run steps that initialize resources before application deployment starts.
ms.date: 01/22/2025
monikerRange: ">=azure-pipelines-2020"
---

# preDeployHook definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Used to run steps that initialize resources before application deployment starts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020"

```yaml
preDeployHook:
  steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
  pool: string | pool # Pool where pre deploy steps will run.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information on using the definitions that this type supports, see the following definition links.

Definitions that reference this definition: [jobs.deployment.strategy.runOnce](jobs-deployment-strategy-run-once.md), [jobs.deployment.strategy.rolling](jobs-deployment-strategy-rolling.md), [jobs.deployment.strategy.canary](jobs-deployment-strategy-canary.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="steps"::: -->
:::moniker range=">=azure-pipelines-2020"

**`steps`** [steps](steps.md).<br><!-- :::editable-content name="propDescription"::: -->
A list of steps to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
:::moniker range=">=azure-pipelines-2020"

**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where pre deploy steps will run.
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