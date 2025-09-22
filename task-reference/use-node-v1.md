---
title: UseNode@1 - Use Node.js ecosystem v1 task
description: Set up a Node.js environment and add it to the PATH, additionally providing proxy support.
ms.date: 09/22/2025
monikerRange: "=azure-pipelines || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
author: juliakm
ms.author: jukullam
---

# UseNode@1 - Use Node.js ecosystem v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to find, download, and cache a specified version of [Node.js](https://nodejs.org/) and add it to the PATH. This task also provides proxy support.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.2"

```yaml
# Use Node.js ecosystem v1
# Set up a Node.js environment and add it to the PATH, additionally providing proxy support.
- task: UseNode@1
  inputs:
    #version: '10.x' # string. Version. Default: 10.x.
    #checkLatest: false # boolean. Check for Latest Version. Default: false.
    #force32bit: false # boolean. Use 32 bit version on x64 agents. Default: false.
  # advanced
    #retryCountOnDownloadFails: '5' # string. Set retry count when nodes downloads failed. Default: 5.
    #delayBetweenRetries: '1000' # string. Set delay between retries. Default: 1000.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020.1 <=azure-pipelines-2022.1"

```yaml
# Use Node.js ecosystem v1
# Set up a Node.js environment and add it to the PATH, additionally providing proxy support.
- task: UseNode@1
  inputs:
    #version: '10.x' # string. Version. Default: 10.x.
    #checkLatest: false # boolean. Check for Latest Version. Default: false.
    #force32bit: false # boolean. Use 32 bit version on x64 agents. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Use Node.js ecosystem v1
# Set up a Node.js environment and add it to the PATH, additionally providing proxy support.
- task: UseNode@1
  inputs:
    #version: '10.x' # string. Version. Default: 10.x.
    #checkLatest: false # boolean. Check for Latest Version. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="version"::: -->
:::moniker range="<=azure-pipelines"

**`version`** - **Version**<br>
`string`. Default value: `10.x`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Required. Specifies the [Node.js version](https://nodejs.org/en/download/releases/) using SemVer's version range syntax. Examples: `10.x`, `10.15.1`, `>=10.15.0`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkLatest"::: -->
:::moniker range="<=azure-pipelines"

**`checkLatest`** - **Check for Latest Version**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Checks online for the latest available version that satisfies the version spec. This should be `false` unless you need to always have the latest version. Setting the value to `true` will cause the task to incur download costs that may be unnecessary, especially with the hosted build pool.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="force32bit"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`force32bit`** - **Use 32 bit version on x64 agents**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Installs the x86 version of Node.js on a 64-bit Windows agent. Only works on Windows agents.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="retryCountOnDownloadFails"::: -->
:::moniker range=">=azure-pipelines-2022.2"

**`retryCountOnDownloadFails`** - **Set retry count when nodes downloads failed**<br>
`string`. Default value: `5`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this option when the task failed to download node binaries from the mirror. The task will retry to download the binaries for the specified times.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="delayBetweenRetries"::: -->
:::moniker range=">=azure-pipelines-2022.2"

**`delayBetweenRetries`** - **Set delay between retries**<br>
`string`. Default value: `1000`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this option to set the delay between retries in milliseconds. The default value is 1000 milliseconds.
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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: Node, npm, node.js |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Tool |

:::moniker-end

<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->