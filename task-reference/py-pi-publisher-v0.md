---
title: PyPIPublisher@0 - PyPI publisher v0 task
description: Create and upload an sdist or wheel to a PyPI-compatible index using Twine.
ms.date: 02/01/2023
monikerRange: "<=azure-pipelines"
---

# PyPIPublisher@0 - PyPI publisher v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to create and upload an sdist or wheel to a PyPI-compatible index using Twine.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# PyPI publisher v0
# Create and upload an sdist or wheel to a PyPI-compatible index using Twine.
- task: PyPIPublisher@0
  inputs:
    pypiConnection: # string. Alias: serviceEndpoint. Required. PyPI service connection. 
    packageDirectory: # string. Alias: wd. Required. Python package directory. 
    #alsoPublishWheel: false # boolean. Alias: wheel. Also publish a wheel. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# PyPI Publisher v0
# Create and upload an sdist or wheel to a PyPI-compatible index using Twine.
- task: PyPIPublisher@0
  inputs:
    pypiConnection: # string. Alias: serviceEndpoint. Required. PyPI service connection. 
    packageDirectory: # string. Alias: wd. Required. Python package directory. 
    #alsoPublishWheel: false # boolean. Alias: wheel. Also publish a wheel. Default: false.
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

<!-- :::item name="pypiConnection"::: -->
:::moniker range=">=azure-pipelines-2019"

**`pypiConnection`** - **PyPI service connection**<br>
Input alias: `serviceEndpoint`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a generic service connection for connecting to the package index.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`packageDirectory`** - **Python package directory**<br>
Input alias: `wd`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the directory of the Python package that is created and published where `setup.py` is present.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="alsoPublishWheel"::: -->
:::moniker range=">=azure-pipelines-2019"

**`alsoPublishWheel`** - **Also publish a wheel**<br>
Input alias: `wheel`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether to create and publish a universal wheel package (platform independent) in addition to an sdist package. More information about [packaging Python projects](https://packaging.python.org/tutorials/distributing-packages/#wheels).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serviceEndpoint"::: -->
:::moniker range="=azure-pipelines-2018"

**`serviceEndpoint`** - **PyPI connection**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the generic service endpoint where the following PyPI server details are present:

- Connection Name – Use a connection name of your choice.
- Server URL – PyPI package server (for example: https://upload.pypi.org/legacy/).
- User Name – PyPI registered username.
- Password – password for your PyPI account.

*Note*: To configure a new generic service endpoint, under your VSTS project, go to Settings -> Services -> New Service Endpoint -> Generic.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="wd"::: -->
:::moniker range="=azure-pipelines-2018"

**`wd`** - **Python package path**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Python package directory published where `setup.py` is present.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="wheel"::: -->
:::moniker range="=azure-pipelines-2018"

**`wheel`** - **Upload wheel**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, the task will build and publish a universal wheel (platform independent) of this package. More information regarding [universal wheels](https://packaging.python.org/tutorials/distributing-packages/#wheels).
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

> [!IMPORTANT]
> The PyPI Publisher task has been deprecated. You can now [publish PyPI packages using Twine authentication and custom scripts](/azure/devops/pipelines/artifacts/pypi).

Use this task to create and upload an sdist or wheel to a PyPI-compatible index using Twine.

This task builds an sdist package by running `python setup.py sdist` with the Python instance in `PATH`. In addition to the sdist, it can optionally build a universal wheel. It will upload the package to a PyPI index using `twine`.
The task will install the `wheel` and `twine` packages with `python -m pip install --user`.
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
| Agent version |  2.0.0 or greater |
| Task category | Package |

:::moniker-end

:::moniker range="=azure-pipelines-2018"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.0.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
