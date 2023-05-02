---
title: AzureContainerApps@1 - Azure Container Apps Deploy v1 task
description: An Azure DevOps Task to build and deploy Azure Container Apps.
ms.date: 05/02/2023
monikerRange: "=azure-pipelines"
---

# AzureContainerApps@1 - Azure Container Apps Deploy v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
An Azure DevOps Task to build and deploy Azure Container Apps.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure Container Apps Deploy v1
# An Azure DevOps Task to build and deploy Azure Container Apps.
- task: AzureContainerApps@1
  inputs:
  # advanced
    #workingDirectory: # string. Alias: cwd. Working Directory. 
    #appSourcePath: # string. Application source path. 
    azureSubscription: # string. Alias: connectedServiceNameARM. Required. Azure Resource Manager connection. 
    #acrName: # string. Azure Container Registry name. 
    #acrUsername: # string. Azure Container Registry username. 
    #acrPassword: # string. Azure Container Registry password. 
    #dockerfilePath: # string. Dockerfile path. 
    #imageToBuild: # string. Docker image to build. 
    #imageToDeploy: # string. Docker image to deploy. 
    #containerAppName: # string. Azure Container App name. 
    #resourceGroup: # string. Azure resource group name. 
    #containerAppEnvironment: # string. Azure Container App environment. 
    #runtimeStack: # string. Application runtime stack. 
    #targetPort: # string. Application target port. 
    #location: # string. Location of the Container App. 
    #environmentVariables: # string. Environment variables. 
    #ingress: # string. Ingress setting. 
    #yamlConfigPath: # string. YAML configuration file path. 
    #disableTelemetry: # boolean. Disable telemetry.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="workingDirectory"::: -->
:::moniker range="=azure-pipelines"

**`workingDirectory`** - **Working Directory**<br>
Input alias: `cwd`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Current working directory where the script is run.  Empty is the root of the repo (build) or artifacts (release), which is $(System.DefaultWorkingDirectory).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="appSourcePath"::: -->
:::moniker range="=azure-pipelines"

**`appSourcePath`** - **Application source path**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Absolute path on the runner of the source application code to be built. If not provided, the 'imageToDeploy' argument must be provided to ensure the Container App has an image to reference.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscription`** - **Azure Resource Manager connection**<br>
Input alias: `connectedServiceNameARM`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure Resource Manager service connection for the deployment.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="acrName"::: -->
:::moniker range="=azure-pipelines"

**`acrName`** - **Azure Container Registry name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Azure Container Registry that the runnable application image will be pushed to.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="acrUsername"::: -->
:::moniker range="=azure-pipelines"

**`acrUsername`** - **Azure Container Registry username**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The username used to authenticate push requests to the provided Azure Container Registry. If not provided, an access token will be generated via 'az acr login' and provided to 'docker login' to authenticate the requests.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="acrPassword"::: -->
:::moniker range="=azure-pipelines"

**`acrPassword`** - **Azure Container Registry password**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The password used to authenticate push requests to the provided Azure Container Registry. If not provided, an access token will be generated via 'az acr login' and provided to 'docker login' to authenticate the requests.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerfilePath"::: -->
:::moniker range="=azure-pipelines"

**`dockerfilePath`** - **Dockerfile path**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Relative path to the Dockerfile in the provided application source that should be used to build the image that is then pushed to ACR and deployed to the Container App. If not provided, this task will check if there is a file named 'Dockerfile' at the root of the provided application source and use that to build the image. Otherwise, the Oryx++ Builder will be used to create the image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageToBuild"::: -->
:::moniker range="=azure-pipelines"

**`imageToBuild`** - **Docker image to build**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The custom name of the image that is to be built, pushed to ACR and deployed to the Container App by this task. Note: this image name should include the ACR server; e.g., <acr-name>.azurecr.io/<repo>:<tag>. If this argument is not provided, a default image name will be constructed in the form of `<acr-name>.azurecr.io/ado-task/container-app:<build-id>.<build-number>`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageToDeploy"::: -->
:::moniker range="=azure-pipelines"

**`imageToDeploy`** - **Docker image to deploy**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The custom name of the image that has already been pushed to ACR and will be deployed to the Container App by this task. Note: the image name should include the ACR server; e.g., <acr-name>.azurecr.io/<repo>:<tag>. If this argument is not provided, the value provided (or determined) for the 'imageToBuild' argument will be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerAppName"::: -->
:::moniker range="=azure-pipelines"

**`containerAppName`** - **Azure Container App name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Azure Container App that will be created or updated. If not provided, this value will be in the form of `ado-task-app-<build-id>-<build-number>`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroup"::: -->
:::moniker range="=azure-pipelines"

**`resourceGroup`** - **Azure resource group name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The existing resource group that the Azure Container App will be created in. If not provided, this value will be `<container-app-name>-rg` and its existence will first be checked before attempting to create it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerAppEnvironment"::: -->
:::moniker range="=azure-pipelines"

**`containerAppEnvironment`** - **Azure Container App environment**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Azure Container App environment to use with the application. If not provided, an existing environment in the resource group of the Container App will be used, otherwise, an environment will be created in the form of `<container-app-name>-env`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runtimeStack"::: -->
:::moniker range="=azure-pipelines"

**`runtimeStack`** - **Application runtime stack**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The platform version stack that the application runs in when deployed to the Azure Container App. This should be provided in the form of `<platform>:<version>`. If not provided, this value is determined by Oryx based on the contents of the provided application. Please view the following document for more information on the supported runtime stacks for Oryx: https://github.com/microsoft/Oryx/blob/main/doc/supportedRuntimeVersions.md.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targetPort"::: -->
:::moniker range="=azure-pipelines"

**`targetPort`** - **Application target port**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The designated port for the application to run on. If no value is provided and the builder is used to build the runnable application image, the target port will be set to 80 for Python applications and 8080 for all other platform applications. If no value is provided when creating a Container App, the target port will default to 80. Note: when using this task to update a Container App, the target port may be updated if not provided based on changes to the ingress property.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="location"::: -->
:::moniker range="=azure-pipelines"

**`location`** - **Location of the Container App**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The location that the Container App (and other created resources) will be deployed to.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="environmentVariables"::: -->
:::moniker range="=azure-pipelines"

**`environmentVariables`** - **Environment variables**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
A list of environment variable(s) for the container. Space-separated values in 'key=value' format. Empty string to clear existing values. Prefix value with 'secretref:' to reference a secret.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ingress"::: -->
:::moniker range="=azure-pipelines"

**`ingress`** - **Ingress setting**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Possible options: external, internal, disabled. If set to `external` (default value if not provided when creating a Container App), the Container App will be visible from the internet or a VNET, depending on the app environment endpoint configured. If set to `internal`, the Container App will be visible from within the app environment only. If set to `disabled`, ingress will be disabled for this Container App and will not have an HTTP or TCP endpoint.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="yamlConfigPath"::: -->
:::moniker range="=azure-pipelines"

**`yamlConfigPath`** - **YAML configuration file path**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Full path (on the executing Azure Pipelines agent) to the YAML file detailing the configuration of the Container App.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="disableTelemetry"::: -->
:::moniker range="=azure-pipelines"

**`disableTelemetry`** - **Disable telemetry**<br>
`boolean`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to 'true', no telemetry will be collected by this Azure DevOps Task. If set to 'false', or if this argument is not provided, telemetry will be sent to Microsoft about the Container App build and deploy scenario targeted by this Azure DevOps Task.
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
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.144.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->