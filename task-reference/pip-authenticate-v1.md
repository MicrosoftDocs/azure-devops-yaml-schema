---
title: PipAuthenticate@1 - Python pip authenticate v1 task
description: Authentication task for the pip client used for installing Python distributions.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2020"
---

# PipAuthenticate@1 - Python pip authenticate v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Authentication task for the pip client used for installing Python distributions.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Python pip authenticate v1
# Authentication task for the pip client used for installing Python distributions.
- task: PipAuthenticate@1
  inputs:
  # Feeds and Authentication
    #artifactFeeds: # string. My feeds (select below). 
    #pythonDownloadServiceConnections: # string. Feeds from external organizations. 
    #onlyAddExtraIndex: false # boolean. Don't set primary index URL. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="artifactFeeds"::: -->
:::moniker range=">=azure-pipelines-2020"

**`artifactFeeds`** - **My feeds (select below)**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select feeds to authenticate present in this organization.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pythonDownloadServiceConnections"::: -->
:::moniker range=">=azure-pipelines-2020"

**`pythonDownloadServiceConnections`** - **Feeds from external organizations**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of [pip service connection](/azure/devops/pipelines/library/service-endpoints) names from external organizations to authenticate with pip.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="onlyAddExtraIndex"::: -->
:::moniker range=">=azure-pipelines-2020"

**`onlyAddExtraIndex`** - **Don't set primary index URL**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is set to true, no feed will be set as the primary index URL. All of the configured feeds/endpoints will be set as extra index URLs. Defaults to false.
<!-- :::editable-content-end::: -->

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
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="=azure-pipelines"

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

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.120.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->