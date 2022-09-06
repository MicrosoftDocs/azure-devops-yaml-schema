---
title: VSTest@2 - Visual Studio Test v2 task
description: Run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test (VsTest) runner. Test frameworks that have a Visual Studio test adapter such as MsTest, xUnit, NUnit, Chutzpah (for JavaScript tests using QUnit, Mocha and Jasmine), etc. can be run. Tests can be distributed on multiple agents using this task (version 2).
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# VSTest@2 - Visual Studio Test v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test (VsTest) runner. Test frameworks that have a Visual Studio test adapter such as MsTest, xUnit, NUnit, Chutzpah (for JavaScript tests using QUnit, Mocha and Jasmine), etc. can be run. Tests can be distributed on multiple agents using this task (version 2).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# Visual Studio Test v2
# Run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test (VsTest) runner. Test frameworks that have a Visual Studio test adapter such as MsTest, xUnit, NUnit, Chutzpah (for JavaScript tests using QUnit, Mocha and Jasmine), etc. can be run. Tests can be distributed on multiple agents using this task (version 2).
- task: VSTest@2
  inputs:
  # Test selection
    testSelector: 'testAssemblies' # 'testAssemblies' | 'testPlan' | 'testRun'. Required. Select tests using. Default: 'testAssemblies'.
    testAssemblyVer2: # string. Required when testSelector = testAssemblies. Test files. 
    #testPlan: # string. Required when testSelector = testPlan. Test plan. 
    #testSuite: # string. Required when testSelector = testPlan. Test suite. 
    #testConfiguration: # string. Required when testSelector = testPlan. Test configuration. 
    #tcmTestRun: '$(test.RunId)' # string. Optional. Use when testSelector = testRun. Test Run. Default: '$(test.RunId)'.
    searchFolder: '$(System.DefaultWorkingDirectory)' # string. Required. Search folder. Default: '$(System.DefaultWorkingDirectory)'.
    #resultsFolder: '$(Agent.TempDirectory)\TestResults' # string. Test results folder. Default: '$(Agent.TempDirectory)\TestResults'.
    #testFiltercriteria: # string. Optional. Use when testSelector = testAssemblies. Test filter criteria. 
    #runOnlyImpactedTests: False # boolean. Optional. Use when testSelector = testAssemblies. Run only impacted tests. Default: False.
    #runAllTestsAfterXBuilds: '50' # string. Optional. Use when testSelector = testAssemblies && runOnlyImpactedTests = true. Number of builds after which all tests should be run. Default: '50'.
    #uiTests: false # boolean. Test mix contains UI tests. Default: false.
  # Execution options
    #vstestLocationMethod: 'version' # 'version' | 'location'. Select test platform using. Default: 'version'.
    #vsTestVersion: 'latest' # 'latest' | '16.0' | '15.0' | '14.0' | 'toolsInstaller'. Optional. Use when vstestLocationMethod = version. Test platform version. Default: 'latest'.
    #vstestLocation: # string. Optional. Use when vstestLocationMethod = location. Path to vstest.console.exe. 
    #runSettingsFile: # string. Settings file. 
    #overrideTestrunParameters: # string. Override test run parameters. 
    #pathtoCustomTestAdapters: # string. Path to custom test adapters. 
    #runInParallel: False # boolean. Run tests in parallel on multi-core machines. Default: False.
    #runTestsInIsolation: False # boolean. Run tests in isolation. Default: False.
    #codeCoverageEnabled: False # boolean. Code coverage enabled. Default: False.
    #otherConsoleOptions: # string. Other console options. 
    #diagnosticsEnabled: false # boolean. Collect advanced diagnostics in case of catastrophic failures. Default: false.
    #collectDumpOn: 'onAbortOnly' # 'onAbortOnly' | 'always' | 'never'. Optional. Use when diagnosticsEnabled = true. Collect process dump and attach to test run report. Default: 'onAbortOnly'.
    #rerunFailedTests: False # boolean. Rerun failed tests. Default: False.
    #rerunType: 'basedOnTestFailurePercentage' # 'basedOnTestFailurePercentage' | 'basedOnTestFailureCount'. Optional. Use when rerunFailedTests = true. Do not rerun if test failures exceed specified threshold. Default: 'basedOnTestFailurePercentage'.
    #rerunFailedThreshold: '30' # string. Optional. Use when rerunFailedTests = true && rerunType = basedOnTestFailurePercentage. % failure. Default: '30'.
    #rerunFailedTestCasesMaxLimit: '5' # string. Optional. Use when rerunFailedTests = true && rerunType = basedOnTestFailureCount. # of failed tests. Default: '5'.
    #rerunMaxAttempts: '3' # string. Optional. Use when rerunFailedTests = true. Maximum # of attempts. Default: '3'.
  # Advanced execution options
    #distributionBatchType: 'basedOnTestCases' # 'basedOnTestCases' | 'basedOnExecutionTime' | 'basedOnAssembly'. Batch tests. Default: 'basedOnTestCases'.
    #batchingBasedOnAgentsOption: 'autoBatchSize' # 'autoBatchSize' | 'customBatchSize'. Optional. Use when distributionBatchType = basedOnTestCases. Batch options. Default: 'autoBatchSize'.
    #customBatchSizeValue: '10' # string. Required when distributionBatchType = basedOnTestCases && batchingBasedOnAgentsOption = customBatchSize. Number of tests per batch. Default: '10'.
    #batchingBasedOnExecutionTimeOption: 'autoBatchSize' # 'autoBatchSize' | 'customTimeBatchSize'. Optional. Use when distributionBatchType = basedOnExecutionTime. Batch options. Default: 'autoBatchSize'.
    #customRunTimePerBatchValue: '60' # string. Required when distributionBatchType = basedOnExecutionTime && batchingBasedOnExecutionTimeOption = customTimeBatchSize. Running time (sec) per batch. Default: '60'.
    #dontDistribute: False # boolean. Replicate tests instead of distributing when multiple agents are used in the job. Default: False.
  # Reporting options
    #testRunTitle: # string. Test run title. 
    #platform: # string. Build platform. 
    #configuration: # string. Build configuration. 
    #publishRunAttachments: true # boolean. Upload test attachments. Default: true.
    #failOnMinTestsNotRun: False # boolean. Fail the task if a minimum number of tests are not run. Default: False.
    #minimumExpectedTests: '1' # string. Optional. Use when failOnMinTestsNotRun = true. Minimum # of tests. Default: '1'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Visual Studio Test v2
