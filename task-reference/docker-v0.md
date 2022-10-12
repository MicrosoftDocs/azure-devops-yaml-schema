---
title: Docker@0 - Docker v0 task
description: Build, tag, push, or run Docker images, or run a Docker command (task version 0).
ms.date: 09/26/2022
monikerRange: "<=azure-pipelines"
---

# Docker@0 - Docker v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Build, tag, push, run Docker images, or run a Docker command.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Build, tag, push, run Docker images, or run a Docker command. Use this task with Docker or the Azure Container registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Docker v0
# Build, tag, push, or run Docker images, or run a Docker command.
- task: Docker@0
  inputs:
    containerregistrytype: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required. Container Registry Type. Default: Azure Container Registry.
    #dockerRegistryConnection: # string. Optional. Use when containerregistrytype = Container Registry. Docker Registry Service Connection. 
    #azureSubscription: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure Container Registry. 
    action: 'Build an image' # 'Build an image' | 'Tag images' | 'Push an image' | 'Push images' | 'Run an image' | 'Run a Docker command'. Required. Action. Default: Build an image.
    #dockerFile: '**/Dockerfile' # string. Required when action = Build an image. Docker File. Default: **/Dockerfile.
    #buildArguments: # string. Optional. Use when action = Build an image. Build Arguments. 
    #defaultContext: true # boolean. Optional. Use when action = Build an image. Use Default Build Context. Default: true.
    #context: # string. Optional. Use when action = Build an image && defaultContext = false. Build Context. 
    #imageName: '$(Build.Repository.Name):$(Build.BuildId)' # string. Required when action == Build an image || action == Push an image || action == Run an image. Image Name. Default: $(Build.Repository.Name):$(Build.BuildId).
    #imageNamesPath: # string. Required when action == Tag images || action == Push images. Image Names Path. 
    #qualifyImageName: true # boolean. Optional. Use when action = Build an image || action = Tag images || action = Push an image || action = Push images || action = Run an image. Qualify Image Name. Default: true.
    #additionalImageTags: # string. Optional. Use when action = Build an image || action = Tag images || action = Push an image || action = Push images. Additional Image Tags. 
    #includeSourceTags: false # boolean. Optional. Use when action = Build an image || action = Tag image || action = Push an image || action = Push images. Include Source Tags. Default: false.
    #includeLatestTag: false # boolean. Optional. Use when action = Build an image || action = Push an image || action = Push images. Include Latest Tag. Default: false.
    #imageDigestFile: # string. Optional. Use when action = Push an image || action = Push images. Image Digest File. 
    #containerName: # string. Optional. Use when action = Run an image. Container Name. 
    #ports: # string. Optional. Use when action = Run an image. Ports. 
    #volumes: # string. Optional. Use when action = Run an image. Volumes. 
    #envVars: # string. Optional. Use when action = Run an image. Environment Variables. 
    #workDir: # string. Optional. Use when action = Run an image. Working Directory. 
    #entrypoint: # string. Optional. Use when action = Run an image. Entry Point Override. 
    #containerCommand: # string. Optional. Use when action = Run an image. Command. 
    #detached: true # boolean. Optional. Use when action = Run an image. Run In Background. Default: true.
    #restartPolicy: 'no' # 'no' | 'onFailure' | 'always' | 'unlessStopped'. Required when action = Run an image && detached = true. Restart Policy. Default: no.
    #restartMaxRetries: # string. Optional. Use when action = Run an image && detached = true && restartPolicy = onFailure. Maximum Restart Retries. 
    #customCommand: # string. Required when action = Run a Docker command. Command. 
  # commands
    #addBaseImageData: true # boolean. Add base image metadata to image(s). Default: true.
  # Advanced Options
    #dockerHostEndpoint: # string. Docker Host Service Connection. 
    #enforceDockerNamingConvention: true # boolean. Force image name to follow Docker naming convention. Default: true.
    #workingDirectory: '$(System.DefaultWorkingDirectory)' # string. Working Directory. Default: $(System.DefaultWorkingDirectory).
    #memory: # string. Memory limit.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

