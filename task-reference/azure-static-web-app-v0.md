---
title: AzureStaticWebApp@0 - Deploy Azure Static Web App v0 task
description: Build and deploy an Azure Static Web App.
ms.date: 03/28/2025
monikerRange: ">=azure-pipelines-2022"
author: juliakm
ms.author: jukullam
---

# AzureStaticWebApp@0 - Deploy Azure Static Web App v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::editable-content name="description"::: -->
This task builds and deploys an Azure Static Web app.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.1"

```yaml
# Deploy Azure Static Web App v0
# Build and deploy an Azure Static Web App.
- task: AzureStaticWebApp@0
  inputs:
    #workingDirectory: '$(System.DefaultWorkingDirectory)' # string. Alias: cwd | rootDirectory. Working directory. Default: $(System.DefaultWorkingDirectory).
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
    #data_api_location: # string. Data api location.
```

:::moniker-end

:::moniker range="=azure-pipelines-2022"

```yaml
# Deploy Azure Static Web App v0
# Build and deploy an Azure Static Web App.
- task: AzureStaticWebApp@0
  inputs:
    #workingDirectory: '$(System.DefaultWorkingDirectory)' # string. Alias: cwd | rootDirectory. Working directory. Default: $(System.DefaultWorkingDirectory).
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
[Input alias](index.md#what-are-task-input-aliases): `cwd | rootDirectory`. `string`. Default value: `$(System.DefaultWorkingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the absolute working directory in which to execute this task. If left empty, the default working directory is used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="app_location"::: -->
:::moniker range=">=azure-pipelines-2022"

**`app_location`** - **App location**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The directory location of the application source code, relative to the working directory. When used with `skip_app_build: true`, this value is the app's build output location.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="app_build_command"::: -->
:::moniker range=">=azure-pipelines-2022"

**`app_build_command`** - **App build command**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The custom command used to run Oryx when building application source code.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="output_location"::: -->
:::moniker range=">=azure-pipelines-2022"

**`output_location`** - **Output location**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The directory location of the compiled application code after building is complete, relative to the working directory. Set this an empty string (`''`) when bypassing automatic build and only deploy is required.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="api_location"::: -->
:::moniker range=">=azure-pipelines-2022"

**`api_location`** - **Api location**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The directory location of the Azure Functions source code, relative to the working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="api_build_command"::: -->
:::moniker range=">=azure-pipelines-2022"

**`api_build_command`** - **Api build command**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The custom command used to run Oryx when building Azure Functions source code.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="routes_location"::: -->
:::moniker range=">=azure-pipelines-2022"

**`routes_location`** - **Routes location**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The directory location of the routes.json file, relative to the working directory.  
*Note:* Routes.json is deprecated. Use staticwebapp.config.json.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="config_file_location"::: -->
:::moniker range=">=azure-pipelines-2022"

**`config_file_location`** - **Config file location**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The directory location of the staticwebapp.config.json file, relative to the working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skip_app_build"::: -->
:::moniker range=">=azure-pipelines-2022"

**`skip_app_build`** - **Skip app build**<br>
`boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Skips Oryx build for the app folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="skip_api_build"::: -->
:::moniker range=">=azure-pipelines-2022"

**`skip_api_build`** - **Skip api build**<br>
`boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Skips Oryx build for the API folder.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="is_static_export"::: -->
:::moniker range=">=azure-pipelines-2022"

**`is_static_export`** - **Set static export**<br>
`boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set this flag to `true` when your application is configured to export to static HTML, like when using `next export`.

When this flag is set to `true`
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
Specifies the time limit of the Oryx app folder build in minutes.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azure_static_web_apps_api_token"::: -->
:::moniker range=">=azure-pipelines-2022"

**`azure_static_web_apps_api_token`** - **Azure Static Web Apps api token**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the API token for deployment.  
*Note:* Not required if passed as an environment variable.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deployment_environment"::: -->
:::moniker range=">=azure-pipelines-2022"

**`deployment_environment`** - **Deployment Environment**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the environment to deploy to. Leave blank for the production environment. This input takes precedence over the production branch.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="production_branch"::: -->
:::moniker range=">=azure-pipelines-2022"

**`production_branch`** - **Production Branch**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the production branch. When defined, and the deployment environment is empty, deployments from other branches will be preview environments.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="data_api_location"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`data_api_location`** - **Data api location**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Directory location of the Data API source files relative to working directory.
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

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="AZURESTATICWEBAPP_STATIC_WEB_APP_URL"::: -->
**`AZURESTATICWEBAPP_STATIC_WEB_APP_URL`**<br><!-- :::editable-content name="Value"::: -->
URL of the Static Web App after a successful deployment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

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

### Skip building front-end app and run only deploy
```YAML

trigger:
- main

pool:
  vmImage: ubuntu-latest

steps:
  - task: NodeTool@0
    inputs:
      versionSpec: '20.x'
    displayName: 'Install Node.js'

  - script: |
      npm ci
      npm run build
    displayName: 'dependencies install and distribution build'

- task: AzureStaticWebApp@0
  inputs:
    app_location : '/dist'
    output_location: '' # Leave this empty
    skip_app_build: true
    skip_api_build: true
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
