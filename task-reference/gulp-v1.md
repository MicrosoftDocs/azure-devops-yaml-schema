---
title: gulp@1 - gulp v1 task
description: Run the gulp Node.js streaming task-based build system.
ms.date: 02/01/2023
monikerRange: ">=azure-pipelines-2019.1"
---

# gulp@1 - gulp v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Use this task to run the gulp Node.js streaming task-based build system.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Node.js streaming task based build system.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# gulp v1
# Run the gulp Node.js streaming task-based build system.
- task: gulp@1
  inputs:
    #gulpFile: 'gulpfile.js' # string. gulp File Path. Default: gulpfile.js.
    #targets: # string. gulp Task(s). 
    #arguments: # string. Arguments. 
  # Advanced
    #workingDirectory: # string. Alias: cwd. Working Directory. 
    #gulpjs: # string. gulp.js location. 
  # JUnit Test Results
    #publishJUnitResults: false # boolean. Publish to Azure Pipelines. Default: false.
    #testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test Results Files. Default: **/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test Run Title. 
  # Code Coverage
    enableCodeCoverage: false # boolean. Required. Enable code Coverage. Default: false.
    #testFramework: 'Mocha' # 'Mocha' | 'Jasmine'. Optional. Use when enableCodeCoverage = true. Test Framework. Default: Mocha.
    #srcFiles: # string. Optional. Use when enableCodeCoverage = true. Source Files. 
    #testFiles: 'test/*.js' # string. Required when enableCodeCoverage = true. Test Script Files. Default: test/*.js.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Gulp v1
# Node.js streaming task based build system.
- task: Gulp@1
  inputs:
    gulpFile: 'gulpfile.js' # string. Required. Gulp File Path. Default: gulpfile.js.
    #targets: # string. Gulp Task(s). 
    #arguments: # string. Arguments. 
  # Advanced
    #workingDirectory: # string. Alias: cwd. Working Directory. 
    #gulpjs: # string. gulp.js location. 
  # JUnit Test Results
    #publishJUnitResults: false # boolean. Publish to Azure Pipelines/TFS. Default: false.
    #testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test Results Files. Default: **/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test Run Title. 
  # Code Coverage
    enableCodeCoverage: false # boolean. Required. Enable code Coverage. Default: false.
    #testFramework: 'Mocha' # 'Mocha' | 'Jasmine'. Optional. Use when enableCodeCoverage = true. Test Framework. Default: Mocha.
    #srcFiles: # string. Optional. Use when enableCodeCoverage = true. Source Files. 
    #testFiles: 'test/*.js' # string. Required when enableCodeCoverage = true. Test Script Files. Default: test/*.js.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="gulpFile"::: -->
:::moniker range=">=azure-pipelines-2020"

**`gulpFile`** - **gulp File Path**<br>
`string`. Default value: `gulpfile.js`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root of the gulp file script file you want to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`gulpFile`** - **Gulp File Path**<br>
`string`. Required. Default value: `gulpfile.js`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repo root of the gulp file script file you want to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targets"::: -->
:::moniker range=">=azure-pipelines-2020"

**`targets`** - **gulp Task(s)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional space-delimited list of tasks to run. If this input isn't specified, the default task will run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`targets`** - **Gulp Task(s)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional space-delimited list of tasks to run. If this input isn't specified, the default task will run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`arguments`** - **Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments passed to gulp. `--gulpfile` is not needed since it's already added via `gulpFile` input above.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`workingDirectory`** - **Working Directory**<br>
Input alias: `cwd`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The current working directory to use when the script is run. This input defaults to the folder where the script is located.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="gulpjs"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`gulpjs`** - **gulp.js location**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to an alternative `gulp.js`, relative to the working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range=">=azure-pipelines-2020"

**`publishJUnitResults`** - **Publish to Azure Pipelines**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Publishes JUnit test results produced by the gulp build to Azure Pipelines/TFS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

**`publishJUnitResults`** - **Publish to Azure Pipelines/TFS**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Publishes JUnit test results produced by the gulp build to Azure Pipelines/TFS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testResultsFiles"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`testResultsFiles`** - **Test Results Files**<br>
`string`. Required when `publishJUnitResults = true`. Default value: `**/TEST-*.xml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Test results files path. You can use wildcards. For example, you can use `**/TEST-*.xml` for all XML files whose name starts with `TEST-`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`testRunTitle`** - **Test Run Title**<br>
`string`. Optional. Use when `publishJUnitResults = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a name for the test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableCodeCoverage"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`enableCodeCoverage`** - **Enable code Coverage**<br>
`boolean`. Required. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enables Code Coverage using Istanbul.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testFramework"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`testFramework`** - **Test Framework**<br>
`string`. Optional. Use when `enableCodeCoverage = true`. Allowed values: `Mocha`, `Jasmine`. Default value: `Mocha`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies your test framework.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="srcFiles"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`srcFiles`** - **Source Files**<br>
`string`. Optional. Use when `enableCodeCoverage = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides the path to the source files you want to hookRequire().
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testFiles"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`testFiles`** - **Test Script Files**<br>
`string`. Required when `enableCodeCoverage = true`. Default value: `test/*.js`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides the path to your test script files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019.1"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to run gulp tasks using the Node.js streaming task-based build system.

> [!NOTE]
> Gulp is not preinstalled on all hosted agents. See [installed software on virtual machine images](/azure/devops/pipelines/agents/hosted#software).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Run gulp.js

```yml
- task: Npm@1
  inputs:
    command: 'install'

- task: gulp@1
  inputs:
    gulpFile: 'gulpfile.js'
    gulpjs: 'node_modules/gulp/bin/gulp.js'
```

### Build a Node.js app

* [Build your Node.js app with gulp](/azure/devops/pipelines/ecosystems/javascript)
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019.1"

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
## See also

* [Build your Node.js app with gulp](/azure/devops/pipelines/ecosystems/javascript)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->