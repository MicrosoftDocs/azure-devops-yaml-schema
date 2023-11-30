---
title: PublishTestResults@1 - Publish test results v1 task
description: Publish test results to Azure Pipelines (task version 1).
ms.date: 11/30/2023
monikerRange: "<=azure-pipelines"
---

# PublishTestResults@1 - Publish test results v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Publish test results to Azure Pipelines.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Publish Test Results to VSTS/TFS.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Publish test results v1
# Publish test results to Azure Pipelines.
- task: PublishTestResults@1
  inputs:
    testRunner: 'JUnit' # 'JUnit' | 'NUnit' | 'VSTest' | 'XUnit'. Required. Test Result Format. Default: JUnit.
    testResultsFiles: '**/TEST-*.xml' # string. Required. Test Results Files. Default: **/TEST-*.xml.
    #mergeTestResults: false # boolean. Merge Test Results. Default: false.
    #testRunTitle: # string. Test Run Title. 
  # Advanced
    #platform: # string. Platform. 
    #configuration: # string. Configuration. 
    #publishRunAttachments: true # boolean. Upload Test Attachments. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Publish Test Results v1
# Publish Test Results to VSTS/TFS.
- task: PublishTestResults@1
  inputs:
    testRunner: 'JUnit' # 'JUnit' | 'NUnit' | 'VSTest' | 'XUnit'. Required. Test Result Format. Default: JUnit.
    testResultsFiles: '**/TEST-*.xml' # string. Required. Test Results Files. Default: **/TEST-*.xml.
    #mergeTestResults: false # boolean. Merge Test Results. Default: false.
    #testRunTitle: # string. Test Run Title. 
  # Advanced
    #platform: # string. Platform. 
    #configuration: # string. Configuration. 
    #publishRunAttachments: true # boolean. Upload Test Attachments. Default: true.
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

<!-- :::item name="testRunner"::: -->
:::moniker range="<=azure-pipelines"

**`testRunner`** - **Test Result Format**<br>
`string`. Required. Allowed values: `JUnit`, `NUnit`, `VSTest`, `XUnit`. Default value: `JUnit`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the format of the results files you want to publish. The following formats are supported: [CTest](https://cmake.org/cmake/help/latest/manual/ctest.1.html), [JUnit](https://github.com/windyroad/JUnit-Schema/blob/master/JUnit.xsd), [NUnit 2](https://docs.nunit.org/), [NUnit 3](https://github.com/nunit/docs/wiki/Test-Result-XML-Format), Visual Studio Test (TRX) and [xUnit 2](https://xunit.net/docs/format-xml-v2).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testResultsFiles"::: -->
:::moniker range="<=azure-pipelines"

**`testResultsFiles`** - **Test Results Files**<br>
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
<!-- :::item name="mergeTestResults"::: -->
:::moniker range="<=azure-pipelines"

**`mergeTestResults`** - **Merge Test Results**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When this boolean's value is `true`, the task reports test results from all the files against a single [test run](/azure/devops/pipelines/test/test-glossary). If the value is `false`, the task creates a separate test run for each test result file.

> [!NOTE]
> Use the merge test results setting to combine files from the same test framework to ensure results mapping and duration are calculated correctly.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range="<=azure-pipelines"

**`testRunTitle`** - **Test Run Title**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies a name for the test run against which the results will be reported. Variable names declared in the build or release pipeline can be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="platform"::: -->
:::moniker range="<=azure-pipelines"

**`platform`** - **Platform**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the build platform against which the test run should be reported. For example: `x64` or `x86`. If you defined a variable for the platform in your build task, use it here.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configuration"::: -->
:::moniker range="<=azure-pipelines"

**`configuration`** - **Configuration**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies the build configuration against which the test run should be reported. For example: `Debug` or `Release`. If you defined a variable for the configuration in your build task, use it here.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishRunAttachments"::: -->
:::moniker range="<=azure-pipelines"

**`publishRunAttachments`** - **Upload Test Attachments**<br>
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

[PublishTestResults@2](publish-test-results-v2.md) is a newer version of this task that provides NUnit3 support and support for Minimatch files patterns.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Test |

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.83.0 or greater |
| Task category | Test |

:::moniker-end

:::moniker range="=azure-pipelines-2018"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | All |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.83.0 or greater |
| Task category | Test |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [PublishTestResults@2](publish-test-results-v2.md)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
