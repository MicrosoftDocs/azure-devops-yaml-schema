---
title: Maven@1 - Maven v1 task
description: Build with Apache Maven (task version 1).
ms.date: 09/22/2025
monikerRange: "=azure-pipelines || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
---

# Maven@1 - Maven v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to build with Apache Maven.

This version of the task is deprecated; use [Maven@4](./maven-v4.md).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Maven v1
# Build with Apache Maven.
- task: Maven@1
  inputs:
    mavenPOMFile: 'pom.xml' # string. Required. Maven POM file. Default: pom.xml.
    #goals: 'package' # string. Goal(s). Default: package.
    #options: # string. Options. 
  # JUnit Test Results
    #publishJUnitResults: true # boolean. Publish to TFS/Team Services. Default: true.
    testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test Results Files. Default: **/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test Run Title. 
  # Code Coverage
    #codeCoverageToolOption: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code Coverage Tool. Default: None.
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class Inclusion/Exclusion Filters. 
    #codeCoverageClassFilesDirectories: # string. Alias: classFilesDirectories. Optional. Use when codeCoverageTool = JaCoCo. Class Files Directories. 
    #codeCoverageSourceDirectories: # string. Alias: srcDirectories. Optional. Use when codeCoverageTool = JaCoCo. Source Files Directories. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail When Code Coverage Results Are Missing. Default: false.
  # Advanced
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK Version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK Path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK Architecture. Default: x64.
    mavenVersionOption: 'Default' # 'Default' | 'Path'. Alias: mavenVersionSelection. Required. Maven Version. Default: Default.
    #mavenDirectory: # string. Alias: mavenPath. Required when mavenVersionSelection = Path. Maven Path. 
    #mavenSetM2Home: false # boolean. Optional. Use when mavenVersionSelection = Path. Set M2_HOME variable. Default: false.
    #mavenOptions: '-Xmx1024m' # string. Alias: mavenOpts. Set MAVEN_OPTS to. Default: -Xmx1024m.
    #mavenAuthenticateFeed: true # boolean. Alias: mavenFeedAuthenticate. Authenticate built-in Maven feeds. Default: true.
  # Code Analysis
    #sonarQubeRunAnalysis: false # boolean. Alias: sqAnalysisEnabled. Run SonarQube Analysis. Default: false.
    #sonarQubeServiceEndpoint: # string. Alias: sqConnectedServiceName. Required when sqAnalysisEnabled = true. SonarQube Endpoint. 
    #sonarQubeProjectName: # string. Alias: sqProjectName. Optional. Use when sqAnalysisEnabled = true. SonarQube Project Name. 
    #sonarQubeProjectKey: # string. Alias: sqProjectKey. Optional. Use when sqAnalysisEnabled = true. SonarQube Project Key. 
    #sonarQubeProjectVersion: # string. Alias: sqProjectVersion. Optional. Use when sqAnalysisEnabled = true. SonarQube Project Version. 
    #sonarQubeSpecifyDB: false # boolean. Alias: sqDbDetailsRequired. Optional. Use when sqAnalysisEnabled = true. The SonarQube server version is lower than 5.2. Default: false.
    #sonarQubeDBUrl: # string. Alias: sqDbUrl. Optional. Use when sqDbDetailsRequired = true. Db Connection String. 
    #sonarQubeDBUsername: # string. Alias: sqDbUsername. Optional. Use when sqDbDetailsRequired = true. Db Username. 
    #sonarQubeDBPassword: # string. Alias: sqDbPassword. Optional. Use when sqDbDetailsRequired = true. Db User Password. 
    #sonarQubeIncludeFullReport: true # boolean. Alias: sqAnalysisIncludeFullReport. Optional. Use when sqAnalysisEnabled = true. Include full analysis report in the build summary (SQ 5.3+). Default: true.
    #sonarQubeFailWhenQualityGateFails: # boolean. Alias: sqAnalysisBreakBuildIfQualityGateFailed. Optional. Use when sqAnalysisEnabled = true. Fail the build on quality gate failure (SQ 5.3+). 
    #checkStyleRunAnalysis: false # boolean. Alias: checkstyleAnalysisEnabled. Run Checkstyle. Default: false.
    #pmdRunAnalysis: false # boolean. Alias: pmdAnalysisEnabled. Run PMD. Default: false.
    #findBugsRunAnalysis: false # boolean. Alias: findbugsAnalysisEnabled. Run FindBugs. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="mavenPOMFile"::: -->
