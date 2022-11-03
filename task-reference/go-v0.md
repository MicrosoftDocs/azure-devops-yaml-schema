---
title: Go@0 - Go v0 task
description: Get, build, or test a Go application, or run a custom Go command.
ms.date: 11/03/2022
monikerRange: ">=azure-pipelines-2019"
---

# Go@0 - Go v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to get, build, or test a Go application, or to run a custom Go command.
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
    command: 'get' # 'get' | 'build' | 'test' | 'custom'. Required. Command. Default: get.
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
`string`. Required. Allowed values: `get`, `build`, `test`, `custom`. Default value: `get`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a Go command to run. Use `Custom` to run a command not listed here.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customCommand"::: -->
:::moniker range=">=azure-pipelines-2019"

**`customCommand`** - **Custom command**<br>
`string`. Required when `command == custom`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A custom Go command to execute. For example, to execute `go version`, use `version`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range=">=azure-pipelines-2019"

**`arguments`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The optional arguments to the selected command. For example, use build-time arguments for the `go build` command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`workingDirectory`** - **Working directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The working directory where you want the command to run. When empty, the root of the repository (for builds) or artifacts (for releases) is used, which is the value of `$(System.DefaultWorkingDirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to get, build, or test a Go application, or to run a custom Go command.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yml
variables:
  GOBIN:  '$(GOPATH)/bin' # Go binaries path
  GOROOT: '/usr/local/go1.11' # Go installation path
  GOPATH: '$(system.defaultWorkingDirectory)/gopath' # Go workspace path
  modulePath: '$(GOPATH)/src/github.com/$(build.repository.name)' # Path to the module's code

steps:
- task: GoTool@0
  displayName: 'Use Go 1.10'

- task: Go@0
  displayName: 'go get'
  inputs:
    arguments: '-d'

- task: Go@0
  displayName: 'go build'
  inputs:
    command: build
    arguments: '-o "$(System.TeamProject).exe"'

- task: ArchiveFiles@2
  displayName: 'Archive files'
  inputs:
    rootFolderOrFile: '$(Build.Repository.LocalPath)'
    includeRootFolder: False

- task: PublishBuildArtifacts@1
  displayName: 'Publish artifact'
  condition: succeededOrFailed()
```
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