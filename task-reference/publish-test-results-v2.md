---
title: PublishTestResults@2 - Publish Test Results v2 task
description: Publish test results to Azure Pipelines.
ms.date: 05/06/2025
monikerRange: "<=azure-pipelines"
---

# PublishTestResults@2 - Publish Test Results v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Publish test results to Azure Pipelines.
<!-- :::editable-content-end::: -->

:::moniker-end

<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.2"

```yaml
# Publish Test Results v2
# Publish test results to Azure Pipelines.
- task: PublishTestResults@2
  inputs:
    testResultsFormat: 'JUnit' # 'JUnit' | 'NUnit' | 'VSTest' | 'XUnit' | 'CTest'. Alias: testRunner. Required. Test result format. Default: JUnit.
    testResultsFiles: '**/TEST-*.xml' # string. Required. Test results files. Default: **/TEST-*.xml.
    #searchFolder: '$(System.DefaultWorkingDirectory)' # string. Search folder. Default: $(System.DefaultWorkingDirectory).
    #mergeTestResults: false # boolean. Merge test results. Default: false.
    #failTaskOnFailedTests: false # boolean. Fail if there are test failures. Default: false.
    #failTaskOnFailureToPublishResults: false # boolean. Fail if there is failure in publishing test results. Default: false.
    #failTaskOnMissingResultsFile: false # boolean. Fail if no result files are found. Default: false.
    #testRunTitle: # string. Test run title. 
  # Advanced
    #buildPlatform: # string. Alias: platform. Build Platform. 
    #buildConfiguration: # string. Alias: configuration. Build Configuration. 
    #publishRunAttachments: true # boolean. Upload test results files. Default: true.
```

:::moniker-end

:::moniker range="<=azure-pipelines-2022.1"

```yaml
# Publish Test Results v2
# Publish test results to Azure Pipelines.
- task: PublishTestResults@2
  inputs:
    testResultsFormat: 'JUnit' # 'JUnit' | 'NUnit' | 'VSTest' | 'XUnit' | 'CTest'. Alias: testRunner. Required. Test result format. Default: JUnit.
    testResultsFiles: '**/TEST-*.xml' # string. Required. Test results files. Default: **/TEST-*.xml.
    #searchFolder: '$(System.DefaultWorkingDirectory)' # string. Search folder. Default: $(System.DefaultWorkingDirectory).
    #mergeTestResults: false # boolean. Merge test results. Default: false.
    #failTaskOnFailedTests: false # boolean. Fail if there are test failures. Default: false.
    #testRunTitle: # string. Test run title. 
  # Advanced
    #buildPlatform: # string. Alias: platform. Build Platform. 
    #buildConfiguration: # string. Alias: configuration. Build Configuration. 
    #publishRunAttachments: true # boolean. Upload test results files. Default: true.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="testResultsFormat"::: -->
:::moniker range="<=azure-pipelines"

**`testResultsFormat`** - **Test result format**<br>
[Input alias](index.md#what-are-task-input-aliases): `testRunner`. `string`. Required. Allowed values: `JUnit`, `NUnit`, `VSTest`, `XUnit`, `CTest`. Default value: `JUnit`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the format of the results files you want to publish. The following formats are supported: [CTest](https://cmake.org/cmake/help/latest/manual/ctest.1.html), [JUnit](https://github.com/windyroad/JUnit-Schema/blob/master/JUnit.xsd), [NUnit 2](https://docs.nunit.org/), [NUnit 3](https://docs.nunit.org/articles/nunit/technical-notes/usage/Test-Result-XML-Format.html), Visual Studio Test (TRX) and [xUnit 2](https://xunit.net/docs/format-xml-v2).

> [!TIP]
> `VSTest` format refers to the TRX format. So, it works also if you are producing TRX with [Microsoft.Testing.Platform (MTP)](https://aka.ms/mtp-overview) and is not specific to VSTest. The value is VSTest for historical reasons, before the introduction of MTP.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testResultsFiles"::: -->
:::moniker range="<=azure-pipelines"

**`testResultsFiles`** - **Test results files**<br>
`string`. Required. Default value: `**/TEST-*.xml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies one or more test results files.

