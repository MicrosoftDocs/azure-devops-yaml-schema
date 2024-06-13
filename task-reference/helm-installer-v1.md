---
title: HelmInstaller@1 - Helm tool installer v1 task
description: Install Helm on an agent machine.
ms.date: 06/11/2024
monikerRange: ">=azure-pipelines-2019.1"
---

# HelmInstaller@1 - Helm tool installer v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to install Helm on an agent machine.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Helm tool installer v1
# Install Helm on an agent machine.
- task: HelmInstaller@1
  inputs:
    #helmVersionToInstall: 'latest' # string. Helm Version Spec. Default: latest.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="helmVersionToInstall"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`helmVersionToInstall`** - **Helm Version Spec**<br>
`string`. Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of Helm to install. Acceptable values include any semantic version string, like `2.14.1`.
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

This task can be used for installing a specific version of helm binary on agents.

### Troubleshooting

#### HelmInstaller task running on a private agent behind a proxy fails to download helm package

The HelmInstaller task does not use the proxy settings to download the file `https://get.helm.sh/helm-v3.1.0-linux-amd64.zip`. You can work around this by pre-installing Helm on your private agents.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

The following YAML example showcases the installation of latest version of helm binary on the agent - 

```YAML
- task: HelmInstaller@1
  displayName: Helm installer
  inputs: 
    helmVersionToInstall: latest
```

The following YAML example demonstrates the use of an explicit version string rather than installing the latest version available at the time of task execution - 

```YAML
- task: HelmInstaller@1
  displayName: Helm installer
  inputs: 
    helmVersionToInstall: 2.14.1
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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: Helm |
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