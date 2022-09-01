---
title: CondaEnvironment@1 - Conda environment v1 task
description: This task is deprecated. Use `conda` directly in script to work with Anaconda environments.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019"
---

# CondaEnvironment@1 - Conda environment v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
This task is deprecated. Use `conda` directly in script to work with Anaconda environments.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Create and activate a Conda environment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Conda environment v1
# This task is deprecated. Use `conda` directly in script to work with Anaconda environments.
- task: CondaEnvironment@1
  inputs:
    #createCustomEnvironment: false # boolean. Create a custom environment. Default: false.
    #environmentName: # string. Required when createCustomEnvironment == true. Environment name. 
    #packageSpecs: 'python=3' # string. Package specs. Default: 'python=3'.
    #updateConda: true # boolean. Update to the latest Conda. Default: true.
    #installOptions: # string. Optional. Use when createCustomEnvironment == false. Other options for `conda install`. 
    #createOptions: # string. Optional. Use when createCustomEnvironment == true. Other options for `conda create`. 
    #cleanEnvironment: false # boolean. Optional. Use when createCustomEnvironment == true. Clean the environment. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Conda Environment v1
# Create and activate a Conda environment.
- task: CondaEnvironment@1
  inputs:
    #createCustomEnvironment: false # boolean. Create a custom environment. Default: false.
    #environmentName: # string. Required when createCustomEnvironment == true. Environment name. 
    #packageSpecs: 'python=3' # string. Package specs. Default: 'python=3'.
    #updateConda: true # boolean. Update to the latest Conda. Default: true.
    #installOptions: # string. Optional. Use when createCustomEnvironment == false. Other options for `conda install`. 
    #createOptions: # string. Optional. Use when createCustomEnvironment == true. Other options for `conda create`. 
    #cleanEnvironment: false # boolean. Optional. Use when createCustomEnvironment == true. Clean the environment. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="createCustomEnvironment"::: -->
:::moniker range=">=azure-pipelines-2019"

**`createCustomEnvironment`** - **Create a custom environment**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Create or reactivate a Conda environment instead of using the `base` environment (recommended for self-hosted agents).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="environmentName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`environmentName`** - **Environment name**<br>
Type: string. Required when createCustomEnvironment == true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the Conda environment to create and activate, or reactivate if it already exists.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageSpecs"::: -->
:::moniker range=">=azure-pipelines-2019"

**`packageSpecs`** - **Package specs**<br>
Type: string. Default value: 'python=3'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Space-delimited list of packages to install in the environment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="updateConda"::: -->
:::moniker range=">=azure-pipelines-2019"

**`updateConda`** - **Update to the latest Conda**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Update Conda to the latest version. This applies to the Conda installation found in `PATH` or at the path specified by the `CONDA` environment variable.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="installOptions"::: -->
:::moniker range=">=azure-pipelines-2019"

**`installOptions`** - **Other options for `conda install`**<br>
Type: string. Optional. Use when createCustomEnvironment == false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Space-delimited list of additional arguments to pass to the `conda install` command.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="createOptions"::: -->
:::moniker range=">=azure-pipelines-2019"

**`createOptions`** - **Other options for `conda create`**<br>
Type: string. Optional. Use when createCustomEnvironment == true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Space-delimited list of additional arguments to pass to the `conda create` command.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cleanEnvironment"::: -->
:::moniker range=">=azure-pipelines-2019"

**`cleanEnvironment`** - **Clean the environment**<br>
Type: boolean. Optional. Use when createCustomEnvironment == true. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Delete the environment and recreate it if it already exists. If not selected, the task will reactivate an existing environment.
<!-- :::editable-content-end::: -->

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
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Package |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->