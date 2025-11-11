---
title: Gradle@2 - Gradle v2 task
description: Build using a Gradle wrapper script (task version 2).
ms.date: 11/11/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
---

# Gradle@2 - Gradle v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Build using a Gradle wrapper script.

This version of the task is deprecated; use [Gradle@3](./gradle-v3.md).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Build using a Gradle wrapper script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Gradle v2
# Build using a Gradle wrapper script.
- task: Gradle@2
  inputs:
    gradleWrapperFile: 'gradlew' # string. Alias: wrapperScript. Required. Gradle wrapper. Default: gradlew.
    #workingDirectory: # string. Alias: cwd. Working directory. 
    #options: # string. Options. 
    tasks: 'build' # string. Required. Tasks. Default: build.
  # JUnit Test Results
    #publishJUnitResults: true # boolean. Publish to Azure Pipelines. Default: true.
    testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: **/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
  # Code Coverage
    #codeCoverageToolOption: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code coverage tool. Default: None.
    codeCoverageClassFilesDirectories: 'build/classes/main/' # string. Alias: classFilesDirectories. Required when codeCoverageTool != None. Class files directories. Default: build/classes/main/.
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
    #codeCoverageGradle5xOrHigher: true # boolean. Alias: gradle5xOrHigher. Optional. Use when codeCoverageTool = JaCoCo. Gradle version >= 5.x. Default: true.
  # Advanced
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.17' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64' | 'arm64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
    #gradleOptions: '-Xmx1024m' # string. Alias: gradleOpts. Set GRADLE_OPTS. Default: -Xmx1024m.
  # Code Analysis
    #sonarQubeRunAnalysis: false # boolean. Alias: sqAnalysisEnabled. Run SonarQube or SonarCloud Analysis. Default: false.
    #sqGradlePluginVersionChoice: 'specify' # 'specify' | 'build'. Required when sqAnalysisEnabled = true. SonarQube scanner for Gradle version. Default: specify.
    #sonarQubeGradlePluginVersion: '2.6.1' # string. Alias: sqGradlePluginVersion. Required when sqAnalysisEnabled = true && sqGradlePluginVersionChoice = specify. SonarQube scanner for Gradle plugin version. Default: 2.6.1.
    #checkStyleRunAnalysis: false # boolean. Alias: checkstyleAnalysisEnabled. Run Checkstyle. Default: false.
    #findBugsRunAnalysis: false # boolean. Alias: findbugsAnalysisEnabled. Run FindBugs. Default: false.
    #pmdRunAnalysis: false # boolean. Alias: pmdAnalysisEnabled. Run PMD. Default: false.
    #spotBugsAnalysis: false # boolean. Alias: spotBugsAnalysisEnabled. Run SpotBugs. Default: false.
    #spotBugsGradlePluginVersionChoice: 'specify' # 'specify' | 'build'. Required when spotBugsAnalysisEnabled = true. Spotbugs plugin version. Default: specify.
    #spotbugsGradlePluginVersion: '4.7.0' # string. Required when spotBugsAnalysisEnabled = true && spotBugsGradlePluginVersionChoice = specify. Version number. Default: 4.7.0.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2022.1 <=azure-pipelines-server"

