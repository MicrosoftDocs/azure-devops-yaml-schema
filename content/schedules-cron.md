---
title: schedules.cron definition
description: A scheduled trigger specifies a schedule on which branches are built.
ms.date: 02/27/2024
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
:::moniker range=">=azure-pipelines-2022.1"

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

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2022"

```yaml
schedules:
- cron: string # Required as first property. Cron syntax defining a schedule in UTC time.
  displayName: string # Optional friendly name given to a specific schedule.
  branches: # Branch names to include or exclude for triggering a run.
    include: [ string ] # List of items to include.
    exclude: [ string ] # List of items to exclude.
  always: boolean # Whether to always run the pipeline or only if there have been source code changes since the last successful scheduled run; the default is false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [schedules](schedules.md)

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
:::moniker range=">=azure-pipelines-2022.1"

**`batch`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Whether to run the pipeline if the previously scheduled run is in-progress; the default is `false`. This is regardless of the version of the pipeline repository.

The following table describes how `always` and `batch` interact.

| Always | Batch | Behavior |
|--------|-------|----------|
| `false` | `false` | Pipeline runs only if there's a change with respect to the last successful scheduled pipeline run. |
| `false` | `true` | Pipeline runs only if there's a change with respect to the last successful scheduled pipeline run, and there's no in-progress scheduled pipeline run. |
| `true` | `false` | Pipeline runs according to the cron schedule. |
| `true` | `true` | Pipeline runs according to the cron schedule. |

> [!IMPORTANT]
> When `always` is `true`, the pipeline runs according to the cron schedule, even when `batch` is `true`.
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

:::moniker range=">=azure-pipelines-2022.1"

### Build.CronSchedule.DisplayName variable

When a pipeline is running due to a cron scheduled trigger, the pre-defined `Build.CronSchedule.DisplayName` variable contains the `displayName` of the cron schedule that triggered the pipeline run.

Your YAML pipeline may contain multiple cron schedules, and you may want your pipeline to run different stages or jobs based on which cron schedule runs. For example, you have a nightly build and a weekly build, and you want to run a certain stage only during the nightly build. You can use the `Build.CronSchedule.DisplayName` variable in a job or stage condition to determine whether to run that job or stage.

```yml
- stage: stage1
  # Run this stage only when the pipeline is triggered by the 
  # "Daily midnight build" cron schedule
  condition: eq(variables['Build.CronSchedule.DisplayName'], 'Daily midnight build')
```

For more examples, see the following [Examples](#examples) section.

:::moniker-end
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

The following example defines two schedules.

The first schedule, **Daily midnight build**, runs a pipeline at midnight every day only if the code has changed since the last successful scheduled run.
It runs the pipeline for `main` and all `releases/*` branches, except for those branches under `releases/ancient/*`.

The second schedule, **Weekly Sunday build**, runs a pipeline at noon on Sundays for all `releases/*` branches.
It does so regardless of whether the code has changed since the last run.

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

:::moniker range=">azure-pipelines-2022"

To conditionally run a stage or job based on whether it was scheduled by a scheduled trigger, use the `Build.CronSchedule.DisplayName` variable in a condition. In this example, `stage1` only runs if the pipeline was triggered by the `Daily midnight build` schedule, and `job3` only runs if the pipeline was triggered by the `Weekly Sunday build` schedule.

```yml
stages:
- stage: stage1
  # Run this stage only when the pipeline is triggered by the 
  # "Daily midnight build" cron schedule
  condition: eq(variables['Build.CronSchedule.DisplayName'], 'Daily midnight build')
  jobs:
  - job: job1
    steps:
    - script: echo Hello from Stage 1 Job 1

- stage: stage2
  dependsOn: [] # Indicate this stage does not depend on the previous stage
  jobs:
  - job: job2
    steps:
    - script: echo Hello from Stage 2 Job 2
  - job: job3 
    # Run this job only when the pipeline is triggered by the 
    # "Weekly Sunday build" cron schedule
    condition: eq(variables['Build.CronSchedule.DisplayName'], 'Weekly Sunday build')
    steps:
    - script: echo Hello from Stage 2 Job 3
```

:::moniker-end
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- Learn more about [scheduled triggers](/azure/devops/pipelines/process/scheduled-triggers).
- Learn more about [triggers](/azure/devops/pipelines/build/triggers#pr-triggers) in general and how to specify them.
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
