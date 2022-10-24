---
title: Gradle@1 - Gradle v1 task
description: Build using a Gradle wrapper script (task version 1).
ms.date: 10/21/2022
monikerRange: "<=azure-pipelines"
---

# Gradle@1 - Gradle v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Build using a Gradle wrapper script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Gradle v1
# Build using a Gradle wrapper script.
- task: Gradle@1
  inputs:
    gradleWrapperFile: 'gradlew' # string. Alias: wrapperScript. Required. Gradle Wrapper. Default: gradlew.
    #options: # string. Options. 
    tasks: 'build' # string. Required. Tasks. Default: build.
  # Advanced
    #workingDirectory: # string. Alias: cwd. Working Directory. 
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK Version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK Path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK Architecture. Default: x64.
    #gradleOptions: '-Xmx1024m' # string. Alias: gradleOpts. Set GRADLE_OPTS. Default: -Xmx1024m.
  # JUnit Test Results
    publishJUnitResults: true # boolean. Required. Publish to TFS/Team Services. Default: true.
    testResultsFiles: '**/build/test-results/TEST-*.xml' # string. Required when publishJUnitResults = true. Test Results Files. Default: **/build/test-results/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test Run Title. 
  # Code Coverage
    #codeCoverageToolOption: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code Coverage Tool. Default: None.
    #codeCoverageClassFilesDirectories: 'build/classes/main/' # string. Alias: classFilesDirectories. Required when codeCoverageTool = false. Class Files Directories. Default: build/classes/main/.
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class Inclusion/Exclusion Filters. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail When Code Coverage Results Are Missing. Default: false.
  # Code Analysis
    sonarQubeRunAnalysis: false # boolean. Alias: sqAnalysisEnabled. Required. Run SonarQube Analysis. Default: false.
    #sonarQubeServiceEndpoint: # string. Alias: sqConnectedServiceName. Required when sqAnalysisEnabled = true. SonarQube Endpoint. 
    #sonarQubeProjectName: # string. Alias: sqProjectName. Required when sqAnalysisEnabled = true. SonarQube Project Name. 
    #sonarQubeProjectKey: # string. Alias: sqProjectKey. Required when sqAnalysisEnabled = true. SonarQube Project Key. 
    #sonarQubeProjectVersion: # string. Alias: sqProjectVersion. Required when sqAnalysisEnabled = true. SonarQube Project Version. 
    #sonarQubeGradlePluginVersion: '2.0.1' # string. Alias: sqGradlePluginVersion. Required when sqAnalysisEnabled = true. SonarQube Gradle Plugin Version. Default: 2.0.1.
    #sonarQubeSpecifyDB: false # boolean. Alias: sqDbDetailsRequired. Required when sqAnalysisEnabled = true. The SonarQube server version is lower than 5.2. Default: false.
    #sonarQubeDBUrl: # string. Alias: sqDbUrl. Optional. Use when sqDbDetailsRequired = true. Db Connection String. 
    #sonarQubeDBUsername: # string. Alias: sqDbUsername. Optional. Use when sqDbDetailsRequired = true. Db Username. 
    #sonarQubeDBPassword: # string. Alias: sqDbPassword. Optional. Use when sqDbDetailsRequired = true. Db User Password. 
    #sonarQubeIncludeFullReport: true # boolean. Alias: sqAnalysisIncludeFullReport. Optional. Use when sqAnalysisEnabled = true. Include full analysis report in the build summary (SQ 5.3+). Default: true.
    #sonarQubeFailWhenQualityGateFails: # boolean. Alias: sqAnalysisBreakBuildIfQualityGateFailed. Optional. Use when sqAnalysisEnabled = true. Fail the build on quality gate failure (SQ 5.3+). 
    #checkStyleRunAnalysis: false # boolean. Alias: checkstyleAnalysisEnabled. Run Checkstyle. Default: false.
    #findBugsRunAnalysis: false # boolean. Alias: findbugsAnalysisEnabled. Run FindBugs. Default: false.
    #pmdRunAnalysis: false # boolean. Alias: pmdAnalysisEnabled. Run PMD. Default: false.
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

<!-- :::item name="gradleWrapperFile"::: -->
:::moniker range="<=azure-pipelines"

**`gradleWrapperFile`** - **Gradle Wrapper**<br>
Input alias: `wrapperScript`. `string`. Required. Default value: `gradlew`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repository root to the Gradle Wrapper script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="options"::: -->
:::moniker range="<=azure-pipelines"

