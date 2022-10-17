---
title: Npm@0 - npm v0 task
description: Run an npm command. Use NpmAuthenticate@0 task for latest capabilities.
ms.date: 09/26/2022
monikerRange: "<=azure-pipelines"
---

# Npm@0 - npm v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Use this task to install and publish npm packages or to run an `npm` command. Supports `npmjs.com` and authenticated registries like Azure Artifacts.

>[!NOTE]
> The [npm Authenticate task](/azure/devops/pipelines/tasks/reference/npm-authenticate-v0) is the recommended way to authenticate with Azure Artifacts. This task no longer takes new features and only critical bugs are addressed.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to install and publish npm packages or to run an `npm` command. Supports `npmjs.com` and authenticated registries like Azure Artifacts.

>[!NOTE]
> The [npm Authenticate task](/azure/devops/pipelines/tasks/reference/npm-authenticate-v0) is the recommended way to authenticate with Azure Artifacts. This task no longer takes new features and only critical bugs are addressed.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# npm v0
# Run an npm command. Use NpmAuthenticate@0 task for latest capabilities.
- task: Npm@0
  inputs:
    #cwd: # string. working folder. 
    command: 'install' # string. Required. npm command. Default: install.
    #arguments: # string. arguments.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
# npm v0
# Run an npm command.
- task: Npm@0
  inputs:
    #cwd: # string. working folder. 
    command: 'install' # string. Required. npm command. Default: install.
    #arguments: # string. arguments.
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

<!-- :::item name="cwd"::: -->
:::moniker range="<=azure-pipelines"

**`cwd`** - **working folder**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the working directory where the `npm` command is run. Defaults to the root of the repo.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="command"::: -->
:::moniker range="<=azure-pipelines"

**`command`** - **npm command**<br>
`string`. Required. Default value: `install`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the command and arguments, which are passed to `npm` for execution.

If your arguments contain double quotes (`"`), escape them with a slash (`\`), and surround the escaped string with double quotes (`"`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The additional arguments that are passed to `npm`.
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
> The [npm Authenticate](npm-authenticate-v0.md) task is the recommended way to authenticate with Azure Artifacts. This npm no longer takes new features and only critical bugs are addressed.

### Where can I learn npm commands and arguments?

* [npm docs](https://docs.npmjs.com/)
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
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: npm |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Package |

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: npm |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.91.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->