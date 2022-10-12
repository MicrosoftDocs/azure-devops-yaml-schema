---
title: DockerInstaller@0 - Docker CLI installer v0 task
description: Install Docker CLI on agent machine.
ms.date: 10/12/2022
monikerRange: ">=azure-pipelines-2019.1"
---

# DockerInstaller@0 - Docker CLI installer v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Install the Docker CLI on an agent machine.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Docker CLI installer v0
# Install Docker CLI on agent machine.
- task: DockerInstaller@0
  inputs:
    dockerVersion: '17.09.0-ce' # string. Required. Docker Version. Default: 17.09.0-ce.
    #releaseType: 'stable' # 'stable' | 'edge' | 'test' | 'nightly'. Release type. Default: stable.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="dockerVersion"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`dockerVersion`** - **Docker Version**<br>
`string`. Required. Default value: `17.09.0-ce`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of the Docker CLI to install.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="releaseType"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`releaseType`** - **Release type**<br>
`string`. Allowed values: `stable`, `edge`, `test`, `nightly`. Default value: `stable`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the release type to install. The value `nightly` is not supported on Windows.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019.1"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to install a specific version of
the Docker CLI on the agent machine.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

This YAML example installs the Docker CLI on the agent machine:

```YAML
- task: DockerInstaller@0
  displayName: Docker Installer
  inputs:
    dockerVersion: 17.09.0-ce
    releaseType: stable
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: Docker |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.142.1 or greater |
| Task category | Tool |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->