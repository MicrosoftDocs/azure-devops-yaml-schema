---
title: KubectlInstaller@0 - Kubectl tool installer v0 task
description: Install Kubectl on agent machine.
ms.date: 09/08/2023
monikerRange: ">=azure-pipelines-2019.1"
---

# KubectlInstaller@0 - Kubectl tool installer v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task for installing a specific version of kubectl binary on agents.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Kubectl tool installer v0
# Install Kubectl on agent machine.
- task: KubectlInstaller@0
  inputs:
    #kubectlVersion: 'latest' # string. Kubectl Version Spec. Default: latest.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="kubectlVersion"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`kubectlVersion`** - **Kubectl Version Spec**<br>
`string`. Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of kubectl to install. The acceptable values are `latest` or any semantic version string, e.g. `1.15.0`.
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

This task is used for installing a specific version of kubectl binary on agents.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

The following YAML example showcases the installation of latest version of kubectl binary on the agent:

```YAML
- task: KubectlInstaller@0
  displayName: Kubectl installer
  inputs: 
    kubectlVersion: latest
```

The following YAML example demonstrates the use of an explicit version string rather than installing the latest version available at the time of task execution:

```YAML
- task: KubectlInstaller@0
  displayName: Kubectl installer
  inputs: 
    kubectlVersion: 1.15.0
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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: Kubectl |
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