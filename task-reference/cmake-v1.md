---
title: CMake@1 - CMake v1 task
description: Build with the CMake cross-platform build system.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# CMake@1 - CMake v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Build with the CMake cross-platform build system.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020.1"

```yaml
# CMake v1
# Build with the CMake cross-platform build system.
- task: CMake@1
  inputs:
    #workingDirectory: 'build' # string. Working Directory. Default: 'build'.
    #cmakeArgs: # string. Arguments. 
  # Advanced
    #runInsideShell: false # boolean. Run cmake command inside shell. Default: false.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020"

```yaml
# CMake v1
# Build with the CMake cross-platform build system.
- task: CMake@1
  inputs:
    #workingDirectory: 'build' # string. Working Directory. Default: 'build'.
    #cmakeArgs: # string. Arguments.
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

<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working Directory**<br>
Input alias: `cwd`. Type: string. Default value: 'build'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Current working directory when cmake is run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cmakeArgs"::: -->
:::moniker range="<=azure-pipelines"

**`cmakeArgs`** - **Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Arguments passed to cmake.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runInsideShell"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`runInsideShell`** - **Run cmake command inside shell**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
CMake arguments will be handled like they would be inside of an OS specific shell. It can be used to handle environment variables inside of argument strings.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

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