```yaml
# Docker v0
# Build, tag, push, or run Docker images, or run a Docker command.
- task: Docker@0
  inputs:
    containerregistrytype: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required. Container Registry Type. Default: Azure Container Registry.
    #dockerRegistryConnection: # string. Optional. Use when containerregistrytype = Container Registry. Docker Registry Service Connection. 
    #azureSubscription: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure Container Registry. 
    action: 'Build an image' # 'Build an image' | 'Tag images' | 'Push an image' | 'Push images' | 'Run an image' | 'Run a Docker command'. Required. Action. Default: Build an image.
    #dockerFile: '**/Dockerfile' # string. Required when action = Build an image. Docker File. Default: **/Dockerfile.
    #buildArguments: # string. Optional. Use when action = Build an image. Build Arguments. 
    #defaultContext: true # boolean. Optional. Use when action = Build an image. Use Default Build Context. Default: true.
    #context: # string. Optional. Use when action = Build an image && defaultContext = false. Build Context. 
    #imageName: '$(Build.Repository.Name):$(Build.BuildId)' # string. Required when action == Build an image || action == Push an image || action == Run an image. Image Name. Default: $(Build.Repository.Name):$(Build.BuildId).
    #imageNamesPath: # string. Required when action == Tag images || action == Push images. Image Names Path. 
    #qualifyImageName: true # boolean. Optional. Use when action = Build an image || action = Tag images || action = Push an image || action = Push images || action = Run an image. Qualify Image Name. Default: true.
    #additionalImageTags: # string. Optional. Use when action = Build an image || action = Tag images || action = Push an image || action = Push images. Additional Image Tags. 
    #includeSourceTags: false # boolean. Optional. Use when action = Build an image || action = Tag image || action = Push an image || action = Push images. Include Source Tags. Default: false.
    #includeLatestTag: false # boolean. Optional. Use when action = Build an image || action = Push an image || action = Push images. Include Latest Tag. Default: false.
    #imageDigestFile: # string. Optional. Use when action = Push an image || action = Push images. Image Digest File. 
    #containerName: # string. Optional. Use when action = Run an image. Container Name. 
    #ports: # string. Optional. Use when action = Run an image. Ports. 
    #volumes: # string. Optional. Use when action = Run an image. Volumes. 
    #envVars: # string. Optional. Use when action = Run an image. Environment Variables. 
    #workDir: # string. Optional. Use when action = Run an image. Working Directory. 
    #entrypoint: # string. Optional. Use when action = Run an image. Entry Point Override. 
    #containerCommand: # string. Optional. Use when action = Run an image. Command. 
    #detached: true # boolean. Optional. Use when action = Run an image. Run In Background. Default: true.
    #restartPolicy: 'no' # 'no' | 'onFailure' | 'always' | 'unlessStopped'. Required when action = Run an image && detached = true. Restart Policy. Default: no.
    #restartMaxRetries: # string. Optional. Use when action = Run an image && detached = true && restartPolicy = onFailure. Maximum Restart Retries. 
    #customCommand: # string. Required when action = Run a Docker command. Command. 
  # Advanced Options
    #dockerHostEndpoint: # string. Docker Host Service Connection. 
    #enforceDockerNamingConvention: true # boolean. Force image name to follow Docker naming convention. Default: true.
    #workingDirectory: '$(System.DefaultWorkingDirectory)' # string. Working Directory. Default: $(System.DefaultWorkingDirectory).
    #memory: # string. Memory limit.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Docker v0
# Build, tag, push, or run Docker images, or run a Docker command. Task can be used with Docker or Azure Container registry.
- task: Docker@0
  inputs:
    containerregistrytype: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required. Container Registry Type. Default: Azure Container Registry.
    #dockerRegistryConnection: # string. Optional. Use when containerregistrytype = Container Registry. Docker Registry Service Connection. 
    #azureSubscription: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure Container Registry. 
    action: 'Build an image' # 'Build an image' | 'Tag images' | 'Push an image' | 'Push images' | 'Run an image' | 'Run a Docker command'. Required. Action. Default: Build an image.
    #dockerFile: '**/Dockerfile' # string. Required when action = Build an image. Docker File. Default: **/Dockerfile.
    #buildArguments: # string. Optional. Use when action = Build an image. Build Arguments. 
    #defaultContext: true # boolean. Optional. Use when action = Build an image. Use Default Build Context. Default: true.
    #context: # string. Optional. Use when action = Build an image && defaultContext = false. Build Context. 
    #imageName: '$(Build.Repository.Name):$(Build.BuildId)' # string. Required when action == Build an image || action == Push an image || action == Run an image. Image Name. Default: $(Build.Repository.Name):$(Build.BuildId).
    #imageNamesPath: # string. Required when action == Tag images || action == Push images. Image Names Path. 
    #qualifyImageName: true # boolean. Optional. Use when action = Build an image || action = Tag images || action = Push an image || action = Push images || action = Run an image. Qualify Image Name. Default: true.
    #additionalImageTags: # string. Optional. Use when action = Build an image || action = Tag images || action = Push an image || action = Push images. Additional Image Tags. 
    #includeSourceTags: false # boolean. Optional. Use when action = Build an image || action = Tag image || action = Push an image || action = Push images. Include Source Tags. Default: false.
    #includeLatestTag: false # boolean. Optional. Use when action = Build an image || action = Push an image || action = Push images. Include Latest Tag. Default: false.
    #imageDigestFile: # string. Optional. Use when action = Push an image || action = Push images. Image Digest File. 
    #containerName: # string. Optional. Use when action = Run an image. Container Name. 
    #ports: # string. Optional. Use when action = Run an image. Ports. 
    #volumes: # string. Optional. Use when action = Run an image. Volumes. 
    #envVars: # string. Optional. Use when action = Run an image. Environment Variables. 
    #workDir: # string. Optional. Use when action = Run an image. Working Directory. 
    #entrypoint: # string. Optional. Use when action = Run an image. Entry Point Override. 
    #containerCommand: # string. Optional. Use when action = Run an image. Command. 
    #detached: true # boolean. Optional. Use when action = Run an image. Run In Background. Default: true.
    #restartPolicy: 'no' # 'no' | 'onFailure' | 'always' | 'unlessStopped'. Required when action = Run an image && detached = true. Restart Policy. Default: no.
    #restartMaxRetries: # string. Optional. Use when action = Run an image && detached = true && restartPolicy = onFailure. Maximum Restart Retries. 
    #customCommand: # string. Required when action = Run a Docker command. Command. 
  # Advanced Options
    #dockerHostEndpoint: # string. Docker Host Service Connection. 
    #enforceDockerNamingConvention: true # boolean. Force image name to follow Docker naming convention. Default: true.
    #workingDirectory: '$(System.DefaultWorkingDirectory)' # string. Working Directory. Default: $(System.DefaultWorkingDirectory).
    #memory: # string. Memory limit.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="containerregistrytype"::: -->
:::moniker range="<=azure-pipelines"

**`containerregistrytype`** - **Container Registry Type**<br>
`string`. Required. Allowed values: `Azure Container Registry`, `Container Registry`. Default value: `Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select 'Azure Container Registry' to connect to it by using an Azure Service Connection. Select 'Container registry' to connect to Docker Hub or any other private container registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerRegistryConnection"::: -->
:::moniker range=">=azure-pipelines-2019"

