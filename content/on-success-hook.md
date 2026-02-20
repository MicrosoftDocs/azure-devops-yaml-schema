---
title: onSuccessHook definition
description: Used to run steps for clean-up actions.
ms.date: 01/27/2026
monikerRange: "<=azure-pipelines"
author: steved0x
ms.author: sdanie
---

# onSuccessHook definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Used to run steps for rollback actions or clean-up.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
onSuccessHook:
  steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
  pool: string | pool # Pool where on success steps will run.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

> [!NOTE]
> This definition is a supporting definition and is not intended for use directly in a pipeline. This article provides the YAML syntax for this supporting type, but does not show usage examples. For more information and examples for using this supporting type, see the following **Definitions that reference this definition** articles.

Definitions that reference this definition: [onSuccessOrFailureHook](on-success-or-failure-hook.md)

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
Pool where on success steps will run.
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