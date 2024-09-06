---
title: VSTest@3 - Visual Studio Test v2 task
description: Run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test (VsTest) runner. Test frameworks that have a Visual Studio test adapter such as MsTest, xUnit, NUnit, Chutzpah (for JavaScript tests using QUnit, Mocha and Jasmine), etc. can be run. Tests can be distributed on multiple agents using this task.
ms.date: 08/19/2024
monikerRange: "=azure-pipelines"
---

# VSTest@3 - Visual Studio Test v3 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test (VSTest) runner. You can run test frameworks that have a Visual Studio test adapter. Example frameworks are MSTest, xUnit, NUnit, Chutzpah (for JavaScript tests using QUnit, Mocha and Jasmine), etc. Tests can be distributed on multiple agents using this task.

> [!NOTE]
> VSTest@3 is the newest version of the task and should be used in your pipelines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Visual Studio Test v3
# Run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test (VsTest) runner. Test frameworks that have a Visual Studio test adapter such as MsTest, xUnit, NUnit, Chutzpah (for JavaScript tests using QUnit, Mocha and Jasmine), etc. can be run. Tests can be distributed on multiple agents using this task (version 2 and later).
- task: VSTest@3
  inputs:
  # Test selection
    testSelector: 'testAssemblies' # 'testAssemblies' | 'testPlan' | 'testRun'. Required. Select tests using. Default: testAssemblies.
    testAssemblyVer2: # string. Required when testSelector = testAssemblies. Test files. 
    #testPlan: # string. Required when testSelector = testPlan. Test plan. 
    #testSuite: # string. Required when testSelector = testPlan. Test suite. 
    #testConfiguration: # string. Required when testSelector = testPlan. Test configuration. 
    #tcmTestRun: '$(test.RunId)' # string. Optional. Use when testSelector = testRun. Test Run. Default: $(test.RunId).
    searchFolder: '$(System.DefaultWorkingDirectory)' # string. Required. Search folder. Default: $(System.DefaultWorkingDirectory).
    #resultsFolder: '$(Agent.TempDirectory)\TestResults' # string. Test results folder. Default: $(Agent.TempDirectory)\TestResults.
    #testFiltercriteria: # string. Optional. Use when testSelector = testAssemblies. Test filter criteria. 
    #runOnlyImpactedTests: False # boolean. Optional. Use when testSelector = testAssemblies. Run only impacted tests. Default: False.
    #runAllTestsAfterXBuilds: '50' # string. Optional. Use when testSelector = testAssemblies && runOnlyImpactedTests = true. Number of builds after which all tests should be run. Default: 50.
    #uiTests: false # boolean. Test mix contains UI tests. Default: false.
  # Execution options
    #vstestLocationMethod: 'version' # 'version' | 'location'. Select test platform using. Default: version.
    #vsTestVersion: 'latest' # 'latest' | '17.0' | '16.0' | '15.0' | '14.0' | 'toolsInstaller'. Optional. Use when vstestLocationMethod = version. Test platform version. Default: latest.
    #vstestLocation: # string. Optional. Use when vstestLocationMethod = location. Path to vstest.console.exe. 
    #runSettingsFile: # string. Settings file. 
    #overrideTestrunParameters: # string. Override test run parameters. 
    #pathtoCustomTestAdapters: # string. Path to custom test adapters. 
    #runInParallel: False # boolean. Run tests in parallel on multi-core machines. Default: False.
    #runTestsInIsolation: False # boolean. Run tests in isolation. Default: False.
    #codeCoverageEnabled: False # boolean. Code coverage enabled. Default: False.
    #otherConsoleOptions: # string. Other console options. 
    #diagnosticsEnabled: false # boolean. Collect advanced diagnostics in case of catastrophic failures. Default: false.
    #collectDumpOn: 'onAbortOnly' # 'onAbortOnly' | 'always' | 'never'. Optional. Use when diagnosticsEnabled = true. Collect process dump and attach to test run report. Default: onAbortOnly.
    #rerunFailedTests: False # boolean. Rerun failed tests. Default: False.
    #rerunType: 'basedOnTestFailurePercentage' # 'basedOnTestFailurePercentage' | 'basedOnTestFailureCount'. Optional. Use when rerunFailedTests = true. Do not rerun if test failures exceed specified threshold. Default: basedOnTestFailurePercentage.
    #rerunFailedThreshold: '30' # string. Optional. Use when rerunFailedTests = true && rerunType = basedOnTestFailurePercentage. % failure. Default: 30.
    #rerunFailedTestCasesMaxLimit: '5' # string. Optional. Use when rerunFailedTests = true && rerunType = basedOnTestFailureCount. # of failed tests. Default: 5.
    #rerunMaxAttempts: '3' # string. Optional. Use when rerunFailedTests = true. Maximum # of attempts. Default: 3.
  # Advanced execution options
    #distributionBatchType: 'basedOnTestCases' # 'basedOnTestCases' | 'basedOnExecutionTime' | 'basedOnAssembly'. Batch tests. Default: basedOnTestCases.
    #batchingBasedOnAgentsOption: 'autoBatchSize' # 'autoBatchSize' | 'customBatchSize'. Optional. Use when distributionBatchType = basedOnTestCases. Batch options. Default: autoBatchSize.
    #customBatchSizeValue: '10' # string. Required when distributionBatchType = basedOnTestCases && batchingBasedOnAgentsOption = customBatchSize. Number of tests per batch. Default: 10.
    #batchingBasedOnExecutionTimeOption: 'autoBatchSize' # 'autoBatchSize' | 'customTimeBatchSize'. Optional. Use when distributionBatchType = basedOnExecutionTime. Batch options. Default: autoBatchSize.
    #customRunTimePerBatchValue: '60' # string. Required when distributionBatchType = basedOnExecutionTime && batchingBasedOnExecutionTimeOption = customTimeBatchSize. Running time (sec) per batch. Default: 60.
    #dontDistribute: False # boolean. Replicate tests instead of distributing when multiple agents are used in the job. Default: False.
  # Reporting options
    #testRunTitle: # string. Test run title. 
    #platform: # string. Build platform. 
    #configuration: # string. Build configuration. 
    #publishRunAttachments: true # boolean. Upload test attachments. Default: true.
    #failOnMinTestsNotRun: False # boolean. Fail the task if a minimum number of tests are not run. Default: False.
    #minimumExpectedTests: '1' # string. Optional. Use when failOnMinTestsNotRun = true. Minimum # of tests. Default: 1.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="testSelector"::: -->
