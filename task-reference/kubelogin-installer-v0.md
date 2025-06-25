---
title: KubeloginInstaller@0 - Kubelogin tool installer v0 task
description: Helps to install kubelogin.
ms.date: 06/24/2025
monikerRange: "=azure-pipelines"
---

# KubeloginInstaller@0 - Kubelogin tool installer v0 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Installs kubelogin and adds it to the PATH of your agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Kubelogin tool installer v0
# Helps to install kubelogin.
- task: KubeloginInstaller@0
  inputs:
    #kubeloginVersion: 'latest' # string. kubelogin version. Default: latest.
    #gitHubConnection: # string. GitHub Connection.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="kubeloginVersion"::: -->
:::moniker range="=azure-pipelines"

**`kubeloginVersion`** - **kubelogin version**<br>
`string`. Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of kubelogin to use, for example `0.0.30`, or `latest` to use the latest version. For more information about kubelogin versions, see [kubelogin releases](https://github.com/Azure/kubelogin/releases).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="gitHubConnection"::: -->
:::moniker range="=azure-pipelines"

**`gitHubConnection`** - **GitHub Connection**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A GitHub connection is needed to prevent anonymous requests limits to the Github API for [Azure/kubelogin](https://github.com/azure/kubelogin) from impacting the installation. Leaving this empty may cause failures if the request limit is reached. This connection does not require ANY permissions.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

The kubelogin installer task acquires the specified version of [kubelogin](https://azure.github.io/kubelogin/index.html) from the internet or the tools cache and adds it to the PATH of the agent (hosted or private). Use this task to change the version of kubelogin used in subsequent tasks like [KubernetesManifest@1](./kubernetes-manifest-v1.md), [HelmDeploy@0](./helm-deploy-v0.md), [AzureFunctionOnKubernetes@1](./azure-function-on-kubernetes-v1.md), and [Kubernetes@1](./kubernetes-v1.md).

Adding `KubeloginInstaller@0` before the previously listed tasks in a build definition ensures that the desired kubelogin version is available at the time of building, testing and publishing your app.

The tool installer approach also allows you to decouple from the agent update cycles. If the kubelogin version you are looking for is missing from the agent (hosted or private), then you can use `KubeloginInstaller@0` to get the right version installed on the agent.

For more information on kubelogin, see [Non-interactive sign-in with kubelogin](/azure/aks/managed-azure-ad#non-interactive-sign-in-with-kubelogin).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

The following example shows how to install the latest version of kubelogin. The default value for `kubeloginVersion` is `latest`, so you can omit the `kubeloginVersion` input if desired.

```yml
- task: KubeloginInstaller@0

# Other tasks that depend on kubelogin
- task: HelmDeploy@0
  # task inputs...
```

To explicitly specify `kubeloginVersion`, use the following syntax.

```yml
- task: KubeloginInstaller@0
  inputs:
    kubeloginVersion: 'latest' # or a specific version like '0.0.30'
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: Kubelogin |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Tool |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Non-interactive sign-in with kubelogin](/azure/aks/managed-azure-ad#non-interactive-sign-in-with-kubelogin)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->