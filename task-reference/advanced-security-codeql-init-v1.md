---
title: AdvancedSecurity-Codeql-Init@1 - Advanced Security Initialize CodeQL v1 task
description: Initializes the CodeQL database in preparation for building.
ms.date: 06/11/2024
monikerRange: "=azure-pipelines"
---

# AdvancedSecurity-Codeql-Init@1 - Advanced Security Initialize CodeQL v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Initializes the CodeQL database in preparation for building.

You must have [GitHub Advanced Security for Azure DevOps](/azure/devops/repos/security/configure-github-advanced-security-features) enabled for the repository being scanned.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Advanced Security Initialize CodeQL v1
# Initializes the CodeQL database in preparation for building.
- task: AdvancedSecurity-Codeql-Init@1
  inputs:
    #languages: # 'csharp' | 'cpp' | 'go' | 'java' | 'javascript' | 'python' | 'ruby' | 'swift'. Languages to analyze. 
    #querysuite: 'Select a query suite...' # 'Select a query suite...' | 'code-scanning' | 'security-extended' | 'security-experimental' | 'security-and-quality'. CodeQL Query Suite to use for analysis. Default: Select a query suite....
  # Advanced
    #ram: # string. Options to control RAM usage in MB. 
    #threads: # string. Use this many threads to evaluate queries. 
    #codeqlpathstoignore: # string. Set a list of paths to exclude in the CodeQL analysis. 
    #codeqlpathstoinclude: # string. Set a list of additional paths to include in the CodeQL analysis. 
    #sourcesfolder: # string. Sets the folder that contains the sources to be analyzed. 
    #loglevel: '_' # '0' | '1' | '2' | '_'. Set the log level for the CodeQL analysis. Default: _.
    #configfilepath: # string. Use this to enable custom query analysis in codeql (path must be absolute). 
    #codeqltoolsdirectory: # string. Set a custom CodeQL tools directory (path must be absolute).
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="languages"::: -->
:::moniker range="=azure-pipelines"

**`languages`** - **Languages to analyze**<br>
`string`. Allowed values: `csharp`, `cpp`, `go`, `java`, `javascript`, `python`, `ruby`, `swift`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The programming language to analyze. Multiple languages can be separated by a comma.

You can set the language here in the task, or you can specify the language in a pipeline variable named `advancedsecurity.codeql.language`. If both are set, the value specified in the task takes precedence.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="querysuite"::: -->
:::moniker range="=azure-pipelines"

**`querysuite`** - **CodeQL Query Suite to use for analysis.**<br>
`string`. Allowed values: `Select a query suite...`, `code-scanning`, `security-extended`, `security-experimental`, `security-and-quality`. Default value: `Select a query suite...`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The query suite, i.e. ruleset, used for analysis. You can specify the value here in the task, or you can specify it in a pipeline variable named `advancedsecurity.codeql.querysuite`. If both are set, the value specified in the task takes precedence. The default value is `Select a query suite...` which indicates that the query suite must be specified in the `advancedsecurity.codeql.querysuite` variable.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ram"::: -->
:::moniker range="=azure-pipelines"

**`ram`** - **Options to control RAM usage in MB**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set total amount of RAM the query evaluator should be allowed to use.

You can specify `ram` here in the task, or you can specify it in a pipeline variable named `advancedsecurity.codeql.ram`. If both are set, the value specified in the task takes precedence.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="threads"::: -->
:::moniker range="=azure-pipelines"

**`threads`** - **Use this many threads to evaluate queries**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You can pass 0 to use one thread per core on the machine, or -N to leave N cores unused (except still use at least one thread).

You can specify `threads` here in the task, or you can specify it in a pipeline variable named `advancedsecurity.codeql.threads`. If both are set, the value specified in the task takes precedence.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeqlpathstoignore"::: -->
:::moniker range="=azure-pipelines"

**`codeqlpathstoignore`** - **Set a list of paths to exclude in the CodeQL analysis**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You can provide multiple paths separated by commas. The paths must be relative to the `sourcesfolder` where CodeQL is running, which defaults to the `Build.SourcesDirectory` pipeline environment variable. For example, to ignore the `$(Build.SourcesDirectory)/donotscan` directory, set `codeqlpathstoignore: donotscan` rather than `codeqlpathstoignore: $(Build.SourcesDirectory)/donotscan`.

> [!IMPORTANT]
> The `codeqlpathstoignore` setting applies only when you run the CodeQL tasks on an interpreted language (Python, Ruby, and JavaScript/TypeScript).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeqlpathstoinclude"::: -->
:::moniker range="=azure-pipelines"

**`codeqlpathstoinclude`** - **Set a list of additional paths to include in the CodeQL analysis**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You can provide multiple paths separated by commas. The paths must be relative to the `sourcesfolder` where CodeQL is running, which defaults to the `Build.SourcesDirectory` pipeline environment variable. For example, to include the `$(Build.SourcesDirectory)/app` directory, set `codeqlpathstoinclude: app` rather than `codeqlpathstoinclude: $(Build.SourcesDirectory)/app`.

> [!IMPORTANT]
> The `codeqlpathstoinclude` setting applies only when you run the CodeQL tasks on an interpreted language (Python, Ruby, and JavaScript/TypeScript).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sourcesfolder"::: -->
:::moniker range="=azure-pipelines"

**`sourcesfolder`** - **Sets the folder that contains the sources to be analyzed**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If you don't provide this value, the default sources folder for the pipeline infrastructure is used (provided by the `Build.SourcesDirectory` variable).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="loglevel"::: -->
:::moniker range="=azure-pipelines"

**`loglevel`** - **Set the log level for the CodeQL analysis**<br>
`string`. Allowed values: `0` (Warning), `1` (Verbose), `2` (Debug), `_` (Default (Warning)). Default value: `_`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the level of logging.

You can specify `loglevel` here in the task, or you can specify it in a pipeline variable named `advancedsecurity.codeql.loglevel`. If both are set, the value specified in the task takes precedence, unless the default value `_` for `loglevel` in the task is specified. If `_` is specified, the value from `advancedsecurity.codeql.loglevel` is used if available.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configfilepath"::: -->
:::moniker range="=azure-pipelines"

**`configfilepath`** - **Use this to enable custom query analysis in codeql (path must be absolute).**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If path is not provided, then codeql analysis will proceed with default queries.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeqltoolsdirectory"::: -->
:::moniker range="=azure-pipelines"

**`codeqltoolsdirectory`** - **Set a custom CodeQL tools directory (path must be absolute)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the path is not provided, the default value of `$agent_toolsdirectory` will be utilized.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

You must have [GitHub Advanced Security for Azure DevOps](/azure/devops/repos/security/configure-github-advanced-security-features) enabled for the repository being scanned.

> [!IMPORTANT]
> This task is supported with Azure Repos Git repositories only.

The pipeline must call the tasks in the following order.

1. Initialize CodeQL
1. AutoBuild (or your custom build tasks)
1. Perform CodeQL analysis

The AutoBuild task is optional and may be replaced with your custom build tasks. Either AutoBuild or your custom build tasks must be run for your project to be analyzed.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Code scanning for GitHub Advanced Security](/azure/devops/repos/security/github-advanced-security-code-scanning)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