```yaml
# Gradle v2
# Build using a Gradle wrapper script.
- task: Gradle@2
  inputs:
    gradleWrapperFile: 'gradlew' # string. Alias: wrapperScript. Required. Gradle wrapper. Default: gradlew.
    #workingDirectory: # string. Alias: cwd. Working directory. 
    #options: # string. Options. 
    tasks: 'build' # string. Required. Tasks. Default: build.
  # JUnit Test Results
    #publishJUnitResults: true # boolean. Publish to Azure Pipelines. Default: true.
    testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: **/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
  # Code Coverage
    #codeCoverageToolOption: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code coverage tool. Default: None.
    codeCoverageClassFilesDirectories: 'build/classes/main/' # string. Alias: classFilesDirectories. Required when codeCoverageTool != None. Class files directories. Default: build/classes/main/.
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
    #codeCoverageGradle5xOrHigher: true # boolean. Alias: gradle5xOrHigher. Optional. Use when codeCoverageTool = JaCoCo. Gradle version >= 5.x. Default: true.
  # Advanced
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.17' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
    #gradleOptions: '-Xmx1024m' # string. Alias: gradleOpts. Set GRADLE_OPTS. Default: -Xmx1024m.
  # Code Analysis
    #sonarQubeRunAnalysis: false # boolean. Alias: sqAnalysisEnabled. Run SonarQube or SonarCloud Analysis. Default: false.
    #sqGradlePluginVersionChoice: 'specify' # 'specify' | 'build'. Required when sqAnalysisEnabled = true. SonarQube scanner for Gradle version. Default: specify.
    #sonarQubeGradlePluginVersion: '2.6.1' # string. Alias: sqGradlePluginVersion. Required when sqAnalysisEnabled = true && sqGradlePluginVersionChoice = specify. SonarQube scanner for Gradle plugin version. Default: 2.6.1.
    #checkStyleRunAnalysis: false # boolean. Alias: checkstyleAnalysisEnabled. Run Checkstyle. Default: false.
    #findBugsRunAnalysis: false # boolean. Alias: findbugsAnalysisEnabled. Run FindBugs. Default: false.
    #pmdRunAnalysis: false # boolean. Alias: pmdAnalysisEnabled. Run PMD. Default: false.
    #spotBugsAnalysis: false # boolean. Alias: spotBugsAnalysisEnabled. Run SpotBugs. Default: false.
    #spotBugsGradlePluginVersionChoice: 'specify' # 'specify' | 'build'. Required when spotBugsAnalysisEnabled = true. Spotbugs plugin version. Default: specify.
    #spotbugsGradlePluginVersion: '4.7.0' # string. Required when spotBugsAnalysisEnabled = true && spotBugsGradlePluginVersionChoice = specify. Version number. Default: 4.7.0.
```

:::moniker-end

:::moniker range="=azure-pipelines-2022"

```yaml
# Gradle v2
# Build using a Gradle wrapper script.
- task: Gradle@2
  inputs:
    gradleWrapperFile: 'gradlew' # string. Alias: wrapperScript. Required. Gradle wrapper. Default: gradlew.
    #workingDirectory: # string. Alias: cwd. Working directory. 
    #options: # string. Options. 
    tasks: 'build' # string. Required. Tasks. Default: build.
  # JUnit Test Results
    #publishJUnitResults: true # boolean. Publish to Azure Pipelines. Default: true.
    testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: **/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
  # Code Coverage
    #codeCoverageToolOption: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code coverage tool. Default: None.
    codeCoverageClassFilesDirectories: 'build/classes/main/' # string. Alias: classFilesDirectories. Required when codeCoverageTool != None. Class files directories. Default: build/classes/main/.
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
    #codeCoverageGradle5xOrHigher: true # boolean. Alias: gradle5xOrHigher. Optional. Use when codeCoverageTool = JaCoCo. Gradle version >= 5.x. Default: true.
  # Advanced
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
    #gradleOptions: '-Xmx1024m' # string. Alias: gradleOpts. Set GRADLE_OPTS. Default: -Xmx1024m.
  # Code Analysis
    #sonarQubeRunAnalysis: false # boolean. Alias: sqAnalysisEnabled. Run SonarQube or SonarCloud Analysis. Default: false.
    #sqGradlePluginVersionChoice: 'specify' # 'specify' | 'build'. Required when sqAnalysisEnabled = true. SonarQube scanner for Gradle version. Default: specify.
    #sonarQubeGradlePluginVersion: '2.6.1' # string. Alias: sqGradlePluginVersion. Required when sqAnalysisEnabled = true && sqGradlePluginVersionChoice = specify. SonarQube scanner for Gradle plugin version. Default: 2.6.1.
    #checkStyleRunAnalysis: false # boolean. Alias: checkstyleAnalysisEnabled. Run Checkstyle. Default: false.
    #findBugsRunAnalysis: false # boolean. Alias: findbugsAnalysisEnabled. Run FindBugs. Default: false.
    #pmdRunAnalysis: false # boolean. Alias: pmdAnalysisEnabled. Run PMD. Default: false.
    #spotBugsAnalysis: false # boolean. Alias: spotBugsAnalysisEnabled. Run SpotBugs. Default: false.
    #spotBugsGradlePluginVersionChoice: 'specify' # 'specify' | 'build'. Required when spotBugsAnalysisEnabled = true. Spotbugs plugin version. Default: specify.
    #spotbugsGradlePluginVersion: '4.7.0' # string. Required when spotBugsAnalysisEnabled = true && spotBugsGradlePluginVersionChoice = specify. Version number. Default: 4.7.0.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

```yaml
# Gradle v2
# Build using a Gradle wrapper script.
- task: Gradle@2
  inputs:
    gradleWrapperFile: 'gradlew' # string. Alias: wrapperScript. Required. Gradle wrapper. Default: gradlew.
    #workingDirectory: # string. Alias: cwd. Working directory. 
    #options: # string. Options. 
    tasks: 'build' # string. Required. Tasks. Default: build.
  # JUnit Test Results
    #publishJUnitResults: true # boolean. Publish to Azure Pipelines. Default: true.
    testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: **/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
  # Code Coverage
    #codeCoverageToolOption: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code coverage tool. Default: None.
    codeCoverageClassFilesDirectories: 'build/classes/main/' # string. Alias: classFilesDirectories. Required when codeCoverageTool != None. Class files directories. Default: build/classes/main/.
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
  # Advanced
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
    #gradleOptions: '-Xmx1024m' # string. Alias: gradleOpts. Set GRADLE_OPTS. Default: -Xmx1024m.
  # Code Analysis
    #sonarQubeRunAnalysis: false # boolean. Alias: sqAnalysisEnabled. Run SonarQube or SonarCloud Analysis. Default: false.
    #sqGradlePluginVersionChoice: 'specify' # 'specify' | 'build'. Required when sqAnalysisEnabled = true. SonarQube scanner for Gradle version. Default: specify.
    #sonarQubeGradlePluginVersion: '2.6.1' # string. Alias: sqGradlePluginVersion. Required when sqAnalysisEnabled = true && sqGradlePluginVersionChoice = specify. SonarQube scanner for Gradle plugin version. Default: 2.6.1.
    #checkStyleRunAnalysis: false # boolean. Alias: checkstyleAnalysisEnabled. Run Checkstyle. Default: false.
    #findBugsRunAnalysis: false # boolean. Alias: findbugsAnalysisEnabled. Run FindBugs. Default: false.
    #pmdRunAnalysis: false # boolean. Alias: pmdAnalysisEnabled. Run PMD. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Gradle v2
