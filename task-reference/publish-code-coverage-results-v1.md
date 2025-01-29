---
title: PublishCodeCoverageResults@1 - Publish code coverage results v1 task
description: Publish Cobertura or JaCoCo code coverage results from a build.
ms.date: 01/29/2025
monikerRange: "<=azure-pipelines"
---

# PublishCodeCoverageResults@1 - Publish code coverage results v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to publish Cobertura or JaCoCo code coverage results from a build.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range=">=azure-pipelines-2022.1 <=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Publish Cobertura or JaCoCo code coverage results from a build.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022"

<!-- :::editable-content name="description"::: -->
Use this task to publish Cobertura or JaCoCo code coverage results from a build.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Publish code coverage results v1
# Publish Cobertura or JaCoCo code coverage results from a build.
- task: PublishCodeCoverageResults@1
  inputs:
    codeCoverageTool: 'JaCoCo' # 'Cobertura' | 'JaCoCo'. Required. Code coverage tool. Default: JaCoCo.
    summaryFileLocation: # string. Required. Summary file. 
    #pathToSources: # string. Path to Source files. 
    #reportDirectory: # string. Report directory. 
    #additionalCodeCoverageFiles: # string. Additional files. 
    #failIfCoverageEmpty: false # boolean. Fail when code coverage results are missing. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Publish Code Coverage Results v1
# Publish Cobertura or JaCoCo code coverage results from a build.
- task: PublishCodeCoverageResults@1
  inputs:
    codeCoverageTool: 'JaCoCo' # 'Cobertura' | 'JaCoCo'. Required. Code coverage tool. Default: JaCoCo.
    summaryFileLocation: # string. Required. Summary file. 
    #reportDirectory: # string. Report directory. 
    #additionalCodeCoverageFiles: # string. Additional files. 
    #failIfCoverageEmpty: false # boolean. Fail when code coverage results are missing. Default: false.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="codeCoverageTool"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageTool`** - **Code coverage tool**<br>
`string`. Required. Allowed values: `Cobertura`, `JaCoCo`. Default value: `JaCoCo`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the tool that generates code coverage results.
<!-- :::editable-content-end::: -->
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

Multiple sources can be added by delimiting each list item with the `;` character, for example `pathToSources: $(System.DefaultWorkingDirectory)/path/to/first/source;$(System.DefaultWorkingDirectory)/path/to/second/source`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="reportDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`reportDirectory`** - **Report directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path of the code coverage HTML report directory. The report directory is published for later viewing as an artifact of the build. The value may contain minimatch patterns. For example: `$(System.DefaultWorkingDirectory)/MyApp/**/site/cobertura`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="additionalCodeCoverageFiles"::: -->
:::moniker range="<=azure-pipelines"

**`additionalCodeCoverageFiles`** - **Additional files**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the file path pattern and notes any additional code coverage files to be published as artifacts of the build. The value may contain minimatch patterns. For example: `$(System.DefaultWorkingDirectory)/**/*.exec`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failIfCoverageEmpty"::: -->
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

:::moniker range=">azure-pipelines-2022.1"

:::moniker-end


Use this task in a build pipeline to publish code coverage results produced when running tests to Azure Pipelines or TFS in order to obtain coverage reporting. The task supports popular coverage result formats such as [Cobertura](https://cobertura.github.io/cobertura/) and [JaCoCo](https://www.eclemma.org/jacoco/).

This task is only supported in build pipelines, not release pipelines.

Tasks such as [Visual Studio Test](vstest-v2.md), [.NET Core](dotnet-core-cli-v2.md), [Ant](ant-v1.md), [Maven](maven-v2.md), [Gulp](gulp-v1.md), and [Grunt](grunt-v0.md) also provide the option to publish code coverage data to the pipeline. If you are using these tasks, you do not need a separate Publish Code Coverage Results task in the pipeline.

To generate the HTML code coverage report you need dotnet framework 2.0.0 or later on the agent. The dotnet folder must be in the environment path. If there are multiple folders containing dotnet, the one with version 2.0.0 must be before any others in the path list.

### Code coverage results for JavaScript with Istanbul using YAML

To publish code coverage results for JavaScript with Istanbul using YAML, see [Customize JavaScript](/azure/devops/pipelines/ecosystems/customize-javascript) in the Ecosystems section of these topics, which also includes examples for other languages.

See an [example of publishing code coverage using Cobertura](/azure/devops/pipelines/ecosystems/customize-javascript#publish-code-coverage-results).

## Docker

For apps using Docker, build and tests may run inside the container and generate code coverage results within the container. In order to publish the results to the pipeline, the resulting artifacts should be made available to the **Publish Code Coverage Results** task. For reference, you can see a similar example for publishing test results under the [Build, test, and publish results with a Docker file](publish-test-results-v2.md#docker) section for **Docker**.

## View results

In order to view the code coverage results in the pipeline, see [Review code coverage results](/azure/devops/pipelines/test/review-code-coverage-results).

### Is code coverage data merged when multiple files are provided as input to the task or multiple tasks are used in the pipeline?

At present, the code coverage reporting functionality provided by this task is limited, and it does not merge coverage data. If you provide multiple files as input to the task, only the first match is considered.
If you use multiple publish code coverage tasks in the pipeline, the summary and report is shown for the last task. Any previously uploaded data is ignored.

### Known issues

The publish code coverage results task generates and publishes the HTML report, which is a set of HTML files that are linked from the main *index.html* file. If the code coverage tab fails to show the code coverage report, check whether the size of the *index.html* file is close to or larger than 7 MB. Complete the following steps to check the size of the file. Then, if the file size is close to or larger than 7 MB, you can use the following workaround to view the coverage report.

1. Select the build **Summary** tab, and then select the **published** link:

   :::image type="content" source="media/publish-code-coverage-result-build-summary.png" alt-text="Screenshot that shows the published link in the Summary pane.":::

2. Next to the *Code Coverage Report_\** artifact, select **Download artifacts**:

   :::image type="content" source="media/publish-code-coverage-result-build-artifacts.png" alt-text="Screenshot that shows the Download artifacts link for the code coverage report under Artifacts.":::

3. When the code coverage report is downloaded, extract the .zip file.
4. In the code coverage report, check the size of *index.html* to help determine whether the file size is causing the issue described here.
5. Open *index.html* in a browser to view the code coverage report.
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
