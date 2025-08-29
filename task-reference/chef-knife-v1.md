---
title: ChefKnife@1 - Chef Knife v1 task
description: Run scripts with Knife commands on your Chef workstation.
ms.date: 08/29/2025
monikerRange: "<=azure-pipelines"
---

# ChefKnife@1 - Chef Knife v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Run scripts with Knife commands on your Chef workstation.

> [!IMPORTANT]
> [!INCLUDE [task-deprecation](includes/task-deprecation.md)] Use [Chef knife client](https://docs.chef.io/workstation/knife_client/).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Run scripts with Knife commands on your Chef workstation.

> [!IMPORTANT]
> This task is deprecated. Use [Chef knife client](https://docs.chef.io/workstation/knife_client/).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Chef Knife v1
# Run scripts with Knife commands on your Chef workstation.
- task: ChefKnife@1
  inputs:
    ConnectedServiceName: # string. Required. Chef Subscription. 
    ScriptPath: # string. Required. Script Path. 
    #ScriptArguments: # string. Script Arguments.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="ConnectedServiceName"::: -->
:::moniker range="<=azure-pipelines"

**`ConnectedServiceName`** - **Chef Subscription**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Chef subscription to configure before running knife commands.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptPath"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptPath`** - **Script Path**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path of the script. This should be fully qualified path or a relative to the default working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptArguments"::: -->
:::moniker range="<=azure-pipelines"

**`ScriptArguments`** - **Script Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. The additional parameters to pass to the script. Can be either ordinal or named parameters.
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

> [!IMPORTANT]
> This task is deprecated. Use [Chef knife client](https://docs.chef.io/workstation/knife_client/).
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
| Pipeline types | YAML, Preview, Classic build |
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: Chef, DotNetFramework |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.83.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->