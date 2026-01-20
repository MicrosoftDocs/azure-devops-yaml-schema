---
title: GoTool@0 - Go tool installer v0 task
description: Find in cache or download a specific version of Go and add it to the PATH.
ms.date: 01/20/2026
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022"
---

# GoTool@0 - Go tool installer v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to find in the tools cache or download a specific version of Go and add it to the PATH.
<!-- :::editable-content-end::: -->

:::moniker-end

<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Go tool installer v0
# Find in cache or download a specific version of Go and add it to the PATH.
- task: GoTool@0
  inputs:
    version: '1.10' # string. Required. Version. Default: 1.10.
  # Advanced
    #goPath: # string. GOPATH. 
    #goBin: # string. GOBIN. 
    #goDownloadUrl: 'https://go.dev/dl' # string. Go download URL. Default: https://go.dev/dl.
```

:::moniker-end

:::moniker range="<=azure-pipelines-server"

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

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="version"::: -->
:::moniker range="<=azure-pipelines"

**`version`** - **Version**<br>
`string`. Required. Default value: `1.10`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Go version to download (if necessary) and use, for example `1.9.3`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="goPath"::: -->
:::moniker range="<=azure-pipelines"

**`goPath`** - **GOPATH**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A custom value for the GOPATH environment variable.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="goBin"::: -->
:::moniker range="<=azure-pipelines"

**`goBin`** - **GOBIN**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A custom value for the GOBIN environment variable.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="goDownloadUrl"::: -->
:::moniker range=">azure-pipelines-server"

**`goDownloadUrl`** - **Go download URL**<br>
`string`. Default value: `https://go.dev/dl`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
URL for downloading Go binaries. The following values are supported:

- `https://go.dev/dl` - [Official Go distribution](https://go.dev/dl). This is the default if this parameter is not set.
- `https://aka.ms/golang/release/latest` - the [Microsoft build of Go](https://github.com/microsoft/go) prefix, a fork of the official Go distribution. See [the Migration Guide](https://github.com/microsoft/go/blob/microsoft/main/eng/doc/MigrationGuide.md) for an introduction to the Microsoft build of Go.

> [!NOTE]
> You can optionally specify the download URL for Go binaries by setting the `GOTOOL_GODOWNLOADURL` environment variable. If both the **Go download URL** task parameter and the `GOTOOL_GODOWNLOADURL` environment variable are set, the task parameter takes precedence.
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

Use this task to find or download a specific version of the Go tool into the tools cache and add it to the PATH. Use the task to change the version of Go Lang used in subsequent tasks.
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