# Build using a Gradle wrapper script.
- task: Gradle@2
  inputs:
    gradleWrapperFile: 'gradlew' # string. Alias: wrapperScript. Required. Gradle wrapper. Default: gradlew.
    #workingDirectory: # string. Alias: cwd. Working directory. 
    #options: # string. Options. 
    tasks: 'build' # string. Required. Tasks. Default: build.
  # JUnit Test Results
    #publishJUnitResults: true # boolean. Publish to Azure Pipelines. Default: true.
    testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: **/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
  # Code Coverage
    #codeCoverageToolOption: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code coverage tool. Default: None.
    #codeCoverageClassFilesDirectories: 'build/classes/main/' # string. Alias: classFilesDirectories. Required when codeCoverageTool = false. Class files directories. Default: build/classes/main/.
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
  # Advanced
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
    #gradleOptions: '-Xmx1024m' # string. Alias: gradleOpts. Set GRADLE_OPTS. Default: -Xmx1024m.
  # Code Analysis
    #sonarQubeRunAnalysis: false # boolean. Alias: sqAnalysisEnabled. Run SonarQube or SonarCloud Analysis. Default: false.
    #sqGradlePluginVersionChoice: 'specify' # 'specify' | 'build'. Required when sqAnalysisEnabled = true. SonarQube scanner for Gradle version. Default: specify.
    #sonarQubeGradlePluginVersion: '2.6.1' # string. Alias: sqGradlePluginVersion. Required when sqAnalysisEnabled = true && sqGradlePluginVersionChoice = specify. SonarQube scanner for Gradle plugin version. Default: 2.6.1.
    #checkStyleRunAnalysis: false # boolean. Alias: checkstyleAnalysisEnabled. Run Checkstyle. Default: false.
    #findBugsRunAnalysis: false # boolean. Alias: findbugsAnalysisEnabled. Run FindBugs. Default: false.
    #pmdRunAnalysis: false # boolean. Alias: pmdAnalysisEnabled. Run PMD. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="gradleWrapperFile"::: -->
:::moniker range="<=azure-pipelines"

