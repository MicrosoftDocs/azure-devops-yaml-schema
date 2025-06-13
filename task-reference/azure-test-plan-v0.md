---
title: AzureTestPlan@0 - Azure Test Plan v0 task
description: Run manual and automated tests in test plan in Java and Python language.
ms.date: 05/06/2025
monikerRange: "=azure-pipelines"
---

# AzureTestPlan@0 - Azure Test Plan v0 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Run manual and automated tests in test plan in Java, JavaScript and Python language.

> [!NOTE]
> This task is in Public Preview.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure Test Plan v0
# Run manual and automated tests points of test plan for different testing frameworks like Maven and Gradle for Java, PyTest for Python and Jest for JavaScript.
- task: AzureTestPlan@0
  inputs:
    testSelector: # 'manualTests' | 'automatedTests'. Required. Test cases to be executed. 
    testPlanOrRunSelector: 'testPlan' # 'testPlan' | 'testRun'. Required. Select tests using. Default: testPlan.
    #testRunId: '$(test.RunId)' # string. Required when testPlanOrRunSelector = testRun. Test Run. Default: $(test.RunId).
    testPlan: # string. Required when testPlanOrRunSelector = testPlan. Test plan. 
    testSuite: # string. Required when testPlanOrRunSelector = testPlan. Test suite. 
    testConfiguration: # string. Required. Test configuration. 
    #testLanguageInput: # 'JavaMaven' | 'JavaGradle' | 'Python' | 'JavaScriptJest'. Select Test framework language. 
    #pomFilePath: # string. Optional. Use when testLanguageInput = JavaMaven. Pom file path. 
    #gradleFilePath: # string. Optional. Use when testLanguageInput = JavaGradle. Gradle file path. 
    #failTaskOnFailedTests: true # boolean. Fail if there are test failures. Default: true.
    #failTaskOnFailureToPublishResults: false # boolean. Fail if there is failure in publishing test results. Default: false.
    #failTaskOnMissingResultsFile: false # boolean. Fail if no result files are found. Default: false.
  # advanced
    #publishRunAttachments: true # boolean. Upload test results files. Default: true.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="testSelector"::: -->
:::moniker range="=azure-pipelines"

**`testSelector`** - **Test cases to be executed**<br>
`string`. Required. Allowed values: `manualTests` (Manual tests), `automatedTests` (Automated tests).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<ul><li><b>Manual tests: </b>Use this option to trigger manual tests from your test plan.</li><li><b>Automated tests: </b>Use this option to run tests from your test plan that have automated test method associated with it.</li>.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testPlanOrRunSelector"::: -->
:::moniker range="=azure-pipelines"

**`testPlanOrRunSelector`** - **Select tests using**<br>
`string`. Required. Allowed values: `testPlan` (Test plan), `testRun` (Test run). Default value: `testPlan`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<ul><li><b>Test assembly: </b>Use this option to specify one or more test assemblies that contain your tests. You can optionally specify a filter criteria to select only specific tests.</li><li><b>Test plan: </b>Use this option to run tests from your test plan that have an automated test method associated with it.</li><li><b>Test run: </b>Use this option when you are setting up an environment to run tests from the Test hub. This option should not be used when running tests in a continuous integration / continuous deployment (CI/CD) pipeline.</li>.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunId"::: -->
:::moniker range="=azure-pipelines"