:::moniker range="<=azure-pipelines"

**`mavenPOMFile`** - **Maven POM file**<br>
`string`. Required. Default value: `pom.xml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path from the repository root to the Maven POM file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="goals"::: -->
:::moniker range="<=azure-pipelines"

**`goals`** - **Goal(s)**<br>
`string`. Default value: `package`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
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
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range="<=azure-pipelines"

**`publishJUnitResults`** - **Publish to TFS/Team Services**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to publish the JUnit test results produced by the Maven build to TFS/Team Services. Each test results file matching `Test Results Files` will be published as a test run in TFS/Team Services.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testResultsFiles"::: -->
:::moniker range="<=azure-pipelines"

**`testResultsFiles`** - **Test Results Files**<br>
`string`. Required when `publishJUnitResults = true`. Default value: `**/TEST-*.xml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path and pattern of the test results files to publish. For example, `**/TEST-*.xml` for all XML files with a name that starts with `TEST-`. If no root path is specified, files are matched beneath the default working directory, the value of which is available in the variable `$(System.DefaultWorkingDirectory)`. For example, a value of `**/TEST-*.xml` will actually result in matching files from `$(System.DefaultWorkingDirectory)/**/TEST-*.xml`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range="<=azure-pipelines"

**`testRunTitle`** - **Test Run Title**<br>
`string`. Optional. Use when `publishJUnitResults = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a name for the test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageToolOption"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageToolOption`** - **Code Coverage Tool**<br>
[Input alias](index.md#what-are-task-input-aliases): `codeCoverageTool`. `string`. Allowed values: `None`, `Cobertura`, `JaCoCo`. Default value: `None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the code coverage tool.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilter"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageClassFilter`** - **Class Inclusion/Exclusion Filters**<br>
[Input alias](index.md#what-are-task-input-aliases): `classFilter`. `string`. Optional. Use when `codeCoverageTool != None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a comma-separated list of filters to include or exclude classes from collecting code coverage. For example, `+:com.*,+:org.*,-:my.app*.*`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilesDirectories"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageClassFilesDirectories`** - **Class Files Directories**<br>
[Input alias](index.md#what-are-task-input-aliases): `classFilesDirectories`. `string`. Optional. Use when `codeCoverageTool = JaCoCo`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This field is required for a multi-module project.  
Specifies a comma-separated list of relative paths from the Maven POM file to the directories containing class files and archive files (JAR, WAR, etc.). Code coverage is reported for class files in these directories. For example, `target/classes,target/testClasses`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageSourceDirectories"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageSourceDirectories`** - **Source Files Directories**<br>
[Input alias](index.md#what-are-task-input-aliases): `srcDirectories`. `string`. Optional. Use when `codeCoverageTool = JaCoCo`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This field is required for a multi-module project.  
Specifies a comma-separated list of relative paths from the Maven POM file to source code directories. Code coverage reports will use these to highlight source code. For example, `src/java,src/Test`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageFailIfEmpty"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageFailIfEmpty`** - **Fail When Code Coverage Results Are Missing**<br>
[Input alias](index.md#what-are-task-input-aliases): `failIfCoverageEmpty`. `boolean`. Optional. Use when `codeCoverageTool != None`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fails the build if code coverage did not produce any results to publish.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="javaHomeOption"::: -->
:::moniker range="<=azure-pipelines"

**`javaHomeOption`** - **Set JAVA_HOME by**<br>
[Input alias](index.md#what-are-task-input-aliases): `javaHomeSelection`. `string`. Required. Allowed values: `JDKVersion` (JDK Version), `Path`. Default value: `JDKVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets `JAVA_HOME` either by selecting a JDK version that will be discovered during builds or by manually entering a JDK path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkVersionOption"::: -->
:::moniker range="<=azure-pipelines"

**`jdkVersionOption`** - **JDK Version**<br>
[Input alias](index.md#what-are-task-input-aliases): `jdkVersion`. `string`. Optional. Use when `javaHomeSelection = JDKVersion`. Allowed values: `default`, `1.9` (JDK 9), `1.8` (JDK 8), `1.7` (JDK 7), `1.6` (JDK 6). Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Attempts to discover the path to the selected JDK version, and sets `JAVA_HOME` accordingly.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`jdkDirectory`** - **JDK Path**<br>
[Input alias](index.md#what-are-task-input-aliases): `jdkUserInputPath`. `string`. Required when `javaHomeSelection = Path`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets `JAVA_HOME` to the given path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkArchitectureOption"::: -->
:::moniker range="<=azure-pipelines"

**`jdkArchitectureOption`** - **JDK Architecture**<br>
[Input alias](index.md#what-are-task-input-aliases): `jdkArchitecture`. `string`. Optional. Use when `jdkVersion != default`. Allowed values: `x86`, `x64`. Default value: `x64`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Supplies the architecture (`x86`, `x64`) of the JDK.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenVersionOption"::: -->
:::moniker range="<=azure-pipelines"

**`mavenVersionOption`** - **Maven Version**<br>
[Input alias](index.md#what-are-task-input-aliases): `mavenVersionSelection`. `string`. Required. Allowed values: `Default`, `Path` (Custom Path). Default value: `Default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uses either the default Maven version or the version in the specified custom path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`mavenDirectory`** - **Maven Path**<br>
[Input alias](index.md#what-are-task-input-aliases): `mavenPath`. `string`. Required when `mavenVersionSelection = Path`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Supplies the custom path to the Maven installation (for example: `/usr/share/maven`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenSetM2Home"::: -->
:::moniker range="<=azure-pipelines"

**`mavenSetM2Home`** - **Set M2_HOME variable**<br>
`boolean`. Optional. Use when `mavenVersionSelection = Path`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets the `M2_HOME` variable to a custom Maven installation path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenOptions"::: -->
:::moniker range="<=azure-pipelines"

**`mavenOptions`** - **Set MAVEN_OPTS to**<br>
[Input alias](index.md#what-are-task-input-aliases): `mavenOpts`. `string`. Default value: `-Xmx1024m`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets the `MAVEN_OPTS` environment variable, which is used to send command-line arguments to start the JVM. The `-Xmx` flag specifies the maximum memory available to the JVM.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenAuthenticateFeed"::: -->
:::moniker range="<=azure-pipelines"

**`mavenAuthenticateFeed`** - **Authenticate built-in Maven feeds**<br>
[Input alias](index.md#what-are-task-input-aliases): `mavenFeedAuthenticate`. `boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Automatically authenticates with Azure Artifacts feeds. If Artifacts feeds are not in use, deselect this option for faster builds.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeRunAnalysis"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeRunAnalysis`** - **Run SonarQube Analysis**<br>
[Input alias](index.md#what-are-task-input-aliases): `sqAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs a [SonarQube analysis](https://go.microsoft.com/fwlink/?LinkID=708598) after executing the current goals. `install` or `package` goals should be executed first.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeServiceEndpoint"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeServiceEndpoint`** - **SonarQube Endpoint**<br>
[Input alias](index.md#what-are-task-input-aliases): `sqConnectedServiceName`. `string`. Required when `sqAnalysisEnabled = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SonarQube server generic endpoint.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeProjectName"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeProjectName`** - **SonarQube Project Name**<br>
[Input alias](index.md#what-are-task-input-aliases): `sqProjectName`. `string`. Optional. Use when `sqAnalysisEnabled = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SonarQube project name, for example `sonar.projectName`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeProjectKey"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeProjectKey`** - **SonarQube Project Key**<br>
[Input alias](index.md#what-are-task-input-aliases): `sqProjectKey`. `string`. Optional. Use when `sqAnalysisEnabled = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SonarQube project unique key, for example `sonar.projectKey`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeProjectVersion"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeProjectVersion`** - **SonarQube Project Version**<br>
[Input alias](index.md#what-are-task-input-aliases): `sqProjectVersion`. `string`. Optional. Use when `sqAnalysisEnabled = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SonarQube project version, for example `sonar.projectVersion`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeSpecifyDB"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeSpecifyDB`** - **The SonarQube server version is lower than 5.2**<br>
[Input alias](index.md#what-are-task-input-aliases): `sqDbDetailsRequired`. `boolean`. Optional. Use when `sqAnalysisEnabled = true`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If using a SonarQube server 5.1 or lower, you must specify the database connection details.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeDBUrl"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeDBUrl`** - **Db Connection String**<br>
[Input alias](index.md#what-are-task-input-aliases): `sqDbUrl`. `string`. Optional. Use when `sqDbDetailsRequired = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use for SonarQube server 5.1 and lower only.  
Specifies the database connection setting (for example, `sonar.jdbc.url` or `jdbc:jtds:sqlserver://localhost/sonar;SelectMethod=Cursor`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeDBUsername"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeDBUsername`** - **Db Username**<br>
[Input alias](index.md#what-are-task-input-aliases): `sqDbUsername`. `string`. Optional. Use when `sqDbDetailsRequired = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use for SonarQube server 5.1 and lower only.  
Specifies the username for the database user (for example, `sonar.jdbc.username`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeDBPassword"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeDBPassword`** - **Db User Password**<br>
[Input alias](index.md#what-are-task-input-aliases): `sqDbPassword`. `string`. Optional. Use when `sqDbDetailsRequired = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use for SonarQube server 5.1 and lower only.  
Specifies the password for the database user (for example, `sonar.jdbc.password`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeIncludeFullReport"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeIncludeFullReport`** - **Include full analysis report in the build summary (SQ 5.3+)**<br>
[Input alias](index.md#what-are-task-input-aliases): `sqAnalysisIncludeFullReport`. `boolean`. Optional. Use when `sqAnalysisEnabled = true`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This option will delay the build until the SonarQube analysis is completed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeFailWhenQualityGateFails"::: -->
:::moniker range="<=azure-pipelines"

**`sonarQubeFailWhenQualityGateFails`** - **Fail the build on quality gate failure (SQ 5.3+)**<br>
[Input alias](index.md#what-are-task-input-aliases): `sqAnalysisBreakBuildIfQualityGateFailed`. `boolean`. Optional. Use when `sqAnalysisEnabled = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This option is only available when using a SonarQube server 5.3 or above. Introduces delays, as the build must wait for SonarQube to complete the analysis. More information about [SonarQube quality gates](https://devblogs.microsoft.com/devops/use-sonarqube-quality-gates-to-control-your-visual-studio-team-services-builds/).
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
<!-- :::item name="pmdRunAnalysis"::: -->
:::moniker range="<=azure-pipelines"

**`pmdRunAnalysis`** - **Run PMD**<br>
[Input alias](index.md#what-are-task-input-aliases): `pmdAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uses the PMD static analysis tool to look for bugs in the code. Results are uploaded as build artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="findBugsRunAnalysis"::: -->
:::moniker range="<=azure-pipelines"

**`findBugsRunAnalysis`** - **Run FindBugs**<br>
[Input alias](index.md#what-are-task-input-aliases): `findbugsAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uses the FindBugs static analysis tool to look for bugs in the code. Results are uploaded as build artifacts.
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
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: maven |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.89.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Maven authenticate](maven-authenticate-v0.md)
- [Publish Maven artifacts with Azure Pipelines](/azure/devops/pipelines/artifacts/publish-maven-artifacts)
- [Java Tool Installer](java-tool-installer-v0.md)
- [Build Java apps](/azure/devops/pipelines/ecosystems/java)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
