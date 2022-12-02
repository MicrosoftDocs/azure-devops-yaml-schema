---
title: UsePythonVersion@0 - Use Python version v0 task
description: Use the specified version of Python from the tool cache, optionally adding it to the PATH.
ms.date: 11/03/2022
ms.custom: py-fresh-zinc
monikerRange: ">=azure-pipelines-2019"
---

# UsePythonVersion@0 - Use Python version v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to select a version of Python to run on an agent, and optionally add it to PATH.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Use Python version v0
# Use the specified version of Python from the tool cache, optionally adding it to the PATH.
- task: UsePythonVersion@0
  inputs:
    versionSpec: '3.x' # string. Required. Version spec. Default: 3.x.
    #disableDownloadFromRegistry: false # boolean. Disable downloading releases from the GitHub registry. Default: false.
    #allowUnstable: false # boolean. Optional. Use when disableDownloadFromRegistry = false. Allow downloading unstable releases. Default: false.
    #githubToken: # string. Optional. Use when disableDownloadFromRegistry = false. GitHub token for GitHub Actions python registry. 
    addToPath: true # boolean. Required. Add to PATH. Default: true.
  # Advanced
    architecture: 'x64' # 'x86' | 'x64'. Required. Architecture. Default: x64.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2022"

```yaml
# Use Python version v0
# Use the specified version of Python from the tool cache, optionally adding it to the PATH.
- task: UsePythonVersion@0
  inputs:
    versionSpec: '3.x' # string. Required. Version spec. Default: 3.x.
    addToPath: true # boolean. Required. Add to PATH. Default: true.
  # Advanced
    architecture: 'x64' # 'x86' | 'x64'. Required. Architecture. Default: x64.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Use Python Version v0
# Retrieves the specified version of Python from the tool cache. Optionally add it to PATH.
- task: UsePythonVersion@0
  inputs:
    versionSpec: '3.x' # string. Required. Version spec. Default: 3.x.
    addToPath: true # boolean. Required. Add to PATH. Default: true.
  # Advanced
    architecture: 'x64' # 'x86' | 'x64'. Required. Architecture. Default: x64.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="versionSpec"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionSpec`** - **Version spec**<br>
`string`. Required. Default value: `3.x`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version range or exact version of a Python version to use, using SemVer's version range syntax. Learn more about [SemVer](https://www.npmjs.com/package/semver).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="disableDownloadFromRegistry"::: -->
:::moniker range="=azure-pipelines"

