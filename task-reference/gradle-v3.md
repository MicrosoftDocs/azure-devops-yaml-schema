---
title: Gradle@3 - Gradle v3 task
description: Build using a Gradle wrapper script.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2022"
---

# Gradle@3 - Gradle v3 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::editable-content name="description"::: -->
Build using a Gradle wrapper script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Gradle v3
# Build using a Gradle wrapper script.
- task: Gradle@3
  inputs:
    gradleWrapperFile: 'gradlew' # string. Required. Gradle wrapper. Default: 'gradlew'.
    #workingDirectory: # string. Working directory. 
    #options: # string. Options. 
    tasks: 'build' # string. Required. Tasks. Default: 'build'.
  # JUnit Test Results
    publishJUnitResults: true # boolean. Required. Publish to Azure Pipelines. Default: true.
    testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: '**/TEST-*.xml'.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
  # Code Coverage
    #codeCoverageToolOption: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Code coverage tool. Default: 'None'.
    codeCoverageClassFilesDirectories: 'build/classes/main/' # string. Required when codeCoverageTool != None. Class files directories. Default: 'build/classes/main/'.
    #codeCoverageClassFilter: # string. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageFailIfEmpty: false # boolean. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
    #codeCoverageGradle5xOrHigher: true # boolean. Optional. Use when codeCoverageTool = JaCoCo. Gradle version >= 5.x. Default: true.
  # Advanced
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Required. Set JAVA_HOME by. Default: 'JDKVersion'.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: 'default'.
    #jdkDirectory: # string. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Optional. Use when jdkVersion != default. JDK architecture. Default: 'x64'.
    #gradleOptions: '-Xmx1024m' # string. Set GRADLE_OPTS. Default: '-Xmx1024m'.
  # Code Analysis
    sonarQubeRunAnalysis: false # boolean. Required. Run SonarQube or SonarCloud Analysis. Default: false.
    #sqGradlePluginVersionChoice: 'specify' # 'specify' | 'build'. Required when sqAnalysisEnabled = true. SonarQube scanner for Gradle version. Default: 'specify'.
    #sonarQubeGradlePluginVersion: '2.6.1' # string. Required when sqAnalysisEnabled = true && sqGradlePluginVersionChoice = specify. SonarQube scanner for Gradle plugin version. Default: '2.6.1'.
    #checkStyleRunAnalysis: false # boolean. Run Checkstyle. Default: false.
    #findBugsRunAnalysis: false # boolean. Run FindBugs. Default: false.
    #pmdRunAnalysis: false # boolean. Run PMD. Default: false.
    spotBugsAnalysis: false # boolean. Required. Run SpotBugs. Default: false.
    #spotBugsGradlePluginVersionChoice: 'specify' # 'specify' | 'build'. Required when spotBugsAnalysisEnabled = true. Spotbugs plugin version. Default: 'specify'.
    #spotbugsGradlePluginVersion: '4.7.0' # string. Required when spotBugsAnalysisEnabled = true && spotBugsGradlePluginVersionChoice = specify. Version number. Default: '4.7.0'.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="gradleWrapperFile"::: -->
:::moniker range=">=azure-pipelines-2022"

**`gradleWrapperFile`** - **Gradle wrapper**<br>
Input alias: `wrapperScript`. Type: string. Required. Default value: 'gradlew'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repository root to the Gradle Wrapper script.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2022"

**`workingDirectory`** - **Working directory**<br>
Input alias: `cwd`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Working directory in which to run the Gradle build. If not specified, the repository root directory is used.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="options"::: -->
:::moniker range=">=azure-pipelines-2022"

**`options`** - **Options**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tasks"::: -->
:::moniker range=">=azure-pipelines-2022"

**`tasks`** - **Tasks**<br>
Type: string. Required. Default value: 'build'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range=">=azure-pipelines-2022"

**`publishJUnitResults`** - **Publish to Azure Pipelines**<br>
Type: boolean. Required. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish JUnit test results produced by the Gradle build to Azure Pipelines. Each test results file matching `Test Results Files` will be published as a test run in Azure Pipelines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testResultsFiles"::: -->
:::moniker range=">=azure-pipelines-2022"

