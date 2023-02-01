---
title: Grunt@0 - Grunt v0 task
description: Run the Grunt JavaScript task runner.
ms.date: 02/01/2023
monikerRange: "<=azure-pipelines"
---

# Grunt@0 - Grunt v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to run the Grunt JavaScript task runner.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Grunt v0
# Run the Grunt JavaScript task runner.
- task: Grunt@0
  inputs:
    gruntFile: 'gruntfile.js' # string. Required. Grunt File Path. Default: gruntfile.js.
    #targets: # string. Grunt Task(s). 
    #arguments: # string. Arguments. 
  # Advanced
    #workingDirectory: # string. Alias: cwd. Working Directory. 
    gruntCli: 'node_modules/grunt-cli/bin/grunt' # string. Required. grunt-cli location. Default: node_modules/grunt-cli/bin/grunt.
  # JUnit Test Results
    #publishJUnitResults: false # boolean. Publish to Azure Pipelines. Default: false.
    #testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test Results Files. Default: **/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test Run Title. 
  # Code Coverage
    #enableCodeCoverage: false # boolean. Enable Code Coverage. Default: false.
    #testFramework: 'Mocha' # 'Mocha' | 'Jasmine'. Optional. Use when enableCodeCoverage = true. Test Framework. Default: Mocha.
    #srcFiles: # string. Optional. Use when enableCodeCoverage = true. Source Files. 
    #testFiles: 'test/*.js' # string. Required when enableCodeCoverage = true. Test Script Files. Default: test/*.js.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Grunt v0
# The JavaScript Task Runner.
- task: Grunt@0
  inputs:
    gruntFile: 'gruntfile.js' # string. Required. Grunt File Path. Default: gruntfile.js.
    #targets: # string. Grunt Task(s). 
    #arguments: # string. Arguments. 
  # Advanced
    #workingDirectory: # string. Alias: cwd. Working Directory. 
    gruntCli: 'node_modules/grunt-cli/bin/grunt' # string. Required. grunt-cli location. Default: node_modules/grunt-cli/bin/grunt.
  # JUnit Test Results
    #publishJUnitResults: false # boolean. Publish to Azure Pipelines/TFS. Default: false.
    #testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test Results Files. Default: **/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test Run Title. 
  # Code Coverage
    #enableCodeCoverage: false # boolean. Enable Code Coverage. Default: false.
    #testFramework: 'Mocha' # 'Mocha' | 'Jasmine'. Optional. Use when enableCodeCoverage = true. Test Framework. Default: Mocha.
    #srcFiles: # string. Optional. Use when enableCodeCoverage = true. Source Files. 
    #testFiles: 'test/*.js' # string. Required when enableCodeCoverage = true. Test Script Files. Default: test/*.js.
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

<!-- :::item name="gruntFile"::: -->
:::moniker range="<=azure-pipelines"

**`gruntFile`** - **Grunt File Path**<br>
`string`. Required. Default value: `gruntfile.js`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path from the repo root to the Grunt script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targets"::: -->
:::moniker range="<=azure-pipelines"

**`targets`** - **Grunt Task(s)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional.  Specifies the space-delimited list of tasks to run.  If not specified, the default task will run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the additional arguments passed to Grunt. See [Using the CLI](http://gruntjs.com/using-the-cli) for more information.

*Note:* `--gruntfile` is not needed because it was already added via the gruntFile input above.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working Directory**<br>
Input alias: `cwd`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the current working directory when the script is run. If not specified, the working directory defaults to the folder where the script is located.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="gruntCli"::: -->
:::moniker range="<=azure-pipelines"

**`gruntCli`** - **grunt-cli location**<br>
`string`. Required. Default value: `node_modules/grunt-cli/bin/grunt`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the grunt-cli to run when the agent can't find the globally installed grunt-cli. Defaults to the grunt-cli under the `node_modules` folder of the working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`publishJUnitResults`** - **Publish to Azure Pipelines**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish the JUnit test results produced by the Grunt build to Azure Pipelines/TFS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`publishJUnitResults`** - **Publish to Azure Pipelines/TFS**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish the JUnit test results produced by the Grunt build to Azure Pipelines/TFS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`publishJUnitResults`** - **Publish to TFS/Team Services**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish the JUnit test results produced by the Grunt build to TFS/Team Services.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testResultsFiles"::: -->
:::moniker range="<=azure-pipelines"

**`testResultsFiles`** - **Test Results Files**<br>
`string`. Required when `publishJUnitResults = true`. Default value: `**/TEST-*.xml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the test results files path. Wildcards can be used.

For example, `**/TEST-*.xml` for all XML file names that start with `TEST-`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range="<=azure-pipelines"

**`testRunTitle`** - **Test Run Title**<br>
`string`. Optional. Use when `publishJUnitResults = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a name for the test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableCodeCoverage"::: -->
:::moniker range="<=azure-pipelines"

**`enableCodeCoverage`** - **Enable Code Coverage**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to enable code coverage using Istanbul.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testFramework"::: -->
:::moniker range="<=azure-pipelines"

**`testFramework`** - **Test Framework**<br>
`string`. Optional. Use when `enableCodeCoverage = true`. Allowed values: `Mocha`, `Jasmine`. Default value: `Mocha`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies your test framework.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="srcFiles"::: -->
:::moniker range="<=azure-pipelines"

**`srcFiles`** - **Source Files**<br>
`string`. Optional. Use when `enableCodeCoverage = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to your source files which you want to `hookRequire()`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testFiles"::: -->
:::moniker range="<=azure-pipelines"

**`testFiles`** - **Test Script Files**<br>
`string`. Required when `enableCodeCoverage = true`. Default value: `test/*.js`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to your test script files.
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

Use this task to run Grunt tasks using the JavaScript Task Runner.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

See a [Sample Gruntfile](https://gruntjs.com/sample-gruntfile).
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: node.js |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.91.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->