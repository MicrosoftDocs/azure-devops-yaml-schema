---
title: Delay@1 - Delay v1 task
description: Delay further execution of a workflow by a fixed time.
ms.date: 02/24/2025
monikerRange: "<=azure-pipelines"
---

# Delay@1 - Delay v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Delays further execution of a workflow by a fixed time.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Delays further execution of the workflow by a fixed time.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Delay v1
# Delay further execution of a workflow by a fixed time.
- task: Delay@1
  inputs:
    delayForMinutes: '0' # string. Required. Delay Time (minutes). Default: 0.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Delay v1
# Delay further execution of the workflow by a fixed time.
- task: Delay@1
  inputs:
    delayForMinutes: '0' # string. Required. Delay Time (minutes). Default: 0.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="delayForMinutes"::: -->
:::moniker range="<=azure-pipelines"

**`delayForMinutes`** - **Delay Time (minutes)**<br>
`string`. Required. Default value: `0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Delays the execution of the workflow by specified time in minutes. A `0` value means that workflow execution will start without delay. The maximum value is `86400` (60 days).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) of a release pipeline to pause the execution of the pipeline for a fixed delay time.

> [!NOTE]
> Can be used in only an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) of a release pipeline.

The maximum value for a delay is 60 days (86400 minutes).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Server |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->