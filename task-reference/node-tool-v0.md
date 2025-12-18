---
title: NodeTool@0 - Node.js tool installer v0 task
description: Finds or downloads and caches the specified version spec of Node.js and adds it to the PATH.
ms.date: 11/11/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# NodeTool@0 - Node.js tool installer v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to find, download, and cache a specified version of [Node.js](https://nodejs.org/en/) and add it to the PATH.

There is a newer version of the task available. For more information, see [UseNode@1](./use-node-v1.md).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.2"

```yaml
# Use Node.js ecosystem v0
# Finds or downloads and caches the specified version spec of Node.js and adds it to the PATH.
- task: NodeTool@0
  inputs:
    versionSource: 'spec' # 'spec' | 'fromFile'. Required. Source of version. Default: spec.
    #versionSpec: '6.x' # string. Optional. Use when versionSource = spec. Version Spec. Default: 6.x.
    #versionFilePath: # string. Optional. Use when versionSource = fromFile. Path to the .nvmrc file. 
    #checkLatest: false # boolean. Check for Latest Version. Default: false.
    #force32bit: false # boolean. Use 32 bit version on x64 agents. Default: false.
  # Advanced
    #nodejsMirror: 'https://nodejs.org/dist' # string. Set source for Node.js binaries. Default: https://nodejs.org/dist.
    #retryCountOnDownloadFails: '5' # string. Set retry count when nodes downloads failed. Default: 5.
    #delayBetweenRetries: '1000' # string. Set delay between retries. Default: 1000.
```

:::moniker-end

:::moniker range="=azure-pipelines-2022.1"

```yaml
# Use Node.js ecosystem v0
# Finds or downloads and caches the specified version spec of Node.js and adds it to the PATH.
- task: NodeTool@0
  inputs:
    versionSource: 'spec' # 'spec' | 'fromFile'. Required. Source of version. Default: spec.
    #versionSpec: '6.x' # string. Optional. Use when versionSource = spec. Version Spec. Default: 6.x.
    #versionFilePath: # string. Optional. Use when versionSource = fromFile. Path to the .nvmrc file. 
    #checkLatest: false # boolean. Check for Latest Version. Default: false.
    #force32bit: false # boolean. Use 32 bit version on x64 agents. Default: false.
  # Advanced
    #nodejsMirror: 'https://nodejs.org/dist' # string. Set source for Node.js binaries. Default: https://nodejs.org/dist.
```

:::moniker-end

:::moniker range="=azure-pipelines-2022"

```yaml
# Use Node.js ecosystem v0
# Finds or downloads and caches the specified version spec of Node.js and adds it to the PATH.
- task: NodeTool@0
  inputs:
    versionSpec: '6.x' # string. Required. Version Spec. Default: 6.x.
    #checkLatest: false # boolean. Check for Latest Version. Default: false.
    #force32bit: false # boolean. Use 32 bit version on x64 agents. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="versionSource"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`versionSource`** - **Source of version**<br>
`string`. Required. Allowed values: `spec` (Specify Node version), `fromFile` (Get version from file). Default value: `spec`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionSpec"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`versionSpec`** - **Version Spec**<br>
`string`. Optional. Use when `versionSource = spec`. Default value: `6.x`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version spec of the version to get. Examples: `6.x`, `4.x`, `6.10.0`, `>=6.10.0`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2022"

**`versionSpec`** - **Version Spec**<br>
`string`. Required. Default value: `6.x`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version spec of the version to get. Examples: `6.x`, `4.x`, `6.10.0`, `>=6.10.0`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="versionFilePath"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`versionFilePath`** - **Path to the .nvmrc file**<br>
`string`. Optional. Use when `versionSource = fromFile`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File path to get version.  Example: src/.nvmrc.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkLatest"::: -->
:::moniker range="<=azure-pipelines"

**`checkLatest`** - **Check for Latest Version**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the agent to check for the latest available version that satisfies the version spec. For example, you select this option because you run this build on your [self-hosted agent](/azure/devops/pipelines/agents/agents), and you want to always use the latest `6.x` version.

> [!TIP]
> If you're using [the Microsoft-hosted agents](/azure/devops/pipelines/agents/hosted), you should leave this set to `false`. Microsoft updates the Microsoft-hosted agents on a regular basis, but they're often slightly behind the latest version. Enabling this parameter could result in your build spending a lot of time updating to a newer minor version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="force32bit"::: -->
:::moniker range="<=azure-pipelines"

**`force32bit`** - **Use 32 bit version on x64 agents**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Installs the `x86` version of Node regardless of the CPU architecture of the agent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nodejsMirror"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`nodejsMirror`** - **Set source for Node.js binaries**<br>
`string`. Default value: `https://nodejs.org/dist`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use an alternative installation mirror when sourcing the Node.js binaries.
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
## Remarks

There is a newer version of the task available. For more information, see [UseNode@1](./use-node-v1.md).
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
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: Node, npm, node.js |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task runs using the following [command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): restricted |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): PATH |
| Agent version |  2.182.1 or greater |
| Task category | Tool |

:::moniker-end

<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

For an explanation of tool installers and examples, see [Tool installers](/azure/devops/pipelines/process/tasks#tool-installers).
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->