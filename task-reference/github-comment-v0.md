---
title: GitHubComment@0 - GitHub Comment v0 task
description: Write a comment to your Github entity i.e. issue or a Pull Request (PR).
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2020"
---

# GitHubComment@0 - GitHub Comment v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Write a comment to your Github entity i.e. issue or a Pull Request (PR).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# GitHub Comment v0
# Write a comment to your Github entity i.e. issue or a Pull Request (PR).
- task: GitHubComment@0
  inputs:
    gitHubConnection: # string. Required. GitHub connection (OAuth or PAT). 
    repositoryName: '$(Build.Repository.Name)' # string. Required. Repository. Default: '$(Build.Repository.Name)'.
    #id: # string. ID of the github pr/issue. 
    #comment: # string. Comment.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="gitHubConnection"::: -->
:::moniker range=">=azure-pipelines-2020"

**`gitHubConnection`** - **GitHub connection (OAuth or PAT)**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the GitHub service connection to use to connect to the GitHub repository. The connection must be based on a GitHub user's OAuth or a GitHub personal access token. Learn more about service connections [here](https://aka.ms/AA3am5s).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="repositoryName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`repositoryName`** - **Repository**<br>
Type: string. Required. Default value: '$(Build.Repository.Name)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the GitHub repository in which the GitHub comment will be created.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="id"::: -->
:::moniker range=">=azure-pipelines-2020"

**`id`** - **ID of the github pr/issue**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the issue or pr number; if used in a Pipeline for PRs leave it empty to dynamically figure out the id.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="comment"::: -->
:::moniker range=">=azure-pipelines-2020"

**`comment`** - **Comment**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Contents of the comment to be written.
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

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.0.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->