**`gradleWrapperFile`** - **Gradle wrapper**<br>
[Input alias](index.md#what-are-task-input-aliases): `wrapperScript`. `string`. Required. Default value: `gradlew`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the `gradlew` wrapper's location within the repository that will be used for the build. Agents on Windows (including Microsoft-hosted agents) must use the `gradlew.bat` wrapper. Agents on Linux or macOS can use the `gradlew` shell script. Learn more about the [Gradle Wrapper](https://docs.gradle.org/current/userguide/gradle_wrapper.html). If the Gradle wrapper isn't in the root directory, specify the path to the wrapper script. For example, `subdir/gradlew`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `cwd`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the working directory to run the Gradle build. The task uses the repository root directory if the working directory is not specified.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="options"::: -->
:::moniker range="<=azure-pipelines"

**`options`** - **Options**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the command line options that will be passed to the Gradle wrapper. See [Gradle Command Line](https://docs.gradle.org/current/userguide/command_line_interface.html) for more information.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tasks"::: -->
:::moniker range="<=azure-pipelines"

**`tasks`** - **Tasks**<br>
`string`. Required. Default value: `build`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The task(s) for Gradle to execute. A list of task names should be separated by spaces and can be taken from `gradlew tasks` issued from a command prompt.

See [Gradle Build Script Basics](https://docs.gradle.org/current/userguide/tutorial_using_tasks.html) for more information.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range="<=azure-pipelines"

**`publishJUnitResults`** - **Publish to Azure Pipelines**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Publishes JUnit test results produced by the Gradle build to Azure Pipelines. The task publishes each test results file matching `Test Results Files` as a test run in Azure Pipelines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testResultsFiles"::: -->
:::moniker range="<=azure-pipelines"

**`testResultsFiles`** - **Test results files**<br>
`string`. Required when `publishJUnitResults = true`. Default value: `**/TEST-*.xml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file path for test results. [Wildcards](/azure/devops/pipelines/tasks/file-matching-patterns) can be used. For example, `**/TEST-*.xml` for all XML files whose name starts with `TEST-`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range="<=azure-pipelines"

**`testRunTitle`** - **Test run title**<br>
`string`. Optional. Use when `publishJUnitResults = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a name for the JUnit test case results for this build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageToolOption"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageToolOption`** - **Code coverage tool**<br>
[Input alias](index.md#what-are-task-input-aliases): `codeCoverageTool`. `string`. Allowed values: `None`, `Cobertura`, `JaCoCo`. Default value: `None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a code coverage tool to determine the code that is covered by the test cases for the build.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilesDirectories"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`codeCoverageClassFilesDirectories`** - **Class files directories**<br>
[Input alias](index.md#what-are-task-input-aliases): `classFilesDirectories`. `string`. Required when `codeCoverageTool != None`. Default value: `build/classes/main/`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The comma-separated list of directories containing class files and archive files (.jar, .war, and more). Code coverage is reported for class files in these directories. Normally, the task searches classes under `build/classes/java/main` (for Gradle 4+), which is the default class directory for Gradle builds.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2020"

**`codeCoverageClassFilesDirectories`** - **Class files directories**<br>
[Input alias](index.md#what-are-task-input-aliases): `classFilesDirectories`. `string`. Required when `codeCoverageTool = false`. Default value: `build/classes/main/`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The comma-separated list of directories containing class files and archive files (.jar, .war, and more). Code coverage is reported for class files in these directories. Normally, the task searches classes under `build/classes/java/main` (for Gradle 4+), which is the default class directory for Gradle builds.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilter"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageClassFilter`** - **Class inclusion/exclusion filters**<br>
[Input alias](index.md#what-are-task-input-aliases): `classFilter`. `string`. Optional. Use when `codeCoverageTool != None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The comma-separated list of filters to include or exclude classes from collecting code coverage. For example: `+:com.*`,`+:org.*`,`-:my.app*.*`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageFailIfEmpty"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageFailIfEmpty`** - **Fail when code coverage results are missing**<br>
[Input alias](index.md#what-are-task-input-aliases): `failIfCoverageEmpty`. `boolean`. Optional. Use when `codeCoverageTool != None`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fails the build if code coverage did not produce any results to publish.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageGradle5xOrHigher"::: -->
:::moniker range=">=azure-pipelines-2022"

**`codeCoverageGradle5xOrHigher`** - **Gradle version >= 5.x**<br>
[Input alias](index.md#what-are-task-input-aliases): `gradle5xOrHigher`. `boolean`. Optional. Use when `codeCoverageTool = JaCoCo`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set this to 'true' if gradle version is >= 5.x.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="javaHomeOption"::: -->
:::moniker range="<=azure-pipelines"

**`javaHomeOption`** - **Set JAVA_HOME by**<br>
[Input alias](index.md#what-are-task-input-aliases): `javaHomeSelection`. `string`. Required. Allowed values: `JDKVersion` (JDK Version), `Path`. Default value: `JDKVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets JAVA_HOME by selecting a JDK version that the task discovers during builds or by manually entering a JDK path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkVersionOption"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`jdkVersionOption`** - **JDK version**<br>
[Input alias](index.md#what-are-task-input-aliases): `jdkVersion`. `string`. Optional. Use when `javaHomeSelection = JDKVersion`. Allowed values: `default`, `1.17` (JDK 17), `1.11` (JDK 11), `1.10` (JDK 10 (out of support)), `1.9` (JDK 9 (out of support)), `1.8` (JDK 8), `1.7` (JDK 7), `1.6` (JDK 6 (out of support)). Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Attempts to discover the path to the selected JDK version and set JAVA_HOME accordingly.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2022"

**`jdkVersionOption`** - **JDK version**<br>
[Input alias](index.md#what-are-task-input-aliases): `jdkVersion`. `string`. Optional. Use when `javaHomeSelection = JDKVersion`. Allowed values: `default`, `1.11` (JDK 11), `1.10` (JDK 10 (out of support)), `1.9` (JDK 9 (out of support)), `1.8` (JDK 8), `1.7` (JDK 7), `1.6` (JDK 6 (out of support)). Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Attempts to discover the path to the selected JDK version and set JAVA_HOME accordingly.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`jdkDirectory`** - **JDK path**<br>
[Input alias](index.md#what-are-task-input-aliases): `jdkUserInputPath`. `string`. Required when `javaHomeSelection = Path`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets JAVA_HOME to the given path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkArchitectureOption"::: -->
:::moniker range=">azure-pipelines-server"

**`jdkArchitectureOption`** - **JDK architecture**<br>
[Input alias](index.md#what-are-task-input-aliases): `jdkArchitecture`. `string`. Optional. Use when `jdkVersion != default`. Allowed values: `x86`, `x64`, `arm64`. Default value: `x64`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Supplies the JDK architecture (x86 or x64).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-server"

**`jdkArchitectureOption`** - **JDK architecture**<br>
[Input alias](index.md#what-are-task-input-aliases): `jdkArchitecture`. `string`. Optional. Use when `jdkVersion != default`. Allowed values: `x86`, `x64`. Default value: `x64`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Supplies the JDK architecture (x86 or x64).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="gradleOptions"::: -->
:::moniker range="<=azure-pipelines"

**`gradleOptions`** - **Set GRADLE_OPTS**<br>
[Input alias](index.md#what-are-task-input-aliases): `gradleOpts`. `string`. Default value: `-Xmx1024m`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets the GRADLE_OPTS environment variable, which is used to send command-line arguments to start the JVM. The `xmx` flag specifies the maximum memory available to the JVM.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeRunAnalysis"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeRunAnalysis`** - **Run SonarQube or SonarCloud Analysis**<br>
[Input alias](index.md#what-are-task-input-aliases): `sqAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This option has changed from version 1 of the **Gradle** task to use the [SonarQube](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarqube) and [SonarCloud](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarcloud) marketplace extensions. Enable this option to run [SonarQube or SonarCloud analysis](http://redirect.sonarsource.com/doc/install-configure-scanner-tfs-ts.html) after executing tasks in the **Tasks** field. You must also add a **Prepare Analysis Configuration** task from one of the extensions to the build pipeline before this Gradle task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sqGradlePluginVersionChoice"::: -->
:::moniker range="<=azure-pipelines"

**`sqGradlePluginVersionChoice`** - **SonarQube scanner for Gradle version**<br>
`string`. Required when `sqAnalysisEnabled = true`. Allowed values: `specify` (Specify version number), `build` (Use plugin applied in your build.gradle). Default value: `specify`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SonarQube Gradle plugin version to use. Declare the version in the Gradle configuration file, or specify a version with this string.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeGradlePluginVersion"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeGradlePluginVersion`** - **SonarQube scanner for Gradle plugin version**<br>
[Input alias](index.md#what-are-task-input-aliases): `sqGradlePluginVersion`. `string`. Required when `sqAnalysisEnabled = true && sqGradlePluginVersionChoice = specify`. Default value: `2.6.1`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Contains the version number of the [SonarQube Gradle plugin](https://plugins.gradle.org/plugin/org.sonarqube).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkStyleRunAnalysis"::: -->
:::moniker range="<=azure-pipelines"

**`checkStyleRunAnalysis`** - **Run Checkstyle**<br>
[Input alias](index.md#what-are-task-input-aliases): `checkstyleAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs the Checkstyle tool with the default Sun checks. Results are uploaded as build artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="findBugsRunAnalysis"::: -->
:::moniker range="<=azure-pipelines"

**`findBugsRunAnalysis`** - **Run FindBugs**<br>
[Input alias](index.md#what-are-task-input-aliases): `findbugsAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uses the FindBugs static analysis tool to look for bugs in the code. Results are uploaded as build artifacts. In Gradle 6.0, [this plugin was removed](https://docs.gradle.org/current/userguide/upgrading_version_5.html#the_findbugs_plugin_has_been_removed). Use the SpotBugs plugin instead.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pmdRunAnalysis"::: -->
:::moniker range="<=azure-pipelines"

**`pmdRunAnalysis`** - **Run PMD**<br>
[Input alias](index.md#what-are-task-input-aliases): `pmdAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uses the PMD Java static analysis tool to look for bugs in the code. The results are uploaded as build artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="spotBugsAnalysis"::: -->
:::moniker range=">=azure-pipelines-2022"

**`spotBugsAnalysis`** - **Run SpotBugs**<br>
[Input alias](index.md#what-are-task-input-aliases): `spotBugsAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs `spotBugs` when `true`. This plugin works with Gradle v5.6 or later. Learn more about [using the SpotBugs Gradle plugin](https://spotbugs.readthedocs.io/en/stable/gradle.html#use-spotbugs-gradle-plugin). The plugin may work in an unexpected way or may not work at all with an earlier Gradle version.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="spotBugsGradlePluginVersionChoice"::: -->
:::moniker range=">=azure-pipelines-2022"

**`spotBugsGradlePluginVersionChoice`** - **Spotbugs plugin version**<br>
`string`. Required when `spotBugsAnalysisEnabled = true`. Allowed values: `specify` (Specify version number), `build` (Use plugin applied in your build.gradle). Default value: `specify`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SpotBugs Gradle plugin version to use. The version can be declared in the Gradle configuration file, or the version can be specified in this string.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="spotbugsGradlePluginVersion"::: -->
:::moniker range=">=azure-pipelines-2022"

**`spotbugsGradlePluginVersion`** - **Version number**<br>
`string`. Required when `spotBugsAnalysisEnabled = true && spotBugsGradlePluginVersionChoice = specify`. Default value: `4.7.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Contains the version number of the [SpotBugs Gradle plugin](https://plugins.gradle.org/plugin/com.github.spotbugs).
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

:::moniker range=">=azure-pipelines-2022"

> [!NOTE]
> There is a newer version of this task available at [Gradle@3](./gradle-v3.md).

:::moniker-end

Configuration of the SonarQube analysis was moved to the [SonarQube](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarqube) or [SonarCloud](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarcloud) extensions in the task `Prepare Analysis Configuration`.

Use this task to build using a Gradle wrapper script.

### How do I generate a wrapper from my Gradle project?

The Gradle wrapper allows the build agent to download and configure the exact Gradle environment that is checked into the repository without having any software configuration on the build agent itself other than the JVM.

1. Create the Gradle wrapper by issuing the following command from the root project directory where your build.gradle resides:

   `jamal@fabrikam> gradle wrapper`

2. Upload your Gradle wrapper to your remote repository.

   There is a binary artifact that is generated by the gradle wrapper (located at `gradle/wrapper/gradle-wrapper.jar`).
   This binary file is small and doesn't require updating. If you need to change the Gradle configuration run on the build agent, you update the `gradle-wrapper.properties`.

   The repository should look something like this:

```
|-- gradle/
    `-- wrapper/
        `-- gradle-wrapper.jar
        `-- gradle-wrapper.properties
|-- src/
|-- .gitignore
|-- build.gradle
|-- gradlew
|-- gradlew.bat
```

### How do I fix timeouts when downloading dependencies?

To fix errors such as `Read timed out` when downloading dependencies, users of Gradle 4.3+ can change the timeout by adding `-Dhttp.socketTimeout=60000 -Dhttp.connectionTimeout=60000` to `Options`. This increases the timeout from 10 seconds to 1 minute.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

[Build your Java app with Gradle](/azure/devops/pipelines/ecosystems/java)
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