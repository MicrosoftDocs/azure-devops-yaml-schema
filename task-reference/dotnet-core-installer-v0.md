---
title: DotNetCoreInstaller@0 - .NET Core SDK/runtime installer v0 task
description: Acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH (task version 0).
ms.date: 11/30/2023
monikerRange: "<=azure-pipelines"
---

# DotNetCoreInstaller@0 - .NET Core SDK/runtime installer v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to acquire a specific version of the .NET Core SDK from the internet or local cache and add it to the PATH.

> [!IMPORTANT]
> This task is deprecated. Use [UseDotNet@2](use-dotnet-v2.md).
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
    packageType: 'sdk' # 'runtime' | 'sdk'. Required. Package to install. Default: sdk.
    version: '1.0.4' # string. Required. Version. Default: 1.0.4.
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
`string`. Required. Allowed values: `runtime`, `sdk` (SDK (contains runtime)). Default value: `sdk`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether to install only Runtime or the full SDK.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range="<=azure-pipelines"

**`version`** - **Version**<br>
`string`. Required. Default value: `1.0.4`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the exact version of the .NET Core SDK or Runtime to install.

Find the value of `version-sdk` for installing the SDK, or `version-runtime` for installing Runtime from any releases [in GitHub](https://github.com/microsoft/azure-pipelines-tasks/blob/master/Tasks/DotNetCoreInstallerV0/externals/releases.json).
 
> [!NOTE]
> The task won't work with new versions of .NET Core. Upgrade to [@UseDotNet2](use-dotnet-v2.md) of the task so you can download the latest versions of .NET Core.
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

This task is deprecated. Use [@UseDotNet2](use-dotnet-v2.md).
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