**`dockerRegistryConnection`** - **Docker Registry Service Connection**<br>
Input alias: `dockerRegistryEndpoint`. `string`. Optional. Use when `containerregistrytype = Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a Docker registry service connection. Required for commands that need to authenticate with a registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`dockerRegistryConnection`** - **Docker Registry Connection**<br>
Input alias: `dockerRegistryEndpoint`. `string`. Optional. Use when `containerregistrytype = Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a Docker registry service connection. Required for commands that need to authenticate with a registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `azureSubscriptionEndpoint`. `string`. Optional. Use when `containerregistrytype = Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an Azure subscription.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureContainerRegistry"::: -->
:::moniker range="<=azure-pipelines"

**`azureContainerRegistry`** - **Azure Container Registry**<br>
`string`. Optional. Use when `containerregistrytype = Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an Azure Container Registry in the selected Azure Subscription. The container image is built and then pushed to this container registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="action"::: -->
:::moniker range="<=azure-pipelines"

**`action`** - **Action**<br>
`string`. Required. Allowed values: `Build an image`, `Tag images`, `Push an image`, `Push images`, `Run an image`, `Run a Docker command`. Default value: `Build an image`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a Docker action.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerFile"::: -->
:::moniker range="<=azure-pipelines"

**`dockerFile`** - **Docker File**<br>
`string`. Required when `action = Build an image`. Default value: `**/Dockerfile`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the Dockerfile. The task uses the first Docker file it finds to build the image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addBaseImageData"::: -->
:::moniker range=">=azure-pipelines-2022"

