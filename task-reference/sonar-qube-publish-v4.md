---
title: SonarQubePublish@4 - Publish Quality Gate Result v4 task
description: Publish SonarQube's Quality Gate result on the Azure DevOps build result, to be used after the actual analysis (task version 4).
ms.date: 09/22/2025
monikerRange: "=azure-pipelines"
---

# SonarQubePublish@4 - Publish Quality Gate Result v4 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Use this task to publish SonarQube's Quality Gate result on the Azure DevOps build result. Use this after the analysis.

> [!NOTE]
> This task is deprecated; use [SonarQubePublish@7](./sonar-qube-publish-v7.md).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Publish Quality Gate Result v4
# Publish SonarQube's Quality Gate result on the Azure DevOps build result, to be used after the actual analysis.
- task: SonarQubePublish@4
  inputs:
    pollingTimeoutSec: '300' # string. Required. Timeout (s). Default: 300.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="pollingTimeoutSec"::: -->
:::moniker range=">azure-pipelines-server"

**`pollingTimeoutSec`** - **Timeout (s)**<br>
`string`. Required. Default value: `300`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This task polls SonarQube until the analysis is completed or until the timeout is reached. This task also adds a build property with the Quality Gate status of the current build(s) analyses.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-server"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

> [!NOTE]
> This task is deprecated; use [SonarQubePublish@7](./sonar-qube-publish-v7.md).
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
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [SonarQube Azure DevOps Integration](https://docs.sonarqube.org/latest/analysis/azuredevops-integration/)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->