---
title: PipAuthenticate@0 - Python pip authenticate v0 task
description: Authentication task for the pip client used for installing Python distributions (task version 0).
ms.date: 07/02/2024
monikerRange: ">=azure-pipelines-2019"
---

# PipAuthenticate@0 - Python pip authenticate v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to provide authentication for the `pip` client that installs Python distributions.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Python pip authenticate v0
# Authentication task for the pip client used for installing Python distributions.
- task: PipAuthenticate@0
  inputs:
  # Feeds and Authentication
    #artifactFeeds: # string. Alias: feedList. My feeds (select below). 
    #externalFeeds: # string. Alias: externalSources. Feeds from external organizations.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Python Pip Authenticate v0
# Authentication task for pip client used for installing python distributions.
- task: PipAuthenticate@0
  inputs:
  # Feeds and Authentication
    #artifactFeeds: # string. Alias: feedList. My feeds (select below). 
    #externalFeeds: # string. Alias: externalSources. Feeds from external organizations.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="artifactFeeds"::: -->
:::moniker range=">=azure-pipelines-2019"

**`artifactFeeds`** - **My feeds (select below)**<br>
Input alias: `feedList`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the feeds to authenticate as present in the organization.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="externalFeeds"::: -->
:::moniker range=">=azure-pipelines-2019"

**`externalFeeds`** - **Feeds from external organizations**<br>
Input alias: `externalSources`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the endpoints to authenticate outside the organization.
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
| Task category | Package |

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->