**`testRunId`** - **Test Run**<br>
`string`. Required when `testPlanOrRunSelector = testRun`. Default value: `$(test.RunId)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Test run based selection is used when triggering automated test runs from the test hub, value for this should be kept as it is.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testPlan"::: -->
:::moniker range="=azure-pipelines"

**`testPlan`** - **Test plan**<br>
`string`. Required when `testPlanOrRunSelector = testPlan`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Type or paste the test plan ID containing test suites with test cases.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testSuite"::: -->
:::moniker range="=azure-pipelines"

**`testSuite`** - **Test suite**<br>
`string`. Required when `testPlanOrRunSelector = testPlan`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select one or more test suites containing test cases.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testConfiguration"::: -->
:::moniker range="=azure-pipelines"

**`testConfiguration`** - **Test configuration**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select Test Configuration.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testLanguageInput"::: -->
:::moniker range="=azure-pipelines"

**`testLanguageInput`** - **Select Test framework language**<br>
`string`. Allowed values: `JavaMaven` (Java - Maven), `JavaGradle` (Java - Gradle), `Python` (Python - PyTest), `JavaScriptJest` (JavaScript - Jest).<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Test Framework Language of automated tests in test plan.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pomFilePath"::: -->
:::moniker range="=azure-pipelines"

**`pomFilePath`** - **Pom file path**<br>
`string`. Optional. Use when `testLanguageInput = JavaMaven`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repository root to the Maven POM file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="gradleFilePath"::: -->
:::moniker range="=azure-pipelines"

**`gradleFilePath`** - **Gradle file path**<br>
`string`. Optional. Use when `testLanguageInput = JavaGradle`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repository root to the build.gradle file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishRunAttachments"::: -->
:::moniker range="=azure-pipelines"

**`publishRunAttachments`** - **Upload test results files**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Upload logs and other files containing diagnostic information collected when the tests were run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failTaskOnFailedTests"::: -->
:::moniker range="=azure-pipelines"

**`failTaskOnFailedTests`** - **Fail if there are test failures**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fail the task if there are any test failures. Check this option to fail the task if test failures are detected in the result files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failTaskOnFailureToPublishResults"::: -->
:::moniker range="=azure-pipelines"

**`failTaskOnFailureToPublishResults`** - **Fail if there is failure in publishing test results**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fail if there is failure in publishing test results. Check this option to fail the task if publishing test results is failed partially.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failTaskOnMissingResultsFile"::: -->
:::moniker range="=azure-pipelines"

**`failTaskOnMissingResultsFile`** - **Fail if no result files are found**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fail the task if no result files are found.
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
## Integrate your automated tests with a test plan
Follow the steps below to integrate your automated tests with manual test cases and execute them from Test Plans or via the Azure Test Plan task in your build pipelines:
1. Ensure your project is in Azure DevOps Repos (or GitHub Repos).
2. Create a pipeline that runs the tests using tasks such as Gradle or Maven. If your tests are already executed as part of an existing pipeline, you can skip this step. Running the tests is essential—only after they have been executed at least once will they be available for association with manual test cases.

# [Gradle](#tab/gradle)
```yaml
 trigger:
- none

 pool:
   vmImage: ubuntu-latest

 steps:
  - task: Gradle@3
    inputs:
         gradleWrapperFile: 'gradlew'
         workingDirectory: '$(Build.SourcesDirectory)'
         tasks: 'build'
         publishJUnitResults: true
         testResultsFiles: '**/TEST-*.xml'
         testRunTitle: 'gridinitialexecution'
         javaHomeOption: 'JDKVersion'
         sonarQubeRunAnalysis: false
         spotBugsAnalysis: false
```
# [Maven](#tab/maven)
```yaml
  trigger:
    - none

  variables:
    - name: system.debug
      value: true

  pool:
    vmImage: ubuntu-latest
  
  steps:
    - task: Maven@4
      inputs:
        mavenPomFile: 'pom.xml'
        publishJUnitResults: true
        testResultsFiles: '**/surefire-reports/TEST-*.xml'
        javaHomeOption: 'JDKVersion'
        mavenVersionOption: 'Default'
        mavenAuthenticateFeed: false
        effectivePomSkip: false
        sonarQubeRunAnalysis: false
```
# [Python](#tab/python)
 ```yaml
 trigger:
  - none

 pool:
   vmImage: windows-latest

 steps:
  - task: UsePythonVersion@0
    inputs:
    versionSpec: '3.8.10'
    addToPath: true
    displayName: 'Use Python $(python.version)'

  - script: |
     pip install pytest pytest-azurepipelines
     pytest
     displayName: 'pytest'
```
---
3. The next step is to link the test cases from the Test tab of the pipeline run summary to a manual test case work item. To do this, create a new test case or use an existing one (note the Automation Status column for TC4):

:::image type="content" source="media/test-case-without-automation.png" alt-text="Screenshot of a test case without automation":::

4. Once you have a test case, return to the pipeline run summary page and associate your automated test with the test case.

:::image type="content" source="media/association-experience.png" alt-text="Screenshot of the association experience in Pipelines":::

5. Here’s how you can tell if a manual test case has an associated automated test:

:::image type="content" source="media/test-case-with-automation.png" alt-text="Screenshot of a test case with automation":::

:::image type="content" source="media/test-case-associated-automation-tab.png" alt-text="Screenshot of the associated automation tab":::

6. Now that the test case is associated with a manual test case work item, you can execute it as part of a pipeline by passing the test plan as an argument in the Azure Test Plan task.
```yaml
    trigger:
        - none
    pool:
      vmImage: ubuntu-latest

   - task: AzureTestPlan@0
     inputs:
     testSelector: 'automatedTests'
     testPlanOrRunSelector: 'testPlan'
     testPlan: '21294'
     testSuite: '229461'
     testConfiguration: '82'
     testLanguageInput: 'JavaGradle'
```
Save and run the pipeline.

Here is the pipeline result summary, which shows the outcome for TC4 along with other test cases:

:::image type="content" source="media/test-run-results.png" alt-text="Screenshot of the associated automation tab":::


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
| [Demands](/azure/devops/pipelines/process/demands) | None |
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
