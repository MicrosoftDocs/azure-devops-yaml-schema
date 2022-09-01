---
title: RunVisualStudioTestsusingTestAgent@1 - Run functional tests v1 task
description: RunVisualStudioTestsusingTestAgent@1 and its companion task (Visual Studio Test Agent Deployment) are deprecated. Use the Visual Studio Test task instead. The VSTest task can run unit as well as functional tests. Run tests on one or more agents using the multi-agent job setting. Use the 'Visual Studio Test Platform' task to run tests without needing Visual Studio on the agent. VSTest task also brings new capabilities such as automatically rerunning failed tests.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# RunVisualStudioTestsusingTestAgent@1 - Run functional tests v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
RunVisualStudioTestsusingTestAgent@1 and its companion task (Visual Studio Test Agent Deployment) are deprecated. Use the 'Visual Studio Test' task instead. The VSTest task can run unit as well as functional tests. Run tests on one or more agents using the multi-agent job setting. Use the Visual Studio Test Platform task to run tests without needing Visual Studio on the agent. VSTest task also brings new capabilities such as automatically rerunning failed tests.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Run functional tests v1
# Deprecated: This task and it’s companion task (Visual Studio Test Agent Deployment) are deprecated. Use the 'Visual Studio Test' task instead. The VSTest task can run unit as well as functional tests. Run tests on one or more agents using the multi-agent job setting. Use the 'Visual Studio Test Platform' task to run tests without needing Visual Studio on the agent. VSTest task also brings new capabilities such as automatically rerunning failed tests.
- task: RunVisualStudioTestsusingTestAgent@1
  inputs:
  # Setup Options
    testMachineGroup: # string. Required. Machines. 
    dropLocation: # string. Required. Test Drop Location. 
  # Execution Options
    testSelection: 'testAssembly' # 'testAssembly' | 'testPlan'. Required. Test Selection. Default: 'testAssembly'.
    #testPlan: # string. Required when testSelection = testPlan. Test Plan. 
    #testSuite: # string. Required when testSelection = testPlan. Test Suite. 
    #testConfiguration: # string. Required when testSelection = testPlan. Test Configuration. 
    sourcefilters: '**\*test*.dll' # string. Required when testSelection = testAssembly. Test Assembly. Default: '**\*test*.dll'.
    #testFilterCriteria: # string. Optional. Use when testSelection = testAssembly. Test Filter criteria. 
    #runSettingsFile: # string. Run Settings File. 
    #overrideRunParams: # string. Override Test Run Parameters. 
    #codeCoverageEnabled: false # boolean. Code Coverage Enabled. Default: false.
    #customSlicingEnabled: false # boolean. Distribute tests by number of machines. Default: false.
  # Reporting Options
    #testRunTitle: # string. Test Run Title. 
    #platform: # string. Platform. 
    #configuration: # string. Configuration. 
    #testConfigurations: # string. Test Configurations. 
    #autMachineGroup: # string. Application Under Test Machines.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Run Functional Tests v1
# Deprecated: This task and it’s companion task (Visual Studio Test Agent Deployment) are deprecated. Use the 'Visual Studio Test' task instead. The VSTest task can run unit as well as functional tests. Run tests on one or more agents using the multi-agent job setting. Use the 'Visual Studio Test Platform' task to run tests without needing Visual Studio on the agent. VSTest task also brings new capabilities such as automatically rerunning failed tests.
- task: RunVisualStudioTestsusingTestAgent@1
  inputs:
  # Setup Options
    testMachineGroup: # string. Required. Machines. 
    dropLocation: # string. Required. Test Drop Location. 
  # Execution Options
    testSelection: 'testAssembly' # 'testAssembly' | 'testPlan'. Required. Test Selection. Default: 'testAssembly'.
    #testPlan: # string. Required when testSelection = testPlan. Test Plan. 
    #testSuite: # string. Required when testSelection = testPlan. Test Suite. 
    #testConfiguration: # string. Required when testSelection = testPlan. Test Configuration. 
    sourcefilters: '**\*test*.dll' # string. Required when testSelection = testAssembly. Test Assembly. Default: '**\*test*.dll'.
    #testFilterCriteria: # string. Optional. Use when testSelection = testAssembly. Test Filter criteria. 
    #runSettingsFile: # string. Run Settings File. 
    #overrideRunParams: # string. Override Test Run Parameters. 
    #codeCoverageEnabled: false # boolean. Code Coverage Enabled. Default: false.
    #customSlicingEnabled: false # boolean. Distribute tests by number of machines. Default: false.
  # Reporting Options
    #testRunTitle: # string. Test Run Title. 
    #platform: # string. Platform. 
    #configuration: # string. Configuration. 
    #testConfigurations: # string. Test Configurations. 
    #autMachineGroup: # string. Application Under Test Machines.
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

