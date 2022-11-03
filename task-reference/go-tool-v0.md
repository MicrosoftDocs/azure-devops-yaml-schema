---
title: GoTool@0 - Go tool installer v0 task
description: Find in cache or download a specific version of Go and add it to the PATH.
ms.date: 11/03/2022
monikerRange: ">=azure-pipelines-2019"
---

# GoTool@0 - Go tool installer v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to find in the tools cache or download a specific version of Go and add it to the PATH.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Finds or downloads a specific version of Go in the tools cache and adds it to the PATH. Use this task to set the version of Go used in subsequent tasks.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Go tool installer v0
# Find in cache or download a specific version of Go and add it to the PATH.
- task: GoTool@0
  inputs:
    version: '1.10' # string. Required. Version. Default: 1.10.
  # Advanced
    #goPath: # string. GOPATH. 
    #goBin: # string. GOBIN.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Go Tool Installer v0
# Finds or downloads a specific version of Go in the tools cache and adds it to the PATH. Use this to set the version of Go used in subsequent tasks.
- task: GoTool@0
  inputs:
    version: '1.10' # string. Required. Version. Default: 1.10.
  # Advanced
    #goPath: # string. GOPATH. 
    #goBin: # string. GOBIN.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="version"::: -->
:::moniker range=">=azure-pipelines-2019"

**`version`** - **Version**<br>
`string`. Required. Default value: `1.10`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Go version to download (if necessary) and use, for example `1.9.3`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="goPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`goPath`** - **GOPATH**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A custom value for the GOPATH environment variable.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="goBin"::: -->
:::moniker range=">=azure-pipelines-2019"

**`goBin`** - **GOBIN**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A custom value for the GOBIN environment variable.
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

Use this task to find or download a specific version of the Go tool into the tools cache and add it to the PATH. Use the task to change the version of Go Lang used in subsequent tasks.
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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: GO |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Tool |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->