* You can use a single-folder wildcard (`*`) and recursive wildcards (`**`). For example, `**/TEST-*.xml` searches for all the XML files whose names start with `TEST-` in all subdirectories. If using VSTest as the test result format, the file type should be changed to `.trx` e.g. `**/TEST-*.trx`
* Multiple paths can be specified, separated by a new line.
* Additionally accepts [minimatch patterns](/azure/devops/pipelines/tasks/file-matching-patterns).

For example, `!TEST[1-3].xml` excludes files named `TEST1.xml`, `TEST2.xml`, or `TEST3.xml`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="searchFolder"::: -->
:::moniker range="<=azure-pipelines"

**`searchFolder`** - **Search folder**<br>
`string`. Default value: `$(System.DefaultWorkingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the folder to search for the test result files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mergeTestResults"::: -->
:::moniker range="<=azure-pipelines"

**`mergeTestResults`** - **Merge test results**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When this boolean's value is `true`, the task reports test results from all the files against a single [test run](/azure/devops/pipelines/test/test-glossary). If the value is `false`, the task creates a separate test run for each test result file. To optimize for better performance, results will always be merged into a single run if there are more than 100 result files even if this option is set to `false`.

> [!NOTE]
> Use the merge test results setting to combine files from the same test framework to ensure results mapping and duration are calculated correctly.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failTaskOnFailedTests"::: -->
:::moniker range="<=azure-pipelines"

**`failTaskOnFailedTests`** - **Fail if there are test failures**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. When this boolean's value is `true`, the task will fail if any of the tests in the results file are marked as failed. The default is `false`, which will simply publish the results from the results file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failTaskOnFailureToPublishResults"::: -->
:::moniker range=">=azure-pipelines-2022.2"

**`failTaskOnFailureToPublishResults`** - **Fail if there is failure in publishing test results**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When `true`, fails the task if there is failure in publishing test results.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failTaskOnMissingResultsFile"::: -->
:::moniker range=">=azure-pipelines-2022.2"

**`failTaskOnMissingResultsFile`** - **Fail if no result files are found**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fail the task if no result files are found.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range="<=azure-pipelines"

**`testRunTitle`** - **Test run title**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies a name for the test run against which the results will be reported. Variable names declared in the build or release pipeline can be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildPlatform"::: -->
:::moniker range="<=azure-pipelines"

**`buildPlatform`** - **Build Platform**<br>
[Input alias](index.md#what-are-task-input-aliases): `platform`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the build platform against which the test run should be reported. For example: `x64` or `x86`. If you defined a variable for the platform in your build task, use it here.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildConfiguration"::: -->
:::moniker range="<=azure-pipelines"

**`buildConfiguration`** - **Build Configuration**<br>
[Input alias](index.md#what-are-task-input-aliases): `configuration`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the build configuration against which the test run should be reported. For example: `Debug` or `Release`. If you defined a variable for the configuration in your build task, use it here.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishRunAttachments"::: -->
:::moniker range="<=azure-pipelines"

**`publishRunAttachments`** - **Upload test results files**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. When this boolean's value is `true`, the task uploads all the test result files as attachments to the test run.
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

* [Prerequisites](#prerequisites)
* [Task defaults](#task-defaults)
* [Result formats mapping](#result-formats-mapping)
* [Attachments support](#attachments-support)

This task publishes test results to Azure Pipelines or TFS when tests are executed to provide a comprehensive test reporting and analytics experience. You can use the test runner of your choice that supports the results format you require. Supported results formats include [CTest](https://cmake.org/cmake/help/latest/manual/ctest.1.html), [JUnit](https://github.com/windyroad/JUnit-Schema/blob/master/JUnit.xsd) (including [PHPUnit](https://docs.phpunit.de/en/11.3/configuration.html#the-logging-element)), [NUnit 2](https://docs.nunit.org/), [NUnit 3](https://github.com/nunit/docs/wiki/Test-Result-XML-Format), Visual Studio Test (TRX), and [xUnit 2](https://xunit.net/docs/format-xml-v2).

Other built-in tasks, such as [Visual Studio Test task](vstest-v2.md) and [Dot NetCore CLI task](dotnet-core-cli-v2.md) automatically publish test results to the pipeline. Tasks such as [Ant](ant-v1.md), [Maven](maven-v3.md), [Gulp](gulp-v1.md), [Grunt](grunt-v0.md), and [Xcode](xcode-v5.md) provide publishing results as an option within the task, or build libraries such as [Cobertura](https://cobertura.github.io/cobertura/) and [JaCoCo](https://www.eclemma.org/jacoco/). If you are using any of these tasks, you do not need a separate **Publish Test Results** task in the pipeline.

The published test results are displayed in the [Tests tab](/azure/devops/pipelines/test/review-continuous-test-results-after-build) in the pipeline summary. The results help you to measure pipeline quality, review traceability, troubleshoot failures, and drive failure ownership.

The following example shows the task is configured to publish test results.

![Open the test history page](media/publish-test-results.png)

You can also use this task in a build pipeline to **publish code coverage results** produced when running tests to Azure Pipelines or TFS in order to obtain coverage reporting.

### Prerequisites

If you're using a Windows self-hosted agent, your machine must have this prerequisite installed:

- [.NET Framework](/dotnet/framework/install/) 4.6.2 or a later version

### Task defaults

The default option uses JUnit format to publish test results. When using VSTest as the **testRunner**, the **testResultsFiles** option should be changed to `**/TEST-*.trx`. 

**testResultsFormat** is an alias for the **testRunner** input name. The results files can be produced by multiple runners, not just a specific runner. For example, the jUnit results format is supported by many runners and not just jUnit.

To publish test results for Python using YAML, see [Python](/azure/devops/pipelines/ecosystems/python)
in the **Ecosystems** section of these topics, which also includes examples for other languages.

### Result formats mapping

This table lists the fields reported in the [Tests tab](/azure/devops/pipelines/test/review-continuous-test-results-after-build) in a build or release summary, and the corresponding mapping with the attributes in the supported test result formats.

#### [Visual Studio Test (TRX)](#tab/trx)

| Scope | Field | Visual Studio Test (TRX) |
|-|-|-|
| [**Test run**](/azure/devops/pipelines/test/test-glossary) | Title | **Test run title** specified in the task |
|  | Date started | /TestRun/Times.Attributes["**start**"].Value |
|  | Date completed | /TestRun/Times.Attributes["**finish**"].Value |
|  | Duration | Date completed - Date started |
|  | Attachments | Refer to **Attachments support** section below |
| [**Test result**](/azure/devops/pipelines/test/test-glossary) | Title | /TestRun/Results/UnitTestResult.Attributes["**testName**"].Value Or /TestRun/Results/WebTestResult.Attributes["**testName**"].Value Or /TestRun/Results/TestResultAggregation.Attributes["**testName**"].Value |
|  | Date started | /TestRun/Results/UnitTestResult.Attributes["**startTime**"].Value Or /TestRun/Results/WebTestResult.Attributes["**startTime**"].Value Or /TestRun/Results/TestResultAggregation.Attributes["**startTime**"].Value |
|  | Date completed | /TestRun/Results/UnitTestResult.Attributes["**startTime**"].Value + /TestRun/Results/UnitTestResult.Attributes["**duration**"].Value Or /TestRun/Results/WebTestResult.Attributes["**startTime**"].Value + /TestRun/Results/WebTestResult.Attributes["**duration**"].Value Or /TestRun/Results/TestResultAggregation.Attributes["**startTime**"].Value + /TestRun/Results/TestResultAggregation.Attributes["**duration**"].Value |
|  | Duration | /TestRun/Results/UnitTestResult.Attributes["**duration**"].Value Or /TestRun/Results/WebTestResult.Attributes["**duration**"].Value Or /TestRun/Results/TestResultAggregation.Attributes["**duration**"].Value |
|  | Owner | /TestRun/TestDefinitions/UnitTest/Owners/Owner.Attributes["**name**"].Value |
|  | Outcome | /TestRun/Results/UnitTestResult.Attributes["**outcome**"].Value Or /TestRun/Results/WebTestResult.Attributes["**outcome**"].Value Or /TestRun/Results/TestResultAggregation.Attributes["**outcome**"].Value |
|  | Error message | /TestRun/Results/UnitTestResult/Output/ErrorInfo/**Message.InnerText** Or /TestRun/Results/WebTestResultOutput/ErrorInfo/**Message.InnerText** Or /TestRun/Results/TestResultAggregation/Output/ErrorInfo/**Message.InnerText** |
|  | Stack trace | /TestRun/Results/UnitTestResult/Output/ErrorInfo/**StackTrace.InnerText** Or /TestRun/Results/WebTestResultOutput/ErrorInfo/**StackTrace.InnerText** Or /TestRun/Results/TestResultAggregation/Output/ErrorInfo/**StackTrace.InnerText** |
|  | Attachments | Refer to **Attachments support** section below |
|  | Console log | /TestRun/Results/UnitTestResult/Output/**StdOut.InnerText** Or /TestRun/Results/WebTestResultOutput/Output/**StdOut.InnerText** Or /TestRun/Results/TestResultAggregation/Output/**StdOut.InnerText** |
|  | Console error log | /TestRun/Results/UnitTestResult/Output/**StdErr.InnerText** Or /TestRun/Results/WebTestResultOutput/Output/**StdErr.InnerText** Or /TestRun/Results/TestResultAggregation/Output/**StdErr.InnerText** |
|  | Agent name | /TestRun/Results/UnitTestResult.Attributes["**computerName**"].Value Or /TestRun/Results/WebTestResult.Attributes["**computerName**"].Value Or /TestRun/Results/TestResultAggregation.Attributes["**computerName**"].Value |
|  | Test file | /TestRun/TestDefinitions/UnitTest.Attributes["**storage**"].Value |
|  | Priority | /TestRun/TestDefinitions/UnitTest.Attributes["**priority**"].Value |

#### [JUnit](#tab/junit)

| Scope | Field | JUnit |
|-|-|-|
| [**Test run**](/azure/devops/pipelines/test/test-glossary) | Title | **Test run title** specified in the task |
|  | Date started | /testsuites/testsuite.Attributes["**timestamp**"].Value |
|  | Date completed | /testsuites/testsuite.Attributes["**timestamp**"].Value + SUM(/testsuites/testsuite/testcase.Attributes["**time**"].Value) for all test cases in the test suite |
|  | Duration | Date completed - Date started |
|  | Attachments | Results file, used to publish test results |
| [**Test result**](/azure/devops/pipelines/test/test-glossary) | Title | /testsuites/testsuite/testcase/Attributes["**name**"].Value |
|  | Date started | /testsuites/testsuite.Attributes["**timestamp**"].Value |
|  | Date completed | /testsuites/testsuite.Attributes["**timestamp**"].Value +  /testsuites/testsuite/testcase.Attributes["**time**"].Value |
|  | Duration | /testsuites/testsuite/testcase/.Attributes["**time**"].Value |
|  | Owner | /testsuites/testsuite/testcase/Attributes["**owner**"].Value |
|  | Outcome | **Failed**: if exists /Testsuites/testsuite/testcase/**failure** Or /Testsuites/testsuite/testcase/**error**  **Not Executed**: if exists Testsuites/testsuite/testcase/**skipped**  **Passed**: for all other cases |
|  | Error message | /Testsuites/testsuite/testcase/failure.Attributes["**message**"].Value Or /Testsuites/testsuite/testcase/error.Attributes["**message**"].Value Or /Testsuites/testsuite/testcase/skipped.Attributes["**message**"].Value |
|  | Stack trace | /Testsuites/testsuite/testcase/failure.**InnerText** Or /Testsuites/testsuite/testcase/error.**InnerText** |
|  | Attachments | - |
|  | Console log | /Testsuites/testsuite/testcase/**system-out** |
|  | Console error log | /Testsuites/testsuite/testcase/**system-err** |
|  | Agent name | /testsuites/testsuite.Attributes["**hostname**"].Value |
|  | Test file | /testsuites/testsuite/testcase/Attributes["**classname**"].Value |
|  | Priority | - |

#### [NUnit 2](#tab/nunit2)

| Scope | Field | NUnit 2 |
|-|-|-|
| [**Test run**](/azure/devops/pipelines/test/test-glossary) | Title | **Test run title** specified in the task |
|  | Date started | /test-results.Attributes["**date**"].Value + /test-results.Attributes["**time**"].Value |
|  | Date completed | Date started + /test-results/results/test-case.Attributes["**time**"].Value for all test cases |
|  | Duration | Date completed - Date started |
|  | Attachments | Results file used to publish test results |
| [**Test result**](/azure/devops/pipelines/test/test-glossary) | Title | /test-results/results/test-case.Attributes["**name**"].Value |
|  | Date started | /test-results.Attributes["**date**"].Value + /test-results.Attributes["**time**"].Value |
|  | Date completed | Date started + /test-results/results/test-case.Attributes["**time**"].Value |
|  | Duration | /test-results/results/test-case.Attributes["**time**"].Value |
|  | Owner | build or release requested for user |
|  | Outcome | **Failed**: if exists /test-results/results/test-case/**failure**  **Not Executed**: if exists /test-results/results/test-case.Attributes["**result**"].Value=="Ignored"  **Passed**: for all other cases |
|  | Error message | /test-results/results/test-casefailure/**message.InnerText** |
|  | Stack trace | /test-results/results/test-case/failure/**stack-trace.InnerText** |
|  | Attachments | - |
|  | Console log | /test-results/results/test-case/failure/**message.InnerText** |
|  | Console error log | /test-results/results/test-case/**output.InnerText** |
|  | Agent name | /test-results/environment.Attributes["**machine-name**"].Value |
|  | Test file | /test-results/test-suite.Attributes["**name**"].Value |
|  | Priority | - |

#### [NUnit 3](#tab/nunit3)

| Scope | Field | NUnit 3 |
|-|-|-|
| [**Test run**](/azure/devops/pipelines/test/test-glossary) | Title | **Test run title** specified in the task |
|  | Date started | /test-run/**start-time** |
|  | Date completed | /test-run/**end-time** |
|  | Duration | Date completed - Date started |
|  | Attachments | Refer to **Attachments support** section below |
| [**Test result**](/azure/devops/pipelines/test/test-glossary) | Title | /test-suite[@type='Assembly']/test-case.Attributes["**name**"].Value |
|  | Date started | /test-suite[@type='Assembly']/test-case.Attributes["**start-time**"].Value |
|  | Date completed | /test-suite[@type='Assembly']/test-case.Attributes["**end-time**"].Value |
|  | Duration | /test-suite[@type='Assembly']/test-case.Attributes["**duration**"].Value |
|  | Owner | build or release requested for user |
|  | Outcome | /test-results/test-suite/results/test-case.Attributes["**result**"].Value |
|  | Error message | /test-suite[@type='Assembly']/test-case/failure/**message** |
|  | Stack trace | /test-suite[@type='Assembly']//test-case/failure/**stack-trace** |
|  | Attachments | Refer to **Attachments support** section below |
|  | Console log | /test-suite[@type='Assembly']/test-case/failure/**output** |
|  | Console error log | - |
|  | Agent name | /test-suite[@type='Assembly']/environment.Attributes["**machine-name**"].Value |
|  | Test file | /test-suite[@type='Assembly'].Attributes["**name**"].Value |
|  | Priority | - |

#### [xUnit 2](#tab/xunit2)

| Scope | Field | xUnit 2 |
|-|-|-|
| [**Test run**](/azure/devops/pipelines/test/test-glossary) | Title | **Test run title** specified in the task |
|  | Date started | /assemblies/assembly/**run-date** + /assemblies/assembly/**run-time** |
|  | Date completed | Date started + /assemblies/assembly/**time** |
|  | Duration | Date completed - Date started |
|  | Attachments | Results file used to publish test results |
| [**Test result**](/azure/devops/pipelines/test/test-glossary) | Title | /assemblies/assembly/collection/test.Attributes["**method**"].Value |
|  | Date started | /assemblies/assembly/**run-date** + /assemblies/assembly/**run-time** |
|  | Date completed | Date started + /assemblies/assembly/collection/test.Attributes["**time**"].Value |
|  | Duration | /assemblies/assembly/collection/test.Attributes["**time**"].Value |
|  | Owner | /assemblies/assembly/collection/test/traits/trait[@name='owner'].Attributes["**value**"].Value |
|  | Outcome | /assemblies/assembly/collection/test/failure.Attributes["**result**"].Value |
|  | Error message | /assemblies/assembly/collection/test/failure/**message** |
|  | Stack trace | /assemblies/assembly/collection/test/failure/**stack-trace** |
|  | Attachments | - |
|  | Console log | /assemblies/assembly/collection/test/failure/**output** |
|  | Console error log | - |
|  | Agent name | - |
|  | Test file | /assemblies/assembly.Attributes["**name**"].Value |
|  | Priority | /testcaseNode/traits/trait[@name='priority'].Attributes["**value**"].Value |

#### [CTest](#tab/ctest)

| Scope | Field | CTest |
|-|-|-|
| [**Test run**](/azure/devops/pipelines/test/test-glossary) | Title | **Test run title** specified in the task |
|  | Date started | /Site/Testing/**StartTestTime.InnerText** |
|  | Date completed | /Site/Testing/**EndTestTime.InnerText** |
|  | Duration | Date completed - Date started |
|  | Attachments | Results file, used to publish test results |
| [**Test result**](/azure/devops/pipelines/test/test-glossary) | Title | /Site/Testing/Test/**Name.InnerText** |
|  | Date started | /Site/Testing/**StartTestTime.InnerText** |
|  | Date completed | Date Started + /Site/Testing/Test/Results/**NamedMeasurement[@name= 'Execution Time']/Value.InnerText** |
|  | Duration | /Site/Testing/Test/Results/**NamedMeasurement[@name= 'Execution Time']/Value.InnerText** |
|  | Owner | Build or release requested for user |
|  | Outcome | /Site/Testing/**Test.Attributes["Status"].Value** |
|  | Error message | - |
|  | Stack trace | /Site/Testing/Test/Results/Measurement/**Value.InnerText** |
|  | Attachments | - |
|  | Console log | - |
|  | Console error log | - |
|  | Agent name | - |
|  | Test file | /Site/Testing/Test/**Path.InnerText** |
|  | Priority | - |

* * *

> [!NOTE]
> **Duration** is used only when **Date started** and **Date completed** are not available.
>
> The fully qualified name format for **testName** is **Namespace.Testclass.Methodname** with a character limit of 512. If the test is data driven and has parameters, the character limit will include the parameters.
>
> **While publishing the test result, you may get this error: Failed to publish test results: Invalid Priority specified**
>
> This error occurs if any of the test methods has priority set above 255, fix the test method priority in the code and execute the tests again. You can review the trx file generated to see all the tests having priority greater than 255.

### Attachments support

The Publish Test Results task provides support for attachments for both test run and test results for the following formats. For public projects, we support 2GB of total attachments.

#### [Visual Studio Test (TRX)](#tab/trxattachments)

#### Visual Studio Test (TRX)

| Scope | Type | Path |
| ----- | ---- | ---- |
| **Test run** | Data Collector | /TestRun/ResultSummary/CollectorDataEntries/Collector/UriAttachments/UriAttachment/A.Attributes["**href**"].Value |
| | Test Result | /TestRun/ResultSummary/ResultFiles/ResultFile.Attributes["**path**"].Value |
| | Code Coverage | /TestRun/TestSettings/Execution/AgentRule/DataCollectors/DataCollector/Configuration/CodeCoverage/Regular/CodeCoverageItem.Attributes["**binaryFile**"].Value And /TestRun/TestSettings/Execution/AgentRule/DataCollectors/DataCollector/Configuration/CodeCoverage/Regular/CodeCoverageItem.Attributes["**pdbFile**"].Value |
| **Test result** | Data Collectors | /TestRun/Results/UnitTestResult/CollectorDataEntries/Collector/UriAttachments/UriAttachment/A.Attributes["**href**"].Value Or /TestRun/Results/WebTestResult/CollectorDataEntries/Collector/UriAttachments/UriAttachment/A.Attributes["**href**"].Value Or /TestRun/Results/TestResultAggregation/CollectorDataEntries/Collector/UriAttachments/UriAttachment/A.Attributes["**href**"].Value |
| | Test Result | /TestRun/Results/UnitTestResult/ResultFiles/ResultFile.Attributes["**path**"].Value Or /TestRun/Results/WebTestResult/ResultFiles/ResultFile.Attributes["**path**"].Value Or /TestRun/Results/TestResultAggregation/ResultFiles/ResultFile.Attributes["**path**"].Value |

#### [NUnit 3](#tab/nunit3attachments)

#### NUnit 3

| Scope | Path |
| ----- | ---- |
| **Test run** | /test-suite/attachments/attachment/**filePath** |
| **Test run** | /test-suite[@type='Assembly']/test-case/attachments/attachment/**filePath** |

#### [JUnit](#tab/junitattachments)

#### JUnit

:::moniker range="<= azure-pipelines-2022.1"

JUnit attachment support was added in [Azure DevOps sprint 229](/azure/devops/release-notes/2023/sprint-229-update#publish-test-results-task), and is not available in Azure DevOps Server 2022.1 and lower.

:::moniker-end

:::moniker range="> azure-pipelines-2022.1"

| Scope | Path |
| ----- | ---- |
| **Test Result** | /testsuites/testsuite/testcase/system-out/ -> Contents matching pattern **[[ATTACHMENT\|filePath]]**  |

:::moniker-end

* * *

> [!NOTE]
> The option to upload the test results file as an attachment is a default option in the task, applicable to all formats.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Docker

For Docker based apps, there are many ways to build your application and run tests:

* **Build and test in a build pipeline**: builds and tests execute in the pipeline and test results are published using the **Publish Test Results** task.
* **Build and test with a multi-stage Dockerfile**: builds and tests execute inside the container using a multi-stage Docker file, as such test results are not published back to the pipeline.
* **Build, test, and publish results with a Dockerfile**: builds and tests execute inside the container, and results are published back to the pipeline. See the example below.

<a name="publishtestindocker"></a>

#### Build, test, and publish results with a Docker file

In this approach, you build your code and run tests inside the container using a Docker file. The test results are then copied to the host to be published to the pipeline. To publish the test results to Azure Pipelines, you can use the **Publish Test Results** task. The final image will be published to Docker or Azure Container Registry.

##### Get the code

1. Create a `Dockerfile.build` file at the root of your project directory with the following:

   ```Dockerfile
   # Build and run tests inside the docker container
   FROM mcr.microsoft.com/dotnet/sdk:2.1
   WORKDIR /app
   # copy the contents of agent working directory on host to workdir in container
   COPY . ./
   # dotnet commands to build, test, and publish
   RUN dotnet restore
   RUN dotnet build -c Release
   RUN dotnet test dotnetcore-tests/dotnetcore-tests.csproj -c Release --logger "trx;LogFileName=testresults.trx"
   RUN dotnet publish -c Release -o out
   ENTRYPOINT dotnet dotnetcore-sample/out/dotnetcore-sample.dll
   ```

   This file contains the instructions to build code and run tests. The tests are then copied to a file `testresults.trx` inside the container.

2. To make the final image as small as possible, containing only the runtime and deployment artifacts, replace the contents of the existing `Dockerfile` with the following:

   ```Dockerfile
   # This Dockerfile creates the final image to be published to Docker or
   # Azure Container Registry
   # Create a container with the compiled asp.net core app
   FROM mcr.microsoft.com/dotnet/aspnet:2.1
   # Create app directory
   WORKDIR /app
   # Copy only the deployment artifacts
   COPY /out .
   ENTRYPOINT ["dotnet", "dotnetcore-sample.dll"]
   ```

##### Define the build pipeline

#### [YAML](#tab/yaml/)

1. If you have a Docker Hub account, and want to push the image to your Docker registry,
   replace the contents of the `.vsts-ci.docker.yml` file with the following:

   ```YAML
   # Build Docker image for this app, to be published to Docker Registry
   pool:
     vmImage: 'ubuntu-latest'
   variables:
     buildConfiguration: 'Release'
   steps:
   - script: |
       docker build -f Dockerfile.build -t $(dockerId)/dotnetcore-build:$BUILD_BUILDID .
       docker run --name dotnetcoreapp --rm -d $(dockerId)/dotnetcore-build:$BUILD_BUILDID
       docker cp dotnetcoreapp:app/dotnetcore-tests/TestResults $(System.DefaultWorkingDirectory)
       docker cp dotnetcoreapp:app/dotnetcore-sample/out $(System.DefaultWorkingDirectory)
       docker stop dotnetcoreapp

   - task: PublishTestResults@2
     inputs:
       testRunner: VSTest
       testResultsFiles: '**/*.trx'
       failTaskOnFailedTests: true

   - script: |
       docker build -f Dockerfile -t $(dockerId)/dotnetcore-sample:$BUILD_BUILDID .
       docker login -u $(dockerId) -p $pswd
       docker push $(dockerId)/dotnetcore-sample:$BUILD_BUILDID
     env:
       pswd: $(dockerPassword)
   ```

   Alternatively, if you configure an Azure Container Registry and want to push the image to that registry, replace the contents of the `.vsts-ci.yml` file with the following:

   ```YAML
   # Build Docker image for this app to be published to Azure Container Registry
   pool:
     vmImage: 'ubuntu-latest'
   variables:
     buildConfiguration: 'Release'

   steps:
   - script: |
       docker build -f Dockerfile.build -t $(dockerId)/dotnetcore-build:$BUILD_BUILDID .
       docker run --name dotnetcoreapp --rm -d $(dockerId)/dotnetcore-build:$BUILD_BUILDID
       docker cp dotnetcoreapp:app/dotnetcore-tests/TestResults $(System.DefaultWorkingDirectory)
       docker cp dotnetcoreapp:app/dotnetcore-sample/out $(System.DefaultWorkingDirectory)
       docker stop dotnetcoreapp

   - task: PublishTestResults@2
     inputs:
       testRunner: VSTest
       testResultsFiles: '**/*.trx'
       failTaskOnFailedTests: true

   - script: |
       docker build -f Dockerfile -t $(dockerId).azurecr.io/dotnetcore-sample:$BUILD_BUILDID .
       docker login -u $(dockerId) -p $pswd $(dockerid).azurecr.io
       docker push $(dockerId).azurecr.io/dotnetcore-sample:$BUILD_BUILDID 
     env:
       pswd: $(dockerPassword)
   ```

2. Push the change to the main branch in your repository.

3. If you use Azure Container Registry, ensure you have
   [pre-created the registry](/azure/container-registry/container-registry-get-started-portal) in the Azure portal.
   Copy the admin user name and password shown in the **Access keys** section of the registry settings in Azure portal.

4. Update your build pipeline with the following

   * **Agent pool**: `Hosted Ubuntu 1604`
     - **dockerId**: Set the value to your Docker ID for DockerHub or the admin user name for Azure Container Registry.
     - **dockerPassword**: Set the value to your password for DockerHub or the admin password Azure Container Registry.
   * **YAML file path**: `/.vsts-ci.docker.yml`

5. Queue a new build and watch it create and push a Docker image to your registry and the test results to Azure DevOps.

#### [Classic](#tab/classic/)
1. Create a new build pipeline using the **Empty job**.

2. Select **Pipeline** on the **Tasks** page of the build pipeline editor and edit its properties as follows

   * **Agent queue**: `Hosted Ubuntu 1604`

3. Add a [Bash task](bash-v3.md) and configure it as follows to build and copy artifacts to the host:

   * **Type**: Inline
   * **Script**: To build, test and copy artifacts to host, use the following script:

     ```Bash
     docker build -f Dockerfile.build -t $(dockerId)/dotnetcore-build:$BUILD_BUILDID .
     docker run --name dotnetcoreapp --rm -d $(dockerId)/dotnetcore-build:$BUILD_BUILDID
     docker cp dotnetcoreapp:app/dotnetcore-tests/TestResults $(System.DefaultWorkingDirectory)
     docker cp dotnetcoreapp:app/dotnetcore-sample/out $(System.DefaultWorkingDirectory)
     docker stop dotnetcoreapp
     ```

4. Add a **Publish Test Results** task to publish results to the pipeline, and edit its properties as follows:

   * **Test result format**: `VSTest`
   * **Test results files**: `**/*.trx`

5. Add a [Bash task](bash-v3.md) to publish the final image to the repository, and edit its properties as follows:

   * **Type**: `Inline`
   * **Script**:

     * To push to Docker Hub, use the following script:

       ```Bash
       docker build -f Dockerfile -t $(dockerId)/dotnetcore-sample:$BUILD_BUILDID .
       docker login -u $(dockerId) -p $(dockerPassword)
       docker push $(dockerId)/dotnetcore-sample:$BUILD_BUILDID
       ```

     * To push to Azure Container Registry, use the following script:

       ```Bash
       docker build -t $(dockerId).azurecr.io/dotnetcore-sample:$BUILD_BUILDID . 
       docker login -u $(dockerId) -p $(dockerPassword) $(dockerId).azurecr.io 
       docker push $(dockerId).azurecr.io/dotnetcore-sample:$BUILD_BUILDID
       ```
6. If you use Azure Container Registry, ensure you have [pre-created the registry](/azure/container-registry/container-registry-get-started-portal) in the Azure portal. Copy the admin user name and password shown in the **Access keys** section of the registry settings in Azure Portal.

7. In the **Variables** tab of the build pipeline, define two variables:

   * **dockerId**: Set the value to your Docker ID for DockerHub or the admin user name for Azure Container Registry.
   * **dockerPassword**: Set the value to your password for DockerHub or the admin password Azure Container Registry, and mark it as secure.

8. Save the pipeline and queue a build. Watch it create and push a Docker image to your registry and the test results to Azure DevOps.

* * *
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.0.0 or greater |
| Task category | Test |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
