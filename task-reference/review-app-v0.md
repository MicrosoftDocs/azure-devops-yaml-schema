---
title: ReviewApp@0 - Review App v0 task
description: Use this task under deploy phase provider to create a resource dynamically.
ms.date: 01/18/2023
monikerRange: ">=azure-pipelines-2020"
---

# ReviewApp@0 - Review App v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Use this task under a deploy phase provider to create a resource dynamically.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Review App v0
# Use this task under deploy phase provider to create a resource dynamically.
- task: ReviewApp@0
  inputs:
    resourceName: # string. Required. Resource name. 
    #baseEnvironmentName: # string. Environment name. 
    #reviewResourceName: # string. Review Resource Name.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="resourceName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`resourceName`** - **Resource name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of an existing resource in the environment, which will be used for resource-type information.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="baseEnvironmentName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`baseEnvironmentName`** - **Environment name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="reviewResourceName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`reviewResourceName`** - **Review Resource Name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task under a deploy phase provider to create a resource dynamically.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
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