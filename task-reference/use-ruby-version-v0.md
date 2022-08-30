---
title: UseRubyVersion@0 - Use Ruby version v0 task
description: Use the specified version of Ruby from the tool cache, optionally adding it to the PATH.
ms.date: 08/10/2022
monikerRange: ">=azure-pipelines-2019"
---

# UseRubyVersion@0 - Use Ruby version v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use the specified version of Ruby from the tool cache, optionally adding it to the PATH.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Retrieves the specified version of Ruby from the tool cache. Optionally add it to PATH.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Use Ruby version v0
# Use the specified version of Ruby from the tool cache, optionally adding it to the PATH.
- task: UseRubyVersion@0
  inputs:
    versionSpec: '>= 2.4' # string. Required. Version spec. Default: '>= 2.4'.
    #addToPath: true # boolean. Add to PATH. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Use Ruby Version v0
# Retrieves the specified version of Ruby from the tool cache. Optionally add it to PATH.
- task: UseRubyVersion@0
  inputs:
    versionSpec: '>= 2.4' # string. Required. Version spec. Default: '>= 2.4'.
    #addToPath: true # boolean. Add to PATH. Default: true.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="versionSpec"::: -->
:::moniker range=">=azure-pipelines-2019"

**`versionSpec`** - **Version spec**<br>
Type: string. Required. Default value: '>= 2.4'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Version range or exact version of a Ruby version to use.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addToPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`addToPath`** - **Add to PATH**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prepend the retrieved Ruby version to the PATH environment variable to make it available in subsequent tasks or scripts without using the output variable.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="rubyLocation"::: -->
**`rubyLocation`**<br><!-- :::editable-content name="Value"::: -->
The resolved folder of the Ruby distribution.
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
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | This task has permission to [set the following variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions): rubyLocation, PATH |
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
| Agent version |  2.115.0 or greater |
| Task category | Tool |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->