---
title: AdvancedSecurity-Codeql-Init@1 - Advanced Security Initialize CodeQL v1 task
description: Initializes the CodeQL database in preparation for building.
ms.date: 10/18/2023
monikerRange: "=azure-pipelines"
---

# AdvancedSecurity-Codeql-Init@1 - Advanced Security Initialize CodeQL v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Initializes the CodeQL database in preparation for building.
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
The programming language to analyze. Valid values for the languages are csharp,cpp,go,java,javascript,python,ruby,swift. Multiple languages can be separated by a comma. Note: setting this value will override the pipeline variable.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="querysuite"::: -->
:::moniker range="=azure-pipelines"

**`querysuite`** - **CodeQL Query Suite to use for analysis.**<br>
`string`. Allowed values: `Select a query suite...`, `code-scanning`, `security-extended` (security-extended (default)), `security-experimental`, `security-and-quality`. Default value: `Select a query suite...`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The query suite, i.e. ruleset, used for analysis. Valid values for query suite are 'code-scanning', 'security-extended', 'security-experimental', and 'security-and-quality'. Note: setting this value will override the pipeline variable.
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
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeqlpathstoignore"::: -->
:::moniker range="=azure-pipelines"

**`codeqlpathstoignore`** - **Set a list of paths to exclude in the CodeQL analysis**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You can provide multiple paths seperated by commas, for example: 'c:\test,c:\test\ignored'.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeqlpathstoinclude"::: -->
:::moniker range="=azure-pipelines"

**`codeqlpathstoinclude`** - **Set a list of additional paths to include in the CodeQL analysis**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
You can provide multiple paths seperated by commas, for example: 'c:\test,c:\test\ignored'.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sourcesfolder"::: -->
:::moniker range="=azure-pipelines"

**`sourcesfolder`** - **Sets the folder that contains the sources to be analyzed**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If you don't provide this value, the default sources folder for the pipeline infrastructure is used (provided by the 'Build.SourcesDirectory' variable).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="loglevel"::: -->
:::moniker range="=azure-pipelines"

**`loglevel`** - **Set the log level for the CodeQL analysis**<br>
`string`. Allowed values: `0` (Warning), `1` (Verbose), `2` (Debug), `_` (Default (Warning)). Default value: `_`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If you don't provide this value, the default sources folder for the pipeline infrastructure is used (provided by the 'Build.SourcesDirectory' variable).
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
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->