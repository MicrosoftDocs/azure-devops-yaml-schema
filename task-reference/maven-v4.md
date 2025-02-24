---
title: Maven@4 - Maven v4 task
description: Build, test, and deploy with Apache Maven.
ms.date: 02/24/2025
monikerRange: ">=azure-pipelines-2022.1"
---

# Maven@4 - Maven v4 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2022.1"

<!-- :::editable-content name="description"::: -->
Build, test, and deploy with Apache Maven.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Maven v4
# Build, test, and deploy with Apache Maven.
- task: Maven@4
  inputs:
    #azureSubscription: # string. Alias: ConnectedServiceName. Azure Resource Manager connection. 
    mavenPOMFile: 'pom.xml' # string. Required. Maven POM file. Default: pom.xml.
    #goals: 'package' # string. Goal(s). Default: package.
    #options: # string. Options. 
  # JUnit Test Results
    #publishJUnitResults: true # boolean. Publish to Azure Pipelines. Default: true.
    testResultsFiles: '**/surefire-reports/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: **/surefire-reports/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
    #allowBrokenSymlinks: true # boolean. Alias: allowBrokenSymbolicLinks. Optional. Use when publishJUnitResults = true. Allow broken symbolic links. Default: true.
  # Code Coverage
    #codeCoverageToolOption: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code coverage tool. Default: None.
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageClassFilesDirectories: # string. Alias: classFilesDirectories. Optional. Use when codeCoverageTool = JaCoCo. Class files directories. 
    #codeCoverageSourceDirectories: # string. Alias: srcDirectories. Optional. Use when codeCoverageTool = JaCoCo. Source files directories. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
    #codeCoverageRestoreOriginalPomXml: false # boolean. Alias: restoreOriginalPomXml. Optional. Use when codeCoverageTool != None. Restore original pom.xml after task execution. Default: false.
  # Advanced
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.21' | '1.17' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
    mavenVersionOption: 'Default' # 'Default' | 'Path'. Alias: mavenVersionSelection. Required. Maven version. Default: Default.
    #mavenDirectory: # string. Alias: mavenPath. Required when mavenVersionSelection = Path. Maven path. 
    #mavenSetM2Home: false # boolean. Optional. Use when mavenVersionSelection = Path. Set M2_HOME variable. Default: false.
    #mavenOptions: '-Xmx1024m' # string. Alias: mavenOpts. Set MAVEN_OPTS to. Default: -Xmx1024m.
    #mavenAuthenticateFeed: false # boolean. Alias: mavenFeedAuthenticate. Authenticate with Artifacts feeds. Default: false.
    #effectivePomSkip: false # boolean. Alias: skipEffectivePom. Skip generating effective POM while authenticating with Artifacts feeds. Default: false.
  # Code Analysis
    #sonarQubeRunAnalysis: false # boolean. Alias: sqAnalysisEnabled. Run SonarQube or SonarCloud analysis. Default: false.
    #isJacocoCoverageReportXML: false # boolean. Optional. Use when sqAnalysisEnabled = true && codeCoverageTool = JaCoCo. Use XML Jacoco reports for SonarQube analysis. Default: false.
    #sqMavenPluginVersionChoice: 'latest' # 'latest' | 'pom'. Required when sqAnalysisEnabled = true. SonarQube scanner for Maven version. Default: latest.
    #checkStyleRunAnalysis: false # boolean. Alias: checkstyleAnalysisEnabled. Run Checkstyle. Default: false.
    #pmdRunAnalysis: false # boolean. Alias: pmdAnalysisEnabled. Run PMD. Default: false.
    #findBugsRunAnalysis: false # boolean. Alias: findbugsAnalysisEnabled. Run FindBugs. Default: false.
    #spotBugsRunAnalysis: false # boolean. Alias: spotBugsAnalysisEnabled. Run SpotBugs analysis. Default: false.
    #spotBugsVersion: '4.5.3.0' # string. Alias: spotBugsMavenPluginVersion. Optional. Use when spotBugsAnalysisEnabled = true. Version number. Default: 4.5.3.0.
    #spotBugsGoal: 'spotbugs' # 'spotbugs' | 'check'. Optional. Use when spotBugsAnalysisEnabled = true. The goal for the spotbugs plugin. Default: spotbugs.
    #failWhenBugsFound: true # boolean. Alias: spotBugsFailWhenBugsFound | sbFailWhenBugsFound. Optional. Use when spotBugsAnalysisEnabled = true && spotBugsGoal = check. Fail when bugs are found with spotbugs:check. Default: true.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2022.1 <=azure-pipelines-2022.2"

