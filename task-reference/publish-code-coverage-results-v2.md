---
title: PublishCodeCoverageResults@2 - Publish code coverage results v2 task
description: Publish any of the code coverage results from a build.
ms.date: 02/01/2023
monikerRange: "=azure-pipelines"
---

# PublishCodeCoverageResults@2 - Publish code coverage results v2 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Publish any of the code coverage results from a build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Publish code coverage results v2
# Publish any of the code coverage results from a build.
- task: PublishCodeCoverageResults@2
  inputs:
    summaryFileLocation: # string. Required. Path to summary files. 
    #pathToSources: # string. Path to Source files. 
    #failIfCoverageEmpty: false # boolean. Fail if code coverage results are missing. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="summaryFileLocation"::: -->
:::moniker range="=azure-pipelines"

**`summaryFileLocation`** - **Path to summary files**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Paths to summary files containing code coverage statistics, such as line, method, and class coverage. Multiple summary files will be merged into a single report. Supports multiple lines of minimatch patterns. [More information](https://aka.ms/minimatchexamples).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pathToSources"::: -->
:::moniker range="=azure-pipelines"

**`pathToSources`** - **Path to Source files**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to source files is required when coverage XML reports do not contain absolute path to source files. For e.g., JaCoCo reports do not use absolute paths and when publishing JaCoCo coverage for Java apps, the pattern would be similar to `$(System.DefaultWorkingDirectory)/MyApp/src/main/java/`.<br />This input is also needed if tests are run in a docker container. This input should point to absolute path to source files on the host. For e.g., `$(System.DefaultWorkingDirectory)/MyApp/`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failIfCoverageEmpty"::: -->
:::moniker range="=azure-pipelines"

**`failIfCoverageEmpty`** - **Fail if code coverage results are missing**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fail the task if code coverage did not produce any results to publish.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="=azure-pipelines"

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
| Pipeline types | YAML, Classic build |
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.102.0 or greater |
| Task category | Test |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->