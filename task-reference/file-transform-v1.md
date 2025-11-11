---
title: FileTransform@1 - File transform v1 task
description: Replace tokens with variable values in XML or JSON configuration files (task version 1).
ms.date: 11/11/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
---

# FileTransform@1 - File transform v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Use this task to replace tokens with variable values in XML or JSON configuration files.

This version of the task is deprecated; use [FileTransform@2](./file-transform-v2.md).
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
Use this task to replace tokens with variable values in XML or JSON configuration files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# File transform v1
# Replace tokens with variable values in XML or JSON configuration files.
- task: FileTransform@1
  inputs:
    folderPath: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: $(System.DefaultWorkingDirectory)/**/*.zip.
    #enableXmlTransform: false # boolean. XML transformation. Default: false.
    #xmlTransformationRules: '-transform **\*.Release.config -xml **\*.config' # string. Optional. Use when enableXmlTransform == true. Transformation rules. Default: -transform **\*.Release.config -xml **\*.config.
  # Variable Substitution
    #fileType: # 'xml' | 'json'. File format. 
    #targetFiles: # string. Optional. Use when fileType = xml || fileType = json. Target files.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="folderPath"::: -->
:::moniker range="<=azure-pipelines"

**`folderPath`** - **Package or folder**<br>
`string`. Required. Default value: `$(System.DefaultWorkingDirectory)/**/*.zip`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The file path to the package or a folder.

Variables are [Build](/azure/devops/pipelines/build/variables) and [Release](/azure/devops/pipelines/release/variables#default-variables). Wildcards are supported.

For example, `$(System.DefaultWorkingDirectory)/**/*.zip`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableXmlTransform"::: -->
:::moniker range="<=azure-pipelines"

**`enableXmlTransform`** - **XML transformation**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Config transforms will be run prior to the Variable Substitution.

XML transformations are supported only for Windows platform.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xmlTransformationRules"::: -->
:::moniker range="<=azure-pipelines"

**`xmlTransformationRules`** - **Transformation rules**<br>
`string`. Optional. Use when `enableXmlTransform == true`. Default value: `-transform **\*.Release.config -xml **\*.config`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a new line separated list of transformation file rules using the syntax:

`-transform <pathToTransformFile>  -xml <pathToSourceConfigurationFile>`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="fileType"::: -->
:::moniker range="<=azure-pipelines"

**`fileType`** - **File format**<br>
`string`. Allowed values: `xml`, `json`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides the file format on which the substitution is perfformed.

For XML, variables defined in the build or release pipelines will be matched against the `key` or `name` entries in the `appSettings`, `applicationSettings`, and `connectionStrings` sections of any config file and `parameters.xml`. `Variable Substitution` is run after config transforms.

To substitute JSON variables that are nested or hierarchical, specify them using JSONPath expressions.

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
<!-- :::item name="targetFiles"::: -->
:::moniker range="<=azure-pipelines"

**`targetFiles`** - **Target files**<br>
`string`. Optional. Use when `fileType = xml || fileType = json`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a newline-separated list of files to substitute the variable values. File names are to be provided relative to the root folder.
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
:::moniker range=">=azure-pipelines-2020"

## Remarks

There is a newer version of this task available at [FileTransform@2](./file-transform-v2.md).

:::moniker-end
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
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
