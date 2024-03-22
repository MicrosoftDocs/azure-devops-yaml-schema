---
title: Ant@1 - Ant v1 task
description: Build with Apache Ant.
ms.date: 03/21/2024
monikerRange: "<=azure-pipelines"
---

# Ant@1 - Ant v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to build with Apache Ant.
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
    buildFile: 'build.xml' # string. Alias: antBuildFile. Required. Ant build file. Default: build.xml.
    #options: # string. Options. 
    #targets: # string. Target(s). 
  # JUnit Test Results
    #publishJUnitResults: true # boolean. Publish to Azure Pipelines. Default: true.
    testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: **/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
  # Code Coverage
    #codeCoverageToolOptions: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code coverage tool. Default: None.
    codeCoverageClassFilesDirectories: '.' # string. Alias: classFilesDirectories. Required when codeCoverageTool != None. Class files directories. Default: ..
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageSourceDirectories: # string. Alias: srcDirectories. Optional. Use when codeCoverageTool != None. Source files directories. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
  # Advanced
    #antHomeDirectory: # string. Alias: antHomeUserInputPath. Set ANT_HOME path. 
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: default.
    #jdkUserInputDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Ant v1
# Build with Apache Ant.
- task: Ant@1
  inputs:
    buildFile: 'build.xml' # string. Alias: antBuildFile. Required. Ant build file. Default: build.xml.
    #options: # string. Options. 
    #targets: # string. Target(s). 
  # JUnit Test Results
    #publishJUnitResults: true # boolean. Publish to Azure Pipelines/TFS. Default: true.
    testResultsFiles: '**/TEST-*.xml' # string. Required when publishJUnitResults = true. Test results files. Default: **/TEST-*.xml.
    #testRunTitle: # string. Optional. Use when publishJUnitResults = true. Test run title. 
  # Code Coverage
    #codeCoverageToolOptions: 'None' # 'None' | 'Cobertura' | 'JaCoCo'. Alias: codeCoverageTool. Code coverage tool. Default: None.
    codeCoverageClassFilesDirectories: '.' # string. Alias: classFilesDirectories. Required when codeCoverageTool != None. Class files directories. Default: ..
    #codeCoverageClassFilter: # string. Alias: classFilter. Optional. Use when codeCoverageTool != None. Class inclusion/exclusion filters. 
    #codeCoverageSourceDirectories: # string. Alias: srcDirectories. Optional. Use when codeCoverageTool != None. Source files directories. 
    #codeCoverageFailIfEmpty: false # boolean. Alias: failIfCoverageEmpty. Optional. Use when codeCoverageTool != None. Fail when code coverage results are missing. Default: false.
  # Advanced
    #antHomeDirectory: # string. Alias: antHomeUserInputPath. Set ANT_HOME path. 
    javaHomeOption: 'JDKVersion' # 'JDKVersion' | 'Path'. Alias: javaHomeSelection. Required. Set JAVA_HOME by. Default: JDKVersion.
    #jdkVersionOption: 'default' # 'default' | '1.11' | '1.10' | '1.9' | '1.8' | '1.7' | '1.6'. Alias: jdkVersion. Optional. Use when javaHomeSelection = JDKVersion. JDK version. Default: default.
    #jdkUserInputDirectory: # string. Alias: jdkUserInputPath. Required when javaHomeSelection = Path. JDK path. 
    #jdkArchitectureOption: 'x64' # 'x86' | 'x64'. Alias: jdkArchitecture. Optional. Use when jdkVersion != default. JDK architecture. Default: x64.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="buildFile"::: -->
:::moniker range="<=azure-pipelines"

**`buildFile`** - **Ant build file**<br>
Input alias: `antBuildFile`. `string`. Required. Default value: `build.xml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The relative path from the repository root to the Ant build file.

For more information about build files, see [Using Apache Ant](http://ant.apache.org/manual/using.html#buildfile).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="options"::: -->
:::moniker range="<=azure-pipelines"

**`options`** - **Options**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides options to pass to the Ant command line. You can provide your own properties (for example, `-DmyProperty=myPropertyValue`) and also use built-in variables (for example, `-DcollectionId=$(system.collectionId)`). Alternatively, the built-in variables are already set as environment variables during the build and can be passed directly (for example, `-DcollectionIdAsEnvVar=%SYSTEM_COLLECTIONID%`).

See [Running Apache Ant](http://ant.apache.org/manual/running.html#options).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targets"::: -->
:::moniker range="<=azure-pipelines"

**`targets`** - **Target(s)**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
An optional, space-separated list of targets to build. If not specified, the `default` target will be used. If no `default` target is defined, Ant 1.6.0 and later will build all top-level tasks.

See [Using Apache Ant Targets](http://ant.apache.org/manual/targets.html#targets).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="publishJUnitResults"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`publishJUnitResults`** - **Publish to Azure Pipelines**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish JUnit test results produced by the Ant build to Azure Pipelines. Each test results file matching `Test Results Files` will be published as a test run in Azure Pipelines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`publishJUnitResults`** - **Publish to Azure Pipelines/TFS**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select this option to publish JUnit test results produced by the Ant build to Azure Pipelines. Each test results file matching `Test Results Files` will be published as a test run in Azure Pipelines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end


<!-- :::item-end::: -->
<!-- :::item name="testResultsFiles"::: -->
:::moniker range="<=azure-pipelines"

**`testResultsFiles`** - **Test results files**<br>
`string`. Required when `publishJUnitResults = true`. Default value: `**/TEST-*.xml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The test results file path. Wildcards can be used. For more information, see the [file matching patterns reference](/azure/devops/pipelines/tasks/file-matching-patterns). For example, `**/TEST-*.xml` for all XML files whose name starts with `TEST-`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testRunTitle"::: -->
:::moniker range="<=azure-pipelines"

