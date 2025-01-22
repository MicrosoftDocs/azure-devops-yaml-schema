---
title: schedules definition
description: The schedules list specifies the scheduled triggers for the pipeline.
ms.date: 01/22/2025
monikerRange: ">=azure-pipelines-2020"
---

# schedules definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
The schedules list specifies the scheduled triggers for the pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020"

```yaml
schedules: [ cron ] # The schedules list specifies the scheduled triggers for the pipeline.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [pipeline](pipeline.md)

:::moniker-end
<!-- :::parents-end::: -->

## List types

<!-- :::list-types::: -->
:::moniker range=">=azure-pipelines-2020"

| Type | Description |
|---|---|
| [schedules.cron](schedules-cron.md) | A scheduled trigger specifies a schedule on which branches are built. |

:::moniker-end
<!-- :::list-types-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

If you specify no scheduled trigger, no scheduled builds occur.

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
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [schedules.cron](schedules-cron.md)
- Learn more about [scheduled triggers](/azure/devops/pipelines/process/scheduled-triggers).
- Learn more about [triggers](/azure/devops/pipelines/build/triggers#pr-triggers) in general and how to specify them.
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->