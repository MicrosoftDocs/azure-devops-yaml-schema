---
title: ManualIntervention@8 - Manual intervention v8 task
description: Pause deployment and wait for manual intervention.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# ManualIntervention@8 - Manual intervention v8 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Pause deployment in a classic release pieline and wait for manual intervention.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Pause deployment and wait for intervention.
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
    #onTimeout: 'reject' # 'reject' | 'resume'. On timeout. Default: 'reject'.
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
    #onTimeout: 'reject' # 'reject' | 'resume'. On timeout. Default: 'reject'.
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
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
These instructions will be shown to the user for resuming or rejecting the manual intervention. Based on these instructions the user will take an informed decision about this manual intervention.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="emailRecipients"::: -->
:::moniker range="<=azure-pipelines"

**`emailRecipients`** - **Notify users**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Send a manual intervention pending email to specific users (or groups). Only users with manage deployment permission can act on a manual intervention.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="onTimeout"::: -->
:::moniker range="<=azure-pipelines"

**`onTimeout`** - **On timeout**<br>
Type: string. Allowed values: 'reject', 'resume'. Default value: 'reject'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Reject or resume this manual intervention automatically after it is pending for the specified timeout or 60 days, whichever is earlier.
<!-- :::editable-content-end::: -->

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