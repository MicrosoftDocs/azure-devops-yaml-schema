---
title: HelmInstaller@0 - Helm tool installer v0 task
description: Install Helm and Kubernetes on an agent machine (task version 0).
ms.date: 09/26/2022
monikerRange: ">=azure-pipelines-2019"
---

# HelmInstaller@0 - Helm tool installer v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to install Helm and Kubernetes on an agent machine.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to install Helm and Kubernetes on an agent machine.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Helm tool installer v0
# Install Helm and Kubernetes on an agent machine.
- task: HelmInstaller@0
  inputs:
    helmVersion: '2.14.1' # string. Required. Helm Version Spec. Default: 2.14.1.
    #checkLatestHelmVersion: true # boolean. Check for latest version of Helm. Default: true.
  # Prerequisite
    installKubeCtl: true # boolean. Required. Install Kubectl. Default: true.
    #kubectlVersion: '1.8.9' # string. Optional. Use when installKubeCtl == true. Kubectl Version Spec. Default: 1.8.9.
    #checkLatestKubeCtl: true # boolean. Optional. Use when installKubeCtl == true. Check for latest version of kubectl. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Helm tool installer v0
# Install Helm and Kubernetes on an agent machine.
- task: HelmInstaller@0
  inputs:
    helmVersion: '2.9.1' # string. Required. Helm Version Spec. Default: 2.9.1.
    #checkLatestHelmVersion: true # boolean. Check for latest version of Helm. Default: true.
  # Prerequisite
    installKubeCtl: true # boolean. Required. Install Kubectl. Default: true.
    #kubectlVersion: '1.8.9' # string. Optional. Use when installKubeCtl == true. Kubectl Version Spec. Default: 1.8.9.
    #checkLatestKubeCtl: true # boolean. Optional. Use when installKubeCtl == true. Check for latest version of kubectl. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Helm tool installer v0
# Install Helm and Kubernetes on agent machine.
- task: HelmInstaller@0
  inputs:
    helmVersion: '2.9.1' # string. Required. Helm Version Spec. Default: 2.9.1.
    #checkLatestHelmVersion: true # boolean. Check for latest version of Helm. Default: true.
  # Prerequisite
    installKubeCtl: true # boolean. Required. Install Kubectl. Default: true.
    #kubectlVersion: '1.8.9' # string. Optional. Use when installKubeCtl == true. Kubectl Version Spec. Default: 1.8.9.
    #checkLatestKubeCtl: true # boolean. Optional. Use when installKubeCtl == true. Check for latest version of kubectl. Default: true.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="helmVersion"::: -->
:::moniker range=">=azure-pipelines-2020"

**`helmVersion`** - **Helm Version Spec**<br>
`string`. Required. Default value: `2.14.1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of Helm to install.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

**`helmVersion`** - **Helm Version Spec**<br>
`string`. Required. Default value: `2.9.1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of Helm to install.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkLatestHelmVersion"::: -->
:::moniker range=">=azure-pipelines-2019"

**`checkLatestHelmVersion`** - **Check for latest version of Helm**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Checks for the latest version of Helm.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="installKubeCtl"::: -->
:::moniker range=">=azure-pipelines-2019"

**`installKubeCtl`** - **Install Kubectl**<br>
`boolean`. Required. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Installs Kubectl.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="kubectlVersion"::: -->
:::moniker range=">=azure-pipelines-2019"

**`kubectlVersion`** - **Kubectl Version Spec**<br>
`string`. Optional. Use when `installKubeCtl == true`. Default value: `1.8.9`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of Kubectl to install.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkLatestKubeCtl"::: -->
:::moniker range=">=azure-pipelines-2019"

**`checkLatestKubeCtl`** - **Check for latest version of kubectl**<br>
`boolean`. Optional. Use when `installKubeCtl == true`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Checks for the latest version of Kubectl.
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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: Helm |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Tool |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->