**`options`** - **Options**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tasks"::: -->
:::moniker range="<=azure-pipelines"

**`tasks`** - **Tasks**<br>
`string`. Required. Default value: `build`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working Directory**<br>
Input alias: `cwd`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Working directory in which to run the Gradle build. If not specified, the repository root directory is used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range="<=azure-pipelines"

**`publishJUnitResults`** - **Publish to TFS/Team Services**<br>
`boolean`. Required. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish JUnit test results produced by the Gradle build to TFS/Team Services. Each test results file matching `Test Results Files` will be published as a test run in TFS/Team Services.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testResultsFiles"::: -->
:::moniker range="<=azure-pipelines"

**`testResultsFiles`** - **Test Results Files**<br>
`string`. Required when `publishJUnitResults = true`. Default value: `**/build/test-results/TEST-*.xml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Test results files path. Wildcards can be used. For example, `**/TEST-*.xml` for all XML files whose name starts with TEST-.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range="<=azure-pipelines"

**`testRunTitle`** - **Test Run Title**<br>
`string`. Optional. Use when `publishJUnitResults = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageToolOption"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageToolOption`** - **Code Coverage Tool**<br>
Input alias: `codeCoverageTool`. `string`. Allowed values: `None`, `Cobertura`, `JaCoCo`. Default value: `None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the code coverage tool.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilesDirectories"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageClassFilesDirectories`** - **Class Files Directories**<br>
Input alias: `classFilesDirectories`. `string`. Required when `codeCoverageTool = false`. Default value: `build/classes/main/`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of directories containing class files and archive files (JAR, WAR, etc.). Code coverage is reported for class files in these directories. Normally, classes under `build/classes/main` are searched, which is the default class directory for Gradle builds.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilter"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageClassFilter`** - **Class Inclusion/Exclusion Filters**<br>
Input alias: `classFilter`. `string`. Optional. Use when `codeCoverageTool != None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of filters to include or exclude classes from collecting code coverage. For example: +:com.*,+:org.*,-:my.app*.*.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageFailIfEmpty"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageFailIfEmpty`** - **Fail When Code Coverage Results Are Missing**<br>
Input alias: `failIfCoverageEmpty`. `boolean`. Optional. Use when `codeCoverageTool != None`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fail the build if code coverage did not produce any results to publish.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="javaHomeOption"::: -->
:::moniker range="<=azure-pipelines"