:::moniker range="=azure-pipelines"

**`testSelector`** - **Select tests using**<br>
`string`. Required. Allowed values: `testAssemblies` (Test assemblies), `testPlan` (Test plan), `testRun` (Test run). Default value: `testAssemblies`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
- **Test assembly:** Specifies one or more test assemblies that contain your tests. You can optionally specify a filter criteria to select only specific tests.
- **Test plan:** Runs tests from your test plan that have an automated test method associated with it. To learn more about how to associate tests with a test case work item, see [Associate automated tests with test cases](/azure/devops/test/associate-automated-test-with-test-case).
- **Test run:** Use this option when you are setting up an environment to run tests from [test plans](/azure/devops/test/run-automated-tests-from-test-hub). This option should not be used when running tests in a continuous integration/continuous deployment (CI/CD) pipeline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testAssemblyVer2"::: -->
:::moniker range="=azure-pipelines"

**`testAssemblyVer2`** - **Test files**<br>
`string`. Required when `testSelector = testAssemblies`. Default value: `**\*test*.dll\n!**\*TestAdapter.dll\n!**\obj\**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs tests from the specified files. Ordered tests and webtests can be run by specifying the `.orderedtest` and `.webtest` files respectively. To run `.webtest`, Visual Studio 2017 Update 4 or higher is needed. The file paths are relative to the search folder. This input supports multiple lines of [minimatch patterns](/azure/devops/pipelines/tasks/file-matching-patterns).

```yml
# Example
- task: VSTest@3
  inputs:
    testSelector: 'testAssemblies'
    testAssemblyVer2: |
      **\*test*.dll
      !**\*TestAdapter.dll
      !**\obj\**
