---
title: ManualIntervention@8 - Manual intervention v8 task
description: Pause deployment and wait for manual intervention.
ms.date: 08/25/2023
monikerRange: "<=azure-pipelines"
---

# ManualIntervention@8 - Manual intervention v8 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to pause deployment in a release pipeline and wait for manual intervention.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to pause deployment in a release pipeline and wait for intervention.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Manual intervention v8
# Pause deployment and wait for manual intervention.
- task: ManualIntervention@8
  inputs:
    #instructions: # string. Instructions. 
    #emailRecipients: # string. Notify users. 
    #onTimeout: 'reject' # 'reject' | 'resume'. On timeout. Default: reject.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Manual Intervention v8
# Pause deployment and wait for intervention.
- task: ManualIntervention@8
  inputs:
    #instructions: # string. Instructions. 
    #emailRecipients: # string. Notify users. 
    #onTimeout: 'reject' # 'reject' | 'resume'. On timeout. Default: reject.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="instructions"::: -->
:::moniker range="<=azure-pipelines"

**`instructions`** - **Instructions**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the instructions that are shown to the user when resuming or rejecting the manual intervention. Based on these instructions, the user will make an informed decision about this manual intervention.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="emailRecipients"::: -->
:::moniker range="<=azure-pipelines"

**`emailRecipients`** - **Notify users**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sends a manual intervention pending email to specific users (or groups). Only users with manage deployment permission can act on a manual intervention.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="onTimeout"::: -->
:::moniker range="<=azure-pipelines"

**`onTimeout`** - **On timeout**<br>
`string`. Allowed values: `reject`, `resume`. Default value: `reject`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Automatically rejects or resumes the manual intervention after it is pending for the specified timeout, or 60 days, whichever is earlier.
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

Use this task in a release pipeline to pause an active deployment within a stage. This is typically executed to perform various manual steps or actions and then the automated deployment tasks are resumed.

> [!NOTE]
> This task can only be used in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) and is intended for use in a classic release pipeline. This article refers to classic pipelines. For YAML usage, see [Manual Validation task](manual-validation-v0.md).

:::image type="content" source="media/maninter-use-variables.png" alt-text="Screenshot of configuring a Manual Intervention task.":::

The **Manual Intervention** task does not perform deployment actions directly. Instead, it allows you to pause an active deployment within a stage, typically to perform various manual steps or actions, and then the automated deployment tasks are resumed. For example, the user may
need to edit the details of the current release before continuing (perhaps by entering the values for custom variables used by the tasks in the release).

The **Manual Intervention** task configuration includes an **Instructions** parameter that is used to provide related information or to specify the manual steps the user executes during the agentless job. You can configure the task to send email notifications to users and user groups when it is awaiting intervention and specify the automatic response (reject or resume the deployment) after a configurable timeout occurs.

> [!NOTE]
> You can use built-in and custom variables to generate portions of your instructions.

When the Manual Intervention task is activated during a deployment, it sets the deployment state to **IN PROGRESS**. A message bar is displayed with a link that opens the Manual Intervention dialog, which contains the instructions. After carrying out the manual steps, the administrator or user can choose to resume the deployment or reject it. Users with **Manage deployment** permission on the stage can resume or reject the manual intervention.

For more information about using this task, see [Approvals and gates overview](/azure/devops/pipelines/release/approvals/).
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
| Pipeline types | Classic release |
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
