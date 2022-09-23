---
title: Ant@1 - Ant v1 task
description: Build with Apache Ant.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# Ant@1 - Ant v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Build with Apache Ant.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Ant v1
# Build with Apache Ant.
- task: Ant@1
  inputs:
    buildFile: 'build.xml' # string. Required. Ant build file. Default: 'build.xml'.
    #options: # string. Options. 
    #targets: # string. Target(s). 
  # JUnit Test Results
    publishJUnitResults: true # boolean. Required. Publish to Azure Pipelines. Default: true.
    testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: '**/TEST-*.xml'.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
  # Code Coverage
    #codeCoverageToolOptions: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Code coverage tool. Default: 'None'.
    codeCoverageClassFilesDirectories: '.' # string. Required when codeCoverageTool != None. Class files directories. Default: '.'.
    #codeCoverageClassFilter: # string. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageSourceDirectories: # string. Optional. Use when codeCoverageTool != None. Source files directories. 
    #codeCoverageFailIfEmpty: false # boolean. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
  # Advanced
    #antHomeDirectory: # string. Set ANT_HOME path. 
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Required. Set JAVA_HOME by. Default: 'JDKVersion'.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: 'default'.
    #jdkUserInputDirectory: # string. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Optional. Use when jdkVersion != default. JDK architecture. Default: 'x64'.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Ant v1
# Build with Apache Ant.
- task: Ant@1
  inputs:
    buildFile: 'build.xml' # string. Required. Ant build file. Default: 'build.xml'.
    #options: # string. Options. 
    #targets: # string. Target(s). 
  # JUnit Test Results
    publishJUnitResults: true # boolean. Required. Publish to Azure Pipelines/TFS. Default: true.
    testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: '**/TEST-*.xml'.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
  # Code Coverage
    #codeCoverageToolOptions: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Code coverage tool. Default: 'None'.
    codeCoverageClassFilesDirectories: '.' # string. Required when codeCoverageTool != None. Class files directories. Default: '.'.
    #codeCoverageClassFilter: # string. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageSourceDirectories: # string. Optional. Use when codeCoverageTool != None. Source files directories. 
    #codeCoverageFailIfEmpty: false # boolean. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
  # Advanced
    #antHomeDirectory: # string. Set ANT_HOME path. 
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Required. Set JAVA_HOME by. Default: 'JDKVersion'.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: 'default'.
    #jdkUserInputDirectory: # string. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Optional. Use when jdkVersion != default. JDK architecture. Default: 'x64'.
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

<!-- :::item name="buildFile"::: -->
:::moniker range="<=azure-pipelines"

**`buildFile`** - **Ant build file**<br>
Input alias: `antBuildFile`. Type: string. Required. Default value: 'build.xml'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path from the repository root to the Ant build file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="options"::: -->
:::moniker range="<=azure-pipelines"

**`options`** - **Options**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide any options to pass to the Ant command line. You can provide your own properties (for example, ***-DmyProperty=myPropertyValue***) and also use built-in variables (for example, ***-DcollectionId=$(system.collectionId)***). Alternatively, the built-in variables are already set as environment variables during the build and can be passed directly (for example, ***-DcollectionIdAsEnvVar=%SYSTEM_COLLECTIONID%***).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targets"::: -->
:::moniker range="<=azure-pipelines"

**`targets`** - **Target(s)**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
An optional, space-separated list of targets to build. If not specified, the `default` target will be used. If no `default` target is defined, Ant 1.6.0 and later will build all top-level tasks.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`publishJUnitResults`** - **Publish to Azure Pipelines**<br>
Type: boolean. Required. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish JUnit test results produced by the Ant build to Azure Pipelines. Each test results file matching `Test Results Files` will be published as a test run in Azure Pipelines.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`publishJUnitResults`** - **Publish to Azure Pipelines/TFS**<br>
Type: boolean. Required. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish JUnit test results produced by the Ant build to Azure Pipelines. Each test results file matching `Test Results Files` will be published as a test run in Azure Pipelines.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`publishJUnitResults`** - **Publish to TFS/Team Services**<br>
Type: boolean. Required. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish JUnit test results produced by the Ant build to TFS/Team Services. Each test results file matching `Test Results Files` will be published as a test run in TFS/Team Services.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testResultsFiles"::: -->
:::moniker range="<=azure-pipelines"