<!-- :::item name="testMachineGroup"::: -->
:::moniker range="<=azure-pipelines"

**`testMachineGroup`** - **Machines**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a comma separated list of machine IP addresses or FQDNs. Eg: `dbserver.fabrikam.com or 192.168.12.34` Or provide output variable of other tasks. Eg: `$(variableName)` Or provide a Machine Group Name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dropLocation"::: -->
:::moniker range="<=azure-pipelines"

**`dropLocation`** - **Test Drop Location**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Location where the test binaries have been dropped in the agent machine(s) as part of the 'Windows Machine File Copy' or 'Azure File Copy' task. System Environment Variables can also be used in location string. e.g., `%systemdrive%\Tests`, `%temp%\DropLocation` etc.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testSelection"::: -->
:::moniker range="<=azure-pipelines"

**`testSelection`** - **Test Selection**<br>
Type: string. Required. Allowed values: 'testAssembly', 'testPlan'. Default value: 'testAssembly'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the way you want to run tests : using Test Assemblies or using Test Plan.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testPlan"::: -->
:::moniker range="<=azure-pipelines"

**`testPlan`** - **Test Plan**<br>
Type: string. Required when testSelection = testPlan.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Test Plan.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testSuite"::: -->
:::moniker range="<=azure-pipelines"

**`testSuite`** - **Test Suite**<br>
Type: string. Required when testSelection = testPlan.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select Test Suites from the Test Plan.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testConfiguration"::: -->
:::moniker range="<=azure-pipelines"

**`testConfiguration`** - **Test Configuration**<br>
Type: string. Required when testSelection = testPlan.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select Test Configuration.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sourcefilters"::: -->
:::moniker range="<=azure-pipelines"

**`sourcefilters`** - **Test Assembly**<br>
Type: string. Required when testSelection = testAssembly. Default value: '**\*test*.dll'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Test binaries to run tests on. Wildcards can be used. For example, `**\*test*.dll;` for all dlls containing 'test' in their name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testFilterCriteria"::: -->
:::moniker range="<=azure-pipelines"

**`testFilterCriteria`** - **Test Filter criteria**<br>
Type: string. Optional. Use when testSelection = testAssembly.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally specify the test case filter criteria. For example, `Owner=james&Priority=1`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runSettingsFile"::: -->
:::moniker range="<=azure-pipelines"

**`runSettingsFile`** - **Run Settings File**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to runsettings or testsettings file to use with the tests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideRunParams"::: -->
:::moniker range="<=azure-pipelines"

**`overrideRunParams`** - **Override Test Run Parameters**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Override parameters defined in the `TestRunParameters` section of runsettings file or `Properties` section of testsettings file. For example: `AppURL=$(DeployURL);Port=8080`. Note: Properties specified in testsettings file can be accessed via the TestContext using Test Agent 2017 Update 4 or higher.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageEnabled"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageEnabled`** - **Code Coverage Enabled**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Whether code coverage needs to be enabled.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customSlicingEnabled"::: -->
:::moniker range="<=azure-pipelines"

**`customSlicingEnabled`** - **Distribute tests by number of machines**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Tests will be distributed based on the number of machines provided instead of number of test containers. Note that tests within a dll might also be distributed to multiple machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range="<=azure-pipelines"

**`testRunTitle`** - **Test Run Title**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the Test Run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="platform"::: -->
:::moniker range="<=azure-pipelines"

**`platform`** - **Platform**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Platform against which the tests should be reported. If you have defined a variable for platform in your build task, use that here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Configuration against which the tests should be reported. If you have defined a variable for configuration in your build task, use that here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testConfigurations"::: -->
:::moniker range="<=azure-pipelines"

**`testConfigurations`** - **Test Configurations**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally associate a test case filter against a test configuration ID. Syntax: &lt;Filter1&gt;:&lt;Id1&gt;;DefaultTestConfiguration:&lt;Id3&gt;. For example: `FullyQualifiedName~Chrome:12`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="autMachineGroup"::: -->
:::moniker range="<=azure-pipelines"

**`autMachineGroup`** - **Application Under Test Machines**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma separated list of machines or output variable or Machine Group Name on which server processes such as W3WP.exe is running.
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
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.104.0 or greater |
| Task category | Test |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->