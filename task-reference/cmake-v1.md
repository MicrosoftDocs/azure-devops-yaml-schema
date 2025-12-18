---
title: CMake@1 - CMake v1 task
description: Build with the CMake cross-platform build system.
ms.date: 12/18/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022"
---

# CMake@1 - CMake v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to build with the CMake cross-platform build system.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# CMake v1
# Build with the CMake cross-platform build system.
- task: CMake@1
  inputs:
    #workingDirectory: 'build' # string. Alias: cwd. Working Directory. Default: build.
    #cmakeArgs: # string. Arguments. 
  # Advanced
    #runInsideShell: false # boolean. Run cmake command inside shell. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working Directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `cwd`. `string`. Default value: `build`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The current working directory when CMake is run.

If you specify a relative path, then it is relative to your repo. For example, if you specify `build`, the result is the same as if you specified `$(Build.SourcesDirectory)\build`.

You can also specify a full path outside the repo, and you can use [variables](/azure/devops/pipelines/build/variables). For example: `$(Build.ArtifactStagingDirectory)\build`

If the path you specify does not exist, CMake creates it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cmakeArgs"::: -->
:::moniker range="<=azure-pipelines"

**`cmakeArgs`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The arguments passed to CMake.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runInsideShell"::: -->
:::moniker range="<=azure-pipelines"

**`runInsideShell`** - **Run cmake command inside shell**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
CMake arguments are handled the same way as they are handled inside of an OS specific shell. This input can be used to handle environment variables inside of argument strings.
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

Use this task to build with the CMake cross-platform build system.

### How do I enable CMake for Microsoft-hosted agents?

The [Microsoft-hosted agents](/azure/devops/pipelines/agents/hosted) have CMake installed already, so you don't need to do anything. You do not need to add a demand for CMake in your `azure-pipelines.yml` file.

### How do I enable CMake for my on-premises agent?

1. [Deploy an agent](/azure/devops/pipelines/agents/agents#install).

1. On your agent machine, [install CMake](https://cmake.org/install/) and make sure to add it to the user's path that the agent is running as.

1. In your web browser, go to **Agent pools** and [add a capability](/azure/devops/pipelines/process/demands#manually-entered-demands) named `cmake`. Set its value to `yes`.

### How does CMake work? What arguments can I use?

* [About CMake](https://cmake.org/overview/)
* [CMake documentation](https://cmake.org/documentation/)
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: cmake |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.91.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->