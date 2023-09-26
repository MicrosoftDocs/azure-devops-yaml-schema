---
title: Cache@2 - Cache v2 task
description: Cache files between runs.
ms.date: 09/26/2023
monikerRange: ">=azure-pipelines-2020"
---

# Cache@2 - Cache v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Improve build performance by using this task to cache files, like dependencies, between pipeline runs. See [Cache task: how it works](/azure/devops/pipelines/release/caching#cache-task-:-how-it-works) and [Reduce build time using caching](/azure/devops/pipelines/release/caching) for specific examples and more details.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Cache v2
# Cache files between runs.
- task: Cache@2
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

While there is no defined maximum number of segments for a key, if you are getting cache misses, try using a shorter key with fewer segments, for example by creating a new key that is a hash of your segments.
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
## Remarks

Improve build performance by caching files, like dependencies, between pipeline runs.
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
| Agent version |  2.160.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Pipeline Caching](/azure/devops/pipelines/release/caching)
* [Cache NuGet packages](/azure/devops/pipelines/artifacts/caching-nuget)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->