```
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testPlan"::: -->
:::moniker range="=azure-pipelines"

**`testPlan`** - **Test plan**<br>
`string`. Required when `testSelector = testPlan`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a test plan containing test suites with automated test cases.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testSuite"::: -->
:::moniker range="=azure-pipelines"

**`testSuite`** - **Test suite**<br>
`string`. Required when `testSelector = testPlan`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies one or more test suites containing automated test cases. Test case work items must be associated with an [automated test method](/azure/devops/test/associate-automated-test-with-test-case).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testConfiguration"::: -->
:::moniker range="=azure-pipelines"

**`testConfiguration`** - **Test configuration**<br>
`string`. Required when `testSelector = testPlan`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the test configuration.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tcmTestRun"::: -->
:::moniker range="=azure-pipelines"

**`tcmTestRun`** - **Test Run**<br>
`string`. Optional. Use when `testSelector = testRun`. Default value: `$(test.RunId)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the test run-based selection that is used when triggering automated test runs from [test plans](/azure/devops/test/run-automated-tests-from-test-hub). This option cannot be used for running tests in the CI/CD pipeline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="searchFolder"::: -->
:::moniker range="=azure-pipelines"

**`searchFolder`** - **Search folder**<br>
`string`. Required. Default value: `$(System.DefaultWorkingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the folder to search for the test assemblies.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resultsFolder"::: -->
:::moniker range="=azure-pipelines"

**`resultsFolder`** - **Test results folder**<br>
`string`. Default value: `$(Agent.TempDirectory)\TestResults`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the folder to store test results. When using the default directory, it is cleaned at the end of a pipeline run. The results directory will always be cleaned up at the start of the `vstest` task before the tests are run. The relative folder path, if provided, will be considered relative to `$(Agent.TempDirectory)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testFiltercriteria"::: -->
:::moniker range="=azure-pipelines"

**`testFiltercriteria`** - **Test filter criteria**<br>
`string`. Optional. Use when `testSelector = testAssemblies`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional criteria to filter tests from test assemblies. For example: `Priority=1|Name=MyTestMethod`. Learn about [command-line options](/previous-versions/jj155796(v=vs.140)).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runOnlyImpactedTests"::: -->
:::moniker range="=azure-pipelines"

