---
title: SonarQubePrepare@7 - Prepare Analysis Configuration v7 task
description: Prepare SonarQube analysis configuration.
ms.date: 01/29/2025
monikerRange: "=azure-pipelines"
---

# SonarQubePrepare@7 - Prepare Analysis Configuration v7 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Prepare SonarQube analysis configuration.

[!INCLUDE [SonarQube Tasks note](includes/sonar-qube-tasks-note.md)]
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Prepare Analysis Configuration v7
# Prepare SonarQube Server analysis configuration.
- task: SonarQubePrepare@7
  inputs:
    SonarQube: # string. Required. SonarQube Server Endpoint. 
    scannerMode: 'dotnet' # 'dotnet' | 'cli' | 'other'. Required. Choose the way to run the analysis. Default: dotnet.
    #msBuildVersion: # string. Alias: dotnetScannerVersion. Optional. Use when scannerMode = dotnet. .NET Scanner Version. 
    #cliVersion: # string. Alias: cliScannerVersion. Optional. Use when scannerMode = cli. Scanner CLI Version. 
    #configMode: 'file' # 'file' | 'manual'. Required when scannerMode = cli. Mode. Default: file.
    #configFile: 'sonar-project.properties' # string. Optional. Use when scannerMode = cli && configMode = file. Settings File. Default: sonar-project.properties.
    #cliProjectKey: # string. Required when scannerMode = cli && configMode = manual. Project Key. 
    projectKey: # string. Required when scannerMode = dotnet. Project Key. 
    #cliProjectName: # string. Optional. Use when scannerMode = cli && configMode = manual. Project Name. 
    #projectName: # string. Optional. Use when scannerMode = dotnet. Project Name. 
    #cliProjectVersion: '1.0' # string. Optional. Use when scannerMode = cli && configMode = manual. Project Version. Default: 1.0.
    #projectVersion: '1.0' # string. Optional. Use when scannerMode = dotnet. Project Version. Default: 1.0.
    #cliSources: '.' # string. Required when scannerMode = cli && configMode = manual. Sources directory root. Default: ..
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
Select the SonarQube server endpoint for your project. To create one, click the Manage link and create a new SonarQube Server Endpoint, enter your server url and token.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="scannerMode"::: -->
:::moniker range="=azure-pipelines"

**`scannerMode`** - **Choose the way to run the analysis**<br>
`string`. Required. Allowed values: `dotnet` (Integrate with .NET), `cli` (Use standalone SonarScanner CLI), `other` (Integrate with Maven or Gradle). Default value: `dotnet`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
* `dotnet` (Integrate with .NET)
  * Put this task before your build task
  * Add the 'Run Code Analysis' task after the MSBuild/VSTest tasks
* `other` (Integrate with Maven or Gradle)
  * Put this task before the Maven/Gradle task
  * Tick the 'Run SonarQube Analysis' checkbox in the Maven/Gradle task configuration.
* `cli`
  * For other cases you can use the standalone scanner (sonar-scanner) and set all configuration with this task, and then add the 'Run Code Analysis' task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="msBuildVersion"::: -->
:::moniker range="=azure-pipelines"

**`msBuildVersion`** - **.NET Scanner Version**<br>
Input alias: `dotnetScannerVersion`. `string`. Optional. Use when `scannerMode = dotnet`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the version of the .NET Scanner to use. Versions can be located [here](https://github.com/SonarSource/sonar-scanner-msbuild/tags).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cliVersion"::: -->
:::moniker range="=azure-pipelines"

**`cliVersion`** - **Scanner CLI Version**<br>
Input alias: `cliScannerVersion`. `string`. Optional. Use when `scannerMode = cli`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the version of the CLI scanner to use. Versions can be located [here](https://github.com/SonarSource/sonar-scanner-cli/tags).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configMode"::: -->
:::moniker range="=azure-pipelines"

**`configMode`** - **Mode**<br>
`string`. Required when `scannerMode = cli`. Allowed values: `file` (Store configuration with my source code (sonar-project.properties)), `manual` (Manually provide configuration). Default value: `file`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Choose your preferred configuration method.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="configFile"::: -->
:::moniker range="=azure-pipelines"

**`configFile`** - **Settings File**<br>
`string`. Optional. Use when `scannerMode = cli && configMode = file`. Default value: `sonar-project.properties`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
More information is available [here](https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/scanners/sonarqube-extension-for-azure-devops/).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cliProjectKey"::: -->
:::moniker range="=azure-pipelines"

**`cliProjectKey`** - **Project Key**<br>
`string`. Required when `scannerMode = cli && configMode = manual`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The SonarQube project unique key, i.e. `sonar.projectKey`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="projectKey"::: -->
:::moniker range="=azure-pipelines"

**`projectKey`** - **Project Key**<br>
`string`. Required when `scannerMode = dotnet`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The SonarQube project unique key, i.e. `sonar.projectKey`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cliProjectName"::: -->
:::moniker range="=azure-pipelines"

**`cliProjectName`** - **Project Name**<br>
`string`. Optional. Use when `scannerMode = cli && configMode = manual`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The SonarQube project name, i.e. `sonar.projectName`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="projectName"::: -->
:::moniker range="=azure-pipelines"

**`projectName`** - **Project Name**<br>
`string`. Optional. Use when `scannerMode = dotnet`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The SonarQube project name, i.e. `sonar.projectName`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cliProjectVersion"::: -->
:::moniker range="=azure-pipelines"

**`cliProjectVersion`** - **Project Version**<br>
`string`. Optional. Use when `scannerMode = cli && configMode = manual`. Default value: `1.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The SonarQube project version, i.e. `sonar.projectVersion`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="projectVersion"::: -->
:::moniker range="=azure-pipelines"

**`projectVersion`** - **Project Version**<br>
`string`. Optional. Use when `scannerMode = dotnet`. Default value: `1.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The SonarQube project version, i.e. `sonar.projectVersion`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="cliSources"::: -->
:::moniker range="=azure-pipelines"

**`cliSources`** - **Sources directory root**<br>
`string`. Required when `scannerMode = cli && configMode = manual`. Default value: `.`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the root directory containing source files. This value is set to the `sonar.sources` SonarQube property.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="extraProperties"::: -->
:::moniker range="=azure-pipelines"

**`extraProperties`** - **Additional Properties**<br>
`string`. Default value: `# Additional properties that will be passed to the scanner, \n# Put one key=value per line, example:\n# sonar.exclusions=**/*.bin`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
[Additional properties](https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/analysis-parameters/) to be passed to the scanner. Specify each key=value pair on a new line.
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

[!INCLUDE [SonarQube Tasks note](includes/sonar-qube-tasks-note.md)]
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
| Agent version |  3.218.0 or greater |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->