**`addBaseImageData`** - **Add base image metadata to image(s)**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
By default base image data like base image name and digest are added which helps with traceability. You can opt out of this default behavior by using this input.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildArguments"::: -->
:::moniker range="<=azure-pipelines"

**`buildArguments`** - **Build Arguments**<br>
`string`. Optional. Use when `action = Build an image`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Build-time variables for the Docker file. Specify each name=value pair on a new line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="defaultContext"::: -->
:::moniker range="<=azure-pipelines"

**`defaultContext`** - **Use Default Build Context**<br>
`boolean`. Optional. Use when `action = Build an image`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set the build context to the directory that contains the Docker file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="context"::: -->
:::moniker range="<=azure-pipelines"

**`context`** - **Build Context**<br>
`string`. Optional. Use when `action = Build an image && defaultContext = false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the build context.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageName"::: -->
:::moniker range="<=azure-pipelines"

**`imageName`** - **Image Name**<br>
`string`. Required when `action == Build an image || action == Push an image || action == Run an image`. Default value: `$(Build.Repository.Name):$(Build.BuildId)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the Docker image to build, push, or run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageNamesPath"::: -->
:::moniker range="<=azure-pipelines"

**`imageNamesPath`** - **Image Names Path**<br>
`string`. Required when `action == Tag images || action == Push images`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to a text file that contains the names of the Docker images to tag or push. Each image name is contained on its own line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="qualifyImageName"::: -->
:::moniker range="<=azure-pipelines"

**`qualifyImageName`** - **Qualify Image Name**<br>
`boolean`. Optional. Use when `action = Build an image || action = Tag images || action = Push an image || action = Push images || action = Run an image`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Qualify the image name with the Docker registry service connection's hostname if not otherwise specified.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="additionalImageTags"::: -->
:::moniker range="<=azure-pipelines"

**`additionalImageTags`** - **Additional Image Tags**<br>
`string`. Optional. Use when `action = Build an image || action = Tag images || action = Push an image || action = Push images`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional tags for the Docker image being built or pushed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeSourceTags"::: -->
:::moniker range="<=azure-pipelines"

**`includeSourceTags`** - **Include Source Tags**<br>
`boolean`. Optional. Use when `action = Build an image || action = Tag image || action = Push an image || action = Push images`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Include Git tags when building or pushing the Docker image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeLatestTag"::: -->
:::moniker range="<=azure-pipelines"

**`includeLatestTag`** - **Include Latest Tag**<br>
`boolean`. Optional. Use when `action = Build an image || action = Push an image || action = Push images`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Include the 'latest' tag when building or pushing the Docker image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageDigestFile"::: -->
:::moniker range="<=azure-pipelines"

**`imageDigestFile`** - **Image Digest File**<br>
`string`. Optional. Use when `action = Push an image || action = Push images`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to a file that is created and populated with the full image repository digest of the Docker image that was pushed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerName"::: -->
:::moniker range="<=azure-pipelines"

**`containerName`** - **Container Name**<br>
`string`. Optional. Use when `action = Run an image`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the Docker container to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ports"::: -->
:::moniker range="<=azure-pipelines"

