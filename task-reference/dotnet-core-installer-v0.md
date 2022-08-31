---
title: DotNetCoreInstaller@0 - .NET Core SDK/runtime installer v0 task
description: Acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH (task version 0).
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# DotNetCoreInstaller@0 - .NET Core SDK/runtime installer v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# .NET Core SDK/runtime installer v0
# Acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH.
- task: DotNetCoreInstaller@0
  inputs:
    packageType: 'sdk' # 'runtime' | 'sdk'. Required. Package to install. Default: 'sdk'.
    version: '1.0.4' # string. Required. Version. Default: '1.0.4'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="packageType"::: -->
:::moniker range="<=azure-pipelines"

**`packageType`** - **Package to install**<br>
Type: string. Required. Allowed values: 'runtime', 'sdk'. Default value: 'sdk'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Please select whether to install only runtime or full SDK.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range="<=azure-pipelines"

**`version`** - **Version**<br>
Type: string. Required. Default value: '1.0.4'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify exact version of .NET Core SDK or runtime to install.<br/>Find the value of `version-sdk` for installing SDK, or `version-runtime` for installing Runtime from any releases [here](https://github.com/microsoft/azure-pipelines-tasks/blob/master/Tasks/DotNetCoreInstallerV0/externals/releases.json).
 **NOTE: the task will not work with new versions of .NET Core. Kindly upgrade to 2.\* version of the task to download latest versions od .NET Core.**.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | Running this task satisfies the following [demands](/azure/devops/pipelines/process/demands) for any subsequent tasks in the same job: DotNetCore |
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