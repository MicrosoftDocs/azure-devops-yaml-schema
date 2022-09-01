---
title: UsePythonVersion@0 - Use Python version v0 task
description: Use the specified version of Python from the tool cache, optionally adding it to the PATH.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2019"
---

# UsePythonVersion@0 - Use Python version v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use the specified version of Python from the tool cache, optionally adding it to the PATH.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Retrieves the specified version of Python from the tool cache. Optionally add it to PATH.
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
    versionSpec: '3.x' # string. Required. Version spec. Default: '3.x'.
    #disableDownloadFromRegistry: false # boolean. Disable downloading releases from the GitHub registry. Default: false.
    #allowUnstable: false # boolean. Optional. Use when disableDownloadFromRegistry = false. Allow downloading unstable releases. Default: false.
    #githubToken: # string. Optional. Use when disableDownloadFromRegistry = false. GitHub token for GitHub Actions python registry. 
    addToPath: true # boolean. Required. Add to PATH. Default: true.
  # Advanced
    architecture: 'x64' # 'x86' | 'x64'. Required. Architecture. Default: 'x64'.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2022"

```yaml
# Use Python version v0
# Use the specified version of Python from the tool cache, optionally adding it to the PATH.
- task: UsePythonVersion@0
  inputs:
    versionSpec: '3.x' # string. Required. Version spec. Default: '3.x'.
    addToPath: true # boolean. Required. Add to PATH. Default: true.
  # Advanced
    architecture: 'x64' # 'x86' | 'x64'. Required. Architecture. Default: 'x64'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Use Python Version v0
# Retrieves the specified version of Python from the tool cache. Optionally add it to PATH.
- task: UsePythonVersion@0
  inputs:
    versionSpec: '3.x' # string. Required. Version spec. Default: '3.x'.
    addToPath: true # boolean. Required. Add to PATH. Default: true.
  # Advanced
    architecture: 'x64' # 'x86' | 'x64'. Required. Architecture. Default: 'x64'.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="versionSpec"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionSpec`** - **Version spec**<br>
Type: string. Required. Default value: '3.x'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Version range or exact version of a Python version to use, using semver's version range syntax. [More information](https://go.microsoft.com/fwlink/?LinkID=2006180).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="disableDownloadFromRegistry"::: -->
:::moniker range="=azure-pipelines"

**`disableDownloadFromRegistry`** - **Disable downloading releases from the GitHub registry**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Whether to disable downloading missing python version from the [Github Actions registry](https://github.com/actions/python-versions). Check this if you only want to use local pre-installed python.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowUnstable"::: -->
:::moniker range="=azure-pipelines"

**`allowUnstable`** - **Allow downloading unstable releases**<br>
Type: boolean. Optional. Use when disableDownloadFromRegistry = false. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Allow downloading unstable python versions from [Github Actions python versions registry](https://github.com/actions/python-versions).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="githubToken"::: -->
:::moniker range="=azure-pipelines"

**`githubToken`** - **GitHub token for GitHub Actions python registry**<br>
Type: string. Optional. Use when disableDownloadFromRegistry = false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
GitHub token is needed to prevent anonymous requests limit to the [Github Actions python versions registry](https://github.com/actions/python-versions). Leaving this empty may cause download failures. Not needed if you only use locally installed python.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addToPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`addToPath`** - **Add to PATH**<br>
Type: boolean. Required. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Whether to prepend the retrieved Python version to the PATH environment variable to make it available in subsequent tasks or scripts without using the output variable.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="architecture"::: -->
:::moniker range=">=azure-pipelines-2019"

**`architecture`** - **Architecture**<br>
Type: string. Required. Allowed values: 'x86', 'x64'. Default value: 'x64'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The target architecture (x86, x64) of the Python interpreter.
<!-- :::editable-content-end::: -->

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