**`testRunTitle`** - **Test run title**<br>
`string`. Optional. Use when `publishJUnitResults = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a name for the test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageToolOptions"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageToolOptions`** - **Code coverage tool**<br>
Input alias: `codeCoverageTool`. `string`. Allowed values: `None`, `Cobertura`, `JaCoCo`. Default value: `None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the code coverage tool.

If you are using the [Microsoft-hosted agents](/azure/devops/pipelines/agents/hosted), then the tools are set up for you. If you are using the on-premises [Windows agent](/azure/devops/pipelines/agents/v2-windows), you must ensure the agent is set up for either JaCoco or Cobertura.

- JaCoCo - ensure that jacocoant.jar is available in the lib folder of Ant installation. Learn more about [JaCoCo Ant tasks](http://www.eclemma.org/jacoco/trunk/doc/ant.html).
- Cobertura - ensure that an environment variable COBERTURA_HOME points to the Cobertura .jar files location. Learn more about [Cobertura with Ant tasks](https://github.com/cobertura/cobertura/wiki/Ant-Task-Reference).

After you select one of these tools, the following arguments appear:
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilesDirectories"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageClassFilesDirectories`** - **Class files directories**<br>
Input alias: `classFilesDirectories`. `string`. Required when `codeCoverageTool != None`. Default value: `.`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The comma-separated list of relative paths from the Ant build file to directories containing class files and archive files (`.jar`, `.war`, etc.). Code coverage is reported for class files in these directories. For example: `target/classes,target/testClasses`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageClassFilter"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageClassFilter`** - **Class inclusion/exclusion filters**<br>
Input alias: `classFilter`. `string`. Optional. Use when `codeCoverageTool != None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The comma-separated list of filters to include or exclude classes from collecting code coverage. For example: `+:com.`, `+:org.`, `-:my.app*.`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageSourceDirectories"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageSourceDirectories`** - **Source files directories**<br>
Input alias: `srcDirectories`. `string`. Optional. Use when `codeCoverageTool != None`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The comma-separated list of relative paths from the Ant build file to source code directories. Code coverage reports will use these to highlight source code. For example: `src/java,src/Test`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="codeCoverageFailIfEmpty"::: -->
:::moniker range="<=azure-pipelines"

**`codeCoverageFailIfEmpty`** - **Fail when code coverage results are missing**<br>
Input alias: `failIfCoverageEmpty`. `boolean`. Optional. Use when `codeCoverageTool != None`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fails the build if the code coverage did not produce any results to publish.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="antHomeDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`antHomeDirectory`** - **Set ANT_HOME path**<br>
Input alias: `antHomeUserInputPath`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set, overrides any existing ANT_HOME environment variable with the given path.
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
:::moniker range=">=azure-pipelines-2019"

**`jdkVersionOption`** - **JDK version**<br>
Input alias: `jdkVersion`. `string`. Optional. Use when `javaHomeSelection = JDKVersion`. Allowed values: `default`, `1.11` (JDK 11), `1.10` (JDK 10 (out of support)), `1.9` (JDK 9 (out of support)), `1.8` (JDK 8), `1.7` (JDK 7), `1.6` (JDK 6 (out of support)). Default value: `default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Attempts to discover the path to the selected JDK version and sets JAVA_HOME accordingly.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end


<!-- :::item-end::: -->
<!-- :::item name="jdkUserInputDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`jdkUserInputDirectory`** - **JDK path**<br>
Input alias: `jdkUserInputPath`. `string`. Required when `javaHomeSelection = Path`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets JAVA_HOME to the given path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jdkArchitectureOption"::: -->
:::moniker range="<=azure-pipelines"

**`jdkArchitectureOption`** - **JDK architecture**<br>
Input alias: `jdkArchitecture`. `string`. Optional. Use when `jdkVersion != default`. Allowed values: `x86`, `x64`. Default value: `x64`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supplies the architecture (x86, x64) of the JDK.
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