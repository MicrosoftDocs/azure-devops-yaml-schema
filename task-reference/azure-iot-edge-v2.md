---
title: AzureIoTEdge@2 - Azure IoT Edge v2 task
description: Build and deploy an Azure IoT Edge image.
ms.date: 08/25/2023
monikerRange: ">=azure-pipelines-2019.1"
---

# AzureIoTEdge@2 - Azure IoT Edge v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to build and deploy images quickly and efficiently to Azure IoT Edge.

This task supports custom variables. If you're not familiar with how to use variables in Pipelines, see [define variables](/azure/devops/pipelines/process/variables).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Azure IoT Edge v2
# Build and deploy an Azure IoT Edge image.
- task: AzureIoTEdge@2
  inputs:
    action: 'Build module images' # 'Build module images' | 'Push module images' | 'Generate deployment manifest' | 'Deploy to IoT Edge devices'. Required. Action. Default: Build module images.
    #deploymentFilePath: '$(System.DefaultWorkingDirectory)/config/deployment.json' # string. Required when action == Deploy to IoT Edge devices. Deployment file. Default: $(System.DefaultWorkingDirectory)/config/deployment.json.
    #azureSubscription: # string. Alias: connectedServiceNameARM. Required when action == Deploy to IoT Edge devices. Azure subscription contains IoT Hub. 
    #iothubname: # string. Required when action == Deploy to IoT Edge devices. IoT Hub name. 
    #deviceOption: # 'Single Device' | 'Multiple Devices'. Required when action == Deploy to IoT Edge devices. Choose single/multiple device. 
    #deviceId: # string. Required when deviceOption == Single Device. IoT Edge device ID. 
    #targetcondition: # string. Required when deviceOption == Multiple Devices. IoT Edge device target condition. 
    #containerregistrytype: 'Azure Container Registry' # 'Azure Container Registry' | 'Generic Container Registry'. Required when action = Push module images. Container registry type. Default: Azure Container Registry.
    #dockerRegistryConnection: # string. Alias: dockerRegistryEndpoint. Required when containerregistrytype = Generic Container Registry. Docker Registry Connection. 
    #azureSubscriptionEndpoint: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Required when containerregistrytype = Azure Container Registry. Azure Container Registry. 
    #templateFilePath: 'deployment.template.json' # string. Required when action = Build module images || action = Push module images || action = Generate deployment manifest. .template.json file. Default: deployment.template.json.
    #defaultPlatform: 'amd64' # 'amd64' | 'windows-amd64' | 'arm32v7' | 'arm64v8'. Required when action = Build module images || action = Push module images || action = Generate deployment manifest. Default platform. Default: amd64.
    #fillRegistryCredential: 'true' # 'true' | 'false'. Required when action = Push module images. Add registry credential to deployment manifest. Default: true.
    #deploymentManifestOutputPath: '$(System.DefaultWorkingDirectory)/config/deployment.json' # string. Required when action == Generate deployment manifest. Output path. Default: $(System.DefaultWorkingDirectory)/config/deployment.json.
    #validateGeneratedDeploymentManifest: 'false' # 'true' | 'false'. Required when action = Generate deployment manifest. Validate the schema of generated deployment manifest. Default: false.
  # Advanced
    #deploymentid: '$(System.TeamProject)-devops-deployment' # string. Required when action = Deploy to IoT Edge devices. IoT Edge deployment ID. Default: $(System.TeamProject)-devops-deployment.
    #priority: '0' # string. Required when action = Deploy to IoT Edge devices. IoT Edge deployment priority. Default: 0.
  # Advanced
    #bypassModules: # string. Optional. Use when action = Push module images. Bypass module(s).
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

