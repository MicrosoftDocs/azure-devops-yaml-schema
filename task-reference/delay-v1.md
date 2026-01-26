---
title: Delay@1 - Delay v1 task
description: Delay further execution of a workflow by a fixed time.
ms.date: 12/18/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022"
---

# Delay@1 - Delay v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Delays further execution of a workflow by a fixed time.
<!-- :::editable-content-end::: -->

:::moniker-end

<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Delay v1
# Delay further execution of a workflow by a fixed time.
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

The maximum value for a delay is 60 days (86400 minutes). The default timeout for [agentless jobs](/azure/devops/pipelines/process/phases#server-jobs) is [60 minutes](/azure/devops/pipelines/process/phases#agentless-jobs-supported-tasks). To use delays which are 60 minutes or longer, set the parent job’s [timeoutInMinutes](/azure/devops/pipelines/process/phases#timeouts) property to a higher value. Otherwise, the job will time out and fail.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples
### Delay for 30 minutes

The following YAML snippet creates a job to delay for 30 minutes before continuing execution.
```YAML
- job: DelayTask
  pool: server # 'server' is a reserved word for agentless jobs. Delay task must be agentless.
  steps:
  - task: Delay@V1
    inputs:
      delayForMinutes: '30'
```

### Delay for 7 days

The following YAML snippet creates a job which delays for 7 days (10080 minutes) before continuing execution.
```YAML
- job: DelayTask
  pool: server
  timeoutInMinutes: 10081
  steps:
  - task: Delay@V1
    inputs:
      delayForMinutes: '10080'
```

> [!NOTE]
> You must set the `timeoutInMinutes` property to be at least a minute longer than the `delayForMinutes` parameter on the Delay@V1 task. The default `timeoutInMinutes` is 60 minutes on an agentless job. Failing to do so will cause the task to timeout.
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