**`disableDownloadFromRegistry`** - **Disable downloading releases from the GitHub registry**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Disables downloading missing Python versions from the [Github Actions registry](https://github.com/actions/python-versions). This boolean should only be `true` if using a local installation of Python.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowUnstable"::: -->
:::moniker range="=azure-pipelines"

**`allowUnstable`** - **Allow downloading unstable releases**<br>
`boolean`. Optional. Use when `disableDownloadFromRegistry = false`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Downloads unstable Python versions from the [Github Actions Python versions registry](https://github.com/actions/python-versions) if set to `true`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="githubToken"::: -->
:::moniker range="=azure-pipelines"

**`githubToken`** - **GitHub token for GitHub Actions python registry**<br>
`string`. Optional. Use when `disableDownloadFromRegistry = false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the GitHub token that enforces the anonymous requests limit in the [Github Actions python versions registry](https://github.com/actions/python-versions). Leaving this empty may cause download failures. Not needed if using a local installation of Python.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addToPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`addToPath`** - **Add to PATH**<br>
`boolean`. Required. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prepends the retrieved Python version to the PATH environment variable to make it available in subsequent tasks or scripts without using the output variable.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="architecture"::: -->
:::moniker range=">=azure-pipelines-2019"

**`architecture`** - **Architecture**<br>
`string`. Required. Allowed values: `x86`, `x64`. Default value: `x64`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the target architecture (`x86` or `x64`) of the Python interpreter.
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

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="pythonLocation"::: -->
**`pythonLocation`**<br><!-- :::editable-content name="Value"::: -->
The directory of the installed Python distribution. Use this in subsequent tasks to access this installation of Python.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to select a version of Python to run on an agent, and optionally add it to PATH.

### Prerequisites

* A [Microsoft-hosted agent](/azure/devops/pipelines/agents/hosted#software) with side-by-side versions of Python installed, or a self-hosted agent with `Agent.ToolsDirectory` configured (see [FAQ](#how-can-i-configure-a-self-hosted-agent-to-use-this-task)).

This task will fail if no Python versions are found in `Agent.ToolsDirectory`. Available Python versions on Microsoft-hosted agents can be found [here](/azure/devops/pipelines/agents/hosted#software).

> [!Note]
> x86 and x64 versions of Python are available on Microsoft-hosted Windows agents, but not on Linux or macOS agents.

::: moniker range="> azure-pipelines-2019"

As of version 0.150 of the task, version spec will also accept `pypy2` or `pypy3`.

::: moniker-end

If the task completes successfully, the task's output variable will contain the directory of the Python installation:

:::image type="content" source="media/use-python-version-output-variable.png" alt-text="Screenshot of output variable.":::

After running this task with "Add to PATH," the `python` command in subsequent scripts will be for the highest available version of the interpreter matching the version spec and architecture.

The versions of Python installed on the Microsoft-hosted Ubuntu and macOS images follow the symlinking structure for Unix-like systems that are defined in [PEP 394](https://www.python.org/dev/peps/pep-0394/).

For example, `python3.7` is the actual interpreter for Python 3.7.

`python3` is symlinked to that interpreter, and `python` is a symlink to that symlink.

On the Microsoft-hosted Windows images, the interpreter is just `python`.

For Microsoft-hosted agents, x86 is supported only on Windows. This is because Windows can run executables compiled for the x86 architecture with the WoW64 subsystem.Hosted Ubuntu and Hosted macOS run 64-bit operating systems and run only 64-bit Python.

### How can I configure a self-hosted agent to use this task?

The desired Python version needs to be added to the tool cache on the self-hosted agent so the task can use it. Normally, the tool cache is located under the `_work/_tool` directory of the agent; alternatively, the path can be overridden by the environment variable `AGENT_TOOLSDIRECTORY`. Under that directory, create the following directory structure based off of your Python version:

```
$AGENT_TOOLSDIRECTORY/
    Python/
        {version number}/
            {platform}/
                {tool files}
            {platform}.complete
```

The `version number` should follow the format of `1.2.3`.
The `platform` should either be `x86` or `x64`.
The `tool files` should be the unzipped Python version files.
The `{platform}.complete` should be a 0 byte file that looks like `x86.complete` or `x64.complete` and just signifies the tool has been installed in the cache properly.

As a complete and concrete example, here is how a completed download of Python 3.6.4 for x64 would look in the tool cache:

```
$AGENT_TOOLSDIRECTORY/
    Python/
        3.6.4/
            x64/
                {tool files}
            x64.complete
```

Learn more about the [tool cache](https://github.com/Microsoft/vsts-task-tool-lib/blob/master/docs/overview.md#tool-cache).

To make your scripts work as they would on Microsoft-hosted agents, use the symlinking structure from [PEP 394](https://www.python.org/dev/peps/pep-0394/) on Unix-like systems.

Also note that the embeddable ZIP release of Python requires [extra configuration for installed modules](https://michlstechblog.info/blog/python-install-python-with-pip-on-windows-by-the-embeddable-zip-file/), including `pip`. If possible, we recommend using the [full installer](https://docs.python.org/3/using/windows.html#installing-without-ui) to get a `pip`-compatible Python installation.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task runs using the following [command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): restricted |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): pythonLocation, PATH |
| Agent version |  2.182.1 or greater |
| Task category | Tool |

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
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