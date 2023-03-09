---
title: PublishCodeCoverageResults@2 - Publish code coverage results v2 task
description: Publish code coverage results from a build and generates cjson.
ms.date: 01/18/2023
monikerRange: "<=azure-pipelines"
---

# PublishCodeCoverageResults@2 - Publish code coverage results v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to get code coverage results from a build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Publish code coverage results v2
# Publish code coverage results from a build.
- task: PublishCodeCoverageResults@2
  inputs:
    summaryFileLocation: # string. Required. Summary file. 
    #pathToSources: # string. Path to Source files. 
    #failIfCoverageEmpty: false # boolean. Fail when code coverage results are missing. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Publish Code Coverage Results v2
# Publish code coverage results from a build.
- task: PublishCodeCoverageResults@2
  inputs:
    summaryFileLocation: # string. Required. Summary file. 
    #failIfCoverageEmpty: false # boolean. Fail when code coverage results are missing. Default: false.
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

<!-- :::item name="codeCoverageTool"::: -->
:::moniker range="<=azure-pipelines"

<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="summaryFileLocation"::: -->
:::moniker range="<=azure-pipelines"

**`summaryFileLocation`** - **Summary file**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path of the summary file containing code coverage statistics, such as line, method, and class coverage. Multiple summary files are merged into a single report. The value may contain minimatch patterns. For example: `$(System.DefaultWorkingDirectory)/MyApp/**/site/cobertura/coverage.xml`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pathToSources"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`pathToSources`** - **Path to Source files**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifying a path to source files is required when coverage XML reports don't contain an absolute path to source files. For example, JaCoCo reports don't use absolute paths, so when publishing JaCoCo coverage for Java apps, the pattern is similar to `$(System.DefaultWorkingDirectory)/MyApp/src/main/java/`. This input should point to an absolute path to source files on the host. For example, `$(System.DefaultWorkingDirectory)/MyApp/`.

This input can be used if tests are run in a Docker container.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="reportDirectory"::: -->
:::moniker range="<=azure-pipelines"


:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="additionalCodeCoverageFiles"::: -->
:::moniker range="<=azure-pipelines"

**`failIfCoverageEmpty`** - **Fail when code coverage results are missing**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fails the task if code coverage did not produce any results to publish.
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

Use this task in a build pipeline to publish code coverage results produced when running tests to Azure Pipelines or TFS and after generating the coverage xml files in order to obtain code coverage tab and coverage reporting details in the pipeline. The task supports code coverage generated xml formats. This task generates a cjson file which contains the code coverage details. It will also produce a code coverage HTML report under the build artifacts. 

This task is only supported in build pipelines, not release pipelines.

Tasks such as [Visual Studio Test](vstest-v2.md), [.NET Core](dotnet-core-cli-v2.md), [Ant](ant-v1.md), [Maven](maven-v2.md), [Gulp](gulp-v1.md), and [Grunt](grunt-v0.md) also provide the option to publish code coverage data to the pipeline. If you are using these tasks, you do not need a separate Publish Code Coverage Results task in the pipeline.

Prerequisite- To use the Publish Code Coverage Results v2 task in the pipeline, please use the [dotnet 2.1.x] (https://learn.microsoft.com/en-gb/azure/devops/pipelines/tasks/reference/use-dotnet-v2?view=azure-pipelines&viewFallbackFrom=azure-devops) task as a pre-requisite in the pipeline. Use the dotnet core task before the Publish Code Coverage v2 task. 

1) Following is the configuration of the .Net core sdk task in the azure pipelines that is used before the Publish Code Coverage Results v2 task:

:::image type="content" source="media/dotnet-core-sdk.png" alt-text="Screenshot that shows the .Net Core Sdk task in the pipeline.":::

2) Following is the Configuration of the Publish Code Coverage Results version 2 task in the azure pipelines:

:::image type="content" source="media/publish-code-coverage-resultsv2.png" alt-text="Screenshot that shows the Publish Code Coverage Results v2 task":::

3) Once, the build completes and the Publish Code Coverage Results v2 task succeedes , Following view of the Code coverage tab would be displayed in the UI of the build pipeline. 

:::image type="content" source="media/cjson-codecoverage-UI.png" alt-text="Screenshot that shows the Code Coverage tab generated by the Publish Code coverage V2 task":::

### Code coverage results for JavaScript with Istanbul using YAML

To publish code coverage results for JavaScript with Istanbul using YAML, see [JavaScript](/azure/devops/pipelines/ecosystems/javascript) in the Ecosystems section of these topics, which also includes examples for other languages.

See an [example of publishing code coverage using Cobertura](/azure/devops/pipelines/ecosystems/javascript#publish-code-coverage-results).

## Docker

For apps using Docker, build and tests may run inside the container and generate code coverage results within the container. In order to publish the results to the pipeline, the resulting artifacts should be made available to the **Publish Code Coverage Results** task. For reference, you can see a similar example for publishing test results under the [Build, test, and publish results with a Docker file](publish-test-results-v2.md#docker) section for **Docker**.

## View results

In order to view the code coverage results in the pipeline, see [Review code coverage results](/azure/devops/pipelines/test/review-code-coverage-results).

### Known issues

The publish code coverage results v2 task generates a cjson file and publishes the code coverage report under the code coverage tab. It also produces a build artifacts which is a set of HTML files that are linked from the main *index.html* file. If the code coverage tab fails to show the code coverage report, check whether the input code coverage xml file is in the correct format and has the valid details. 

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
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): Setting variables is disabled |
| Agent version |  2.182.1 or greater |
| Task category | Test |

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
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
## See also

* [Publish Test Results](publish-test-results-v2.md)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
