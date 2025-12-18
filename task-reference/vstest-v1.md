---
title: VSTest@1 - Visual Studio Test v1 task
description: Run tests with Visual Studio test runner.
ms.date: 11/11/2025
monikerRange: "<=azure-pipelines"
author: steved0x
ms.author: sdanie
---

# VSTest@1 - Visual Studio Test v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Use this task to run tests with Visual Studio test runner.

This version of the task is deprecated; use [VSTest@3](./vstest-v3.md).

> [!NOTE]
> The VSTest@1 task can't rerun failed **Data-driven tests**.

> [!NOTE]
> VSTest Azure task is specific to VSTest-platform. It doesn't support the newer [Microsoft.Testing.Platform (MTP)](https://aka.ms/mtp-overview).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Use this task to run tests with Visual Studio test runner.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Visual Studio Test v1
# Run tests with Visual Studio test runner.
- task: VSTest@1
  inputs:
  # Execution Options
    testAssembly: '**\*test*.dll;-:**\obj\**' # string. Required. Test Assembly. Default: **\*test*.dll;-:**\obj\**.
    #testFiltercriteria: # string. Test Filter criteria. 
    #runSettingsFile: # string. Run Settings File. 
    #overrideTestrunParameters: # string. Override TestRun Parameters. 
    #codeCoverageEnabled: False # boolean. Code Coverage Enabled. Default: False.
    #runInParallel: false # boolean. Run In Parallel. Default: false.
  # Advanced Execution Options
    #vstestLocationMethod: 'version' # 'version' | 'location'. VSTest. Default: version.
    #vsTestVersion: '14.0' # 'latest' | '14.0' | '12.0'. Optional. Use when vstestLocationMethod = version. VSTest version. Default: 14.0.
    #vstestLocation: # string. Optional. Use when vstestLocationMethod = location. Path to vstest.console.exe. 
    #pathtoCustomTestAdapters: # string. Path to Custom Test Adapters. 
    #otherConsoleOptions: # string. Other console options. 
  # Reporting Options
    #testRunTitle: # string. Test Run Title. 
    #platform: # string. Platform. 
    #configuration: # string. Configuration. 
    #publishRunAttachments: true # boolean. Upload Test Attachments. Default: true.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="testAssembly"::: -->
:::moniker range="<=azure-pipelines"

**`testAssembly`** - **Test Assembly**<br>
`string`. Required. Default value: `**\*test*.dll;-:**\obj\**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies which test binaries to run tests on.  Wildcards can be used.  For example, using `**\*test*.dll;-:**\obj\**` for all DLLs with "test" in the name and excluding files in any subdirectory named "obj".
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testFiltercriteria"::: -->
:::moniker range="<=azure-pipelines"

**`testFiltercriteria`** - **Test Filter criteria**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional criteria to filter tests from test assemblies. For example: `Priority=1|Name=MyTestMethod`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runSettingsFile"::: -->
:::moniker range="<=azure-pipelines"

**`runSettingsFile`** - **Run Settings File**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the **runsettings** file to use with the tests. Use `$(Build.SourcesDirectory)` to access the Project folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideTestrunParameters"::: -->
:::moniker range="<=azure-pipelines"

**`overrideTestrunParameters`** - **Override TestRun Parameters**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Override parameters defined in the **TestRunParameters** section of the **runsettings** file. For example: `AppURL=$(DeployURL);Port=8080`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageEnabled"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageEnabled`** - **Code Coverage Enabled**<br>
`boolean`. Default value: `False`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Collects code coverage information from the test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runInParallel"::: -->
:::moniker range="<=azure-pipelines"

**`runInParallel`** - **Run In Parallel**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enables a parallel execution of your tests.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstestLocationMethod"::: -->
:::moniker range="<=azure-pipelines"

**`vstestLocationMethod`** - **VSTest**<br>
`string`. Allowed values: `version`, `location` (Specify Location). Default value: `version`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vsTestVersion"::: -->
:::moniker range="<=azure-pipelines"

**`vsTestVersion`** - **VSTest version**<br>
`string`. Optional. Use when `vstestLocationMethod = version`. Allowed values: `latest`, `14.0` (Visual Studio 2015), `12.0` (Visual Studio 2013). Default value: `14.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of Visual Studio Test to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstestLocation"::: -->
:::moniker range="<=azure-pipelines"

**`vstestLocation`** - **Path to vstest.console.exe**<br>
`string`. Optional. Use when `vstestLocationMethod = location`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to VSTest.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pathtoCustomTestAdapters"::: -->
:::moniker range="<=azure-pipelines"

**`pathtoCustomTestAdapters`** - **Path to Custom Test Adapters**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the directory path to the custom test adapters. NuGet restored adapters are automatically searched for.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="otherConsoleOptions"::: -->
:::moniker range="<=azure-pipelines"

**`otherConsoleOptions`** - **Other console options**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies other Console options that can be passed to `vstest.console.exe`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range="<=azure-pipelines"

**`testRunTitle`** - **Test Run Title**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a name for the test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="platform"::: -->
:::moniker range="<=azure-pipelines"

**`platform`** - **Platform**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the platform against which the tests should be reported. If you have defined a variable for the platform in your build task, use that when providing this input.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the configuration against which the tests should be reported. If you have defined a variable for configuration in your build task, use that when providing this input.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishRunAttachments"::: -->
:::moniker range="<=azure-pipelines"

**`publishRunAttachments`** - **Upload Test Attachments**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Opts in or out of publishing test run level attachments.
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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: vstest |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.89.0 or greater |
| Task category | Test |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
