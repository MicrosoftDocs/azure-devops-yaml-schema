---
title: ContainerStructureTest@0 - Container Structure Test v0 task
description: Uses container-structure-test (https://github.com/GoogleContainerTools/container-structure-test) to validate the structure of an image based on four categories of tests - command tests, file existence tests, file content tests and metadata tests.
ms.date: 11/10/2022
monikerRange: ">=azure-pipelines-2020"
---

# ContainerStructureTest@0 - Container Structure Test v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Uses container-structure-test (https://github.com/GoogleContainerTools/container-structure-test) to validate the structure of an image based on four categories of tests - command tests, file existence tests, file content tests and metadata tests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Container Structure Test v0
# Uses container-structure-test (https://github.com/GoogleContainerTools/container-structure-test) to validate the structure of an image based on four categories of tests - command tests, file existence tests, file content tests and metadata tests.
- task: ContainerStructureTest@0
  inputs:
  # Container Repository
    dockerRegistryServiceConnection: # string. Required. Docker registry service connection. 
    repository: # string. Required. Container repository. 
    #tag: '$(Build.BuildId)' # string. Tag. Default: $(Build.BuildId).
    configFile: # string. Required. Config file path. 
    #testRunTitle: # string. Test run title. 
    #failTaskOnFailedTests: false # boolean. Fail task if there are test failures. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="dockerRegistryServiceConnection"::: -->
:::moniker range=">=azure-pipelines-2020"

**`dockerRegistryServiceConnection`** - **Docker registry service connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a Docker registry service connection. Required for commands that need to authenticate with a registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="repository"::: -->
:::moniker range=">=azure-pipelines-2020"

**`repository`** - **Container repository**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the repository.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tag"::: -->
:::moniker range=">=azure-pipelines-2020"

**`tag`** - **Tag**<br>
`string`. Default value: `$(Build.BuildId)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The tag is used in pulling the image from docker registry service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configFile"::: -->
:::moniker range=">=azure-pipelines-2020"

**`configFile`** - **Config file path**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The config file path that contains container structure tests, either in .yaml or .json file formats.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range=">=azure-pipelines-2020"

**`testRunTitle`** - **Test run title**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify a name for the Test Run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failTaskOnFailedTests"::: -->
:::moniker range=">=azure-pipelines-2020"

**`failTaskOnFailedTests`** - **Fail task if there are test failures**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fails the task if there are any test failures. Check this option to fail the task if test failures are detected.
<!-- :::editable-content-end::: -->
<br>

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
## Remarks

This task helps you run container structure tests and publish test results to Azure Pipelines and provides a comprehensive test reporting and analytics experience.

> [!NOTE]
> This is an early preview feature. More upcoming features will be rolled out in upcoming sprints.

The Container Structure Tests provide a powerful framework to validate the structure of a container image. These tests can be used to check the output of commands in an image, as well as verify metadata and contents of the filesystem. Tests can be run either through a standalone binary, or through a Docker image. 

Tests within this framework are specified through a YAML or JSON config file. Multiple config files may be specified in a single test run. The config file will be loaded in by the test runner, which will execute the tests in order. Within this config file, four types of tests can be written:

* Command Tests (testing output/error of a specific command issued)
* File Existence Tests (making sure a file is, or isn't, present in the file system of the image)
* File Content Tests (making sure files in the file system of the image contain, or do not contain, specific contents)
* Metadata Test, singular (making sure certain container metadata is correct)

### Build, Test and Publish Test

The container structure test task can be added in the classic pipeline as well as in unified pipeline (multi-stage) & YAML based pipelines.

# [YAML](#tab/yaml)

In the new YAML based unified pipeline, you can search for task in the window.

> [!div class="mx-imgBorder"]
> ![Container Test in Unified Pipeline](media/unified-pipeline-creation.png)

Once the task is added, you need to set the config file path, docker registory service connection, container repository and tag, if required. Task input in the yaml based pipeline is created.

> [!div class="mx-imgBorder"]
> ![Container Test in YAML based Pipeline](media/yaml-based-pipeline.png)

### YAML file

> [!div class="mx-imgBorder"]
> ![YAML file](media/yaml-file.png)

```yml
steps:
- task: ContainerStructureTest@0
  displayName: 'Container Structure Test '
  inputs:
    dockerRegistryServiceConnection: 'Container_dockerHub'
    repository: adma/hellodocker
    tag: v1
    configFile: /home/user/cstfiles/fileexisttest.yaml
```

# [Classic](#tab/classic)

In the classic pipeline, you can add this task from the designer view. 

> [!div class="mx-imgBorder"]
> ![Container Test in Classic Pipeline](media/classic-pipeline-creation.png)

* * *

### View test report

Once the task is executed, you can directly go to test tab to view the full report. The published test results are displayed in the [Tests tab](/azure/devops/pipelines/test/review-continuous-test-results-after-build)
in the pipeline summary and help you to measure pipeline quality, review traceability,
troubleshoot failures, and drive failure ownership.

> [!div class="mx-imgBorder"]
> ![Test Reporting Page](media/results-page.png)
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
| Task category | Test |

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
| Agent version |  2.0.0 or greater |
| Task category | Test |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->