```yaml
# Maven v4
# Build, test, and deploy with Apache Maven.
- task: Maven@4
  inputs:
    mavenPOMFile: 'pom.xml' # string. Required. Maven POM file. Default: pom.xml.
    #goals: 'package' # string. Goal(s). Default: package.
    #options: # string. Options. 
  # JUnit Test Results
    #publishJUnitResults: true # boolean. Publish to Azure Pipelines. Default: true.
    testResultsFiles: '**/surefire-reports/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: **/surefire-reports/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
    #allowBrokenSymlinks: true # boolean. Alias: allowBrokenSymbolicLinks. Optional. Use when publishJUnitResults = true. Allow broken symbolic links. Default: true.
  # Code Coverage
    #codeCoverageToolOption: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code coverage tool. Default: None.
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageClassFilesDirectories: # string. Alias: classFilesDirectories. Optional. Use when codeCoverageTool = JaCoCo. Class files directories. 
    #codeCoverageSourceDirectories: # string. Alias: srcDirectories. Optional. Use when codeCoverageTool = JaCoCo. Source files directories. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
    #codeCoverageRestoreOriginalPomXml: false # boolean. Alias: restoreOriginalPomXml. Optional. Use when codeCoverageTool != None. Restore original pom.xml after task execution. Default: false.
  # Advanced
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.17' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
    mavenVersionOption: 'Default' # 'Default' | 'Path'. Alias: mavenVersionSelection. Required. Maven version. Default: Default.
    #mavenDirectory: # string. Alias: mavenPath. Required when mavenVersionSelection = Path. Maven path. 
    #mavenSetM2Home: false # boolean. Optional. Use when mavenVersionSelection = Path. Set M2_HOME variable. Default: false.
    #mavenOptions: '-Xmx1024m' # string. Alias: mavenOpts. Set MAVEN_OPTS to. Default: -Xmx1024m.
    #mavenAuthenticateFeed: false # boolean. Alias: mavenFeedAuthenticate. Authenticate with Artifacts feeds. Default: false.
    #effectivePomSkip: false # boolean. Alias: skipEffectivePom. Skip generating effective POM while authenticating with Artifacts feeds. Default: false.
  # Code Analysis
    #sonarQubeRunAnalysis: false # boolean. Alias: sqAnalysisEnabled. Run SonarQube or SonarCloud analysis. Default: false.
    #isJacocoCoverageReportXML: false # boolean. Optional. Use when sqAnalysisEnabled = true && codeCoverageTool = JaCoCo. Use XML Jacoco reports for SonarQube analysis. Default: false.
    #sqMavenPluginVersionChoice: 'latest' # 'latest' | 'pom'. Required when sqAnalysisEnabled = true. SonarQube scanner for Maven version. Default: latest.
    #checkStyleRunAnalysis: false # boolean. Alias: checkstyleAnalysisEnabled. Run Checkstyle. Default: false.
    #pmdRunAnalysis: false # boolean. Alias: pmdAnalysisEnabled. Run PMD. Default: false.
    #findBugsRunAnalysis: false # boolean. Alias: findbugsAnalysisEnabled. Run FindBugs. Default: false.
    #spotBugsRunAnalysis: false # boolean. Alias: spotBugsAnalysisEnabled. Run SpotBugs analysis. Default: false.
    #spotBugsVersion: '4.5.3.0' # string. Alias: spotBugsMavenPluginVersion. Optional. Use when spotBugsAnalysisEnabled = true. Version number. Default: 4.5.3.0.
    #spotBugsGoal: 'spotbugs' # 'spotbugs' | 'check'. Optional. Use when spotBugsAnalysisEnabled = true. The goal for the spotbugs plugin. Default: spotbugs.
    #failWhenBugsFound: true # boolean. Alias: spotBugsFailWhenBugsFound | sbFailWhenBugsFound. Optional. Use when spotBugsAnalysisEnabled = true && spotBugsGoal = check. Fail when bugs are found with spotbugs:check. Default: true.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscription`** - **Azure Resource Manager connection**<br>