**`runOnlyImpactedTests`** - **Run only impacted tests**<br>
`boolean`. Optional. Use when `testSelector = testAssemblies`. Default value: `False`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Automatically specifies and runs the tests needed to validate the code change. Learn about using [Test Impact Analysis](https://aka.ms/tialearnmore).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runAllTestsAfterXBuilds"::: -->
:::moniker range="=azure-pipelines"

**`runAllTestsAfterXBuilds`** - **Number of builds after which all tests should be run**<br>
`string`. Optional. Use when `testSelector = testAssemblies && runOnlyImpactedTests = true`. Default value: `50`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the number of builds to be executed before all tests are automatically run. Test Impact Analysis stores the mapping between test cases and source code. It is recommended to regenerate the mapping by running all tests on a regular basis.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="uiTests"::: -->
:::moniker range="=azure-pipelines"

**`uiTests`** - **Test mix contains UI tests**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
To run UI tests, ensure that the agent is set to run in [interactive mode](/azure/devops/pipelines/agents/agents) with **Autologon** enabled. Setting up an agent to run interactively must be done before queueing the build/release. Checking this box does not configure the agent in interactive mode automatically. This option serves as a reminder to configure the agent appropriately to avoid failures. Hosted Windows agents from the VS 2015 and 2017 pools can be used to run UI tests.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstestLocationMethod"::: -->
:::moniker range="=azure-pipelines"

**`vstestLocationMethod`** - **Select test platform using**<br>
`string`. Allowed values: `version`, `location` (Specific location). Default value: `version`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies which test platform to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vsTestVersion"::: -->
:::moniker range="=azure-pipelines"

**`vsTestVersion`** - **Test platform version**<br>
`string`. Optional. Use when `vstestLocationMethod = version`. Allowed values: `latest`, `17.0` (Visual Studio 2022), `16.0` (Visual Studio 2019), `15.0` (Visual Studio 2017), `14.0` (Visual Studio 2015), `toolsInstaller` (Installed by Tools Installer). Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of Visual Studio Test to use. If **latest** is specified, this input chooses the latest version (from the list of allowed values) that is installed. To run tests without needing Visual Studio on the agent, use the **Installed by tools installer** option. Be sure to include the **Visual Studio Test Platform Installer** task to acquire the test platform from NuGet.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstestLocation"::: -->
:::moniker range="=azure-pipelines"

**`vstestLocation`** - **Path to vstest.console.exe**<br>
`string`. Optional. Use when `vstestLocationMethod = location`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to VSTest.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runSettingsFile"::: -->
:::moniker range="=azure-pipelines"

**`runSettingsFile`** - **Settings file**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to a `runsettings` or `testsettings` file to use with the tests. For Visual Studio 15.7 and higher, use `runsettings` for all test types. Learn more about [converting a `.testsettings` file to a `.runsettings` file](https://github.com/Microsoft/vstest-docs/blob/main/RFCs/0023-TestSettings-Deprecation.md).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideTestrunParameters"::: -->
:::moniker range="=azure-pipelines"

**`overrideTestrunParameters`** - **Override test run parameters**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Overrides the parameters defined in the `TestRunParameters` section of a `runsettings` file or the `Properties` section of a `testsettings` file. For example: `-key1 value1 -key2 value2`. *Note:* Properties specified in a `testsettings` file can be accessed via the `TestContext` using Visual Studio 2017 (update 4 or higher).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pathtoCustomTestAdapters"::: -->
:::moniker range="=azure-pipelines"

**`pathtoCustomTestAdapters`** - **Path to custom test adapters**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the directory path to custom test adapters. Adapters residing in the same folder as the test assemblies are automatically discovered.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runInParallel"::: -->
:::moniker range="=azure-pipelines"

**`runInParallel`** - **Run tests in parallel on multi-core machines**<br>
`boolean`. Default value: `False`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, tests are run in parallel and leverage available cores of the machine. This will override the `MaxCpuCount` if specified in your `runsettings` file. Learn more about how [tests are run in parallel](https://devblogs.microsoft.com/devops/parallel-test-execution/).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runTestsInIsolation"::: -->
:::moniker range="=azure-pipelines"

**`runTestsInIsolation`** - **Run tests in isolation**<br>
`boolean`. Default value: `False`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs the tests in an isolated process. This likely leads to fewer errors in the vstest.console.exe test process, but tests might run slower. This option currently cannot be used when running with the multi-agent job setting.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageEnabled"::: -->
:::moniker range="=azure-pipelines"

**`codeCoverageEnabled`** - **Code coverage enabled**<br>
`boolean`. Default value: `False`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Collects code coverage information from the test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="otherConsoleOptions"::: -->
:::moniker range="=azure-pipelines"

**`otherConsoleOptions`** - **Other console options**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
[Other console options](/visualstudio/test/vstest-console-options) that can be passed to vstest.console.exe.

These options are not supported and will be ignored when running tests using the **Multi-agent parallel** setting of an agent job, when running tests using the **Test plan** or **Test run** option, or when a custom batching option is selected. The options can be specified using a settings file instead.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="distributionBatchType"::: -->
:::moniker range="=azure-pipelines"

**`distributionBatchType`** - **Batch tests**<br>
`string`. Allowed values: `basedOnTestCases` (Based on number of tests and agents), `basedOnExecutionTime` (Based on past running time of tests), `basedOnAssembly` (Based on test assemblies). Default value: `basedOnTestCases`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A batch is a group of tests. A batch of tests runs its tests at the same time, and results are published for the batch. If the job in which the task runs is set to use multiple agents, each agent picks up any available batches of tests to run in parallel. A batch can be run:

**based on the number of tests and agents.** Simple batching based on the number of tests and agents participating in the test run.

**based on the past running time of tests.** This batching considers the past running time to create batches of tests where each batch has approximately equal running time.

**based on test assemblies.** Tests from an assembly are batched together.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="batchingBasedOnAgentsOption"::: -->
:::moniker range="=azure-pipelines"

**`batchingBasedOnAgentsOption`** - **Batch options**<br>
`string`. Optional. Use when `distributionBatchType = basedOnTestCases`. Allowed values: `autoBatchSize` (Automatically determine the batch size), `customBatchSize` (Specify a batch size). Default value: `autoBatchSize`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies simple batching based on the number of tests and agents participating in the test run. When the batch size is automatically determined, each batch contains `(total number of tests / number of agents)` tests. If a batch size is specified, each batch will contain the specified number of tests.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customBatchSizeValue"::: -->
:::moniker range="=azure-pipelines"

**`customBatchSizeValue`** - **Number of tests per batch**<br>
`string`. Required when `distributionBatchType = basedOnTestCases && batchingBasedOnAgentsOption = customBatchSize`. Default value: `10`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the batch size.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="batchingBasedOnExecutionTimeOption"::: -->
:::moniker range="=azure-pipelines"

**`batchingBasedOnExecutionTimeOption`** - **Batch options**<br>
`string`. Optional. Use when `distributionBatchType = basedOnExecutionTime`. Allowed values: `autoBatchSize` (Automatically determine the batch time), `customTimeBatchSize` (Specify running time per batch). Default value: `autoBatchSize`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This batching considers past running times to create batches of tests where each batch has approximately equal running time. Quick-running tests will be batched together, while longer-running tests may belong to a separate batch. When this option is used with the multi-agent job setting, the total test time is reduced to a minimum.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customRunTimePerBatchValue"::: -->
:::moniker range="=azure-pipelines"

**`customRunTimePerBatchValue`** - **Running time (sec) per batch**<br>
`string`. Required when `distributionBatchType = basedOnExecutionTime && batchingBasedOnExecutionTimeOption = customTimeBatchSize`. Default value: `60`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the running time (in seconds) per batch.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dontDistribute"::: -->
:::moniker range="=azure-pipelines"

**`dontDistribute`** - **Replicate tests instead of distributing when multiple agents are used in the job**<br>
`boolean`. Default value: `False`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choosing this option will not distribute tests across agents when the task is running in a multi-agent job.
Each of the selected test(s) will be repeated on each agent. This option is not applicable when the agent job is configured to run with no parallelism or with the multi-config option.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range="=azure-pipelines"

**`testRunTitle`** - **Test run title**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a name for the test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="platform"::: -->
:::moniker range="=azure-pipelines"

**`platform`** - **Build platform**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the build platform against which the tests should be reported. If you have defined a variable for the platform in your build task, use that with this input.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="=azure-pipelines"

**`configuration`** - **Build configuration**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the build configuration against which the tests should be reported. If you have defined a variable for configuration in your build task, use that with this input.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishRunAttachments"::: -->
:::moniker range="=azure-pipelines"

**`publishRunAttachments`** - **Upload test attachments**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Opts in or out of publishing run level attachments.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnMinTestsNotRun"::: -->
:::moniker range="=azure-pipelines"

**`failOnMinTestsNotRun`** - **Fail the task if a minimum number of tests are not run.**<br>
`boolean`. Default value: `False`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fails the task if a minimum number of tests are not run. This may be useful if any changes to task inputs or underlying test adapter dependencies lead to only a subset of the desired tests to be found.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="minimumExpectedTests"::: -->
:::moniker range="=azure-pipelines"

**`minimumExpectedTests`** - **Minimum # of tests**<br>
`string`. Optional. Use when `failOnMinTestsNotRun = true`. Default value: `1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the minimum number of tests to run for the task to succeed. The total tests executed is calculated as the sum of passed, failed and aborted tests.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="diagnosticsEnabled"::: -->
:::moniker range="=azure-pipelines"

**`diagnosticsEnabled`** - **Collect advanced diagnostics in case of catastrophic failures**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Collects diagnostic data to troubleshoot catastrophic failures, such as a test crash.
When this option is checked, a sequence XML file is generated and attached to the test run. The sequence file contains information about the sequence in which the tests had run, so a potential culprit test can be identified.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="collectDumpOn"::: -->
:::moniker range="=azure-pipelines"

**`collectDumpOn`** - **Collect process dump and attach to test run report**<br>
`string`. Optional. Use when `diagnosticsEnabled = true`. Allowed values: `onAbortOnly` (On abort only), `always`, `never`. Default value: `onAbortOnly`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Collects a mini dump that can be used for further analysis.

- **onAbortOnly** - a mini dump will be collected only when the test run is aborted.
- **Always** - a mini dump will always be collected regardless of whether the test run completes or not.
- **Never** - a mini dump will not be collected regardless of whether the test run completes or not.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="rerunFailedTests"::: -->
:::moniker range="=azure-pipelines"

**`rerunFailedTests`** - **Rerun failed tests**<br>
`boolean`. Default value: `False`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Reruns any failed tests until they pass or until the maximum number of attempts is reached.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="rerunType"::: -->
:::moniker range="=azure-pipelines"

**`rerunType`** - **Do not rerun if test failures exceed specified threshold**<br>
`string`. Optional. Use when `rerunFailedTests = true`. Allowed values: `basedOnTestFailurePercentage` (% failure), `basedOnTestFailureCount` (# of failed tests). Default value: `basedOnTestFailurePercentage`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Avoids rerunning tests when the failure rate crosses the specified threshold. This is applicable if environment issues lead to massive failures. You can specify the percentage of failures or number of failed tests as a threshold.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="rerunFailedThreshold"::: -->
:::moniker range="=azure-pipelines"

**`rerunFailedThreshold`** - **% failure**<br>
`string`. Optional. Use when `rerunFailedTests = true && rerunType = basedOnTestFailurePercentage`. Default value: `30`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Avoids rerunning tests when the percentage of failed test cases crosses the specified threshold. This is applicable if environment issues lead to massive failures.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="rerunFailedTestCasesMaxLimit"::: -->
:::moniker range="=azure-pipelines"

**`rerunFailedTestCasesMaxLimit`** - **# of failed tests**<br>
`string`. Optional. Use when `rerunFailedTests = true && rerunType = basedOnTestFailureCount`. Default value: `5`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Avoids rerunning tests when the number of failed test cases crosses the specified limit. This is applicable if environment issues lead to massive failures.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="rerunMaxAttempts"::: -->
:::moniker range="=azure-pipelines"

**`rerunMaxAttempts`** - **Maximum # of attempts**<br>
`string`. Optional. Use when `rerunFailedTests = true`. Default value: `3`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the maximum number of times a failed test should be retried. If a test passes before the maximum number of attempts is reached, it will not be rerun again.
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

Use this task to run unit and functional tests (Selenium, Appium, Coded UI test, and more) using the Visual Studio Test runner. Along with MSTest-based tests, test frameworks that have a Visual Studio test adapter can also be executed, such as xUnit, NUnit, or Chutzpah.

Tests that the target .NET core framework can be executed by specifying the appropriate target framework value in the [.runsettings file](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file).

Tests can be distributed on multiple agents using version 2 of this task. For more information, see [Run tests in parallel using the Visual Studio Test task](/azure/devops/pipelines/test/parallel-testing-vstest).

### Check prerequisites

If you're using a Windows self-hosted agent, this prerequisite must be installed:

- [.NET Framework](/dotnet/framework/install/) 4.6.2 or a later version

### Demands

The agent must have the following capability:

**vstest**

The vstest demand can be satisfied in two ways:

1. Visual Studio is installed on the agent machine.
2. By using the [Visual Studio Test Platform Installer task](visual-studio-test-platform-installer-v1.md) in the pipeline definition.

### How can I run tests that use TestCase as a data source?

To run automated tests that use TestCase as a data source, the following is needed:

1. You must have Visual Studio 2017.6 or higher on the agent machine. Visual Studio Test Platform Installer task cannot be used to run tests that use TestCase as a data source.
1. Create a [PAT](/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate) that is authorized for the scope “Work Items (full)”.
1. Add a secure build or release variable called `Test.TestCaseAccessToken` with the value set to the PAT created in the previous step.

### I am running into issues when running data-driven xUnit and NUnit tests with some of the task options. Are there known limitations?

Data-driven tests that use xUnit and NUnit test frameworks have some known limitations and cannot be used with the following task options:

1. Rerun failed tests.
1. Distributing tests on multiple agents and batching options.
1. Test Impact Analysis.

The above limitations are because of how the adapters for these test frameworks discover and report data-driven tests.

### Does the VSTest task support running tests that target multiple target frameworks at a time?

Yes, starting from version `17.3` VSTest does support running tests that target multiple target frameworks at a time.
Prior to that, this wasn't possible due to a limitation from the [VSTest platform](https://github.com/microsoft/vstest/issues/2310) side.

If you want to run tests that belong to multiple target frameworks, you'll need to install a compatible version of VSTest via **Visual Studio Test Platform Installer** and set `vsTestVersion` to `toolsInstaller` to use it.

### While publishing the test result, getting this error: Failed to publish test results: Invalid Priority specified?

This error occur if any of the test methods has priority set above 255, fix the test method priority in the code and execute the tests again. You can review the trx file generated to see all the tests having priority greater than 255.
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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: vstest |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Test |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
