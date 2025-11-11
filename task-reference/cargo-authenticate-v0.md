---
title: CargoAuthenticate@0 - Cargo authenticate (for task runners) v0 task
description: Authentication task for the cargo client used for installing Cargo crates distribution.
ms.date: 11/11/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1"
author: ramiMSFT
ms.author: rabououn
---

# CargoAuthenticate@0 - Cargo authenticate (for task runners) v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2022.1"

<!-- :::editable-content name="description"::: -->
Authentication task for the cargo client used for installing Cargo crates.

> [!NOTE]
> Cargo support in Azure Artifacts is currently in preview.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.1"

```yaml
# Cargo authenticate (for task runners) v0
# Authentication task for the cargo client used for installing Cargo crates distribution.
- task: CargoAuthenticate@0
  inputs:
    configFile: # string. Required. config.toml file to authenticate. 
    #cargoServiceConnections: # string. Credentials for registries outside this organization/collection.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="configFile"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`configFile`** - **config.toml file to authenticate**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the config.toml file that specifies the registries you want to work with. Select the file, not the folder e.g. "/.cargo/config.toml".
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cargoServiceConnections"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`cargoServiceConnections`** - **Credentials for registries outside this organization/collection**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Credentials to use for external registries located in the project's config.toml. For registries in this organization/collection, don't specify this attribute; the build’s credentials are used automatically.

Use the [task assistant](/azure/devops/pipelines/get-started/yaml-pipeline-editor#use-task-assistant) to select the desired service connections.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2022.1"

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

:::moniker range=">=azure-pipelines-2022.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->