**`testResultsFiles`** - **Test results files**<br>
Type: string. Required when publishJUnitResults = true. Default value: '**/TEST-*.xml'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Test results files path. Wildcards can be used ([more information](https://go.microsoft.com/fwlink/?linkid=856077)). For example, `**/TEST-*.xml` for all XML files whose name starts with TEST-.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range="<=azure-pipelines"

**`testRunTitle`** - **Test run title**<br>
Type: string. Optional. Use when publishJUnitResults = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a name for the test run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageToolOptions"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageToolOptions`** - **Code coverage tool**<br>
Input alias: `codeCoverageTool`. Type: string. Allowed values: 'None', 'Cobertura', 'JaCoCo'. Default value: 'None'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the code coverage tool. For on-premises agent support, refer to the `More Information` link below.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilesDirectories"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageClassFilesDirectories`** - **Class files directories**<br>
Input alias: `classFilesDirectories`. Type: string. Required when codeCoverageTool != None. Default value: '.'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of relative paths from the Ant build file to directories containing class files and archive files (JAR, WAR, etc.). Code coverage is reported for class files in these directories. For example: target/classes,target/testClasses.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilter"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageClassFilter`** - **Class inclusion/exclusion filters**<br>
Input alias: `classFilter`. Type: string. Optional. Use when codeCoverageTool != None.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of filters to include or exclude classes from collecting code coverage. For example: +:com.*,+:org.*,-:my.app*.*.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageSourceDirectories"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageSourceDirectories`** - **Source files directories**<br>
Input alias: `srcDirectories`. Type: string. Optional. Use when codeCoverageTool != None.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Comma-separated list of relative paths from the Ant build file to source code directories. Code coverage reports will use these to highlight source code. For example: src/java,src/Test.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageFailIfEmpty"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageFailIfEmpty`** - **Fail when code coverage results are missing**<br>
Input alias: `failIfCoverageEmpty`. Type: boolean. Optional. Use when codeCoverageTool != None. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fail the build if code coverage did not produce any results to publish.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="antHomeDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`antHomeDirectory`** - **Set ANT_HOME path**<br>
Input alias: `antHomeUserInputPath`. Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set, overrides any existing ANT_HOME environment variable with the given path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="javaHomeOption"::: -->
:::moniker range="<=azure-pipelines"

**`javaHomeOption`** - **Set JAVA_HOME by**<br>
Input alias: `javaHomeSelection`. Type: string. Required. Allowed values: 'JDKVersion', 'Path'. Default value: 'JDKVersion'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets JAVA_HOME either by selecting a JDK version that will be discovered during builds or by manually entering a JDK path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkVersionOption"::: -->
:::moniker range=">=azure-pipelines-2019"

**`jdkVersionOption`** - **JDK version**<br>
Input alias: `jdkVersion`. Type: string. Optional. Use when javaHomeSelection = JDKVersion. Allowed values: 'default', '1.11', '1.10', '1.9', '1.8', '1.7', '1.6'. Default value: 'default'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Will attempt to discover the path to the selected JDK version and set JAVA_HOME accordingly.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`jdkVersionOption`** - **JDK version**<br>
Input alias: `jdkVersion`. Type: string. Optional. Use when javaHomeSelection = JDKVersion. Allowed values: 'default', '1.9', '1.8', '1.7', '1.6'. Default value: 'default'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Will attempt to discover the path to the selected JDK version and set JAVA_HOME accordingly.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkUserInputDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`jdkUserInputDirectory`** - **JDK path**<br>
Input alias: `jdkUserInputPath`. Type: string. Required when javaHomeSelection = Path.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets JAVA_HOME to the given path.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkArchitectureOption"::: -->
:::moniker range="<=azure-pipelines"

**`jdkArchitectureOption`** - **JDK architecture**<br>
Input alias: `jdkArchitecture`. Type: string. Optional. Use when jdkVersion != default. Allowed values: 'x86', 'x64'. Default value: 'x64'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the architecture (x86, x64) of the JDK.
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

Use this task to build with Apache Ant.
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
| [Demands](/azure/devops/pipelines/process/demands) | Self-hosted agents must have [capabilities](/azure/devops/pipelines/agents/agents#capabilities) that match the following [demands](/azure/devops/pipelines/process/demands) to run jobs that use this task: ant |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.89.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->