---
title: Chef@1 - Chef v1 task
description: Deploy to Chef environments by editing environment attributes.
ms.date: 05/17/2024
monikerRange: "<=azure-pipelines"
---

# Chef@1 - Chef v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Deploy to Chef environments by editing environment attributes.

> [!IMPORTANT]
> [!INCLUDE [task-deprecation](includes/task-deprecation.md)] Use [Chef-CLI](https://github.com/chef/chef-cli).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Deploy to Chef environments by editing environment attributes.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.1"

<!-- :::editable-content name="description"::: -->
Deploy to Chef environments by editing environment attributes.

> [!IMPORTANT]
> This task is deprecated. Use [Chef-CLI](https://github.com/chef/chef-cli).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Chef v1
# Deploy to Chef environments by editing environment attributes.
- task: Chef@1
  inputs:
    connectedServiceName: # string. Required. Chef Service Connection. 
    Environment: # string. Required. Environment. 
    Attributes: # string. Required. Environment Attributes. 
    chefWaitTime: '30' # string. Required. Wait Time. Default: 30.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="connectedServiceName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`connectedServiceName`** - **Chef Service Connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Chef subscription service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Environment"::: -->
:::moniker range="<=azure-pipelines"

**`Environment`** - **Environment**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Chef environment to be used for deployment. The attributes of that environment will be edited.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Attributes"::: -->
:::moniker range="<=azure-pipelines"

**`Attributes`** - **Environment Attributes**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the value of the leaf node attribute(s) to be updated. Example: `{ "default_attributes.connectionString" : "$(connectionString)", "override_attributes.buildLocation" : "https://sample.blob.core.windows.net/build" }`. The task fails if the leaf node does not exist.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="chefWaitTime"::: -->
:::moniker range="<=azure-pipelines"

**`chefWaitTime`** - **Wait Time**<br>
`string`. Required. Default value: `30`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The amount of time (in minutes) to wait for this task to complete. Default value: 30 minutes.
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

Use this task to deploy to Chef environments by editing environment attributes.

> [!IMPORTANT]
> This task is deprecated. Use [Chef-CLI](https://github.com/chef/chef-cli).
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
| Pipeline types | YAML, Preview, Classic build, Classic release |
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: Chef, KnifeReporting, DotNetFramework |
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