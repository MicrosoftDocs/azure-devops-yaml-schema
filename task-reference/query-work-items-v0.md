---
title: queryWorkItems@0 - Query work items v0 task
description: Execute a work item query and check the number of items returned.
ms.date: 10/07/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
---

# queryWorkItems@0 - Query work items v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task in an [agentless](/azure/devops/pipelines/process/phases) job of a release pipeline to ensure the number of matching items returned by a work item query is within the configured thresholds.

Can only be used in an [agentless](/azure/devops/pipelines/process/phases) job of a release pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Query work items v0
# Execute a work item query and check the number of items returned.
- task: queryWorkItems@0
  inputs:
    queryId: # string. Required. Query. 
    maxThreshold: '0' # string. Required. Upper threshold. Default: 0.
  # Advanced
    minThreshold: '0' # string. Required. Lower threshold. Default: 0.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="queryId"::: -->
:::moniker range="<=azure-pipelines"

**`queryId`** - **Query**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a saved work item query within the current project to execute. Can be a built-in or custom query.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="maxThreshold"::: -->
:::moniker range="<=azure-pipelines"

**`maxThreshold`** - **Upper threshold**<br>
`string`. Required. Default value: `0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the maximum number of matching work items from the query.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="minThreshold"::: -->
:::moniker range="<=azure-pipelines"

**`minThreshold`** - **Lower threshold**<br>
`string`. Required. Default value: `0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the minimum number of matching work items from the query.
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

Use this task in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) of a release pipeline to ensure the number of matching items returned by a work item query is within the configured thresholds.

> [!NOTE]
> This task can only be used in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) of a release pipeline.

This task succeeds if `_minimum-threshold_` **&lt;=** `_#-matching-workitems_` **&lt;=** `_maximum-threshold_`.

For more information about using this task, see the [Approvals and gates overview](/azure/devops/pipelines/release/approvals/).
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
| Runs on | Server, ServerGate |
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