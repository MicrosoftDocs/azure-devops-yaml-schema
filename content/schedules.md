---
title: schedules list definition
description: schedules list definition reference.
ms.date: 01/18/2023
monikerRange: "= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"
---

# schedules list definition


The schedules list specifies the scheduled triggers for the pipeline.


:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="schedules[schedule]" version="azure-pipelines-2020"::: -->

```yaml
schedules: [ cron ] # 
```


Properties that use this definition: [pipeline.schedules](pipeline.md)

## List types

| Type     | Description |
|----------|-------------|
| [schedules.cron](schedules-cron.md) |  |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="schedules[schedule]" version="azure-pipelines-2020.1"::: -->

```yaml
schedules: [ cron ] # 
```


Properties that use this definition: [pipeline.schedules](pipeline.md)

## List types

| Type     | Description |
|----------|-------------|
| [schedules.cron](schedules-cron.md) |  |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="schedules[schedule]" version="azure-pipelines-2022"::: -->

```yaml
schedules: [ cron ] # 
```


Properties that use this definition: [pipeline.schedules](pipeline.md)

## List types

| Type     | Description |
|----------|-------------|
| [schedules.cron](schedules-cron.md) |  |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="schedules[schedule]" version="azure-pipelines"::: -->

```yaml
schedules: [ cron ] # 
```


Properties that use this definition: [pipeline.schedules](pipeline.md)

## List types

| Type     | Description |
|----------|-------------|
| [schedules.cron](schedules-cron.md) |  |

<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

If you specify no scheduled trigger, no scheduled builds occur.


<!-- Examples -->


## See also

- [schedules.cron](schedules-cron.md)
- Learn more about [scheduled triggers](/azure/devops/pipelines/process/scheduled-triggers).
- Learn more about [triggers](/azure/devops/pipelines/build/triggers#pr-triggers) in general and how to specify them.



