---
title: AzureStaticWebApp@0 - Deploy Azure Static Web App v0 task
description: Build and deploy an Azure Static Web App.
ms.date: 09/26/2022
monikerRange: ">=azure-pipelines-2022"
---

# AzureStaticWebApp@0 - Deploy Azure Static Web App v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::editable-content name="description"::: -->
Build and deploy an Azure Static Web App.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Deploy Azure Static Web App v0
# Build and deploy an Azure Static Web App.
- task: AzureStaticWebApp@0
  inputs:
    #workingDirectory: '$(System.DefaultWorkingDirectory)' # string. Working directory. Default: $(System.DefaultWorkingDirectory).
    #app_location: # string. App location. 
    #app_build_command: # string. App build command. 
    #output_location: # string. Output location. 
    #api_location: # string. Api location. 
    #api_build_command: # string. Api build command. 
    #routes_location: # string. Routes location. 
    #config_file_location: # string. Config file location. 
    #skip_app_build: # boolean. Skip app build. 
    #skip_api_build: # boolean. Skip api build. 
    #is_static_export: # boolean. Set static export. 
    #verbose: # boolean. Verbose. 
    #build_timeout_in_minutes: # string. Build timeout in minutes. 
    #azure_static_web_apps_api_token: # string. Azure Static Web Apps api token. 
    #deployment_environment: # string. Deployment Environment. 
    #production_branch: # string. Production Branch.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2022"

**`workingDirectory`** - **Working directory**<br>
Input alias: `cwd | rootDirectory`. `string`. Default value: `$(System.DefaultWorkingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the absolute working directory in which to execute this task. If left empty, the default working directory will be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="app_location"::: -->
:::moniker range=">=azure-pipelines-2022"

**`app_location`** - **App location**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Directory location of the application source code relative to working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="app_build_command"::: -->
:::moniker range=">=azure-pipelines-2022"

**`app_build_command`** - **App build command**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Custom command for Oryx to run when building application source code.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="output_location"::: -->
:::moniker range=">=azure-pipelines-2022"

**`output_location`** - **Output location**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Directory location of the compiled application code after building.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="api_location"::: -->
:::moniker range=">=azure-pipelines-2022"

**`api_location`** - **Api location**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Directory location of the Azure Functions source code relative to working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="api_build_command"::: -->
:::moniker range=">=azure-pipelines-2022"

**`api_build_command`** - **Api build command**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Custom command for Oryx to run when building Azure Functions source code.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="routes_location"::: -->
:::moniker range=">=azure-pipelines-2022"

**`routes_location`** - **Routes location**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Directory location where the routes.json file can be found, relative to working directory. Note: routes.json is deprecated, use staticwebapp.config.json.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="config_file_location"::: -->
:::moniker range=">=azure-pipelines-2022"

**`config_file_location`** - **Config file location**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Directory location where the staticwebapp.config.json file can be found, relative to working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skip_app_build"::: -->
:::moniker range=">=azure-pipelines-2022"

**`skip_app_build`** - **Skip app build**<br>
`boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Skips Oryx build for app folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skip_api_build"::: -->
:::moniker range=">=azure-pipelines-2022"

**`skip_api_build`** - **Skip api build**<br>
`boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Skips Oryx build for api folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="is_static_export"::: -->
:::moniker range=">=azure-pipelines-2022"

**`is_static_export`** - **Set static export**<br>
`boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set this flag to true when your application is configured to export to static HTML, i.e. when if you're using `next export`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="verbose"::: -->
:::moniker range=">=azure-pipelines-2022"

**`verbose`** - **Verbose**<br>
`boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enables verbose logging.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="build_timeout_in_minutes"::: -->
:::moniker range=">=azure-pipelines-2022"

**`build_timeout_in_minutes`** - **Build timeout in minutes**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Time limit of Oryx app folder build in minutes.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azure_static_web_apps_api_token"::: -->
:::moniker range=">=azure-pipelines-2022"

**`azure_static_web_apps_api_token`** - **Azure Static Web Apps api token**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Api token for deployment. Not required if passed as an environment variable.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployment_environment"::: -->
:::moniker range=">=azure-pipelines-2022"

**`deployment_environment`** - **Deployment Environment**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Environment to deploy to. Leave blank for production environment. Takes precedence over Production Branch.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="production_branch"::: -->
:::moniker range=">=azure-pipelines-2022"

**`production_branch`** - **Production Branch**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Production branch. When specified and Deployment Environment is empty, deployments from other branches will be preview environments.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2022"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
> [!NOTE]
> This task only runs on Linux agents.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```YAML

trigger:
  - main

pool:
  vmImage: ubuntu-latest

steps:
  - checkout: self
    submodules: true
  - task: AzureStaticWebApp@0
    inputs:
      app_location: '/build'
      api_location: 'api'
      output_location: '/output'
      azure_static_web_apps_api_token: $(deployment_token)
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2022"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.95.0 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->