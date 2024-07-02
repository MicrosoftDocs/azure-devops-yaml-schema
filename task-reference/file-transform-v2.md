---
title: FileTransform@2 - File transform v2 task
description: Replace tokens with variable values in XML or JSON configuration files.
ms.date: 07/02/2024
monikerRange: ">=azure-pipelines-2020"
---

# FileTransform@2 - File transform v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Use this task to replace tokens with variable values in XML or JSON configuration files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020"

```yaml
# File transform v2
# Replace tokens with variable values in XML or JSON configuration files.
- task: FileTransform@2
  inputs:
    folderPath: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #xmlTransformationRules: '-transform **\*.Release.config -xml **\*.config' # string. XML Transformation rules. Default: -transform **\*.Release.config -xml **\*.config.
  # Variable Substitution
    #jsonTargetFiles: # string. JSON target files. 
    #xmlTargetFiles: # string. XML target files.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="folderPath"::: -->
:::moniker range=">=azure-pipelines-2020"

**`folderPath`** - **Package or folder**<br>
`string`. Required. Default value: `$(System.DefaultWorkingDirectory)/**/*.zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File path to the package or a folder.

Variables are [Build](/azure/devops/pipelines/build/variables) and [Release](/azure/devops/pipelines/release/variables#default-variables). Wildcards are supported. 

For example, `$(System.DefaultWorkingDirectory)/**/*.zip`. For zipped folders, the contents are extracted to the TEMP location, transformations executed, and the results zipped in original artifact location.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xmlTransformationRules"::: -->
:::moniker range=">=azure-pipelines-2020"

**`xmlTransformationRules`** - **XML Transformation rules**<br>
`string`. Default value: `-transform **\*.Release.config -xml **\*.config`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a newline-separated list of transformation file rules using the syntax:
`-transform <pathToTransformFile>  -xml <pathToSourceConfigurationFile>`. The result file path is optional, and if not specified, the source configuration file will be replaced with the transformed result file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jsonTargetFiles"::: -->
:::moniker range=">=azure-pipelines-2020"

**`jsonTargetFiles`** - **JSON target files**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a newline-separated list of files to substitute the variable values. File names are to be provided relative to the root folder.

For example, to replace the value of `ConnectionString` in the sample below, you need to define a variable as `Data.DefaultConnection.ConnectionString` in the build or release pipeline (or release pipeline's environment). 

```json
{
  "Data": {
    "DefaultConnection": {
      "ConnectionString": "Server=(localdb)\SQLEXPRESS;Database=MyDB;Trusted_Connection=True"
    }
  }
}
```

 Variable Substitution is run after configuration transforms. 


Note: Only custom variables that are defined in build/release pipelines are used in substitution. Default/system defined pipeline variables are excluded. If the same variables are defined in the release pipeline and in the stage, then the stage variables will supersede the release pipeline variables.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xmlTargetFiles"::: -->
:::moniker range=">=azure-pipelines-2020"

**`xmlTargetFiles`** - **XML target files**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a newline-separated list of files to substitute the variable values. File names are to be provided relative to the root folder.

For XML, Variables defined in the build or release pipelines will be matched against the `key` or `name` entries in the `appSettings`, `applicationSettings`, and `connectionStrings` sections of any config file and `parameters.xml`.

Variable Substitution is run after configuration transforms.

Note: Only custom variables defined in build/release pipelines are used in substitution. Default/system defined pipeline variables are excluded. If the same variables are defined in the release pipeline and in the stage, then the stage variables will supersede the release pipeline variables.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2020"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

What's new in File Transform version 2:

* More optimized task fields that allow users to enable any/all of the transformation (XML), variable substitution (JSON and XML) features in a single task instance.
* Task fails when any of the configured transformation/substitution is NOT applied or when the task is no-op.

Use this task to apply file transformations and variable substitutions on configuration and parameters files.
For details of how translations are processed, see [File transforms and variable substitution reference](/azure/devops/pipelines/tasks/transforms-variable-substitution).

> [!IMPORTANT]
> This task is intended for web packages and requires a web package file. It does not work on standalone JSON files.

### File transformations

* At present, file transformations are supported for only XML files.
* To apply an XML transformation to configuration files (*.config) you must specify a newline-separated list of transformation file rules using the syntax:`-t ransform <path to the transform file> -xml <path to the source file> -result <path to the result file>`
* File transformations are useful in many scenarios, particularly when you are deploying to an App service and want to add,
  remove or modify configurations for different environments (such as Dev, Test, or Prod) by following the standard
  [Web.config Transformation Syntax](/aspnet/web-forms/overview/deployment/visual-studio-web-deployment/web-config-transformations).
* You can also use this functionality to transform other files, including Console or Windows service application configuration files
  (for example, `FabrikamService.exe.config`).
* Config file transformations are run before variable substitutions.

### Variable substitution

* At present only XML and JSON file formats are supported for variable substitution.
* Tokens defined in the target configuration files are updated and then replaced with variable values.
* Variable substitutions are run after config file transformations.
* Variable substitution is applied for only the JSON keys predefined in the object hierarchy. It does not create new keys.

> [!NOTE]
> Only custom variables defined in build and release pipelines are used in substitution. Default and system pipeline variables are excluded.
>
> Here's a list of currently excluded prefixes:
> * `agent.`
> * `azure_http_user_agent`
> * `build.`
> * `common.`
> * `release.`
> * `system.`
> * `tf_`
> 
> If the same variables are defined in both the release pipeline and in a stage, the stage-defined variables supersede the pipeline-defined variables.

See also: [File transforms and variable substitution reference](/azure/devops/pipelines/tasks/transforms-variable-substitution).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

If you need XML transformation to run on all the configuration files named with pattern `.Production.config`,
the transformation rule should be specified as:

`-transform **\*.Production.config  -xml **\*.config`

If you have a configuration file named based on the stage name in your pipeline, you can use:

`-transform **\*.$(Release.EnvironmentName).config -xml **\*.config`

To substitute JSON variables that are nested or hierarchical, specify them using JSONPath expressions.
For example, to replace the value of **ConnectionString** in the sample below, you must define a variable
as `Data.DefaultConnection.ConnectionString` in the build or release pipeline (or in a stage within the release pipeline). 

```
{
  "Data": {
    "DefaultConnection": {
      "ConnectionString": "Server=(localdb)\SQLEXPRESS;Database=MyDB;Trusted_Connection=True"
    }
  }
}
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2020"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [File transforms and variable substitution reference](/azure/devops/pipelines/tasks/transforms-variable-substitution)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