**`ports`** - **Ports**<br>
`string`. Optional. Use when `action = Run an image`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Ports in the Docker container to publish to the host. Specify each host-port:container-port binding on a new line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="volumes"::: -->
:::moniker range="<=azure-pipelines"

**`volumes`** - **Volumes**<br>
`string`. Optional. Use when `action = Run an image`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Volumes to mount from the host. Specify each host-dir:container-dir on a new line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="envVars"::: -->
:::moniker range="<=azure-pipelines"

**`envVars`** - **Environment Variables**<br>
`string`. Optional. Use when `action = Run an image`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Environment variables for the Docker container. Specify each name=value pair on a new line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workDir"::: -->
:::moniker range="<=azure-pipelines"

**`workDir`** - **Working Directory**<br>
`string`. Optional. Use when `action = Run an image`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The working directory for the Docker container.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="entrypoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`entrypoint`** - **Entry Point Override**<br>
`string`. Optional. Use when `action = Run an image`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Override the default entry point for the Docker container.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`entrypoint`** - **Entrypoint Override**<br>
`string`. Optional. Use when `action = Run an image`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Override the default entry point for the Docker container.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerCommand"::: -->
:::moniker range="<=azure-pipelines"

**`containerCommand`** - **Command**<br>
`string`. Optional. Use when `action = Run an image`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The docker run command first creates a writeable container layer over the specified image, and then starts it by using the specified run command. For example, if the image contains a simple Python Flask web application you can specify 'python app.py' to launch the web application.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="detached"::: -->
:::moniker range="<=azure-pipelines"

**`detached`** - **Run In Background**<br>
`boolean`. Optional. Use when `action = Run an image`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run the Docker container in the background.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restartPolicy"::: -->
:::moniker range="<=azure-pipelines"

**`restartPolicy`** - **Restart Policy**<br>
`string`. Required when `action = Run an image && detached = true`. Allowed values: `no`, `onFailure` (On failure), `always`, `unlessStopped` (Unless stopped). Default value: `no`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a restart policy.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restartMaxRetries"::: -->
:::moniker range="<=azure-pipelines"

**`restartMaxRetries`** - **Maximum Restart Retries**<br>
`string`. Optional. Use when `action = Run an image && detached = true && restartPolicy = onFailure`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The maximum number of restart retries the Docker daemon attempts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="customCommand"::: -->
:::moniker range="<=azure-pipelines"

**`customCommand`** - **Command**<br>
`string`. Required when `action = Run a Docker command`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Docker command to execute, with arguments. For example, 'rmi -f image-name' to force remove an image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerHostEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`dockerHostEndpoint`** - **Docker Host Service Connection**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker host service connection. Defaults to the agent's host.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`dockerHostEndpoint`** - **Docker Host Connection**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker host service connection. Defaults to the agent's host.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enforceDockerNamingConvention"::: -->
:::moniker range="<=azure-pipelines"

**`enforceDockerNamingConvention`** - **Force image name to follow Docker naming convention**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If enabled Docker image name will be modified to follow Docker naming convention. Converts upper case character to lower case and removes spaces in image name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working Directory**<br>
Input alias: `cwd`. `string`. Default value: `$(System.DefaultWorkingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Working directory for the Docker command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="memory"::: -->
:::moniker range="<=azure-pipelines"

**`memory`** - **Memory limit**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The maximum amount of memory available to the container as a integer with optional suffixes like '2GB'.
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

<!-- :::item name="DockerOutput"::: -->
**`DockerOutput`**<br><!-- :::editable-content name="Value"::: -->
Stores the output of the docker command
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="DockerOutputPath"::: -->
**`DockerOutputPath`**<br><!-- :::editable-content name="Value"::: -->
The path of the file which contains the output of the build command.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2020.1"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="DockerOutput"::: -->
**`DockerOutput`**<br><!-- :::editable-content name="Value"::: -->
Stores the output of the docker command
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

[Docker@2](docker-v2.md) is a newer version of this task that simplifies the task by removing inputs that can be passed as arguments to the command.
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
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Docker@2](docker-v2.md)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->