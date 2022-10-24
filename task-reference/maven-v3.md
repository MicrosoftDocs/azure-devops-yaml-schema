---
title: Maven@3 - Maven v3 task
description: Build, test, and deploy with Apache Maven.
ms.date: 10/21/2022
monikerRange: ">=azure-pipelines-2019"
---

# Maven@3 - Maven v3 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Build, test, and deploy with Apache Maven.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Build with Apache Maven.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Maven v3
# Build, test, and deploy with Apache Maven.
- task: Maven@3
  inputs:
    mavenPOMFile: 'pom.xml' # string. Required. Maven POM file. Default: pom.xml.
    #goals: 'package' # string. Goal(s). Default: package.
    #options: # string. Options. 
  # JUnit Test Results
    publishJUnitResults: true # boolean. Required. Publish to Azure Pipelines. Default: true.
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
    #mavenSetM2Home: false # boolean. Required when mavenVersionSelection = Path. Set M2_HOME variable. Default: false.
    #mavenOptions: '-Xmx1024m' # string. Alias: mavenOpts. Set MAVEN_OPTS to. Default: -Xmx1024m.
    mavenAuthenticateFeed: false # boolean. Alias: mavenFeedAuthenticate. Required. Authenticate built-in Maven feeds. Default: false.
    effectivePomSkip: false # boolean. Alias: skipEffectivePom. Required. Skip generating effective POM while authenticating built-in feeds. Default: false.
  # Code Analysis
    sonarQubeRunAnalysis: false # boolean. Alias: sqAnalysisEnabled. Required. Run SonarQube or SonarCloud analysis. Default: false.
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

:::moniker range="=azure-pipelines-2020.1"

