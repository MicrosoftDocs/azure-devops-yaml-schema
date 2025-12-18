---
title: PyPIPublisher@0 - PyPI publisher v0 task
description: Create and upload an sdist or wheel to a PyPI-compatible index using Twine.
ms.date: 12/18/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022"
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

:::moniker range="<=azure-pipelines"

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

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="pypiConnection"::: -->
:::moniker range="<=azure-pipelines"

**`pypiConnection`** - **PyPI service connection**<br>
[Input alias](index.md#what-are-task-input-aliases): `serviceEndpoint`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a generic service connection for connecting to the package index.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="packageDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`packageDirectory`** - **Python package directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `wd`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the directory of the Python package that is created and published where `setup.py` is present.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="alsoPublishWheel"::: -->
:::moniker range="<=azure-pipelines"

**`alsoPublishWheel`** - **Also publish a wheel**<br>
[Input alias](index.md#what-are-task-input-aliases): `wheel`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies whether to create and publish a universal wheel package (platform independent) in addition to an sdist package. More information about [packaging Python projects](https://packaging.python.org/en/latest/tutorials/packaging-projects/).
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

:::moniker range="<=azure-pipelines"

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

<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
