---
title: CacheBeta@1 - Cache (Beta) v1 task
description: Cache files between runs (task version 1).
ms.date: 06/22/2023
monikerRange: ">=azure-pipelines-2020"
---

# CacheBeta@1 - Cache (Beta) v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Improve build performance by using this task to cache files, like dependencies, between pipeline runs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Cache (Beta) v1
# Cache files between runs.
- task: CacheBeta@1
  inputs:
    key: # string. Required. Key. 
    path: # string. Required. Path. 
    #cacheHitVar: # string. Cache hit variable. 
    #restoreKeys: # string. Additional restore key prefixes.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="key"::: -->
:::moniker range=">=azure-pipelines-2020"

**`key`** - **Key**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The key (unique identifier) for the cache. This should be a string that can be segmented using `|`. File paths can be absolute or relative to `$(System.DefaultWorkingDirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="path"::: -->
:::moniker range=">=azure-pipelines-2020"

**`path`** - **Path**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path of the folder to cache. Can be fully qualified or relative to `$(System.DefaultWorkingDirectory)`. Wildcards are not supported. [Variables](/azure/devops/pipelines/build/variables) are supported.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cacheHitVar"::: -->
:::moniker range=">=azure-pipelines-2020"

**`cacheHitVar`** - **Cache hit variable**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The variable to set to `true` when the cache is restored (i.e. a cache hit). Otherwise, sets the variable to `false`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restoreKeys"::: -->
:::moniker range=">=azure-pipelines-2020"

**`restoreKeys`** - **Additional restore key prefixes**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The additional restore key prefixes that the task uses if the primary key misses. This can be a newline-delimited list of key prefixes.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020"

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

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.159.2 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->