# Run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test (VsTest) runner. Test frameworks that have a Visual Studio test adapter such as MsTest, xUnit, NUnit, Chutzpah (for JavaScript tests using QUnit, Mocha and Jasmine), etc. can be run. Tests can be distributed on multiple agents using this task (version 2).
- task: VSTest@2
  inputs:
  # Test selection
    testSelector: 'testAssemblies' # 'testAssemblies' | 'testPlan' | 'testRun'. Required. Select tests using. Default: 'testAssemblies'.
    testAssemblyVer2: # string. Required when testSelector = testAssemblies. Test files. 
    #testPlan: # string. Required when testSelector = testPlan. Test plan. 
    #testSuite: # string. Required when testSelector = testPlan. Test suite. 
    #testConfiguration: # string. Required when testSelector = testPlan. Test configuration. 
    #tcmTestRun: '$(test.RunId)' # string. Optional. Use when testSelector = testRun. Test Run. Default: '$(test.RunId)'.
    searchFolder: '$(System.DefaultWorkingDirectory)' # string. Required. Search folder. Default: '$(System.DefaultWorkingDirectory)'.
    #testFiltercriteria: # string. Optional. Use when testSelector = testAssemblies. Test filter criteria. 
    #runOnlyImpactedTests: False # boolean. Optional. Use when testSelector = testAssemblies. Run only impacted tests. Default: False.
    #runAllTestsAfterXBuilds: '50' # string. Optional. Use when testSelector = testAssemblies && runOnlyImpactedTests = true. Number of builds after which all tests should be run. Default: '50'.
    #uiTests: false # boolean. Test mix contains UI tests. Default: false.
  # Execution options
    #vstestLocationMethod: 'version' # 'version' | 'location'. Select test platform using. Default: 'version'.
    #vsTestVersion: 'latest' # 'latest' | '16.0' | '15.0' | '14.0' | 'toolsInstaller'. Optional. Use when vstestLocationMethod = version. Test platform version. Default: 'latest'.
    #vstestLocation: # string. Optional. Use when vstestLocationMethod = location. Path to vstest.console.exe. 
    #runSettingsFile: # string. Settings file. 
    #overrideTestrunParameters: # string. Override test run parameters. 
    #pathtoCustomTestAdapters: # string. Path to custom test adapters. 
    #runInParallel: False # boolean. Run tests in parallel on multi-core machines. Default: False.
    #runTestsInIsolation: False # boolean. Run tests in isolation. Default: False.
    #codeCoverageEnabled: False # boolean. Code coverage enabled. Default: False.
    #otherConsoleOptions: # string. Other console options. 
    #diagnosticsEnabled: false # boolean. Collect advanced diagnostics in case of catastrophic failures. Default: false.
    #collectDumpOn: 'onAbortOnly' # 'onAbortOnly' | 'always' | 'never'. Optional. Use when diagnosticsEnabled = true. Collect process dump and attach to test run report. Default: 'onAbortOnly'.
    #rerunFailedTests: False # boolean. Rerun failed tests. Default: False.
    #rerunType: 'basedOnTestFailurePercentage' # 'basedOnTestFailurePercentage' | 'basedOnTestFailureCount'. Optional. Use when rerunFailedTests = true. Do not rerun if test failures exceed specified threshold. Default: 'basedOnTestFailurePercentage'.
    #rerunFailedThreshold: '30' # string. Optional. Use when rerunFailedTests = true && rerunType = basedOnTestFailurePercentage. % failure. Default: '30'.
    #rerunFailedTestCasesMaxLimit: '5' # string. Optional. Use when rerunFailedTests = true && rerunType = basedOnTestFailureCount. # of failed tests. Default: '5'.
    #rerunMaxAttempts: '3' # string. Optional. Use when rerunFailedTests = true. Maximum # of attempts. Default: '3'.
  # Advanced execution options
    #distributionBatchType: 'basedOnTestCases' # 'basedOnTestCases' | 'basedOnExecutionTime' | 'basedOnAssembly'. Batch tests. Default: 'basedOnTestCases'.
    #batchingBasedOnAgentsOption: 'autoBatchSize' # 'autoBatchSize' | 'customBatchSize'. Optional. Use when distributionBatchType = basedOnTestCases. Batch options. Default: 'autoBatchSize'.
    #customBatchSizeValue: '10' # string. Required when distributionBatchType = basedOnTestCases && batchingBasedOnAgentsOption = customBatchSize. Number of tests per batch. Default: '10'.
    #batchingBasedOnExecutionTimeOption: 'autoBatchSize' # 'autoBatchSize' | 'customTimeBatchSize'. Optional. Use when distributionBatchType = basedOnExecutionTime. Batch options. Default: 'autoBatchSize'.
    #customRunTimePerBatchValue: '60' # string. Required when distributionBatchType = basedOnExecutionTime && batchingBasedOnExecutionTimeOption = customTimeBatchSize. Running time (sec) per batch. Default: '60'.
    #dontDistribute: False # boolean. Replicate tests instead of distributing when multiple agents are used in the job. Default: False.
  # Reporting options
    #testRunTitle: # string. Test run title. 
    #platform: # string. Build platform. 
    #configuration: # string. Build configuration. 
    #publishRunAttachments: true # boolean. Upload test attachments. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Visual Studio Test v2
