---
title: FileTransform@2 - File transform v2 task
description: Replace tokens with variable values in XML or JSON configuration files.
ms.date: 09/01/2022
monikerRange: ">=azure-pipelines-2020"
---

# FileTransform@2 - File transform v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Replace tokens with variable values in XML or JSON configuration files.
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
    folderPath: '$(System.DefaultWorkingDirectory)/**/*.zip' # string. Required. Package or folder. Default: '$(System.DefaultWorkingDirectory)/**/*.zip'.
    #xmlTransformationRules: '-transform **\*.Release.config -xml **\*.config' # string. XML Transformation rules. Default: '-transform **\*.Release.config -xml **\*.config'.
    #enableXmlTransform: # bool. If true then the web transforms will actually happen.  Default false
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
Type: string. Required. Default value: '$(System.DefaultWorkingDirectory)/**/*.zip'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
File path to the package or a folder.<br />Variables ( [Build](/azure/devops/pipelines/build/variables) | [Release](/azure/devops/pipelines/release/variables#default-variables)), wildcards are supported. <br/> For example, $(System.DefaultWorkingDirectory)/\*\*/\*.zip. For zipped folders, the contents are extracted to the TEMP location, transformations executed, and the results zipped in original artifact location.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xmlTransformationRules"::: -->
:::moniker range=">=azure-pipelines-2020"

**`xmlTransformationRules`** - **XML Transformation rules**<br>
Type: string. Default value: '-transform **\*.Release.config -xml **\*.config'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide new line separated list of transformation file rules using the syntax: <br/>`-transform <pathToTransformFile>  -xml <pathToSourceConfigurationFile>`. The result file path is optional and, if not specified, the source configuration file will be replaced with the transformed result file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enableXmlTransform"::: -->
:::moniker range=">=azure-pipelines-2020"

**`enableXmlTransform`** - **enableXmlTransform**<br>
Type: bool. Default value: false<br>
<!-- :::editable-content name="helpMarkDown"::: -->
When true, then the config transforms will actually take place.  If false, the transforms are discovered and processed but not actually saved to the `-xml` path specified in `xmlTransformRules`
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jsonTargetFiles"::: -->
:::moniker range=">=azure-pipelines-2020"

**`jsonTargetFiles`** - **JSON target files**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide new line separated list of files to substitute the variable values. Files names are to be provided relative to the root folder. <br/> <br/> For example, to replace the value of ‘ConnectionString’ in the sample below, you need to define a variable as ‘Data.DefaultConnection.ConnectionString’ in the build or release pipeline (or release pipeline's environment). <br/> {<br/>&nbsp;&nbsp;"Data": {<br/>&nbsp;&nbsp;&nbsp;&nbsp;"DefaultConnection": {<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"ConnectionString": "Server=(localdb)\SQLEXPRESS;Database=MyDB;Trusted_Connection=True"<br/>&nbsp;&nbsp;&nbsp;&nbsp;}<br/>&nbsp;&nbsp;}<br/> } <br/> Variable Substitution is run after configuration transforms. </br> </br> Note: Only custom variables defined in build/release pipelines are used in substitution. Default/system defined pipeline variables are excluded. <br/>Note: If same variables are defined in the release pipeline and in the stage, then the stage variables will supersede the release pipeline variables.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="xmlTargetFiles"::: -->
:::moniker range=">=azure-pipelines-2020"

**`xmlTargetFiles`** - **XML target files**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide new line separated list of files to substitute the variable values. Files names are to be provided relative to the root folder. <br/>For XML, Variables defined in the build or release pipelines will be matched against the 'key' or 'name' entries in the appSettings, applicationSettings, and connectionStrings sections of any config file and parameters.xml. <br/> Variable Substitution is run after configuration transforms. </br> Note: Only custom variables defined in build/release pipelines are used in substitution. Default/system defined pipeline variables are excluded. <br/>Note: If same variables are defined in the release pipeline and in the stage, then the stage variables will supersede the release pipeline variables.
<!-- :::editable-content-end::: -->

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

More optimized task fields that allow users to enable any/all of the transformation (XML), variable substitution (JSON and XML) features in a single task instance.</br>Task fails when any of the configured transformation/substitution is NOT applied or when the task is no-op.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
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
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