```yaml
# Maven v3
# Build, test, and deploy with Apache Maven.
- task: Maven@3
  inputs:
    mavenPOMFile: 'pom.xml' # string. Required. Maven POM file. Default: pom.xml.
    #goals: 'package' # string. Goal(s). Default: package.
    #options: # string. Options. 
  # JUnit Test Results
    publishJUnitResults: true # boolean. Required. Publish to Azure Pipelines. Default: true.
    testResultsFiles: '**/surefire-reports/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: **/surefire-reports/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
  # Code Coverage
    #codeCoverageToolOption: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code coverage tool. Default: None.
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageClassFilesDirectories: # string. Alias: classFilesDirectories. Optional. Use when codeCoverageTool = JaCoCo. Class files directories. 
    #codeCoverageSourceDirectories: # string. Alias: srcDirectories. Optional. Use when codeCoverageTool = JaCoCo. Source files directories. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
    #codeCoverageRestoreOriginalPomXml: false # boolean. Alias: restoreOriginalPomXml. Optional. Use when codeCoverageTool != None. Restore original pom.xml after task execution. Default: false.
  # Advanced
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
    mavenVersionOption: 'Default' # 'Default' | 'Path'. Alias: mavenVersionSelection. Required. Maven version. Default: Default.
    #mavenDirectory: # string. Alias: mavenPath. Required when mavenVersionSelection = Path. Maven path. 
    #mavenSetM2Home: false # boolean. Required when mavenVersionSelection = Path. Set M2_HOME variable. Default: false.
    #mavenOptions: '-Xmx1024m' # string. Alias: mavenOpts. Set MAVEN_OPTS to. Default: -Xmx1024m.
    mavenAuthenticateFeed: false # boolean. Alias: mavenFeedAuthenticate. Required. Authenticate built-in Maven feeds. Default: false.
    effectivePomSkip: false # boolean. Alias: skipEffectivePom. Required. Skip generating effective POM while authenticating built-in feeds. Default: false.
  # Code Analysis
    sonarQubeRunAnalysis: false # boolean. Alias: sqAnalysisEnabled. Required. Run SonarQube or SonarCloud analysis. Default: false.
    #isJacocoCoverageReportXML: false # boolean. Optional. Use when sqAnalysisEnabled = true && codeCoverageTool = JaCoCo. Use XML Jacoco reports for SonarQube analysis. Default: false.
    #sqMavenPluginVersionChoice: 'latest' # 'latest' | 'pom'. Required when sqAnalysisEnabled = true. SonarQube scanner for Maven version. Default: latest.
    #checkStyleRunAnalysis: false # boolean. Alias: checkstyleAnalysisEnabled. Run Checkstyle. Default: false.
    #pmdRunAnalysis: false # boolean. Alias: pmdAnalysisEnabled. Run PMD. Default: false.
    #findBugsRunAnalysis: false # boolean. Alias: findbugsAnalysisEnabled. Run FindBugs. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Maven v3
# Build, test, and deploy with Apache Maven.
- task: Maven@3
  inputs:
    mavenPOMFile: 'pom.xml' # string. Required. Maven POM file. Default: pom.xml.
    #goals: 'package' # string. Goal(s). Default: package.
    #options: # string. Options. 
  # JUnit Test Results
    publishJUnitResults: true # boolean. Required. Publish to Azure Pipelines. Default: true.
    testResultsFiles: '**/surefire-reports/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: **/surefire-reports/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
  # Code Coverage
    #codeCoverageToolOption: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code coverage tool. Default: None.
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageClassFilesDirectories: # string. Alias: classFilesDirectories. Optional. Use when codeCoverageTool = JaCoCo. Class files directories. 
    #codeCoverageSourceDirectories: # string. Alias: srcDirectories. Optional. Use when codeCoverageTool = JaCoCo. Source files directories. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
  # Advanced
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
    mavenVersionOption: 'Default' # 'Default' | 'Path'. Alias: mavenVersionSelection. Required. Maven version. Default: Default.
    #mavenDirectory: # string. Alias: mavenPath. Required when mavenVersionSelection = Path. Maven path. 
    #mavenSetM2Home: false # boolean. Required when mavenVersionSelection = Path. Set M2_HOME variable. Default: false.
    #mavenOptions: '-Xmx1024m' # string. Alias: mavenOpts. Set MAVEN_OPTS to. Default: -Xmx1024m.
    mavenAuthenticateFeed: false # boolean. Alias: mavenFeedAuthenticate. Required. Authenticate built-in Maven feeds. Default: false.
    effectivePomSkip: false # boolean. Alias: skipEffectivePom. Required. Skip generating effective POM while authenticating built-in feeds. Default: false.
  # Code Analysis
    sonarQubeRunAnalysis: false # boolean. Alias: sqAnalysisEnabled. Required. Run SonarQube or SonarCloud analysis. Default: false.
    #sqMavenPluginVersionChoice: 'latest' # 'latest' | 'pom'. Required when sqAnalysisEnabled = true. SonarQube scanner for Maven version. Default: latest.
    #checkStyleRunAnalysis: false # boolean. Alias: checkstyleAnalysisEnabled. Run Checkstyle. Default: false.
    #pmdRunAnalysis: false # boolean. Alias: pmdAnalysisEnabled. Run PMD. Default: false.
    #findBugsRunAnalysis: false # boolean. Alias: findbugsAnalysisEnabled. Run FindBugs. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Maven v3
# Build, test, and deploy with Apache Maven.
- task: Maven@3
  inputs:
    mavenPOMFile: 'pom.xml' # string. Required. Maven POM file. Default: pom.xml.
    #goals: 'package' # string. Goal(s). Default: package.
    #options: # string. Options. 
  # JUnit Test Results
    publishJUnitResults: true # boolean. Required. Publish to Azure Pipelines. Default: true.
    testResultsFiles: '**/surefire-reports/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: **/surefire-reports/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
  # Code Coverage
    #codeCoverageToolOption: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code coverage tool. Default: None.
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageClassFilesDirectories: # string. Alias: classFilesDirectories. Optional. Use when codeCoverageTool = JaCoCo. Class files directories. 
    #codeCoverageSourceDirectories: # string. Alias: srcDirectories. Optional. Use when codeCoverageTool = JaCoCo. Source files directories. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
  # Advanced
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
    mavenVersionOption: 'Default' # 'Default' | 'Path'. Alias: mavenVersionSelection. Required. Maven version. Default: Default.
    #mavenDirectory: # string. Alias: mavenPath. Required when mavenVersionSelection = Path. Maven path. 
    #mavenSetM2Home: false # boolean. Required when mavenVersionSelection = Path. Set M2_HOME variable. Default: false.
    #mavenOptions: '-Xmx1024m' # string. Alias: mavenOpts. Set MAVEN_OPTS to. Default: -Xmx1024m.
    mavenAuthenticateFeed: false # boolean. Alias: mavenFeedAuthenticate. Required. Authenticate built-in Maven feeds. Default: false.
  # Code Analysis
    sonarQubeRunAnalysis: false # boolean. Alias: sqAnalysisEnabled. Required. Run SonarQube or SonarCloud analysis. Default: false.
    #sqMavenPluginVersionChoice: 'latest' # 'latest' | 'pom'. Required when sqAnalysisEnabled = true. SonarQube scanner for Maven version. Default: latest.
    #checkStyleRunAnalysis: false # boolean. Alias: checkstyleAnalysisEnabled. Run Checkstyle. Default: false.
    #pmdRunAnalysis: false # boolean. Alias: pmdAnalysisEnabled. Run PMD. Default: false.
    #findBugsRunAnalysis: false # boolean. Alias: findbugsAnalysisEnabled. Run FindBugs. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Maven v3
# Build with Apache Maven.
- task: Maven@3
  inputs:
    mavenPOMFile: 'pom.xml' # string. Required. Maven POM file. Default: pom.xml.
    #goals: 'package' # string. Goal(s). Default: package.
    #options: # string. Options. 
  # JUnit Test Results
    publishJUnitResults: true # boolean. Required. Publish to Azure Pipelines/TFS. Default: true.
    testResultsFiles: '**/surefire-reports/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: **/surefire-reports/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
  # Code Coverage
    #codeCoverageToolOption: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code coverage tool. Default: None.
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageClassFilesDirectories: # string. Alias: classFilesDirectories. Optional. Use when codeCoverageTool = JaCoCo. Class files directories. 
    #codeCoverageSourceDirectories: # string. Alias: srcDirectories. Optional. Use when codeCoverageTool = JaCoCo. Source files directories. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
  # Advanced
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: default.
    #jdkDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
    mavenVersionOption: 'Default' # 'Default' | 'Path'. Alias: mavenVersionSelection. Required. Maven version. Default: Default.
    #mavenDirectory: # string. Alias: mavenPath. Required when mavenVersionSelection = Path. Maven path. 
    #mavenSetM2Home: false # boolean. Required when mavenVersionSelection = Path. Set M2_HOME variable. Default: false.
    #mavenOptions: '-Xmx1024m' # string. Alias: mavenOpts. Set MAVEN_OPTS to. Default: -Xmx1024m.
    mavenAuthenticateFeed: false # boolean. Alias: mavenFeedAuthenticate. Required. Authenticate built-in Maven feeds. Default: false.
  # Code Analysis
    sonarQubeRunAnalysis: false # boolean. Alias: sqAnalysisEnabled. Required. Run SonarQube or SonarCloud analysis. Default: false.
    #sqMavenPluginVersionChoice: 'latest' # 'latest' | 'pom'. Required when sqAnalysisEnabled = true. SonarQube scanner for Maven version. Default: latest.
    #checkStyleRunAnalysis: false # boolean. Alias: checkstyleAnalysisEnabled. Run Checkstyle. Default: false.
    #pmdRunAnalysis: false # boolean. Alias: pmdAnalysisEnabled. Run PMD. Default: false.
    #findBugsRunAnalysis: false # boolean. Alias: findbugsAnalysisEnabled. Run FindBugs. Default: false.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="mavenPOMFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`mavenPOMFile`** - **Maven POM file**<br>
`string`. Required. Default value: `pom.xml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repository root to the Maven POM file. See [Introduction to the POM](https://maven.apache.org/guides/introduction/introduction-to-the-pom.html)
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="goals"::: -->
:::moniker range=">=azure-pipelines-2019"

**`goals`** - **Goal(s)**<br>
`string`. Default value: `package`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) In most cases, set this to package to compile your code and package it into a .war file. If you leave this argument blank, the build will fail. See [Introduction to the Maven build lifecycle](https://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html)
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="options"::: -->
:::moniker range=">=azure-pipelines-2019"

**`options`** - **Options**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
(Optional) Specify any Maven command-line options you want to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`publishJUnitResults`** - **Publish to Azure Pipelines**<br>
`boolean`. Required. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish JUnit test results produced by the Maven build to Azure Pipelines. Each test results file matching `Test Results Files` will be published as a test run in Azure Pipelines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`publishJUnitResults`** - **Publish to Azure Pipelines/TFS**<br>
`boolean`. Required. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish JUnit test results produced by the Maven build to Azure Pipelines/TFS. Each test results file matching `Test Results Files` will be published as a test run in Azure Pipelines/TFS.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testResultsFiles"::: -->
:::moniker range=">=azure-pipelines-2019"

**`testResultsFiles`** - **Test results files**<br>
`string`. Required when `publishJUnitResults = true`. Default value: `**/surefire-reports/TEST-*.xml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the path and pattern of test results files to publish. Wildcards can be used ([more information](https://go.microsoft.com/fwlink/?linkid=856077)). For example, `**/TEST-*.xml` for all XML files whose name starts with `TEST-`. If no root path is specified, files are matched beneath the default working directory, the value of which is available in the variable: $(System.DefaultWorkingDirectory).  For example, a value of '**/TEST-*.xml' will actually result in matching files from '$(System.DefaultWorkingDirectory)/**/TEST-*.xml'.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range=">=azure-pipelines-2019"

**`testRunTitle`** - **Test run title**<br>
`string`. Optional. Use when `publishJUnitResults = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="allowBrokenSymlinks"::: -->
:::moniker range=">=azure-pipelines-2022"

**`allowBrokenSymlinks`** - **Allow broken symbolic links**<br>
Input alias: `allowBrokenSymbolicLinks`. `boolean`. Optional. Use when `publishJUnitResults = true`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set false to fail build when task finds broken symbolic link during publishing tests result.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageToolOption"::: -->
:::moniker range=">=azure-pipelines-2019"

**`codeCoverageToolOption`** - **Code coverage tool**<br>
Input alias: `codeCoverageTool`. `string`. Allowed values: `None`, `Cobertura`, `JaCoCo`. Default value: `None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the code coverage tool. Enabling code coverage inserts the clean goal into the Maven goals list when Maven runs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilter"::: -->
:::moniker range=">=azure-pipelines-2019"

**`codeCoverageClassFilter`** - **Class inclusion/exclusion filters**<br>
Input alias: `classFilter`. `string`. Optional. Use when `codeCoverageTool != None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of filters to include or exclude classes from collecting code coverage. For example: +:com.*,+:org.*,-:my.app*.*.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilesDirectories"::: -->
:::moniker range=">=azure-pipelines-2019"

**`codeCoverageClassFilesDirectories`** - **Class files directories**<br>
Input alias: `classFilesDirectories`. `string`. Optional. Use when `codeCoverageTool = JaCoCo`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This field is required for a multi-module project. Specify a comma-separated list of relative paths from the Maven POM file to directories containing class files and archive files (JAR, WAR, etc.). Code coverage is reported for class files in these directories. For example: target/classes,target/testClasses.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageSourceDirectories"::: -->
:::moniker range=">=azure-pipelines-2019"

**`codeCoverageSourceDirectories`** - **Source files directories**<br>
Input alias: `srcDirectories`. `string`. Optional. Use when `codeCoverageTool = JaCoCo`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This field is required for a multi-module project. Specify a comma-separated list of relative paths from the Maven POM file to source code directories. Code coverage reports will use these to highlight source code. For example: src/java,src/Test.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageFailIfEmpty"::: -->
:::moniker range=">=azure-pipelines-2019"

**`codeCoverageFailIfEmpty`** - **Fail when code coverage results are missing**<br>
Input alias: `failIfCoverageEmpty`. `boolean`. Optional. Use when `codeCoverageTool != None`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fail the build if code coverage did not produce any results to publish.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageRestoreOriginalPomXml"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`codeCoverageRestoreOriginalPomXml`** - **Restore original pom.xml after task execution**<br>
Input alias: `restoreOriginalPomXml`. `boolean`. Optional. Use when `codeCoverageTool != None`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Code coverage modifies pom.xml to produce results. Use this option if you need to keep original pom.xml.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="javaHomeOption"::: -->
:::moniker range=">=azure-pipelines-2019"

**`javaHomeOption`** - **Set JAVA_HOME by**<br>
Input alias: `javaHomeSelection`. `string`. Required. Allowed values: `JDKVersion` (JDK Version), `Path`. Default value: `JDKVersion`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets JAVA_HOME either by selecting a JDK version that will be discovered during builds or by manually entering a JDK path. Please note that if you already have java installed on agent machine - you can specify it by setting up 'javaHomeOption' as 'path', and 'jdkDirectory' - as a path to jdk installed directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkVersionOption"::: -->
:::moniker range=">=azure-pipelines-2022"

**`jdkVersionOption`** - **JDK version**<br>
Input alias: `jdkVersion`. `string`. Optional. Use when `javaHomeSelection = JDKVersion`. Allowed values: `default`, `1.17` (JDK 17), `1.11` (JDK 11), `1.10` (JDK 10 (out of support)), `1.9` (JDK 9 (out of support)), `1.8` (JDK 8), `1.7` (JDK 7), `1.6` (JDK 6 (out of support)). Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Will attempt to discover the path to the selected JDK version and set JAVA_HOME accordingly. Note: If running on an agent not hosted by Microsoft, and the requested Java version is not the one indicated by the JAVA_HOME variable set on the agent machine, the task will rely on the variable JAVA_HOME_{version}_{arch} (e.g. JAVA_HOME_8_X64), to locate the necessary JDK. Ensure this variable is set on self-hosted agents for any version and architecture of the JDK that may be requested by this parameter and/or by jdkArchitecture.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020.1"

**`jdkVersionOption`** - **JDK version**<br>
Input alias: `jdkVersion`. `string`. Optional. Use when `javaHomeSelection = JDKVersion`. Allowed values: `default`, `1.11` (JDK 11), `1.10` (JDK 10 (out of support)), `1.9` (JDK 9 (out of support)), `1.8` (JDK 8), `1.7` (JDK 7), `1.6` (JDK 6 (out of support)). Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Will attempt to discover the path to the selected JDK version and set JAVA_HOME accordingly.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`jdkDirectory`** - **JDK path**<br>
Input alias: `jdkUserInputPath`. `string`. Required when `javaHomeSelection = Path`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets JAVA_HOME to the given path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkArchitectureOption"::: -->
:::moniker range=">=azure-pipelines-2019"

**`jdkArchitectureOption`** - **JDK architecture**<br>
Input alias: `jdkArchitecture`. `string`. Optional. Use when `jdkVersion != default`. Allowed values: `x86`, `x64`. Default value: `x64`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the architecture (x86, x64) of the JDK.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenVersionOption"::: -->
:::moniker range=">=azure-pipelines-2019"

**`mavenVersionOption`** - **Maven version**<br>
Input alias: `mavenVersionSelection`. `string`. Required. Allowed values: `Default`, `Path` (Custom Path). Default value: `Default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Uses either the default Maven version or the version in the specified custom path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`mavenDirectory`** - **Maven path**<br>
Input alias: `mavenPath`. `string`. Required when `mavenVersionSelection = Path`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Supply the custom path to the Maven installation (e.g., /usr/share/maven).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenSetM2Home"::: -->
:::moniker range=">=azure-pipelines-2019"

**`mavenSetM2Home`** - **Set M2_HOME variable**<br>
`boolean`. Required when `mavenVersionSelection = Path`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets the M2_HOME variable to a custom Maven installation path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenOptions"::: -->
:::moniker range=">=azure-pipelines-2019"

**`mavenOptions`** - **Set MAVEN_OPTS to**<br>
Input alias: `mavenOpts`. `string`. Default value: `-Xmx1024m`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets the MAVEN_OPTS environment variable, which is used to send command-line arguments to start the JVM. The -Xmx flag specifies the maximum memory available to the JVM.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mavenAuthenticateFeed"::: -->
:::moniker range=">=azure-pipelines-2019"

**`mavenAuthenticateFeed`** - **Authenticate built-in Maven feeds**<br>
Input alias: `mavenFeedAuthenticate`. `boolean`. Required. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Automatically authenticate built-in Maven feeds from the Azure Artifacts/TFS [Package Management](https://marketplace.visualstudio.com/items?itemName=ms.feed) extension. If built-in Maven feeds are not in use, deselect this option for faster builds.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="effectivePomSkip"::: -->
:::moniker range=">=azure-pipelines-2020"

**`effectivePomSkip`** - **Skip generating effective POM while authenticating built-in feeds**<br>
Input alias: `skipEffectivePom`. `boolean`. Required. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Authenticate built-in Maven feeds using the POM only, allowing parent POMs in Azure Artifacts/Azure DevOps Server [Package Management] feeds.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sonarQubeRunAnalysis"::: -->
:::moniker range=">=azure-pipelines-2019"

**`sonarQubeRunAnalysis`** - **Run SonarQube or SonarCloud analysis**<br>
Input alias: `sqAnalysisEnabled`. `boolean`. Required. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This option has changed from version 1 of the **Maven** task to use the [SonarQube](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarqube) and [SonarCloud](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarcloud) marketplace extensions.  Enable this option to run [SonarQube or SonarCloud analysis](http://redirect.sonarsource.com/doc/install-configure-scanner-tfs-ts.html) after executing goals in the **Goals** field. The **install** or **package** goal should run first. You must also add a **Prepare Analysis Configuration** task from one of the extensions to the build pipeline before this Maven task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isJacocoCoverageReportXML"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`isJacocoCoverageReportXML`** - **Use XML Jacoco reports for SonarQube analysis**<br>
`boolean`. Optional. Use when `sqAnalysisEnabled = true && codeCoverageTool = JaCoCo`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use XML Jacoco reports for SonarQube analysis. [More info](https://docs.sonarqube.org/latest/analysis/coverage/).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sqMavenPluginVersionChoice"::: -->
:::moniker range=">=azure-pipelines-2019"

**`sqMavenPluginVersionChoice`** - **SonarQube scanner for Maven version**<br>
`string`. Required when `sqAnalysisEnabled = true`. Allowed values: `latest` (Use latest release), `pom` (Use version declared in your pom.xml). Default value: `latest`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The SonarQube Maven plugin version to use. You can use latest version, or rely on the version in your pom.xml.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="checkStyleRunAnalysis"::: -->
:::moniker range=">=azure-pipelines-2019"

**`checkStyleRunAnalysis`** - **Run Checkstyle**<br>
Input alias: `checkstyleAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run the Checkstyle tool with the default Sun checks. If no checkstyle configuration is specified in the pom.xml file, default Sun checks will be used. Results are uploaded as build artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pmdRunAnalysis"::: -->
:::moniker range=">=azure-pipelines-2019"

**`pmdRunAnalysis`** - **Run PMD**<br>
Input alias: `pmdAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use the PMD static analysis tool to look for bugs in the code. Results are uploaded as build artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="findBugsRunAnalysis"::: -->
:::moniker range=">=azure-pipelines-2019"

**`findBugsRunAnalysis`** - **Run FindBugs**<br>
Input alias: `findbugsAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Use the FindBugs static analysis tool to look for bugs in the code. Results are uploaded as build artifacts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="spotBugsRunAnalysis"::: -->
:::moniker range=">=azure-pipelines-2022"

**`spotBugsRunAnalysis`** - **Run SpotBugs analysis**<br>
Input alias: `spotBugsAnalysisEnabled`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enable this option to run spotBugs code analysis plugin. [More info](https://spotbugs.github.io/spotbugs-maven-plugin).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="spotBugsVersion"::: -->
:::moniker range=">=azure-pipelines-2022"

**`spotBugsVersion`** - **Version number**<br>
Input alias: `spotBugsMavenPluginVersion`. `string`. Optional. Use when `spotBugsAnalysisEnabled = true`. Default value: `4.5.3.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Refer to https://mvnrepository.com/artifact/com.github.spotbugs/spotbugs-maven-plugin for all available versions.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="spotBugsGoal"::: -->
:::moniker range=">=azure-pipelines-2022"

**`spotBugsGoal`** - **The goal for the spotbugs plugin**<br>
`string`. Optional. Use when `spotBugsAnalysisEnabled = true`. Allowed values: `spotbugs` ("spotbugs" - Creates a report on found bugs), `check` ("check" - Pipeline fails if bugs were detected). Default value: `spotbugs`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the goal of the plugin. Refer https://spotbugs.readthedocs.io/en/stable/maven.html#goals-of-spotbugs-maven-plugin to for more detailed description.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failWhenBugsFound"::: -->
:::moniker range=">=azure-pipelines-2022"

**`failWhenBugsFound`** - **Fail when bugs are found with spotbugs:check**<br>
Input alias: `spotBugsFailWhenBugsFound | sbFailWhenBugsFound`. `boolean`. Optional. Use when `spotBugsAnalysisEnabled = true && spotBugsGoal = check`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fail when the bugs found when check goal specified. Refers to https://spotbugs.github.io/spotbugs-maven-plugin/check-mojo.html#failonerror for more detailed description.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Configuration of the SonarQube analysis was moved to the [SonarQube](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarqube) or [SonarCloud](https://marketplace.visualstudio.com/items?itemName=SonarSource.sonarcloud) extensions, in task `Prepare Analysis Configuration`.

>[!IMPORTANT]
>When using the `-q` option in your MAVEN_OPTS, an effective pom won't be generated correctly and Azure Artifacts feeds may not be able to be authenticated. 

> [!IMPORTANT]
> If the JDK version you want to use is already installed on your agent, set `javaHomeOption` to `path` and set the `jdkDirectory` to the path of the JDK version. These options set the `JAVA_HOME_11_X64` environment variable which is required by the Maven task. This environment variable is set automatically if you are using the Java Tool installer task.

### FAQ

### I have a multimodule project, but my build is failing. What I should check?
Please check, that you have specify `#codeCoverageClassFilesDirectories` and `#codeCoverageSourceDirectories` as a task input. These two parameters are optional only for a single module project but are required for multi-module projects.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

* [Build and Deploy your Java application to an Azure Web App](/azure/devops/pipelines/ecosystems/java)
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019"

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

* [Maven authenticate](maven-authenticate-v0.md)
* [Build Java apps](/azure/devops/pipelines/ecosystems/java)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
