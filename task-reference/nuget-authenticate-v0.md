---
title: NuGetAuthenticate@0 - NuGet authenticate v0 task
description: This version of the task is deprecated, use NuGetAuthenticateV1 instead. Configure NuGet tools to authenticate with Azure Artifacts and other NuGet repositories. Requires NuGet >= 4.8.5385, dotnet >= 2.1.400, or MSBuild >= 15.8.166.59604.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2020"
---

# NuGetAuthenticate@0 - NuGet authenticate v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::editable-content name="description"::: -->
This version of the task is deprecated, use NuGetAuthenticateV1 instead. Configure NuGet tools to authenticate with Azure Artifacts and other NuGet repositories. Requires NuGet >= 4.8.5385, dotnet >= 2.1.400, or MSBuild >= 15.8.166.59604.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

<!-- :::editable-content name="description"::: -->
Configure NuGet tools to authenticate with Azure Artifacts and other NuGet repositories. Requires NuGet >= 4.8.5385, dotnet >= 2.1.400, or MSBuild >= 15.8.166.59604.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# NuGet authenticate v0
# This version of the task is deprecated, use NuGetAuthenticateV1 instead. Configure NuGet tools to authenticate with Azure Artifacts and other NuGet repositories. Requires NuGet >= 4.8.5385, dotnet >= 2.1.400, or MSBuild >= 15.8.166.59604.
- task: NuGetAuthenticate@0
  inputs:
    #nuGetServiceConnections: # string. Service connection credentials for feeds outside this organization. 
    #forceReinstallCredentialProvider: false # boolean. Reinstall the credential provider even if already installed. Default: false.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

```yaml
# NuGet authenticate v0
# Configure NuGet tools to authenticate with Azure Artifacts and other NuGet repositories. Requires NuGet >= 4.8.5385, dotnet >= 2.1.400, or MSBuild >= 15.8.166.59604.
- task: NuGetAuthenticate@0
  inputs:
    #nuGetServiceConnections: # string. Service connection credentials for feeds outside this organization. 
    #forceReinstallCredentialProvider: false # boolean. Reinstall the credential provider even if already installed. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="nuGetServiceConnections"::: -->
:::moniker range=">=azure-pipelines-2020"

**`nuGetServiceConnections`** - **Service connection credentials for feeds outside this organization**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of NuGet service connection names for feeds outside this organization/collection. For feeds in this organization/collection, leave this blank; the build’s credentials are used automatically.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="forceReinstallCredentialProvider"::: -->
:::moniker range=">=azure-pipelines-2020"

**`forceReinstallCredentialProvider`** - **Reinstall the credential provider even if already installed**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the credential provider is already installed in the user profile, determines if it is overwritten with the task-provided credential provider. This may upgrade (or potentially downgrade) the credential provider.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020"

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

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.120.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->