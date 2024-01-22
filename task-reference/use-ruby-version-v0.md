---
title: UseRubyVersion@0 - Use Ruby version v0 task
description: Use the specified version of Ruby from the tool cache, optionally adding it to the PATH.
ms.date: 01/22/2024
monikerRange: ">=azure-pipelines-2019"
---

# UseRubyVersion@0 - Use Ruby version v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to select a version of Ruby to run on an agent. Optionally, the task can add the Ruby version to PATH.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Use Ruby version v0
# Use the specified version of Ruby from the tool cache, optionally adding it to the PATH.
- task: UseRubyVersion@0
  inputs:
    versionSpec: '>= 2.4' # string. Required. Version spec. Default: >= 2.4.
    #addToPath: true # boolean. Add to PATH. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Use Ruby Version v0
# Retrieves the specified version of Ruby from the tool cache. Optionally add it to PATH.
- task: UseRubyVersion@0
  inputs:
    versionSpec: '>= 2.4' # string. Required. Version spec. Default: >= 2.4.
    #addToPath: true # boolean. Add to PATH. Default: true.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="versionSpec"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionSpec`** - **Version spec**<br>
`string`. Required. Default value: `>= 2.4`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version range or a version of a Ruby version to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addToPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`addToPath`** - **Add to PATH**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Prepends the retrieved Ruby version to the PATH environment variable to make it available in subsequent tasks or scripts without using the output variable.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="rubyLocation"::: -->
**`rubyLocation`**<br><!-- :::editable-content name="Value"::: -->
The resolved folder of the Ruby distribution.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to select a version of Ruby to run on an agent, and optionally add it to PATH.

### Prerequisites

* A [Microsoft-hosted agent](/azure/devops/pipelines/agents/hosted#software) with side-by-side versions of Ruby installed, or a self-hosted agent with `Agent.ToolsDirectory` configured (see [FAQ](#how-can-i-configure-a-self-hosted-agent-to-use-this-task)).

This task will fail if no Ruby versions are found in `Agent.ToolsDirectory`. See other available Ruby versions on [Microsoft-hosted agents](/azure/devops/pipelines/agents/hosted#software).

### Where can I learn more about tool installers?

For an explanation of tool installers and examples, see [Tool installers](/azure/devops/pipelines/process/tasks#tool-installers).

### How can I configure a self-hosted agent to use this task?

You can run this task on a self-hosted agent with your own Ruby versions. To run this task on a self-hosted agent, set up `Agent.ToolsDirectory` by following the [Tool Cache instructions](https://github.com/Microsoft/vsts-task-tool-lib/blob/master/docs/overview.md#tool-cache). The tool name to use is `Ruby`.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task runs using the following [command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): restricted |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): rubyLocation, PATH |
| Agent version |  2.182.1 or greater |
| Task category | Tool |

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Tool |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Tool installers](/azure/devops/pipelines/process/tasks#tool-installers)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->