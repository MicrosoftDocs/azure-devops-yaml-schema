---
title: gulp@0 - gulp v0 task
description: Run the gulp Node.js streaming task-based build system (task version 0).
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# gulp@0 - gulp v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Run the gulp Node.js streaming task-based build system.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Node.js streaming task based build system.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# gulp v0
# Run the gulp Node.js streaming task-based build system.
- task: gulp@0
  inputs:
    gulpFile: 'gulpfile.js' # string. Required. gulp File Path. Default: 'gulpfile.js'.
    #targets: # string. gulp Task(s). 
    #arguments: # string. Arguments. 
  # Advanced
    #workingDirectory: # string. Working Directory. 
    gulpjs: 'node_modules/gulp/bin/gulp.js' # string. Required. gulp.js location. Default: 'node_modules/gulp/bin/gulp.js'.
  # JUnit Test Results
    #publishJUnitResults: false # boolean. Publish to Azure Pipelines. Default: false.
    #testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test Results Files. Default: '**/TEST-*.xml'.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test Run Title. 
  # Code Coverage
    enableCodeCoverage: false # boolean. Required. Enable code Coverage. Default: false.
    #testFramework: 'Mocha' # 'Mocha' | 'Jasmine'. Optional. Use when enableCodeCoverage = true. Test Framework. Default: 'Mocha'.
    #srcFiles: # string. Optional. Use when enableCodeCoverage = true. Source Files. 
    #testFiles: 'test/*.js' # string. Required when enableCodeCoverage = true. Test Script Files. Default: 'test/*.js'.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
# Gulp v0
# Node.js streaming task based build system.
- task: Gulp@0
  inputs:
    gulpFile: 'gulpfile.js' # string. Required. Gulp File Path. Default: 'gulpfile.js'.
    #targets: # string. Gulp Task(s). 
    #arguments: # string. Arguments. 
  # Advanced
    #workingDirectory: # string. Working Directory. 
    gulpjs: 'node_modules/gulp/bin/gulp.js' # string. Required. gulp.js location. Default: 'node_modules/gulp/bin/gulp.js'.
  # JUnit Test Results
    #publishJUnitResults: false # boolean. Publish to Azure Pipelines/TFS. Default: false.
    #testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test Results Files. Default: '**/TEST-*.xml'.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test Run Title. 
  # Code Coverage
    enableCodeCoverage: false # boolean. Required. Enable code Coverage. Default: false.
    #testFramework: 'Mocha' # 'Mocha' | 'Jasmine'. Optional. Use when enableCodeCoverage = true. Test Framework. Default: 'Mocha'.
    #srcFiles: # string. Optional. Use when enableCodeCoverage = true. Source Files. 
    #testFiles: 'test/*.js' # string. Required when enableCodeCoverage = true. Test Script Files. Default: 'test/*.js'.
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

<!-- :::item name="gulpFile"::: -->
:::moniker range=">=azure-pipelines-2020"

**`gulpFile`** - **gulp File Path**<br>
Type: string. Required. Default value: 'gulpfile.js'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from repo root of the gulp file script file to run.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`gulpFile`** - **Gulp File Path**<br>
Type: string. Required. Default value: 'gulpfile.js'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from repo root of the gulp file script file to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targets"::: -->
:::moniker range=">=azure-pipelines-2020"

**`targets`** - **gulp Task(s)**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional.  Space delimited list of tasks to run.  If not specified, the default task will run.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

**`targets`** - **Gulp Task(s)**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional.  Space delimited list of tasks to run.  If not specified, the default task will run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="<=azure-pipelines"

**`arguments`** - **Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments passed to gulp.  --gulpfile is not needed since already added via gulpFile input above.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working Directory**<br>
Input alias: `cwd`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Current working directory when script is run.  Defaults to the folder where the script is located.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="gulpjs"::: -->
:::moniker range="<=azure-pipelines"

**`gulpjs`** - **gulp.js location**<br>
Type: string. Required. Default value: 'node_modules/gulp/bin/gulp.js'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
gulp.js to run when agent can't find global installed gulp.  Defaults to the gulp.js under node_modules folder of the working directory.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range=">=azure-pipelines-2020"

**`publishJUnitResults`** - **Publish to Azure Pipelines**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish JUnit test results produced by the Gulp build to Azure Pipelines/TFS.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

**`publishJUnitResults`** - **Publish to Azure Pipelines/TFS**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish JUnit test results produced by the Gulp build to Azure Pipelines/TFS.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`publishJUnitResults`** - **Publish to TFS/Team Services**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish JUnit test results produced by the Gulp build to Azure Pipelines/TFS.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testResultsFiles"::: -->
:::moniker range="<=azure-pipelines"

**`testResultsFiles`** - **Test Results Files**<br>
Type: string. Required when publishJUnitResults = true. Default value: '**/TEST-*.xml'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Test results files path. Wildcards can be used. For example, `**/TEST-*.xml` for all XML files whose name starts with TEST-.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range="<=azure-pipelines"

**`testRunTitle`** - **Test Run Title**<br>
Type: string. Optional. Use when publishJUnitResults = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the test run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableCodeCoverage"::: -->
:::moniker range="<=azure-pipelines"

**`enableCodeCoverage`** - **Enable code Coverage**<br>
Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to enable Code Coverage using Istanbul.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testFramework"::: -->
:::moniker range="<=azure-pipelines"

**`testFramework`** - **Test Framework**<br>
Type: string. Optional. Use when enableCodeCoverage = true. Allowed values: 'Mocha', 'Jasmine'. Default value: 'Mocha'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select your test framework.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="srcFiles"::: -->
:::moniker range="<=azure-pipelines"

**`srcFiles`** - **Source Files**<br>
Type: string. Optional. Use when enableCodeCoverage = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the path to your source files which you want to hookRequire().
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testFiles"::: -->
:::moniker range="<=azure-pipelines"

**`testFiles`** - **Test Script Files**<br>
Type: string. Required when enableCodeCoverage = true. Default value: 'test/*.js'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide the path to your test script files.
<!-- :::editable-content-end::: -->

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