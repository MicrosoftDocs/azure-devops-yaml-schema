---
title: schedules.cron definition
description: A scheduled trigger specifies a schedule on which branches are built.
ms.date: 04/28/2023
monikerRange: ">=azure-pipelines-2020"
---

# schedules.cron definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
A scheduled trigger specifies a schedule on which branches are built.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020"

```yaml
schedules:
- cron: string # Required as first property. Cron syntax defining a schedule in UTC time.
  displayName: string # Optional friendly name given to a specific schedule.
  branches: # Branch names to include or exclude for triggering a run.
    include: [ string ] # List of items to include.
    exclude: [ string ] # List of items to exclude.
  batch: boolean # Whether to run the pipeline if the previously scheduled run is in-progress; the default is false.
  always: boolean # Whether to always run the pipeline or only if there have been source code changes since the last successful scheduled run; the default is false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that that reference this definition: [schedules](schedules.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="cron"::: -->
:::moniker range=">=azure-pipelines-2020"

**`cron`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Cron syntax defining a schedule in UTC time.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`displayName`** string.<br><!-- :::editable-content name="propDescription"::: -->
Optional friendly name given to a specific schedule.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="branches"::: -->
:::moniker range=">=azure-pipelines-2020"

**`branches`** [includeExcludeFilters](include-exclude-filters.md).<br><!-- :::editable-content name="propDescription"::: -->
Branch names to include or exclude for triggering a run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="batch"::: -->
:::moniker range=">=azure-pipelines-2020"

**`batch`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Whether to run the pipeline if the previously scheduled run is in-progress; the default is false.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="always"::: -->
:::moniker range=">=azure-pipelines-2020"

**`always`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Whether to always run the pipeline or only if there have been source code changes since the last successful scheduled run; the default is false.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

If you specify no scheduled trigger, no scheduled builds occur.

> [!NOTE]
> If you specify an `exclude` clause without an `include` clause for `branches`, it is equivalent to specifying `*` in the `include` clause.

> [!IMPORTANT]
> Scheduled triggers defined using the pipeline settings UI take precedence over YAML scheduled triggers.
> 
> If your YAML pipeline has both YAML scheduled triggers and UI defined scheduled triggers, 
> only the UI defined scheduled triggers are run. 
> To run the YAML defined scheduled triggers in your YAML pipeline,
> you must remove the scheduled triggers defined in the pipeline settings UI.
> Once all UI scheduled triggers are removed, a push must be made in order for the YAML 
> scheduled triggers to start being evaluated.
>
> To delete UI scheduled triggers from a YAML pipeline, see [UI settings override YAML scheduled triggers](/azure/devops/pipelines/troubleshooting/troubleshooting#ui-settings-override-yaml-scheduled-triggers).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yaml
schedules:
- cron: '0 0 * * *'
  displayName: Daily midnight build
  branches:
    include:
    - main
    - releases/*
    exclude:
    - releases/ancient/*
- cron: '0 12 * * 0'
  displayName: Weekly Sunday build
  branches:
    include:
    - releases/*
  always: true
```

In the preceding example, two schedules are defined.

The first schedule, **Daily midnight build**, runs a pipeline at midnight every day only if the code has changed since the last successful scheduled run.
It runs the pipeline for `main` and all `releases/*` branches, except for those branches under `releases/ancient/*`.

The second schedule, **Weekly Sunday build**, runs a pipeline at noon on Sundays for all `releases/*` branches.
It does so regardless of whether the code has changed since the last run.
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- Learn more about [scheduled triggers](/azure/devops/pipelines/process/scheduled-triggers).
- Learn more about [triggers](/azure/devops/pipelines/build/triggers#pr-triggers) in general and how to specify them.
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
