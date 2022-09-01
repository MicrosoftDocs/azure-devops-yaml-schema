---
title: ManualValidation@0 - Manual validation v0 task
description: Pause a YAML pipeline run to wait for manual interaction (Preview).
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2020.1"
---

# ManualValidation@0 - Manual validation v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020.1"

<!-- :::editable-content name="description"::: -->
Pause a YAML pipeline run to wait for manual interaction.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020.1"

```yaml
# Manual validation v0
# [PREVIEW] Pause a pipeline run to wait for manual interaction. Works only with YAML pipelines.
- task: ManualValidation@0
  inputs:
    notifyUsers: # string. Required. Notify users. 
    #instructions: # string. Instructions. 
    #onTimeout: 'reject' # 'reject' | 'resume'. On timeout. Default: 'reject'.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="notifyUsers"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`notifyUsers`** - **Notify users**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Send a manual validation pending email to specific users (or groups). Only users with queue build permission can act on a manual validation.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="instructions"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`instructions`** - **Instructions**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
These instructions will be shown to the user for resuming or rejecting the manual validation. Based on these instructions the user will take an informed decision about this manual validation.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="onTimeout"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`onTimeout`** - **On timeout**<br>
Type: string. Allowed values: 'reject', 'resume'. Default value: 'reject'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Reject or resume this manual validation automatically after it is pending for the specified timeout or 30 days, whichever is earlier.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020.1"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
This task only works with YAML pipelines.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2020.1"

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