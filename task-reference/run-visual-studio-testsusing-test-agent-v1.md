---
title: RunVisualStudioTestsusingTestAgent@1 - Run functional tests v1 task
description: RunVisualStudioTestsusingTestAgent@1 and its companion task (Visual Studio Test Agent Deployment) are deprecated. Use the Visual Studio Test task instead. The VSTest task can run unit as well as functional tests. Run tests on one or more agents using the multi-agent job setting. Use the 'Visual Studio Test Platform' task to run tests without needing Visual Studio on the agent. VSTest task also brings new capabilities such as automatically rerunning failed tests.
ms.date: 04/16/2024
monikerRange: "<=azure-pipelines"
---

# RunVisualStudioTestsusingTestAgent@1 - Run functional tests v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
RunVisualStudioTestsusingTestAgent@1 and its companion task (Visual Studio Test Agent Deployment) are deprecated. Use the Visual Studio Test task instead. The VSTest task can run unit as well as functional tests. Run tests on one or more agents using the multi-agent job setting. Use the Visual Studio Test Platform task to run tests without needing Visual Studio on the agent. VSTest task also brings new capabilities, such as automatically rerunning failed tests.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

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
    testSelection: 'testAssembly' # 'testAssembly' | 'testPlan'. Required. Test Selection. Default: testAssembly.
    #testPlan: # string. Required when testSelection = testPlan. Test Plan. 
    #testSuite: # string. Required when testSelection = testPlan. Test Suite. 
    #testConfiguration: # string. Required when testSelection = testPlan. Test Configuration. 
    sourcefilters: '**\*test*.dll' # string. Required when testSelection = testAssembly. Test Assembly. Default: **\*test*.dll.
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
    testSelection: 'testAssembly' # 'testAssembly' | 'testPlan'. Required. Test Selection. Default: testAssembly.
    #testPlan: # string. Required when testSelection = testPlan. Test Plan. 
    #testSuite: # string. Required when testSelection = testPlan. Test Suite. 
    #testConfiguration: # string. Required when testSelection = testPlan. Test Configuration. 
    sourcefilters: '**\*test*.dll' # string. Required when testSelection = testAssembly. Test Assembly. Default: **\*test*.dll.
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


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="testMachineGroup"::: -->
:::moniker range="<=azure-pipelines"

**`testMachineGroup`** - **Machines**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A comma separated list of machine FQDNs or IP addresses, which may include the port number. The maximum is 32 machines or 32 agents. The list items can be:

- The name of an [Azure Resource Group](/azure/azure-resource-manager/management/overview).
- A comma-delimited list of machine names. Example: `dbserver.fabrikam.com,dbserver_int.fabrikam.com:5986,192.168.34:5986`
- An output variable from a previous task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dropLocation"::: -->
:::moniker range="<=azure-pipelines"

**`dropLocation`** - **Test Drop Location**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location on the test machine(s) where the test binaries have been copied by a [Windows Machine File Copy](windows-machine-file-copy-v2.md) or an [Azure File Copy](azure-file-copy-v3.md) task. System stage variables from the test agent machines can be used to specify the drop location. Examples: `c:\tests` and `%systemdrive%\Tests`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testSelection"::: -->
:::moniker range="<=azure-pipelines"

**`testSelection`** - **Test Selection**<br>
`string`. Required. Allowed values: `testAssembly` (Test Assembly), `testPlan` (Test Plan). Default value: `testAssembly`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies how tests are run: using test assemblies or Test Plan.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testPlan"::: -->
:::moniker range="<=azure-pipelines"

**`testPlan`** - **Test Plan**<br>
`string`. Required when `testSelection = testPlan`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a test plan that is already configured for this organization.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testSuite"::: -->
:::moniker range="<=azure-pipelines"

**`testSuite`** - **Test Suite**<br>
`string`. Required when `testSelection = testPlan`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a test suite from the selected test plan.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testConfiguration"::: -->
:::moniker range="<=azure-pipelines"

**`testConfiguration`** - **Test Configuration**<br>
`string`. Required when `testSelection = testPlan`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a test configuration from the selected test plan.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sourcefilters"::: -->
:::moniker range="<=azure-pipelines"

**`sourcefilters`** - **Test Assembly**<br>
`string`. Required when `testSelection = testAssembly`. Default value: `**\*test*.dll`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the test binaries to run tests on. Wildcards can be used. For example, `**\*test*.dll;` for all `.dll` files containing `test` in the file name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testFilterCriteria"::: -->
:::moniker range="<=azure-pipelines"

**`testFilterCriteria`** - **Test Filter criteria**<br>
`string`. Optional. Use when `testSelection = testAssembly`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The filter that specfies the tests to execute within the test assembly files. Works the same way as the `/TestCaseFilter` option in `vstest.console.exe`. Example: `Owner=james&Priority=1`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runSettingsFile"::: -->
:::moniker range="<=azure-pipelines"

**`runSettingsFile`** - **Run Settings File**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the file path to the `runsettings` or `testsettings` file to use with the tests.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideRunParams"::: -->
:::moniker range="<=azure-pipelines"

**`overrideRunParams`** - **Override Test Run Parameters**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the override parameters that are defined in the `TestRunParameters` section of the `runsettings` file or the `Properties` section of the `testsettings` file. Example: `AppURL=$(DeployURL);Port=8080`.

> [!NOTE]
> The properties specified in the `testsettings` file can be accessed via `TestContext` using Test Agent 2017 Update 4 or higher.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageEnabled"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageEnabled`** - **Code Coverage Enabled**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies if Code Coverage is enabled for the task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customSlicingEnabled"::: -->
:::moniker range="<=azure-pipelines"

**`customSlicingEnabled`** - **Distribute tests by number of machines**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When the value of this boolean is set to `true`, the tests are distributed based on the number of machines provided instead of the number of test containers.

> [!NOTE]
> Tests within a `.dll` might also be distributed to multiple machines.
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
Specifies the platform against which the tests should be reported. If you have defined a variable for `platform` in your build task, use the variable as the value.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the configuration against which the tests should be reported. If you have defined a variable for `configuration` in your build task, use the variable as the value.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testConfigurations"::: -->
:::moniker range="<=azure-pipelines"

**`testConfigurations`** - **Test Configurations**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Associates a test case filter against a test configuration ID. Syntax: `<Filter1>:<Id1>;DefaultTestConfiguration:<Id3>`. Example: `FullyQualifiedName~Chrome:12`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="autMachineGroup"::: -->
:::moniker range="<=azure-pipelines"

**`autMachineGroup`** - **Application Under Test Machines**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A comma separated list of machines, output variables, or machine group names on which server processes, such as `W3WP.exe`, are running.
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
