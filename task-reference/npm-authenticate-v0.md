---
title: npmAuthenticate@0 - npm authenticate (for task runners) v0 task
description: Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like gulp and Grunt to authenticate with private registries.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# npmAuthenticate@0 - npm authenticate (for task runners) v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like gulp and Grunt to authenticate with private registries.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like Gulp and Grunt to authenticate with private registries.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# npm authenticate (for task runners) v0
# Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like gulp and Grunt to authenticate with private registries.
- task: npmAuthenticate@0
  inputs:
    workingFile: # string. Required. .npmrc file to authenticate. 
    #customEndpoint: # string. Credentials for registries outside this organization/collection.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
# npm Authenticate (for task runners) v0
# Don't use this task if you're also using the npm task. Provides npm credentials to an .npmrc file in your repository for the scope of the build. This enables npm task runners like Gulp and Grunt to authenticate with private registries.
- task: npmAuthenticate@0
  inputs:
    #workingFile: # string. .npmrc file to authenticate. 
    #customEndpoint: # string. Credentials for registries outside this account/collection.
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

<!-- :::item name="workingFile"::: -->
:::moniker range=">=azure-pipelines-2020"

**`workingFile`** - **.npmrc file to authenticate**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the .npmrc file that specifies the registries you want to work with. Select the file, not the folder e.g. "/packages/mypackage.npmrc".
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`workingFile`** - **.npmrc file to authenticate**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the .npmrc file that specifies the registries you want to work with. Select the file, not the folder e.g. "/packages/mypackage.npmrc".
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customEndpoint"::: -->
:::moniker range=">=azure-pipelines-2020"

**`customEndpoint`** - **Credentials for registries outside this organization/collection**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Credentials to use for external registries located in the project's .npmrc. For registries in this organization/collection, leave this blank; the build’s credentials are used automatically.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`customEndpoint`** - **Credentials for registries outside this account/collection**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Credentials to use for external registries located in the project's .npmrc. For registries in this account/collection, leave this blank; the build’s credentials are used automatically.
<!-- :::editable-content-end::: -->

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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.115.0 or greater |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->