**`javaHomeOption`** - **Set JAVA_HOME by**<br>
Input alias: `javaHomeSelection`. `string`. Required. Allowed values: `JDKVersion` (JDK Version), `Path`. Default value: `JDKVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets JAVA_HOME either by selecting a JDK version that will be discovered during builds or by manually entering a JDK path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkVersionOption"::: -->
:::moniker range="<=azure-pipelines"

**`jdkVersionOption`** - **JDK Version**<br>
Input alias: `jdkVersion`. `string`. Optional. Use when `javaHomeSelection = JDKVersion`. Allowed values: `default`, `1.9` (JDK 9), `1.8` (JDK 8), `1.7` (JDK 7), `1.6` (JDK 6). Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Will attempt to discover the path to the selected JDK version and set JAVA_HOME accordingly.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`jdkDirectory`** - **JDK Path**<br>
Input alias: `jdkUserInputPath`. `string`. Required when `javaHomeSelection = Path`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets JAVA_HOME to the given path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkArchitectureOption"::: -->
:::moniker range="<=azure-pipelines"

**`jdkArchitectureOption`** - **JDK Architecture**<br>
Input alias: `jdkArchitecture`. `string`. Optional. Use when `jdkVersion != default`. Allowed values: `x86`, `x64`. Default value: `x64`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the architecture (x86, x64) of the JDK.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="gradleOptions"::: -->
:::moniker range="<=azure-pipelines"

**`gradleOptions`** - **Set GRADLE_OPTS**<br>
Input alias: `gradleOpts`. `string`. Default value: `-Xmx1024m`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets the GRADLE_OPTS environment variable, which is used to send command-line arguments to start the JVM. The xmx flag specifies the maximum memory available to the JVM.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeRunAnalysis"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeRunAnalysis`** - **Run SonarQube Analysis**<br>
Input alias: `sqAnalysisEnabled`. `boolean`. Required. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run a [SonarQube analysis](https://go.microsoft.com/fwlink/?LinkID=708598) after executing the current goals. 'install' or 'package' goals should be executed first.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeServiceEndpoint"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeServiceEndpoint`** - **SonarQube Endpoint**<br>
Input alias: `sqConnectedServiceName`. `string`. Required when `sqAnalysisEnabled = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The endpoint that specifies the SonarQube server to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeProjectName"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeProjectName`** - **SonarQube Project Name**<br>
Input alias: `sqProjectName`. `string`. Required when `sqAnalysisEnabled = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The SonarQube project name, i.e. sonar.projectName.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeProjectKey"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeProjectKey`** - **SonarQube Project Key**<br>
Input alias: `sqProjectKey`. `string`. Required when `sqAnalysisEnabled = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The SonarQube project unique key, i.e. sonar.projectKey.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeProjectVersion"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeProjectVersion`** - **SonarQube Project Version**<br>
Input alias: `sqProjectVersion`. `string`. Required when `sqAnalysisEnabled = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The SonarQube project version, i.e. sonar.projectVersion.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeGradlePluginVersion"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeGradlePluginVersion`** - **SonarQube Gradle Plugin Version**<br>
Input alias: `sqGradlePluginVersion`. `string`. Required when `sqAnalysisEnabled = true`. Default value: `2.0.1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The SonarQube Gradle plugin version to use. Refer to https://plugins.gradle.org/plugin/org.sonarqube for all available versions.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeSpecifyDB"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeSpecifyDB`** - **The SonarQube server version is lower than 5.2**<br>
Input alias: `sqDbDetailsRequired`. `boolean`. Required when `sqAnalysisEnabled = true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If using a SonarQube server 5.1 or lower, you must specify the database connection details.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeDBUrl"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeDBUrl`** - **Db Connection String**<br>
Input alias: `sqDbUrl`. `string`. Optional. Use when `sqDbDetailsRequired = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
SonarQube server 5.1 and lower only. Enter the database connection setting (i.e. sonar.jdbc.url). For example: jdbc:jtds:sqlserver://localhost/sonar;SelectMethod=Cursor.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeDBUsername"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeDBUsername`** - **Db Username**<br>
Input alias: `sqDbUsername`. `string`. Optional. Use when `sqDbDetailsRequired = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
SonarQube server 5.1 and lower only. Enter the username for the database user (i.e. sonar.jdbc.username).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeDBPassword"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeDBPassword`** - **Db User Password**<br>
Input alias: `sqDbPassword`. `string`. Optional. Use when `sqDbDetailsRequired = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
SonarQube server 5.1 and lower only. Enter the password for the database user i.e. sonar.jdbc.password.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeIncludeFullReport"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeIncludeFullReport`** - **Include full analysis report in the build summary (SQ 5.3+)**<br>
Input alias: `sqAnalysisIncludeFullReport`. `boolean`. Optional. Use when `sqAnalysisEnabled = true`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This option will delay the build until the SonarQube analysis is completed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeFailWhenQualityGateFails"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeFailWhenQualityGateFails`** - **Fail the build on quality gate failure (SQ 5.3+)**<br>
Input alias: `sqAnalysisBreakBuildIfQualityGateFailed`. `boolean`. Optional. Use when `sqAnalysisEnabled = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This option is only available when using a SonarQube server 5.3 or above. It will introduce delays as the build must wait for SonarQube to complete the analysis. [More information](https://go.microsoft.com/fwlink/?LinkId=722407).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkStyleRunAnalysis"::: -->
:::moniker range="<=azure-pipelines"

**`checkStyleRunAnalysis`** - **Run Checkstyle**<br>
Input alias: `checkstyleAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run the Checkstyle tool with the default Sun checks. Results are uploaded as build artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="findBugsRunAnalysis"::: -->
:::moniker range="<=azure-pipelines"

**`findBugsRunAnalysis`** - **Run FindBugs**<br>
Input alias: `findbugsAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use the FindBugs static analysis tool to look for bugs in the code. Results are uploaded as build artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pmdRunAnalysis"::: -->
:::moniker range="<=azure-pipelines"

**`pmdRunAnalysis`** - **Run PMD**<br>
Input alias: `pmdAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use the PMD Java static analysis tool to look for bugs in the code. Results are uploaded as build artifacts.
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
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: java |
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