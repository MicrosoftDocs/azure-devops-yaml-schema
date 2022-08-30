---
title: Go@0 - Go v0 task
description: Get, build, or test a Go application, or run a custom Go command.
ms.date: 08/10/2022
monikerRange: ">=azure-pipelines-2019"
---

# Go@0 - Go v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Get, build, or test a Go application, or run a custom Go command.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Go v0
# Get, build, or test a Go application, or run a custom Go command.
- task: Go@0
  inputs:
    command: 'get' # 'get' | 'build' | 'test' | 'custom'. Required. Command. Default: 'get'.
    #customCommand: # string. Required when command == custom. Custom command. 
    #arguments: # string. Arguments. 
  # Advanced
    #workingDirectory: # string. Working directory.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="command"::: -->
:::moniker range=">=azure-pipelines-2019"

**`command`** - **Command**<br>
Type: string. Required. Allowed values: 'get', 'build', 'test', 'custom'. Default value: 'get'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Go command to run. Select 'Custom' to use a command not listed here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customCommand"::: -->
:::moniker range=">=azure-pipelines-2019"

**`customCommand`** - **Custom command**<br>
Type: string. Required when command == custom.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A custom Go command to execute. For example, to execute 'go version', enter 'version'.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range=">=azure-pipelines-2019"

**`arguments`** - **Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional arguments to the selected command. For example, build-time arguments for the 'go build' command.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`workingDirectory`** - **Working directory**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The working directory where the command will run. When empty, the root of the repository (for builds) or artifacts (for releases) is used, which is the value of '$(System.DefaultWorkingDirectory)'.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019"

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

:::moniker range=">=azure-pipelines-2019"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->