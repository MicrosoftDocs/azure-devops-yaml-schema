---
title: SonarQubeAnalyze@6 - Run Code Analysis v6 task
description: Run scanner and upload the results to the SonarQube server (task version 6).
ms.date: 01/27/2026
monikerRange: "=azure-pipelines"
---

# SonarQubeAnalyze@6 - Run Code Analysis v6 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Run scanner and upload the results to the SonarQube server.

[!INCLUDE [SonarQube Tasks note](includes/sonar-qube-tasks-note.md)]
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Run Code Analysis v6
# Run scanner and upload the results to the SonarQube server.
- task: SonarQubeAnalyze@6
  inputs:
    jdkversion: 'JAVA_HOME_17_X64' # 'JAVA_HOME' | 'JAVA_HOME_17_X64' | 'JAVA_HOME_21_X64'. Required. JDK version source for analysis. Default: JAVA_HOME_17_X64.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="jdkversion"::: -->
:::moniker range=">azure-pipelines-server"

**`jdkversion`** - **JDK version source for analysis**<br>
`string`. Required. Allowed values: `JAVA_HOME` (Use JAVA_HOME), `JAVA_HOME_17_X64` (Use built-in JAVA_HOME_17_X64 (hosted agent)), `JAVA_HOME_21_X64` (Use built-in JAVA_HOME_21_X64 (hosted agent)). Default value: `JAVA_HOME_17_X64`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the wanted Java version for the analysis : You can choose with either Self provided JAVA_HOME which will pick up the value of this env variable, or you can choose the built-in JAVA_HOME_XX_X64 value on hosted agent. 
Default value is JAVA_HOME_17_X64, however if you choose either of the proposed value and they are not available, JAVA_HOME value will be picked up instead.
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

[!INCLUDE [SonarQube Tasks note](includes/sonar-qube-tasks-note.md)]
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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: java |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  3.218.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