**`testResultsFiles`** - **Test results files**<br>
Type: string. Required when publishJUnitResults = true. Default value: '**/TEST-*.xml'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Test results files path. Wildcards can be used ([more information](https://go.microsoft.com/fwlink/?linkid=856077)). For example, `**/TEST-*.xml` for all XML files whose name starts with TEST-.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range=">=azure-pipelines-2022"

**`testRunTitle`** - **Test run title**<br>
Type: string. Optional. Use when publishJUnitResults = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the test run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageToolOption"::: -->
:::moniker range=">=azure-pipelines-2022"

**`codeCoverageToolOption`** - **Code coverage tool**<br>
Input alias: `codeCoverageTool`. Type: string. Allowed values: 'None', 'Cobertura', 'JaCoCo'. Default value: 'None'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the code coverage tool.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilesDirectories"::: -->
:::moniker range=">=azure-pipelines-2022"

**`codeCoverageClassFilesDirectories`** - **Class files directories**<br>
Input alias: `classFilesDirectories`. Type: string. Required when codeCoverageTool != None. Default value: 'build/classes/main/'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of directories containing class files and archive files (JAR, WAR, etc.). Code coverage is reported for class files in these directories. Normally, classes under `build/classes/java/main` (for Gradle 4+) are searched, which is the default class directory for Gradle builds.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilter"::: -->
:::moniker range=">=azure-pipelines-2022"

**`codeCoverageClassFilter`** - **Class inclusion/exclusion filters**<br>
Input alias: `classFilter`. Type: string. Optional. Use when codeCoverageTool != None.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of filters to include or exclude classes from collecting code coverage. For example: +:com.*,+:org.*,-:my.app*.*.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageFailIfEmpty"::: -->
:::moniker range=">=azure-pipelines-2022"

**`codeCoverageFailIfEmpty`** - **Fail when code coverage results are missing**<br>
Input alias: `failIfCoverageEmpty`. Type: boolean. Optional. Use when codeCoverageTool != None. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fail the build if code coverage did not produce any results to publish.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageGradle5xOrHigher"::: -->
:::moniker range=">=azure-pipelines-2022"

**`codeCoverageGradle5xOrHigher`** - **Gradle version >= 5.x**<br>
Input alias: `gradle5xOrHigher`. Type: boolean. Optional. Use when codeCoverageTool = JaCoCo. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set this to 'true' if gradle version is >= 5.x.'True' by default.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="javaHomeOption"::: -->
:::moniker range=">=azure-pipelines-2022"

**`javaHomeOption`** - **Set JAVA_HOME by**<br>
Input alias: `javaHomeSelection`. Type: string. Required. Allowed values: 'JDKVersion', 'Path'. Default value: 'JDKVersion'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets JAVA_HOME either by selecting a JDK version that will be discovered during builds or by manually entering a JDK path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkVersionOption"::: -->
:::moniker range=">=azure-pipelines-2022"

**`jdkVersionOption`** - **JDK version**<br>
Input alias: `jdkVersion`. Type: string. Optional. Use when javaHomeSelection = JDKVersion. Allowed values: 'default', '1.11', '1.10', '1.9', '1.8', '1.7', '1.6'. Default value: 'default'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Will attempt to discover the path to the selected JDK version and set JAVA_HOME accordingly.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkDirectory"::: -->
:::moniker range=">=azure-pipelines-2022"

**`jdkDirectory`** - **JDK path**<br>
Input alias: `jdkUserInputPath`. Type: string. Required when javaHomeSelection = Path.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets JAVA_HOME to the given path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkArchitectureOption"::: -->
:::moniker range=">=azure-pipelines-2022"

**`jdkArchitectureOption`** - **JDK architecture**<br>
Input alias: `jdkArchitecture`. Type: string. Optional. Use when jdkVersion != default. Allowed values: 'x86', 'x64'. Default value: 'x64'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the architecture (x86, x64) of the JDK.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="gradleOptions"::: -->
:::moniker range=">=azure-pipelines-2022"

**`gradleOptions`** - **Set GRADLE_OPTS**<br>
Input alias: `gradleOpts`. Type: string. Default value: '-Xmx1024m'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets the GRADLE_OPTS environment variable, which is used to send command-line arguments to start the JVM. The xmx flag specifies the maximum memory available to the JVM.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeRunAnalysis"::: -->
:::moniker range=">=azure-pipelines-2022"

**`sonarQubeRunAnalysis`** - **Run SonarQube or SonarCloud Analysis**<br>
Input alias: `sqAnalysisEnabled`. Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This option has changed from version 1 of the **Gradle** task to use the [SonarQube](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarqube) and [SonarCloud](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarcloud) marketplace extensions. Enable this option to run [SonarQube or SonarCloud analysis](http://redirect.sonarsource.com/doc/install-configure-scanner-tfs-ts.html) after executing tasks in the **Tasks** field. You must also add a **Prepare Analysis Configuration** task from one of the extensions to the build pipeline before this Gradle task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sqGradlePluginVersionChoice"::: -->
:::moniker range=">=azure-pipelines-2022"

**`sqGradlePluginVersionChoice`** - **SonarQube scanner for Gradle version**<br>
Type: string. Required when sqAnalysisEnabled = true. Allowed values: 'specify', 'build'. Default value: 'specify'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The SonarQube Gradle plugin version to use. You can declare it in your Gradle configuration file, or specify a version here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeGradlePluginVersion"::: -->
:::moniker range=">=azure-pipelines-2022"

**`sonarQubeGradlePluginVersion`** - **SonarQube scanner for Gradle plugin version**<br>
Input alias: `sqGradlePluginVersion`. Type: string. Required when sqAnalysisEnabled = true && sqGradlePluginVersionChoice = specify. Default value: '2.6.1'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Refer to https://plugins.gradle.org/plugin/org.sonarqube for all available versions.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkStyleRunAnalysis"::: -->
:::moniker range=">=azure-pipelines-2022"

**`checkStyleRunAnalysis`** - **Run Checkstyle**<br>
Input alias: `checkstyleAnalysisEnabled`. Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run the Checkstyle tool with the default Sun checks. Results are uploaded as build artifacts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="findBugsRunAnalysis"::: -->
:::moniker range=">=azure-pipelines-2022"

**`findBugsRunAnalysis`** - **Run FindBugs**<br>
Input alias: `findbugsAnalysisEnabled`. Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use the FindBugs static analysis tool to look for bugs in the code. Results are uploaded as build artifacts. In Gradle 6.0 this plugin was removed. Use spotbugs plugin instead. [More info](https://docs.gradle.org/current/userguide/upgrading_version_5.html#the_findbugs_plugin_has_been_removed).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pmdRunAnalysis"::: -->
:::moniker range=">=azure-pipelines-2022"

**`pmdRunAnalysis`** - **Run PMD**<br>
Input alias: `pmdAnalysisEnabled`. Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use the PMD Java static analysis tool to look for bugs in the code. Results are uploaded as build artifacts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="spotBugsAnalysis"::: -->
:::moniker range=">=azure-pipelines-2022"

**`spotBugsAnalysis`** - **Run SpotBugs**<br>
Input alias: `spotBugsAnalysisEnabled`. Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enable this option to run spotBugs. This plugin works with Gradle v5.6 or later. [More info](https://spotbugs.readthedocs.io/en/stable/gradle.html#use-spotbugs-gradle-plugin).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="spotBugsGradlePluginVersionChoice"::: -->
:::moniker range=">=azure-pipelines-2022"

**`spotBugsGradlePluginVersionChoice`** - **Spotbugs plugin version**<br>
Type: string. Required when spotBugsAnalysisEnabled = true. Allowed values: 'specify', 'build'. Default value: 'specify'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Spotbugs Gradle plugin version to use. You can declare it in your Gradle configuration file, or specify a version here.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="spotbugsGradlePluginVersion"::: -->
:::moniker range=">=azure-pipelines-2022"

**`spotbugsGradlePluginVersion`** - **Version number**<br>
Type: string. Required when spotBugsAnalysisEnabled = true && spotBugsGradlePluginVersionChoice = specify. Default value: '4.7.0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Refer to https://plugins.gradle.org/plugin/com.github.spotbugs for all available versions.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2022"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Configuration of the SonarQube analysis was moved to the [SonarQube](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarqube) or [SonarCloud](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarcloud) extensions, in task `Prepare Analysis Configuration`.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
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