Input alias: `ConnectedServiceName`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify an Azure Resource Manager service connection configured with workload identity federation to use [AzurePipelinesCredential](https://devblogs.microsoft.com/azure-sdk/improve-security-posture-in-azure-service-connections-with-azurepipelinescredential/) in integration tests. For more information, see [Use AzurePipelinesCredential in integration tests](#use-azurepipelinescredential-in-integration-tests).

> [!NOTE]
> This input only supports ARM service connections that are configured to use workload identity federation.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenPOMFile"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`mavenPOMFile`** - **Maven POM file**<br>
`string`. Required. Default value: `pom.xml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the relative path from the repository root to the Maven POM file. See [Introduction to the POM](https://maven.apache.org/guides/introduction/introduction-to-the-pom.html) for more information.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="goals"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`goals`** - **Goal(s)**<br>
`string`. Default value: `package`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Set to `package` to compile your code and package it into a .war file. If you leave this argument blank, the build will fail. See [Introduction to the Maven build lifecycle](https://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html) for more information.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="options"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`options`** - **Options**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Specifies any Maven command-line options you want to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`publishJUnitResults`** - **Publish to Azure Pipelines**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the option to publish the JUnit test results produced by the Maven build to Azure Pipelines. Each test results file matching `Test Results Files` will be published as a test run in Azure Pipelines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testResultsFiles"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`testResultsFiles`** - **Test results files**<br>
`string`. Required when `publishJUnitResults = true`. Default value: `**/surefire-reports/TEST-*.xml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path and pattern of test results files to publish.  
Wildcards can be used.  
More information about [file matching patterns](/azure/devops/pipelines/tasks/file-matching-patterns).  
For example, `**/TEST-*.xml` for all XML files whose name starts with `TEST-`. If no root path is specified, files are matched beneath the default working directory, the value of which is available in the variable `$(System.DefaultWorkingDirectory)`. For example, a value of `**/TEST-*.xml` will actually result in matching files from `$(System.DefaultWorkingDirectory)/**/TEST-*.xml`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`testRunTitle`** - **Test run title**<br>
`string`. Optional. Use when `publishJUnitResults = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a name for the test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowBrokenSymlinks"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`allowBrokenSymlinks`** - **Allow broken symbolic links**<br>
Input alias: `allowBrokenSymbolicLinks`. `boolean`. Optional. Use when `publishJUnitResults = true`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `false`, fails the build when the task finds a broken symbolic link while publishing tests result.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageToolOption"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`codeCoverageToolOption`** - **Code coverage tool**<br>
Input alias: `codeCoverageTool`. `string`. Allowed values: `None`, `Cobertura`, `JaCoCo`. Default value: `None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the code coverage tool. Enabling code coverage inserts the clean goal into the Maven goals list when Maven runs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilter"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`codeCoverageClassFilter`** - **Class inclusion/exclusion filters**<br>
Input alias: `classFilter`. `string`. Optional. Use when `codeCoverageTool != None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a comma-separated list of filters to include or exclude classes from collecting code coverage. For example, `+:com.*,+:org.*,-:my.app*.*`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilesDirectories"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`codeCoverageClassFilesDirectories`** - **Class files directories**<br>
Input alias: `classFilesDirectories`. `string`. Optional. Use when `codeCoverageTool = JaCoCo`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This field is required for a multi-module project.  
Specifies a comma-separated list of relative paths from the Maven POM file to directories containing class files and archive files (JAR, WAR, etc.). Code coverage is reported for class files in these directories. For example, `target/classes,target/testClasses`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageSourceDirectories"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`codeCoverageSourceDirectories`** - **Source files directories**<br>
Input alias: `srcDirectories`. `string`. Optional. Use when `codeCoverageTool = JaCoCo`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This field is required for a multi-module project.  
Specifies a comma-separated list of relative paths from the Maven POM file to source code directories. Code coverage reports use these to highlight source code. For example, `src/java,src/Test`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageFailIfEmpty"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`codeCoverageFailIfEmpty`** - **Fail when code coverage results are missing**<br>
Input alias: `failIfCoverageEmpty`. `boolean`. Optional. Use when `codeCoverageTool != None`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fails the build if code coverage did not produce any results to publish.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageRestoreOriginalPomXml"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`codeCoverageRestoreOriginalPomXml`** - **Restore original pom.xml after task execution**<br>
Input alias: `restoreOriginalPomXml`. `boolean`. Optional. Use when `codeCoverageTool != None`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Code coverage modifies `pom.xml` to produce results. Use this option if you need to keep the original `pom.xml`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="javaHomeOption"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`javaHomeOption`** - **Set JAVA_HOME by**<br>
Input alias: `javaHomeSelection`. `string`. Required. Allowed values: `JDKVersion` (JDK Version), `Path`. Default value: `JDKVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets `JAVA_HOME` either by selecting a JDK version that will be discovered during builds or by manually entering a JDK path. If you already have Java installed on the agent machine, you can specify it by setting up `javaHomeOption` as `path` and `jdkDirectory` as a path to the JDK installed directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkVersionOption"::: -->
:::moniker range="=azure-pipelines"

**`jdkVersionOption`** - **JDK version**<br>
Input alias: `jdkVersion`. `string`. Optional. Use when `javaHomeSelection = JDKVersion`. Allowed values: `default`, `1.21` (JDK 21), `1.17` (JDK 17), `1.11` (JDK 11), `1.10` (JDK 10 (out of support)), `1.9` (JDK 9 (out of support)), `1.8` (JDK 8), `1.7` (JDK 7), `1.6` (JDK 6 (out of support)). Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Attempts to discover the path to the selected JDK version and sets `JAVA_HOME` accordingly.  
*Note:* If running on an agent that is not hosted by Microsoft, and the requested Java version is not the one indicated by the `JAVA_HOME` variable set on the agent machine, the task will rely on the variable `JAVA_HOME_{version}_{arch}` (for example: `JAVA_HOME_8_X64`) to locate the necessary JDK. Ensure this variable is set on self-hosted agents for any version and architecture of the JDK that may be requested by this parameter and/or by `jdkArchitecture`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2022.1 <=azure-pipelines-2022.2"

**`jdkVersionOption`** - **JDK version**<br>
Input alias: `jdkVersion`. `string`. Optional. Use when `javaHomeSelection = JDKVersion`. Allowed values: `default`, `1.17` (JDK 17), `1.11` (JDK 11), `1.10` (JDK 10 (out of support)), `1.9` (JDK 9 (out of support)), `1.8` (JDK 8), `1.7` (JDK 7), `1.6` (JDK 6 (out of support)). Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Attempts to discover the path to the selected JDK version and sets `JAVA_HOME` accordingly.  
*Note:* If running on an agent that is not hosted by Microsoft, and the requested Java version is not the one indicated by the `JAVA_HOME` variable set on the agent machine, the task will rely on the variable `JAVA_HOME_{version}_{arch}` (for example: `JAVA_HOME_8_X64`) to locate the necessary JDK. Ensure this variable is set on self-hosted agents for any version and architecture of the JDK that may be requested by this parameter and/or by `jdkArchitecture`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkDirectory"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`jdkDirectory`** - **JDK path**<br>
Input alias: `jdkUserInputPath`. `string`. Required when `javaHomeSelection = Path`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets `JAVA_HOME` to the given path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkArchitectureOption"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`jdkArchitectureOption`** - **JDK architecture**<br>
Input alias: `jdkArchitecture`. `string`. Optional. Use when `jdkVersion != default`. Allowed values: `x86`, `x64`. Default value: `x64`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Supplies the architecture (`x86`, `x64`) of the JDK.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenVersionOption"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`mavenVersionOption`** - **Maven version**<br>
Input alias: `mavenVersionSelection`. `string`. Required. Allowed values: `Default`, `Path` (Custom Path). Default value: `Default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies either the default Maven version or the version in the specified custom path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenDirectory"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`mavenDirectory`** - **Maven path**<br>
Input alias: `mavenPath`. `string`. Required when `mavenVersionSelection = Path`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Supplies the custom path to the Maven installation (for example: `/usr/share/maven`).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenSetM2Home"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`mavenSetM2Home`** - **Set M2_HOME variable**<br>
`boolean`. Optional. Use when `mavenVersionSelection = Path`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets the `M2_HOME` variable to a custom Maven installation path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenOptions"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`mavenOptions`** - **Set MAVEN_OPTS to**<br>
Input alias: `mavenOpts`. `string`. Default value: `-Xmx1024m`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets the `MAVEN_OPTS` environment variable, which is used to send command-line arguments to start the JVM. The `-Xmx` flag specifies the maximum memory available to the JVM.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenAuthenticateFeed"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`mavenAuthenticateFeed`** - **Authenticate with Artifacts feeds**<br>
Input alias: `mavenFeedAuthenticate`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Automatically authenticates with Azure Artifacts feeds. If Artifacts feeds are not in use, deselect this option for faster builds.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="effectivePomSkip"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`effectivePomSkip`** - **Skip generating effective POM while authenticating with Artifacts feeds**<br>
Input alias: `skipEffectivePom`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Authenticates with Artifacts feeds using the POM only.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeRunAnalysis"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`sonarQubeRunAnalysis`** - **Run SonarQube or SonarCloud analysis**<br>
Input alias: `sqAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This option has changed from using version 1 of the **Maven** task to using the [SonarQube](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarqube) and [SonarCloud](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarcloud) marketplace extensions.  
Enable this option to run [SonarQube or SonarCloud analysis](http://redirect.sonarsource.com/doc/install-configure-scanner-tfs-ts.html) after executing goals in the **Goals** field. The **install** or **package** goal should run first. Before this Maven task, you must also add a **Prepare Analysis Configuration** task from one of the extensions to the build pipeline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isJacocoCoverageReportXML"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`isJacocoCoverageReportXML`** - **Use XML Jacoco reports for SonarQube analysis**<br>
`boolean`. Optional. Use when `sqAnalysisEnabled = true && codeCoverageTool = JaCoCo`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uses XML Jacoco reports for SonarQube analysis. Learn more about [test reports](https://docs.sonarqube.org/latest/analysis/coverage/).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sqMavenPluginVersionChoice"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`sqMavenPluginVersionChoice`** - **SonarQube scanner for Maven version**<br>
`string`. Required when `sqAnalysisEnabled = true`. Allowed values: `latest` (Use latest release), `pom` (Use version declared in your pom.xml). Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SonarQube Maven plugin version to use. You can use the latest version or rely on the version in your `pom.xml`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkStyleRunAnalysis"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`checkStyleRunAnalysis`** - **Run Checkstyle**<br>
Input alias: `checkstyleAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Runs the Checkstyle tool with the default Sun checks. If no Checkstyle configuration is specified in the `pom.xml` file, default Sun checks are used. Results are uploaded as build artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pmdRunAnalysis"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`pmdRunAnalysis`** - **Run PMD**<br>
Input alias: `pmdAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uses the PMD static analysis tool to look for bugs in the code. Results are uploaded as build artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="findBugsRunAnalysis"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`findBugsRunAnalysis`** - **Run FindBugs**<br>
Input alias: `findbugsAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uses the FindBugs static analysis tool to look for bugs in the code. Results are uploaded as build artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="spotBugsRunAnalysis"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`spotBugsRunAnalysis`** - **Run SpotBugs analysis**<br>
Input alias: `spotBugsAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enable this option to run the SpotBugs code analysis plugin. More information about the [SpotBugs Maven plugin](https://spotbugs.github.io/spotbugs-maven-plugin).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="spotBugsVersion"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`spotBugsVersion`** - **Version number**<br>
Input alias: `spotBugsMavenPluginVersion`. `string`. Optional. Use when `spotBugsAnalysisEnabled = true`. Default value: `4.5.3.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Learn about [the available versions of SpotBugs](https://mvnrepository.com/artifact/com.github.spotbugs/spotbugs-maven-plugin).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="spotBugsGoal"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`spotBugsGoal`** - **The goal for the spotbugs plugin**<br>
`string`. Optional. Use when `spotBugsAnalysisEnabled = true`. Allowed values: `spotbugs` ("spotbugs" - Creates a report on found bugs), `check` ("check" - Pipeline fails if bugs were detected). Default value: `spotbugs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the goal of the plugin. Learn more about [SpotBugs goals](https://spotbugs.readthedocs.io/en/stable/maven.html#goals-of-spotbugs-maven-plugin).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failWhenBugsFound"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`failWhenBugsFound`** - **Fail when bugs are found with spotbugs:check**<br>
Input alias: `spotBugsFailWhenBugsFound | sbFailWhenBugsFound`. `boolean`. Optional. Use when `spotBugsAnalysisEnabled = true && spotBugsGoal = check`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fails when bugs are found if **Check Goal** is specified. Learn more about [SpotBug parameter details](https://spotbugs.github.io/spotbugs-maven-plugin/check-mojo.html#failonerror).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2022.1"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Configuration of the SonarQube analysis was moved to the [SonarQube](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarqube) or [SonarCloud](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarcloud) extensions in the task **Prepare Analysis Configuration**.

>[!IMPORTANT]
>When using the `-q` option in your `MAVEN_OPTS`, an effective pom won't be generated correctly, and Azure Artifacts feeds may not be able to be authenticated.

> [!IMPORTANT]
> If the JDK version you want to use is already installed on your agent, set `javaHomeOption` to `path` and set the `jdkDirectory` to the path of the JDK version. These options set the `JAVA_HOME_11_X64` environment variable, which is required by the Maven task. This environment variable is set automatically if you are using the Java Tool installer task.

:::moniker range="azure-pipelines"

[!INCLUDE [temp](includes/azure-pipeline-credential-integration-tests.md)]

:::moniker-end

### FAQ

### I have a multi-module project, but my build is failing. What should I check?

Make sure you have specified `#codeCoverageClassFilesDirectories` and `#codeCoverageSourceDirectories` as a task input. These two parameters are optional for a single module project but are required for multi-module projects.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

* [Build and Deploy your Java application to an Azure Web App](/azure/devops/pipelines/ecosystems/java).
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022.1"

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
