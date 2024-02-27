---
title: SonarQubePrepare@5 - Prepare Analysis Configuration v5 task
description: Prepare SonarQube analysis configuration.
ms.date: 02/27/2024
monikerRange: "=azure-pipelines"
---

# SonarQubePrepare@5 - Prepare Analysis Configuration v5 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to prepare a SonarQube analysis configuration.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Prepare Analysis Configuration v5
# Prepare SonarQube analysis configuration.
- task: SonarQubePrepare@5
  inputs:
    SonarQube: # string. Required. SonarQube Server Endpoint. 
    scannerMode: 'MSBuild' # 'MSBuild' | 'Other' | 'CLI'. Required. Choose the way to run the analysis. Default: MSBuild.
    #configMode: 'file' # 'file' | 'manual'. Required when scannerMode = CLI. Mode. Default: file.
    #configFile: 'sonar-project.properties' # string. Optional. Use when scannerMode = CLI && configMode = file. Settings File. Default: sonar-project.properties.
    #cliProjectKey: # string. Required when scannerMode = CLI && configMode = manual. Project Key. 
    projectKey: # string. Required when scannerMode = MSBuild. Project Key. 
    #cliProjectName: # string. Optional. Use when scannerMode = CLI && configMode = manual. Project Name. 
    #projectName: # string. Optional. Use when scannerMode = MSBuild. Project Name. 
    #cliProjectVersion: '1.0' # string. Optional. Use when scannerMode = CLI && configMode = manual. Project Version. Default: 1.0.
    #projectVersion: '1.0' # string. Optional. Use when scannerMode = MSBuild. Project Version. Default: 1.0.
    #cliSources: '.' # string. Required when scannerMode = CLI && configMode = manual. Sources directory root. Default: ..
  # Advanced
    #extraProperties: # string. Additional Properties.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="SonarQube"::: -->
:::moniker range="=azure-pipelines"

**`SonarQube`** - **SonarQube Server Endpoint**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SonarQube server endpoint for your project. To create one, click the `Manage` link, create a new SonarQube Server Endpoint, and enter your server url and token.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scannerMode"::: -->
:::moniker range="=azure-pipelines"

**`scannerMode`** - **Choose the way to run the analysis**<br>
`string`. Required. Allowed values: `MSBuild` (Integrate with MSBuild), `Other` (Integrate with Maven or Gradle), `CLI` (Use standalone scanner). Default value: `MSBuild`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
**MSBuild**
- Put this task before your MSBuild task.
- Add the `Run Code Analysis` task after the MSBuild/VSTest tasks.

**Maven/Gradle**
- Put this task before the Maven/Gradle task.
- Tick the `Run SonarQube Analysis` checkbox in the Maven/Gradle task configuration.

**Others**
- For other cases, you can use the standalone scanner (sonar-scanner), set all configurations with this task, and then add the `Run Code Analysis` task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configMode"::: -->
:::moniker range="=azure-pipelines"

**`configMode`** - **Mode**<br>
`string`. Required when `scannerMode = CLI`. Allowed values: `file` (Store configuration with my source code (sonar-project.properties)), `manual` (Manually provide configuration). Default value: `file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies your preferred configuration method.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configFile"::: -->
:::moniker range="=azure-pipelines"

**`configFile`** - **Settings File**<br>
`string`. Optional. Use when `scannerMode = CLI && configMode = file`. Default value: `sonar-project.properties`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the configuration settings and project properties. Learn more about the [SonarQube Extension for Azure DevOps](http://redirect.sonarsource.com/doc/install-configure-scanner-tfs-ts.html).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cliProjectKey"::: -->
:::moniker range="=azure-pipelines"

**`cliProjectKey`** - **Project Key**<br>
`string`. Required when `scannerMode = CLI && configMode = manual`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SonarQube project unique key. For example, `sonar.projectKey`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="projectKey"::: -->
:::moniker range="=azure-pipelines"

**`projectKey`** - **Project Key**<br>
`string`. Required when `scannerMode = MSBuild`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SonarQube project unique key. For example, `sonar.projectKey`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cliProjectName"::: -->
:::moniker range="=azure-pipelines"

**`cliProjectName`** - **Project Name**<br>
`string`. Optional. Use when `scannerMode = CLI && configMode = manual`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SonarQube project name. For example, `sonar.projectName`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="projectName"::: -->
:::moniker range="=azure-pipelines"

**`projectName`** - **Project Name**<br>
`string`. Optional. Use when `scannerMode = MSBuild`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SonarQube project name. For example, `sonar.projectName`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cliProjectVersion"::: -->
:::moniker range="=azure-pipelines"

**`cliProjectVersion`** - **Project Version**<br>
`string`. Optional. Use when `scannerMode = CLI && configMode = manual`. Default value: `1.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SonarQube project version. For example, `sonar.projectVersion`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="projectVersion"::: -->
:::moniker range="=azure-pipelines"

**`projectVersion`** - **Project Version**<br>
`string`. Optional. Use when `scannerMode = MSBuild`. Default value: `1.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the SonarQube project version. For example, `sonar.projectVersion`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cliSources"::: -->
:::moniker range="=azure-pipelines"

**`cliSources`** - **Sources directory root**<br>
`string`. Required when `scannerMode = CLI && configMode = manual`. Default value: `.`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the root directory containing source files. This value is set to the `sonar.sources` SonarQube property.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="extraProperties"::: -->
:::moniker range="=azure-pipelines"

**`extraProperties`** - **Additional Properties**<br>
`string`. Default value: `# Additional properties that will be passed to the scanner, \n# Put one key=value per line, example:\n# sonar.exclusions=**/*.bin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies [additional properties](https://redirect.sonarsource.com/doc/analysis-parameters.html) to be passed to the scanner. Specify each `key=value` pair on a new line.
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
## Remarks

- **Support non-MSBuild projects:** This task can also configure analysis for non-MSBuild projects.
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
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [SonarQube Azure DevOps Integration](https://docs.sonarqube.org/latest/analysis/azuredevops-integration/)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->