# Run unit and functional tests (Selenium, Appium, Coded UI test, etc.) using the Visual Studio Test (VsTest) runner. Test frameworks that have a Visual Studio test adapter such as MsTest, xUnit, NUnit, Chutzpah (for JavaScript tests using QUnit, Mocha and Jasmine), etc. can be run. Tests can be distributed on multiple agents using this task (version 2).
- task: VSTest@2
  inputs:
  # Test selection
    testSelector: 'testAssemblies' # 'testAssemblies' | 'testPlan' | 'testRun'. Required. Select tests using. Default: 'testAssemblies'.
    testAssemblyVer2: # string. Required when testSelector = testAssemblies. Test files. 
    #testPlan: # string. Required when testSelector = testPlan. Test plan. 
    #testSuite: # string. Required when testSelector = testPlan. Test suite. 
    #testConfiguration: # string. Required when testSelector = testPlan. Test configuration. 
    #tcmTestRun: '$(test.RunId)' # string. Optional. Use when testSelector = testRun. Test Run. Default: '$(test.RunId)'.
    searchFolder: '$(System.DefaultWorkingDirectory)' # string. Required. Search folder. Default: '$(System.DefaultWorkingDirectory)'.
    #testFiltercriteria: # string. Optional. Use when testSelector = testAssemblies. Test filter criteria. 
    #runOnlyImpactedTests: False # boolean. Optional. Use when testSelector = testAssemblies. Run only impacted tests. Default: False.
    #runAllTestsAfterXBuilds: '50' # string. Optional. Use when testSelector = testAssemblies && runOnlyImpactedTests = true. Number of builds after which all tests should be run. Default: '50'.
    #uiTests: false # boolean. Test mix contains UI tests. Default: false.
  # Execution options
    #vstestLocationMethod: 'version' # 'version' | 'location'. Select test platform using. Default: 'version'.
    #vsTestVersion: 'latest' # 'latest' | '16.0' | '15.0' | '14.0' | 'toolsInstaller'. Optional. Use when vstestLocationMethod = version. Test platform version. Default: 'latest'.
    #vstestLocation: # string. Optional. Use when vstestLocationMethod = location. Path to vstest.console.exe. 
    #runSettingsFile: # string. Settings file. 
    #overrideTestrunParameters: # string. Override test run parameters. 
    #pathtoCustomTestAdapters: # string. Path to custom test adapters. 
    #runInParallel: False # boolean. Run tests in parallel on multi-core machines. Default: False.
    #runTestsInIsolation: False # boolean. Run tests in isolation. Default: False.
    #codeCoverageEnabled: False # boolean. Code coverage enabled. Default: False.
    #otherConsoleOptions: # string. Other console options. 
    #diagnosticsEnabled: True # boolean. Collect advanced diagnostics in case of catastrophic failures. Default: True.
    #collectDumpOn: 'onAbortOnly' # 'onAbortOnly' | 'always' | 'never'. Optional. Use when diagnosticsEnabled = true. Collect process dump and attach to test run report. Default: 'onAbortOnly'.
    #rerunFailedTests: False # boolean. Rerun failed tests. Default: False.
    #rerunType: 'basedOnTestFailurePercentage' # 'basedOnTestFailurePercentage' | 'basedOnTestFailureCount'. Optional. Use when rerunFailedTests = true. Do not rerun if test failures exceed specified threshold. Default: 'basedOnTestFailurePercentage'.
    #rerunFailedThreshold: '30' # string. Optional. Use when rerunFailedTests = true && rerunType = basedOnTestFailurePercentage. % failure. Default: '30'.
    #rerunFailedTestCasesMaxLimit: '5' # string. Optional. Use when rerunFailedTests = true && rerunType = basedOnTestFailureCount. # of failed tests. Default: '5'.
    #rerunMaxAttempts: '3' # string. Optional. Use when rerunFailedTests = true. Maximum # of attempts. Default: '3'.
  # Advanced execution options
    #distributionBatchType: 'basedOnTestCases' # 'basedOnTestCases' | 'basedOnExecutionTime' | 'basedOnAssembly'. Batch tests. Default: 'basedOnTestCases'.
    #batchingBasedOnAgentsOption: 'autoBatchSize' # 'autoBatchSize' | 'customBatchSize'. Optional. Use when distributionBatchType = basedOnTestCases. Batch options. Default: 'autoBatchSize'.
    #customBatchSizeValue: '10' # string. Required when distributionBatchType = basedOnTestCases && batchingBasedOnAgentsOption = customBatchSize. Number of tests per batch. Default: '10'.
    #batchingBasedOnExecutionTimeOption: 'autoBatchSize' # 'autoBatchSize' | 'customTimeBatchSize'. Optional. Use when distributionBatchType = basedOnExecutionTime. Batch options. Default: 'autoBatchSize'.
    #customRunTimePerBatchValue: '60' # string. Required when distributionBatchType = basedOnExecutionTime && batchingBasedOnExecutionTimeOption = customTimeBatchSize. Running time (sec) per batch. Default: '60'.
    #dontDistribute: False # boolean. Do not distribute tests and replicate instead when multiple agents are used in the job. Default: False.
  # Reporting options
    #testRunTitle: # string. Test run title. 
    #platform: # string. Build platform. 
    #configuration: # string. Build configuration. 
    #publishRunAttachments: true # boolean. Upload test attachments. Default: true.
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

