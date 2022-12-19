---
title: CondaEnvironment@0 - Conda environment v0 task
description: Create and activate a Conda environment.
ms.date: 12/19/2022
monikerRange: ">=azure-pipelines-2019"
---

# CondaEnvironment@0 - Conda environment v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to create and activate a Conda environment.

> [!NOTE]
> This task has been deprecated. Use `conda` directly in the [bash task](bash-v3.md) or [batch script task](batch-script-v1.md) as an alternative.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Conda environment v0
# Create and activate a Conda environment.
- task: CondaEnvironment@0
  inputs:
    environmentName: # string. Required. Environment name. 
    #packageSpecs: 'python=3' # string. Package specs. Default: python=3.
    #updateConda: true # boolean. Update to the latest Conda. Default: true.
  # Advanced
    #createOptions: # string. Environment creation options. 
    #cleanEnvironment: false # boolean. Clean the environment. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Conda Environment v0
# Create and activate a Conda environment.
- task: CondaEnvironment@0
  inputs:
    environmentName: # string. Required. Environment name. 
    #packageSpecs: 'python=3' # string. Package specs. Default: python=3.
    #updateConda: true # boolean. Update to the latest Conda. Default: true.
  # Advanced
    #createOptions: # string. Environment creation options. 
    #cleanEnvironment: false # boolean. Clean the environment. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="environmentName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`environmentName`** - **Environment name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Conda environment to create and activate, or reactivate if it already exists.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageSpecs"::: -->
:::moniker range=">=azure-pipelines-2019"

**`packageSpecs`** - **Package specs**<br>
`string`. Default value: `python=3`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The space-delimited list of packages to install in the environment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="updateConda"::: -->
:::moniker range=">=azure-pipelines-2019"

**`updateConda`** - **Update to the latest Conda**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Updates Conda to the latest version. This applies to the Conda installation found in `PATH` or to the path specified by the `CONDA` environment variable.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="createOptions"::: -->
:::moniker range=">=azure-pipelines-2019"

**`createOptions`** - **Environment creation options**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The space-delimited list of additional options to pass to the `conda create` command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cleanEnvironment"::: -->
:::moniker range=">=azure-pipelines-2019"

**`cleanEnvironment`** - **Clean the environment**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Deletes the environment and recreates it if it already exists. If this boolean is not selected, the task will reactivate an existing environment.
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
## Remarks

Use this task to create and activate a Conda environment.

> [!NOTE]
> This task has been deprecated. Use `conda` directly in the [bash task](bash-v3.md) or [batch script task](batch-script-v1.md) as an alternative.

This task will create a Conda environment and activate it for subsequent build tasks.

If the task finds an existing environment with the same name, the task will simply reactivate it. This is possible on self-hosted agents. To recreate the environment and reinstall any of its packages, set the "Clean the environment" option.

Running with the "Update to the latest Conda" option will attempt to update Conda before creating or activating the environment.
If you are running a self-hosted agent and have [configured a Conda installation to work with the task](#how-can-i-configure-a-self-hosted-agent-to-use-this-task), this may result in your Conda installation being updated.

> [!NOTE]
> Microsoft-hosted agents won't have Conda in their `PATH` by default. You will need to run this task in order to use Conda.

After running this task, `PATH` will contain the binary directory for the activated environment, followed by the binary directories for the Conda installation itself.
You can run scripts as subsequent build tasks that run Python, Conda, or the command-line utilities from other packages you install.
For example, you can run tests with [pytest](https://docs.pytest.org/en/latest/) or upload a package to Anaconda Cloud with the [Anaconda client](https://github.com/Anaconda-Platform/anaconda-client).

> [!TIP]
> After running this task, the environment will be "activated", and packages you install by calling `conda install` will get installed to this environment.

### Prerequisites

* A Microsoft-hosted agent, or a self-hosted agent with Anaconda or Miniconda installed.
* If using a self-hosted agent, you must either add the `conda` executable to `PATH` or set the `CONDA` environment variable to the root of the Conda installation.

### How can I configure a self-hosted agent to use this task?

You can use this task either with a full Anaconda installation or a Miniconda installation.
If using a self-hosted agent, you must add the `conda` executable to `PATH`.
Alternatively, you can set the `CONDA` environment variable to the root of the Conda installation -- that is, the directory you specify as the "prefix" when installing Conda.
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