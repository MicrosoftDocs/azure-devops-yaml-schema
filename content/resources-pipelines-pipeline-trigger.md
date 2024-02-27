---
title: resources.pipelines.pipeline.trigger definition
description: Specify none to disable, true to include all branches, or use the full syntax as described in the following examples.
ms.date: 02/27/2024
monikerRange: ">=azure-pipelines-2020"
---

# resources.pipelines.pipeline.trigger definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Specify none to disable, true to include all branches, or use the full syntax as described in the following examples.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [resources.pipelines.pipeline](resources-pipelines-pipeline.md)

:::moniker-end
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range=">=azure-pipelines-2020.1"

| Implementation | Description |
|---|---|
| [trigger: enabled, branches, stages, tags](#triggerobjectproperties) | Configure pipeline resource triggers using the full syntax. |
| [trigger: none | true](#triggerstring) | Specify none to disable or true to include all branches. |

:::moniker-end

:::moniker range="=azure-pipelines-2020"

| Implementation | Description |
|---|---|
| [trigger: enabled, branches](#triggerobjectproperties) | Specify none to disable, true to include all branches, or use the full syntax as described in the following examples. |
| [trigger: none | true](#triggerstring) | Specify none to disable or true to include all branches. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

There are several ways to define triggers in a pipeline resource. To trigger a run when any run of the referenced pipeline completes, use `trigger: true`.

```yaml
resources:
  pipelines:
  - pipeline: source-pipeline
    source: TriggeringPipeline
    trigger: true
```

To disable the pipeline resource trigger, specify a value of `none`.

```yaml
resources:
  pipelines:
  - pipeline: source-pipeline
    source: TriggeringPipeline
    trigger: none
```

To configure branch filters, use the full syntax. Branch filters can be specified as a list of branches to include, or as a list of branches to include combined with a list of branches to exclude.

To specify a list of branches to include and exclude, use the following `trigger` syntax.

```yaml
resources:
  pipelines:
  - pipeline: source-pipeline
    source: TriggeringPipeline
    trigger:
      branches:
        include:
        - main
        - develop
        - features/*
        exclude:
        - features/experimental/*
```

To specify a list of branches to include, with no excludes, omit the `exclude` value, or use the following syntax to specify the list of branches to include directly following `branches`.

```yaml
resources:
  pipelines:
  - pipeline: source-pipeline
    source: TriggeringPipeline
    trigger:
      branches:
      - main
      - develop
```

:::moniker range=">= azure-pipelines-2020.1"

To filter by stages or tags, use the following `trigger` syntax.

```yaml
resources:
  pipelines:
  - pipeline: source-pipeline
    source: TriggeringPipeline
    trigger:
      branches: # Branches to include
      tags: # List of tags that when matched will trigger the pipeline. 
      - release25
      stages: # List of stages that when complete will trigger the pipeline. 
      - build
```

:::moniker-end

For more information, see [Pipeline completion triggers](/azure/devops/pipelines/process/pipeline-triggers).

> [!IMPORTANT]
> When you define a resource trigger, if its pipeline resource is from the same repo as the current pipeline, triggering follows the same branch and commit on which the event is raised.
> But if the pipeline resource is from a different repo, the current pipeline is triggered on the branch specified by the **Default branch for manual and scheduled builds** setting. For more information, see [Branch considerations for pipeline completion triggers](/azure/devops/pipelines/process/pipeline-triggers#branch-considerations).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="trigger: object properties"::: -->
<a name="triggerobjectproperties"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2020.1"

<!-- :::implementation-signature::: -->
## trigger: enabled, branches, stages, tags
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Configure pipeline resource triggers using the full syntax.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
trigger:
  enabled: boolean # Whether the trigger is enabled; defaults to true.
  branches: branches # Branches to include or exclude for triggering a run.
  stages: [ string ] # List of stages that when matched will trigger the pipeline.
  tags: [ string ] # List of tags that when matched will trigger the pipeline.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="enabled"::: -->
**`enabled`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Whether the trigger is enabled; defaults to true.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="branches"::: -->
**`branches`** [resources.pipelines.pipeline.trigger.branches](resources-pipelines-pipeline-trigger-branches.md).<br><!-- :::editable-content name="propDescription"::: -->
Branch names to include or exclude for triggering a run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="stages"::: -->
**`stages`** string list.<br><!-- :::editable-content name="propDescription"::: -->
List of stages that when matched will trigger the pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
**`tags`** string list.<br><!-- :::editable-content name="propDescription"::: -->
List of tags that when matched will trigger the pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## trigger: enabled, branches
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Specify none to disable, true to include all branches, or use the full syntax as described in the following examples.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
trigger:
  enabled: boolean # Whether the trigger is enabled; defaults to true.
  branches: branches # Branches to include or exclude for triggering a run.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="enabled"::: -->
**`enabled`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Whether the trigger is enabled; defaults to true.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="branches"::: -->
**`branches`** [resources.pipelines.pipeline.trigger.branches](resources-pipelines-pipeline-trigger-branches.md).<br><!-- :::editable-content name="propDescription"::: -->
Branch names to include or exclude for triggering a run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end
<!-- :::objectAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="trigger: string"::: -->
<a name="triggerstring"></a>
<!-- :::stringAnyOf::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## trigger: none | true
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Specify none to disable or true to include all branches.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
trigger: none | true # Specify none to disable or true to include all branches.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-string-item::: -->
**`trigger`** string. Allowed values: none | true.<br>
<!-- :::editable-content name="description"::: -->
Specify none to disable or true to include all branches.
<!-- :::editable-content-end::: -->
<!-- :::implementation-string-item-end::: -->

:::moniker-end
<!-- :::stringAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