<!-- :::item name="testSelector"::: -->
:::moniker range="<=azure-pipelines"

**`testSelector`** - **Select tests using**<br>
Type: string. Required. Allowed values: 'testAssemblies', 'testPlan', 'testRun'. Default value: 'testAssemblies'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<ul><li><b>Test assembly: </b>Use this option to specify one or more test assemblies that contain your tests. You can optionally specify a filter criteria to select only specific tests.</li><li><b>Test plan: </b>Use this option to run tests from your test plan that have an automated test method associated with it. To learn more about how to associate tests with a test case work item, see [Associate automated tests with test cases](/azure/devops/test/associate-automated-test-with-test-case).</li><li><b>Test run: </b>Use this option when you are setting up an environment to run tests from [test plans](/azure/devops/test/run-automated-tests-from-test-hub). This option should not be used when running tests in a continuous integration/continuous deployment (CI/CD) pipeline.</li>
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testAssemblyVer2"::: -->
:::moniker range=">=azure-pipelines-2019"

**`testAssemblyVer2`** - **Test files**<br>
Type: string. Required when testSelector = testAssemblies.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run tests from the specified files. Ordered tests and webtests can be run by specifying the `.orderedtest` and `.webtest` files respectively. To run `.webtest`, Visual Studio 2017 Update 4 or higher is needed. The file paths are relative to the search folder. Supports multiple lines of minimatch patterns. [More Information](/azure/devops/pipelines/tasks/file-matching-patterns)
Default value: `**\\*test*.dll\n!**\\*TestAdapter.dll\n!**\\obj\\**`
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`testAssemblyVer2`** - **Test assemblies**<br>
Type: string. Required when testSelector = testAssemblies.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run tests from the specified files.<br>Ordered tests and webtests can be run by specifying the .orderedtest and .webtest files respectively. To run .webtest, Visual Studio 2017 Update 4 or higher is needed. <br><br>The file paths are relative to the search folder. Supports multiple lines of minimatch patterns. [More information](https://aka.ms/minimatchexamples).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testPlan"::: -->
:::moniker range="<=azure-pipelines"

**`testPlan`** - **Test plan**<br>
Type: string. Required when testSelector = testPlan.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a test plan containing test suites with automated test cases.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testSuite"::: -->
:::moniker range="<=azure-pipelines"

**`testSuite`** - **Test suite**<br>
Type: string. Required when testSelector = testPlan.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select one or more test suites containing automated test cases. Test case work items must be associated with an automated test method. [Learn more](https://go.microsoft.com/fwlink/?linkid=847773).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testConfiguration"::: -->
:::moniker range="<=azure-pipelines"

**`testConfiguration`** - **Test configuration**<br>
Type: string. Required when testSelector = testPlan.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select Test Configuration.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tcmTestRun"::: -->
:::moniker range="<=azure-pipelines"

**`tcmTestRun`** - **Test Run**<br>
Type: string. Optional. Use when testSelector = testRun. Default value: '$(test.RunId)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Test run based selection is used when triggering automated test runs from [test plans](/azure/devops/test/run-automated-tests-from-test-hub). This option cannot be used for running tests in the CI/CD pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="searchFolder"::: -->
:::moniker range="<=azure-pipelines"

**`searchFolder`** - **Search folder**<br>
Type: string. Required. Default value: '$(System.DefaultWorkingDirectory)'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Folder to search for the test assemblies.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resultsFolder"::: -->
:::moniker range=">=azure-pipelines-2020"

**`resultsFolder`** - **Test results folder**<br>
Type: string. Default value: '$(Agent.TempDirectory)\TestResults'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Folder to store test results. When this input is not specified, results are stored in $(Agent.TempDirectory)/TestResults by default, which is cleaned at the end of a pipeline run. The results directory will always be cleaned up at the start of the vstest task before the tests are run. Relative folder path if provided will be considered relative to $(Agent.TempDirectory).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testFiltercriteria"::: -->
:::moniker range="<=azure-pipelines"

**`testFiltercriteria`** - **Test filter criteria**<br>
Type: string. Optional. Use when testSelector = testAssemblies.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional criteria to filter tests from Test assemblies. For example: `Priority=1|Name=MyTestMethod`. [More information](/previous-versions/jj155796(v=vs.140)).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runOnlyImpactedTests"::: -->
:::moniker range="<=azure-pipelines"

**`runOnlyImpactedTests`** - **Run only impacted tests**<br>
Type: boolean. Optional. Use when testSelector = testAssemblies. Default value: False.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Automatically select, and run only the tests needed to validate the code change. [More information](https://aka.ms/tialearnmore).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runAllTestsAfterXBuilds"::: -->
:::moniker range="<=azure-pipelines"

**`runAllTestsAfterXBuilds`** - **Number of builds after which all tests should be run**<br>
Type: string. Optional. Use when testSelector = testAssemblies && runOnlyImpactedTests = true. Default value: '50'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Number of builds after which to automatically run all tests. Test Impact Analysis stores the mapping between test cases and source code. It is recommended to regenerate the mapping by running all tests, on a regular basis.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="uiTests"::: -->
:::moniker range="<=azure-pipelines"

**`uiTests`** - **Test mix contains UI tests**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
To run UI tests, ensure that the agent is set to run in [interactive mode](/azure/devops/pipelines/agents/agents) with autologon enabled. Setting up an agent to run interactively must be done before queueing the build/release. Checking this box does not configure the agent in interactive mode automatically. This option in the task is to only serve as a reminder to configure agent appropriately to avoid failures. Hosted Windows agents from the VS 2015 and 2017 pools can be used to run UI tests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstestLocationMethod"::: -->
:::moniker range="<=azure-pipelines"

**`vstestLocationMethod`** - **Select test platform using**<br>
Type: string. Allowed values: 'version', 'location'. Default value: 'version'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify which test platform should be used.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vsTestVersion"::: -->
:::moniker range=">=azure-pipelines-2019"

**`vsTestVersion`** - **Test platform version**<br>
Type: string. Optional. Use when vstestLocationMethod = version. Allowed values: 'latest', '16.0', '15.0', '14.0', 'toolsInstaller'. Default value: 'latest'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of Visual Studio test to use. If latest is specified it chooses Visual Studio 2017 or Visual Studio 2015 depending on what is installed. Visual Studio 2013 is not supported. To run tests without needing Visual Studio on the agent, use the ‘Installed by tools installer’ option. Be sure to include the ‘Visual Studio Test Platform Installer’ task to acquire the test platform from nuget.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`vsTestVersion`** - **Test platform version**<br>
Type: string. Optional. Use when vstestLocationMethod = version. Allowed values: 'latest', '15.0', '14.0', 'toolsInstaller'. Default value: 'latest'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of Visual Studio test to use. If latest is specified it chooses Visual Studio 2017 or Visual Studio 2015 depending on what is installed. Visual Studio 2013 is not supported. To run tests without needing Visual Studio on the agent, use the ‘Installed by tools installer’ option. Be sure to include the ‘Visual Studio Test Platform Installer’ task to acquire the test platform from nuget.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="vstestLocation"::: -->
:::moniker range="<=azure-pipelines"

**`vstestLocation`** - **Path to vstest.console.exe**<br>
Type: string. Optional. Use when vstestLocationMethod = location.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the path to VSTest.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runSettingsFile"::: -->
:::moniker range="<=azure-pipelines"

**`runSettingsFile`** - **Settings file**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to `runsettings` or `testsettings` file to use with the tests.Starting with Visual Studio 15.7, it is recommended to use runsettings for all types of tests. To learn more about converting a .testsettings file to a .runsettings file, see [this topic](https://github.com/Microsoft/vstest-docs/blob/main/RFCs/0023-TestSettings-Deprecation.md).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="overrideTestrunParameters"::: -->
:::moniker range="<=azure-pipelines"

**`overrideTestrunParameters`** - **Override test run parameters**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Override parameters defined in the `TestRunParameters` section of runsettings file or `Properties` section of testsettings file. For example: `-key1 value1 -key2 value2`. Note: Properties specified in testsettings file can be accessed via the TestContext using Visual Studio 2017 Update 4 or higher.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pathtoCustomTestAdapters"::: -->
:::moniker range="<=azure-pipelines"

**`pathtoCustomTestAdapters`** - **Path to custom test adapters**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Directory path to custom test adapters. Adapters residing in the same folder as the test assemblies are automatically discovered.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runInParallel"::: -->
:::moniker range="<=azure-pipelines"

**`runInParallel`** - **Run tests in parallel on multi-core machines**<br>
Type: boolean. Default value: False.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set, tests will run in parallel leveraging available cores of the machine. This will override the MaxCpuCount if specified in your runsettings file. [Click here](https://aka.ms/paralleltestexecution) to learn more about how tests are run in parallel.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runTestsInIsolation"::: -->
:::moniker range="<=azure-pipelines"

**`runTestsInIsolation`** - **Run tests in isolation**<br>
Type: boolean. Default value: False.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs the tests in an isolated process. This makes vstest.console.exe process less likely to be stopped on an error in the tests, but tests might run slower. This option currently cannot be used when running with the multi-agent job setting.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageEnabled"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageEnabled`** - **Code coverage enabled**<br>
Type: boolean. Default value: False.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Collect code coverage information from the test run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="otherConsoleOptions"::: -->
:::moniker range="<=azure-pipelines"

**`otherConsoleOptions`** - **Other console options**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Other console options that can be passed to vstest.console.exe, as documented <a href="https://aka.ms/vstestotherconsoleoptions" target="_blank">here</a>. <p>These options are not supported and will be ignored when running tests using the ‘Multi agent’ parallel setting of an agent job or when running tests using ‘Test plan’ or 'Test run' option or when a custom batching option is selected. The options can be specified using a settings file instead.</p>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="distributionBatchType"::: -->
:::moniker range="<=azure-pipelines"

**`distributionBatchType`** - **Batch tests**<br>
Type: string. Allowed values: 'basedOnTestCases', 'basedOnExecutionTime', 'basedOnAssembly'. Default value: 'basedOnTestCases'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A batch is a group of tests. A batch of tests runs its tests at the same time and results are published for the batch. If the job in which the task runs is set to use multiple agents, each agent picks up any available batches of tests to run in parallel.<br><br><b>Based on the number of tests and agents:</b> Simple batching based on the number of tests and agents participating in the test run.<br><br><b>Based on past running time of tests:</b> This batching considers past running time to create batches of tests such that each batch has approximately equal running time.<br><br><b>Based on test assemblies:</b> Tests from an assembly are batched together.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="batchingBasedOnAgentsOption"::: -->
:::moniker range="<=azure-pipelines"

**`batchingBasedOnAgentsOption`** - **Batch options**<br>
Type: string. Optional. Use when distributionBatchType = basedOnTestCases. Allowed values: 'autoBatchSize', 'customBatchSize'. Default value: 'autoBatchSize'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Simple batching based on the number of tests and agents participating in the test run. When the batch size is automatically determined, each batch contains `(total number of tests / number of agents)` tests. If a batch size is specified, each batch will contain the specified number of tests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customBatchSizeValue"::: -->
:::moniker range="<=azure-pipelines"

**`customBatchSizeValue`** - **Number of tests per batch**<br>
Type: string. Required when distributionBatchType = basedOnTestCases && batchingBasedOnAgentsOption = customBatchSize. Default value: '10'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify batch size.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="batchingBasedOnExecutionTimeOption"::: -->
:::moniker range="<=azure-pipelines"

**`batchingBasedOnExecutionTimeOption`** - **Batch options**<br>
Type: string. Optional. Use when distributionBatchType = basedOnExecutionTime. Allowed values: 'autoBatchSize', 'customTimeBatchSize'. Default value: 'autoBatchSize'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This batching considers past running time to create batches of tests such that each batch has approximately equal running time. Quick running tests will be batched together, while longer running tests may belong to a separate batch. When this option is used with the multi-agent job setting, total test time is reduced to a minimum.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customRunTimePerBatchValue"::: -->
:::moniker range="<=azure-pipelines"

**`customRunTimePerBatchValue`** - **Running time (sec) per batch**<br>
Type: string. Required when distributionBatchType = basedOnExecutionTime && batchingBasedOnExecutionTimeOption = customTimeBatchSize. Default value: '60'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the running time (sec) per batch.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dontDistribute"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`dontDistribute`** - **Replicate tests instead of distributing when multiple agents are used in the job**<br>
Type: boolean. Default value: False.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choosing this option will not distribute tests across agents when the task is running in a multi-agent job.<br>Each of the selected test(s) will be repeated on each agent.<br>The option is not applicable when the agent job is configured to run with no parallelism or with the multi-config option.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`dontDistribute`** - **Do not distribute tests and replicate instead when multiple agents are used in the job**<br>
Type: boolean. Default value: False.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choosing this option will not distribute tests across agents when the task is running in a multi-agent job.<br>Each of the selected test(s) will be repeated on each agent.<br>The option is not applicable when the agent job is configured to run with no parallelism or with the multi-config option.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`dontDistribute`** - **Do not distribute tests and replicate instead when multiple agents are used in the phase**<br>
Type: boolean. Default value: False.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choosing this option will not distribute tests across agents when the task is running in a multi-agent phase.<br>Each of the selected test(s) will be repeated on each agent.<br>The option is not applicable when the agent phase is configured to run with no parallelism or with the multi-config option.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range="<=azure-pipelines"

**`testRunTitle`** - **Test run title**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the test run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="platform"::: -->
:::moniker range="<=azure-pipelines"

**`platform`** - **Build platform**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Build platform against which the tests should be reported. If you have defined a variable for platform in your build task, use that here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Build configuration**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Build configuration against which the tests should be reported. If you have defined a variable for configuration in your build task, use that here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishRunAttachments"::: -->
:::moniker range="<=azure-pipelines"

**`publishRunAttachments`** - **Upload test attachments**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Opt in/out of publishing run level attachments.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnMinTestsNotRun"::: -->
:::moniker range=">=azure-pipelines-2020"

**`failOnMinTestsNotRun`** - **Fail the task if a minimum number of tests are not run.**<br>
Type: boolean. Default value: False.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this option to fail the task if a minimum number of tests are not run. This may be useful if any changes to task inputs or underlying test adapter dependencies lead to only a subset of the desired tests to be found.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="minimumExpectedTests"::: -->
:::moniker range=">=azure-pipelines-2020"

**`minimumExpectedTests`** - **Minimum # of tests**<br>
Type: string. Optional. Use when failOnMinTestsNotRun = true. Default value: '1'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the minimum # of tests that should be run for the task to succeed. Total tests executed is calculated as the sum of passed, failed and aborted tests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="diagnosticsEnabled"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`diagnosticsEnabled`** - **Collect advanced diagnostics in case of catastrophic failures**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this option to turn on collection of diagnostic data to troubleshoot catastrophic failures such as test crash.
When this option is checked, a sequence XML file is generated and attached to the test run. The sequence file contains information about the sequence in which tests ran, so that a potentially culprit test can be identified.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`diagnosticsEnabled`** - **Collect advanced diagnostics in case of catastrophic failures**<br>
Type: boolean. Default value: True.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this option to turn on collection of diagnostic data to troubleshoot catastrophic failures such as test crash.
When this option is checked, a sequence XML file is generated and attached to the test run. The sequence file contains information about the sequence in which tests ran, so that a potentially culprit test can be identified.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="collectDumpOn"::: -->
:::moniker range=">=azure-pipelines-2019"

**`collectDumpOn`** - **Collect process dump and attach to test run report**<br>
Type: string. Optional. Use when diagnosticsEnabled = true. Allowed values: 'onAbortOnly', 'always', 'never'. Default value: 'onAbortOnly'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this option to collect a mini-dump that can be used for further analysis.
* **onAbortOnly** - On abort only: mini-dump will be collected only when test run is aborted.
* **Always** - mini-dump will always be collected regardless of whether the test run completes or not.
* **Never** - mini-dump will not be collected regardless of whether the test run completes or not
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="rerunFailedTests"::: -->
:::moniker range="<=azure-pipelines"

**`rerunFailedTests`** - **Rerun failed tests**<br>
Type: boolean. Default value: False.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selecting this option will rerun any failed tests until they pass or the maximum # of attempts is reached.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="rerunType"::: -->
:::moniker range="<=azure-pipelines"

**`rerunType`** - **Do not rerun if test failures exceed specified threshold**<br>
Type: string. Optional. Use when rerunFailedTests = true. Allowed values: 'basedOnTestFailurePercentage', 'basedOnTestFailureCount'. Default value: 'basedOnTestFailurePercentage'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this option to avoid rerunning tests when failure rate crosses the specified threshold. This is applicable if any environment issues leads to massive failures.<br>You can specify % failures or # of failed tests as a threshold.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="rerunFailedThreshold"::: -->
:::moniker range="<=azure-pipelines"

**`rerunFailedThreshold`** - **% failure**<br>
Type: string. Optional. Use when rerunFailedTests = true && rerunType = basedOnTestFailurePercentage. Default value: '30'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this option to avoid rerunning tests when failure rate crosses the specified threshold. This is applicable if any environment issues leads to massive failures.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="rerunFailedTestCasesMaxLimit"::: -->
:::moniker range="<=azure-pipelines"

**`rerunFailedTestCasesMaxLimit`** - **# of failed tests**<br>
Type: string. Optional. Use when rerunFailedTests = true && rerunType = basedOnTestFailureCount. Default value: '5'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use this option to avoid rerunning tests when number of failed test cases crosses specified limit. This is applicable if any environment issues leads to massive failures.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="rerunMaxAttempts"::: -->
:::moniker range="<=azure-pipelines"

**`rerunMaxAttempts`** - **Maximum # of attempts**<br>
Type: string. Optional. Use when rerunFailedTests = true. Default value: '3'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the maximum # of times a failed test should be retried. If a test passes before the maximum # of attempts is reached, it will not be rerun further.
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
## Remarks

Use this task to run unit and functional tests (Selenium, Appium, Coded UI test, and more)
using the Visual Studio Test Runner. Along with MSTest-based tests, test frameworks that have a
Visual Studio test adapter, such as xUnit, NUnit, Chutzpah, can also be executed.  

Tests that the target .NET core framework can be executed by specifying the appropriate target framework value in the [.runsettings file](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file).

Tests can be distributed on multiple agents using version 2 of this task. For more information, see [Run tests in parallel using the Visual Studio Test task](/azure/devops/pipelines/test/parallel-testing-vstest).

### Check prerequisites

If you're using a Windows self-hosted agent, be sure that your machine has this prerequisite installed:

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
1. Add a secure Build or Release variable called Test.TestCaseAccessToken with the value set to the PAT created in the previous step.

### I am running into issues when running data-driven xUnit and NUnit tests with some of the task options. Are there known limitations?

Data-driven tests that use xUnit and NUnit test frameworks have some known limitations and cannot be used with the following task options:

1. Rerun failed tests.
1. Distributing tests on multiple agents and batching options.
1. Test Impact Analysis.

The above limitations are because of how the adapters for these test frameworks discover and report data-driven tests.

### Does the VsTest task support running tests that target multiple target frameworks at a time?

The VsTest task doesn't support running tests that target multiple target frameworks at a time as this is a limitation from the [vstest platform](https://github.com/microsoft/vstest/issues/2310) side.
If you want to run tests that belong to multiple target frameworks, you'll need multiple instances of the vstest task, one per set of dlls that target a particular framework.
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
| Agent version |  2.103.0 or greater |
| Task category | Test |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->