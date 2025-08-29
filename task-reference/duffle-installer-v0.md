---
title: DuffleInstaller@0 - Duffle tool installer v0 task
description: Install a specified version of Duffle for installing and managing CNAB bundles.
ms.date: 08/29/2025
monikerRange: "<=azure-pipelines"
---

# DuffleInstaller@0 - Duffle tool installer v0 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to install a specified version of Duffle, which is used for installing and managing CNAB bundles.

This task is deprecated as the Duffle project has been archived and is no longer maintained. For more information, see [https://github.com/cnabio/duffle](https://github.com/cnabio/duffle).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Use this task to install a specified version of Duffle, which is used for installing and managing CNAB bundles.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Duffle tool installer v0
# Install a specified version of Duffle for installing and managing CNAB bundles.
- task: DuffleInstaller@0
  inputs:
    version: '0.1.0-ralpha.4+dramallamabuie' # string. Required. Version. Default: 0.1.0-ralpha.4+dramallamabuie.
    #checkLatestVersion: false # boolean. Check for latest version. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="version"::: -->
:::moniker range="<=azure-pipelines"

**`version`** - **Version**<br>
`string`. Required. Default value: `0.1.0-ralpha.4+dramallamabuie`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of Duffle to install.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkLatestVersion"::: -->
:::moniker range="<=azure-pipelines"

**`checkLatestVersion`** - **Check for latest version**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Always checks online for the latest available version (stable.txt) that satisfies the version spec. Typically, the default value, `false`, is used unless you have a specific scenario where the latest update is always needed. This may incur download costs when potentially not necessary, especially with the hosted build pool.
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
| Agent version | All supported agent versions. |
| Task category | Tool |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->