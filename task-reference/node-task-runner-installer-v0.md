---
title: NodeTaskRunnerInstaller@0 - Node.js tasks runner installer v0 task
description: Install specific Node.js version to run node tasks.
ms.date: 10/07/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1"
author: juliakm
ms.author: jukullam
---

# NodeTaskRunnerInstaller@0 - Node.js tasks runner installer v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2022.1"

<!-- :::editable-content name="description"::: -->
Install specific Node.js version to run node tasks.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-server"

```yaml
# Node.js tasks runner installer v0
# Install specific Node.js version to run node tasks.
- task: NodeTaskRunnerInstaller@0
  inputs:
    nodeVersion: '6' # '6' | '10' | '16'. Alias: runnerVersion | installVersion. Required. Version of runner to install. Default: 6.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2022.1 <=azure-pipelines-2022.2"

```yaml
# Node.js tasks runner installer v0
# Install specific Node.js version to run node tasks.
- task: NodeTaskRunnerInstaller@0
  inputs:
    nodeVersion: '6' # '6' | '10'. Alias: runnerVersion | installVersion. Required. Version of runner to install. Default: 6.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="nodeVersion"::: -->
:::moniker range=">=azure-pipelines-server"

**`nodeVersion`** - **Version of runner to install**<br>
[Input alias](index.md#what-are-task-input-aliases): `runnerVersion | installVersion`. `string`. Required. Allowed values: `6` (Node.js 6.17.1), `10` (Node.js 10.24.1), `16` (Node.js 16.20.2). Default value: `6`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the node version to install.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2022.1 <=azure-pipelines-2022.2"

**`nodeVersion`** - **Version of runner to install**<br>
[Input alias](index.md#what-are-task-input-aliases): `runnerVersion | installVersion`. `string`. Required. Allowed values: `6` (Node.js 6.17.1), `10` (Node.js 10.24.1). Default value: `6`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the node version to install.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2022.1"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

When adopting [agent releases that exclude the Node 6 task runner](https://github.com/microsoft/azure-pipelines-agent/blob/master/docs/node6.md) you may have an occasional need to run tasks that have not been updated to use a newer Node runner. For this scenario we provide a way to still use tasks dependent on Node End-of-Life runners. For more information, see Node runner guidance [blog post](https://devblogs.microsoft.com/devops/node-runner-update-guidance-for-azure-pipelines-task-authors/#upcoming-changes).

The following task example shows how to install the Node 6 runner just-in-time, so an older task can successfully run.


```yaml
  steps:
  - task: NodeTaskRunnerInstaller@0
    inputs:
      runnerVersion: 6
```
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->