```yaml
# Azure IoT Edge v2
# Build and deploy an Azure IoT Edge image.
- task: AzureIoTEdge@2
  inputs:
    action: 'Build module images' # 'Build module images' | 'Push module images' | 'Generate deployment manifest' | 'Deploy to IoT Edge devices'. Required. Action. Default: Build module images.
    #deploymentFilePath: '$(System.DefaultWorkingDirectory)/config/deployment.json' # string. Required when action == Deploy to IoT Edge devices. Deployment file. Default: $(System.DefaultWorkingDirectory)/config/deployment.json.
    #azureSubscription: # string. Alias: connectedServiceNameARM. Required when action == Deploy to IoT Edge devices. Azure subscription contains IoT Hub. 
    #iothubname: # string. Required when action == Deploy to IoT Edge devices. IoT Hub name. 
    #deviceOption: # 'Single Device' | 'Multiple Devices'. Required when action == Deploy to IoT Edge devices. Choose single/multiple device. 
    #deviceId: # string. Required when deviceOption == Single Device. IoT Edge device ID. 
    #targetcondition: # string. Required when deviceOption == Multiple Devices. IoT Edge device target condition. 
    #containerregistrytype: 'Azure Container Registry' # 'Azure Container Registry' | 'Generic Container Registry'. Required when action = Push module images. Container registry type. Default: Azure Container Registry.
    #dockerRegistryConnection: # string. Alias: dockerRegistryEndpoint. Required when containerregistrytype = Generic Container Registry. Docker Registry Connection. 
    #azureSubscriptionEndpoint: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Required when containerregistrytype = Azure Container Registry. Azure Container Registry. 
    #templateFilePath: 'deployment.template.json' # string. Required when action = Build module images || action = Push module images || action = Generate deployment manifest. .template.json file. Default: deployment.template.json.
    #defaultPlatform: 'amd64' # 'amd64' | 'windows-amd64' | 'arm32v7'. Required when action = Build module images || action = Push module images || action = Generate deployment manifest. Default platform. Default: amd64.
    #fillRegistryCredential: 'true' # 'true' | 'false'. Required when action = Push module images. Add registry credential to deployment manifest. Default: true.
    #deploymentManifestOutputPath: '$(System.DefaultWorkingDirectory)/config/deployment.json' # string. Required when action == Generate deployment manifest. Output path. Default: $(System.DefaultWorkingDirectory)/config/deployment.json.
    #validateGeneratedDeploymentManifest: 'false' # 'true' | 'false'. Required when action = Generate deployment manifest. Validate the schema of generated deployment manifest. Default: false.
  # Advanced
    #deploymentid: '$(System.TeamProject)-devops-deployment' # string. Required when action = Deploy to IoT Edge devices. IoT Edge deployment ID. Default: $(System.TeamProject)-devops-deployment.
    #priority: '0' # string. Required when action = Deploy to IoT Edge devices. IoT Edge deployment priority. Default: 0.
  # Advanced
    #bypassModules: # string. Optional. Use when action = Push module images. Bypass module(s).
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Azure IoT Edge v2
# Build and deploy an Azure IoT Edge image.
- task: AzureIoTEdge@2
  inputs:
    action: 'Build module images' # 'Build module images' | 'Push module images' | 'Generate deployment manifest' | 'Deploy to IoT Edge devices'. Required. Action. Default: Build module images.
    #deploymentFilePath: '$(System.DefaultWorkingDirectory)/config/deployment.json' # string. Required when action == Deploy to IoT Edge devices. Deployment file. Default: $(System.DefaultWorkingDirectory)/config/deployment.json.
    #azureSubscription: # string. Alias: connectedServiceNameARM. Required when action == Deploy to IoT Edge devices. Azure subscription contains IoT Hub. 
    #iothubname: # string. Required when action == Deploy to IoT Edge devices. IoT Hub name. 
    #deviceOption: # 'Single Device' | 'Multiple Devices'. Required when action == Deploy to IoT Edge devices. Choose single/multiple device. 
    #deviceId: # string. Required when deviceOption == Single Device. IoT Edge device ID. 
    #targetcondition: # string. Required when deviceOption == Multiple Devices. IoT Edge device target condition. 
    #containerregistrytype: 'Azure Container Registry' # 'Azure Container Registry' | 'Generic Container Registry'. Required when action = Push module images. Container registry type. Default: Azure Container Registry.
    #dockerRegistryConnection: # string. Alias: dockerRegistryEndpoint. Required when containerregistrytype = Generic Container Registry. Docker Registry Connection. 
    #azureSubscriptionEndpoint: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Required when containerregistrytype = Azure Container Registry. Azure Container Registry. 
    #templateFilePath: 'deployment.template.json' # string. Required when action = Build module images || action = Push module images || action = Generate deployment manifest. .template.json file. Default: deployment.template.json.
    #defaultPlatform: 'amd64' # 'amd64' | 'windows-amd64' | 'arm32v7'. Required when action = Build module images || action = Push module images || action = Generate deployment manifest. Default platform. Default: amd64.
    #fillRegistryCredential: 'true' # 'true' | 'false'. Required when action = Push module images. Add registry credential to deployment manifest. Default: true.
    #deploymentManifestOutputPath: '$(System.DefaultWorkingDirectory)/config/deployment.json' # string. Required when action == Generate deployment manifest. Output path. Default: $(System.DefaultWorkingDirectory)/config/deployment.json.
  # Advanced
    #deploymentid: '$(System.TeamProject)-devops-deployment' # string. Required when action = Deploy to IoT Edge devices. IoT Edge deployment ID. Default: $(System.TeamProject)-devops-deployment.
    #priority: '0' # string. Required when action = Deploy to IoT Edge devices. IoT Edge deployment priority. Default: 0.
  # Advanced
    #bypassModules: # string. Optional. Use when action = Push module images. Bypass module(s).
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="action"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`action`** - **Action**<br>
`string`. Required. Allowed values: `Build module images`, `Push module images`, `Generate deployment manifest`, `Deploy to IoT Edge devices`. Default value: `Build module images`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects an Azure IoT Edge action.

`Build module images` only builds modules (you can use it to check compilation errors).

`Push module images` pushes modules to the container registry.

`Deploy to IoT Edge devices` deploys the generated deployment file to IoT Hub. (We recommend putting the `Deploy` task in the release pipeline.)
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentFilePath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deploymentFilePath`** - **Deployment file**<br>
`string`. Required when `action == Deploy to IoT Edge devices`. Default value: `$(System.DefaultWorkingDirectory)/config/deployment.json`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the deployment json file.
 If this task is in `release pipeline`, you need to set the location of the deployment file in artifact. (The default value works for most conditions.)
 If this task is in a build pipeline, you must specify the deployment manifest output path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azureSubscription`** - **Azure subscription contains IoT Hub**<br>
Input alias: `connectedServiceNameARM`. `string`. Required when `action == Deploy to IoT Edge devices`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects an Azure subscription that contains IoT Hub.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="iothubname"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`iothubname`** - **IoT Hub name**<br>
`string`. Required when `action == Deploy to IoT Edge devices`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the IoT Hub.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentid"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deploymentid`** - **IoT Edge deployment ID**<br>
`string`. Required when `action = Deploy to IoT Edge devices`. Default value: `$(System.TeamProject)-devops-deployment`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Inputs the IoT Edge Deployment ID. If the ID already exists, it will be overridden.
 This has up to 128 lowercase letters and numbers, and the following characters are allowed: `-:+%_#*?!(),=@;'`.
 For more information, see [Azure IoT Edge deployment](/azure/iot-edge/how-to-deploy-monitor#monitor-a-deployment).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="priority"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`priority`** - **IoT Edge deployment priority**<br>
`string`. Required when `action = Deploy to IoT Edge devices`. Default value: `0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Sets the `priority` to a positive integer to resolve deployment conflicts.  When this task is targeted by multiple deployments, a device will use the one with the highest priority or, in the case of two deployments with the same priority, the latest creation time.
 For more information, see [Azure IoT Edge deployment](/azure/iot-edge/how-to-deploy-monitor#monitor-a-deployment).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deviceOption"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deviceOption`** - **Choose single/multiple device**<br>
`string`. Required when `action == Deploy to IoT Edge devices`. Allowed values: `Single Device`, `Multiple Devices`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
According to tags, chooses to deploy to single or multiple devices.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deviceId"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deviceId`** - **IoT Edge device ID**<br>
`string`. Required when `deviceOption == Single Device`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Inputs the IoT Edge `device ID`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="targetcondition"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`targetcondition`** - **IoT Edge device target condition**<br>
`string`. Required when `deviceOption == Multiple Devices`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Inputs the `target condition` of devices you would like to deploy. Do not use double quotes. Example: `tags.building=9` and `tags.environment='test'`.
 For more information, see [Azure IoT Edge deployment](/azure/iot-edge/how-to-deploy-monitor#monitor-a-deployment).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerregistrytype"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`containerregistrytype`** - **Container registry type**<br>
`string`. Required when `action = Push module images`. Allowed values: `Azure Container Registry`, `Generic Container Registry`. Default value: `Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects a `Container Registry Type`.
 `Azure Container Registry` is for ACR, and `Generic Container Registry` is for generic registries including docker hub.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerRegistryConnection"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`dockerRegistryConnection`** - **Docker Registry Connection**<br>
Input alias: `dockerRegistryEndpoint`. `string`. Required when `containerregistrytype = Generic Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects a generic Docker registry connection. This is required for build and push.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscriptionEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azureSubscriptionEndpoint`** - **Azure subscription**<br>
`string`. Optional. Use when `containerregistrytype = Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects an Azure subscription.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureContainerRegistry"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azureContainerRegistry`** - **Azure Container Registry**<br>
`string`. Required when `containerregistrytype = Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects an Azure Container Registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="templateFilePath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`templateFilePath`** - **.template.json file**<br>
`string`. Required when `action = Build module images || action = Push module images || action = Generate deployment manifest`. Default value: `deployment.template.json`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path of Azure IoT Edge solution `.template.json`. This file defines the modules and routes in Azure IoT Edge solution. The file name must end with `.template.json`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="defaultPlatform"::: -->
:::moniker range=">=azure-pipelines-2022"

**`defaultPlatform`** - **Default platform**<br>
`string`. Required when `action = Build module images || action = Push module images || action = Generate deployment manifest`. Allowed values: `amd64`, `windows-amd64`, `arm32v7`, `arm64v8`. Default value: `amd64`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In your `.template.json`, you can leave the modules platform unspecified. For these modules, the default platform will be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

**`defaultPlatform`** - **Default platform**<br>
`string`. Required when `action = Build module images || action = Push module images || action = Generate deployment manifest`. Allowed values: `amd64`, `windows-amd64`, `arm32v7`. Default value: `amd64`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In your `.template.json`, you can leave the modules platform unspecified. For these modules, the default platform will be used.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="fillRegistryCredential"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`fillRegistryCredential`** - **Add registry credential to deployment manifest**<br>
`string`. Required when `action = Push module images`. Allowed values: `true`, `false`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Adds the registry credential for pushing docker images to the deployment manifest.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploymentManifestOutputPath"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`deploymentManifestOutputPath`** - **Output path**<br>
`string`. Required when `action == Generate deployment manifest`. Default value: `$(System.DefaultWorkingDirectory)/config/deployment.json`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The output path of the generated deployment manifest.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="validateGeneratedDeploymentManifest"::: -->
:::moniker range=">=azure-pipelines-2020"

**`validateGeneratedDeploymentManifest`** - **Validate the schema of generated deployment manifest**<br>
`string`. Required when `action = Generate deployment manifest`. Allowed values: `true`, `false`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Fail this step if the generated deployment manifest does not pass schema validation. Search `Azure IoT Edge deployment` in [JSON Schema Store](http://schemastore.org/json/) to find latest schema.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="bypassModules"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`bypassModules`** - **Bypass module(s)**<br>
`string`. Optional. Use when `action = Push module images`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the module(s) that you do not need to build or push in `.template.json`, specifies the module names, and separates them with commas.
 Example: if you have `SampleModule1` and `SampleModule2` in your `.template.json` and you want to only build or push `SampleModule1`, then you set the bypass modules as `SampleModule2`. Leave this empty if you would like to build all the modules in `.template.json`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019.1"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="DEPLOYMENT_FILE_PATH"::: -->
**`DEPLOYMENT_FILE_PATH`**<br><!-- :::editable-content name="Value"::: -->
This is the path of generated deployment file.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to build, test, and deploy applications quickly and efficiently to Azure IoT Edge.

This task supports custom variables. If you're not familiar with how to use variables in Pipelines, see [Define variables](/azure/devops/pipelines/process/variables).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Build module images

The following YAML example builds module images:

```YAML
- task: AzureIoTEdge@2
  displayName: AzureIoTEdge - Build module images
  inputs:
    action: Build module images
    templateFilePath: deployment.template.json
    defaultPlatform: amd64  
```

### Push module images

The following YAML example pushes module images:

```YAML
variables:
  azureSubscriptionEndpoint: Contoso
  azureContainerRegistry: contoso.azurecr.io

steps:    
- task: AzureIoTEdge@2
  displayName: AzureIoTEdge - Push module images
  inputs:
    action: Push module images
    containerregistrytype: Azure Container Registry
    azureSubscriptionEndpoint: $(azureSubscriptionEndpoint)
    azureContainerRegistry: {"loginServer":"$(azureContainerRegistry)"}
    templateFilePath: deployment.template.json
    defaultPlatform: amd64
    fillRegistryCredential: true
```

### Generate deployment manifest

The following YAML example creates a deployment manifest based on the template file:

```YAML
steps:    
- task: AzureIoTEdge@2
  displayName: AzureIoTEdge - Generate deployment manifest
  inputs:
    action: Generate deployment manifest
    templateFilePath: deployment.template.json
    defaultPlatform: amd64
    deploymentManifestOutputPath: $(System.DefaultWorkingDirectory)/config/deployment.json
    validateGeneratedDeploymentManifest: false
```

### Deploy to IoT Edge devices

The following YAML example deploys module images:

```YAML
steps:
- task: AzureIoTEdge@2
  displayName: 'Azure IoT Edge - Deploy to IoT Edge devices'
  inputs:
    action: 'Deploy to IoT Edge devices'
    deploymentFilePath: $(System.DefaultWorkingDirectory)/config/deployment.json
    azureSubscription: $(azureSubscriptionEndpoint)
    iothubname: iothubname
    deploymentid: '$(System.TeamProject)-devops-deployment'
    priority: '0'
    deviceOption: 'Single Device'
    deviceId: deviceId
```

### More examples

For step-by-step examples of how to use these actions in Azure Pipelines, see the following articles:

* [Continuous integration and continuous deployment to Azure IoT Edge devices (YAML)](/azure/iot-edge/how-to-continuous-integration-continuous-deployment)
* [Continuous integration and continuous deployment to Azure IoT Edge devices (classic editor)](/azure/iot-edge/how-to-continuous-integration-continuous-deployment-classic)
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->