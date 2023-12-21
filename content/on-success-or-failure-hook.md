---
title: onSuccessOrFailureHook definition
description: Used to run steps for rollback actions or clean-up.
ms.date: 12/21/2023
monikerRange: ">=azure-pipelines-2020"
---

# onSuccessOrFailureHook definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Used to run steps for rollback actions or clean-up.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020"

```yaml
onSuccessOrFailureHook:
  failure: # Runs on failure of any step.
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
    pool: string | pool # Pool where post on failure steps will run.
  success: # Runs on success of all of the steps.
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
    pool: string | pool # Pool where on success steps will run.
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
<!-- :::item name="failure"::: -->
:::moniker range=">=azure-pipelines-2020"

**`failure`** [onFailureHook](on-failure-hook.md).<br><!-- :::editable-content name="propDescription"::: -->
Runs on failure of any step.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="success"::: -->
:::moniker range=">=azure-pipelines-2020"

**`success`** [onSuccessHook](on-success-hook.md).<br><!-- :::editable-content name="propDescription"::: -->
Runs on success of all of the steps.
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