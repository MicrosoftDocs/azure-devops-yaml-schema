---
title: ManualValidation@0 - Manual validation v0 task
description: Pause a YAML pipeline run to wait for manual interaction - Preview (task version 0).
ms.date: 11/11/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# ManualValidation@0 - Manual validation v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to pause a YAML pipeline run to wait for manual interaction.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-server"

```yaml
# Manual validation v0
# Pause a pipeline run to wait for manual interaction. Works only with YAML pipelines.
- task: ManualValidation@0
  inputs:
    notifyUsers: # string. Required. Notify users. 
    #instructions: # string. Instructions. 
    #onTimeout: 'reject' # 'reject' | 'resume'. On timeout. Default: reject.
```

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

```yaml
# Manual validation v0
# [PREVIEW] Pause a pipeline run to wait for manual interaction. Works only with YAML pipelines.
- task: ManualValidation@0
  inputs:
    notifyUsers: # string. Required. Notify users. 
    #instructions: # string. Instructions. 
    #onTimeout: 'reject' # 'reject' | 'resume'. On timeout. Default: reject.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="notifyUsers"::: -->
:::moniker range="<=azure-pipelines"

**`notifyUsers`** - **Notify users**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sends a manual validation pending email to specific users (or groups). Only users with queue build permission can act on a manual validation. You can send an email to a group using the `[org name]\group name` syntax.

This task input is required, but you can specify an empty string if you don't want to notify anyone, for example during a test run: `notifyUsers: ''`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="instructions"::: -->
:::moniker range="<=azure-pipelines"

**`instructions`** - **Instructions**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the instructions that are shown to the user when resuming or rejecting the manual validation. Based on these instructions, the user will make an informed decision about this manual validation.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="onTimeout"::: -->
:::moniker range="<=azure-pipelines"

**`onTimeout`** - **On timeout**<br>
`string`. Allowed values: `reject`, `resume`. Default value: `reject`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Automatically rejects or resumes this manual validation after it is pending for the specified timeout, or 30 days, whichever is earlier.
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

Use this task in a YAML pipeline to pause a run within a stage. This is typically executed to perform various manual steps or actions and then the run is resumed or rejected.

> [!IMPORTANT]
> This task is only supported in YAML pipelines and can only be used in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) of a YAML pipeline.

The **Manual Validation** task allows you to pause a pipeline run within a stage, typically to perform some manual steps or actions, and then continue with the pipeline. For example, the user may need to manually validate certain deployment configurations before the pipeline starts a long running computational intensive job.

The **Manual Validation** task configuration includes an **instructions** parameter that is used to provide related information or to specify the manual steps the user executes during the pause. You can configure the task to send email notifications to users and user groups when it is awaiting a review and specify the automatic response (reject or resume) after a configurable timeout occurs.

You can specify the timeout value for the task using the optional `timeoutInMinutes` parameter, available in the [common task properties](/azure/devops/pipelines/yaml-schema/steps-task).

> [!NOTE]
> For the task to run completely, the `timeoutInMinutes` value of the job (`default = 60 minutes`) containing this task should be higher than the `timeoutInMinutes` value of the task itself. See [default job timeout values](/azure/devops/pipelines/process/phases#timeouts).

> [!TIP]
> You can use variables to specify email addresses in the `notifyUsers` parameter.

When the Manual Validation task is activated during a pipeline, it displays
a message bar with a link that opens the Manual validation dialog, which contains the instructions. After carrying out the manual steps, the administrator or user can choose to resume the run or reject it. Users with **Queue builds** permission on the pipeline can resume or reject the run.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yaml
  jobs:
  - job: waitForValidation
    displayName: Wait for external validation
    pool: server
    timeoutInMinutes: 4320 # job times out in 3 days
    steps:
    - task: ManualValidation@0
      timeoutInMinutes: 1440 # task times out in 1 day
      inputs:
        notifyUsers: |
          test@test.com
          example@example.com
        instructions: 'Please validate the build configuration and resume'
        onTimeout: 'resume'
```

This example uses `timeoutInMinutes` which is a [common task property](/azure/devops/pipelines/yaml-schema/steps-task) available in all tasks.
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Server |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
