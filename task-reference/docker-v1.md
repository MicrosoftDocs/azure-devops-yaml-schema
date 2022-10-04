---
title: Docker@1 - Docker v1 task
description: Build, tag, push, or run Docker images, or run a Docker command.
ms.date: 09/26/2022
monikerRange: ">=azure-pipelines-2019"
---

# Docker@1 - Docker v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Build, tag, push, or run Docker images, or run a Docker command.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Build, tag, push, or run Docker images, or run a Docker command. Task can be used with Docker or Azure Container registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Docker v1
# Build, tag, push, or run Docker images, or run a Docker command.
- task: Docker@1
  inputs:
  # Container Registry
    containerregistrytype: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required. Container registry type. Default: Azure Container Registry.
    #dockerRegistryEndpoint: # string. Optional. Use when containerregistrytype = Container Registry. Docker registry service connection. 
    #azureSubscriptionEndpoint: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure container registry. 
  # Commands
    #addBaseImageData: true # boolean. Add base image metadata to image(s). Default: true.
    command: 'Build an image' # 'Build an image' | 'Tag image' | 'Push an image' | 'Run an image' | 'login' | 'logout'. Required. Command. Default: Build an image.
    #dockerFile: '**/Dockerfile' # string. Required when command = Build an image || command = build. Dockerfile. Default: **/Dockerfile.
    #arguments: # string. Optional. Use when command != login && command != logout. Arguments. 
    #pushMultipleImages: false # boolean. Optional. Use when command = Push an image || command = push. Push multiple images. Default: false.
    #tagMultipleImages: false # boolean. Optional. Use when command = Tag image || command = tag. Tag multiple images. Default: false.
    #imageName: '$(Build.Repository.Name):$(Build.BuildId)' # string. Required when command = Build an image || command = build || command = Run an image || command = run || pushMultipleImages = false || tagMultipleImages = false. Image name. Default: $(Build.Repository.Name):$(Build.BuildId).
    #imageNamesPath: # string. Required when tagMultipleImages = true || pushMultipleImages = true. Image names path. 
    #qualifyImageName: true # boolean. Optional. Use when command = Build an image || command = build || command = Tag image || command = tag || command = Push an image || command = push || command = Run an image || command = run. Qualify image name. Default: true.
    #qualifySourceImageName: false # boolean. Optional. Use when command = Tag image || command = tag. Qualify source image name. Default: false.
    #includeSourceTags: false # boolean. Optional. Use when command = Build an image || command = build || command = Tag image || command = tag  || command = Push an image || command = push. Include source tags. Default: false.
    #includeLatestTag: false # boolean. Optional. Use when command = Build an image || command = build. Include latest tag. Default: false.
    #addDefaultLabels: true # boolean. Optional. Use when addDefaultLabels = false. Add default labels. Default: true.
    #useDefaultContext: true # boolean. Optional. Use when command = Build an image || command = build. Use default build context. Default: true.
    #buildContext: # string. Optional. Use when useDefaultContext = false. Build context. 
    #imageDigestFile: # string. Optional. Use when command = Push an image || command = push. Image digest file. 
    #containerName: # string. Optional. Use when command = Run an image || command = run. Container name. 
    #ports: # string. Optional. Use when command = Run an image || command = run. Ports. 
    #volumes: # string. Optional. Use when command = Run an image || command = run. Volumes. 
    #envVars: # string. Optional. Use when command = Run an image || command = run. Environment variables. 
    #workingDirectory: # string. Optional. Use when command = Run an image || command = run. Working directory. 
    #entrypointOverride: # string. Optional. Use when command = Run an image || command = run. Entry point override. 
    #containerCommand: # string. Optional. Use when command = Run an image || command = run. Container command. 
    #runInBackground: true # boolean. Optional. Use when command = Run an image || command = run. Run in background. Default: true.
    restartPolicy: 'no' # 'no' | 'onFailure' | 'always' | 'unlessStopped'. Required when runInBackground = true. Restart policy. Default: no.
    #maxRestartRetries: # string. Optional. Use when runInBackground = true && restartPolicy = onFailure. Maximum restart retries. 
  # Advanced Options
    #dockerHostEndpoint: # string. Docker host service connection. 
    #enforceDockerNamingConvention: true # boolean. Force image name to follow Docker naming convention. Default: true.
    #memoryLimit: # string. Memory limit.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

```yaml
# Docker v1
# Build, tag, push, or run Docker images, or run a Docker command.
- task: Docker@1
  inputs:
  # Container Registry
    containerregistrytype: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required. Container registry type. Default: Azure Container Registry.
    #dockerRegistryEndpoint: # string. Optional. Use when containerregistrytype = Container Registry. Docker registry service connection. 
    #azureSubscriptionEndpoint: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure container registry. 
  # Commands
    command: 'Build an image' # 'Build an image' | 'Tag image' | 'Push an image' | 'Run an image' | 'login' | 'logout'. Required. Command. Default: Build an image.
    #dockerFile: '**/Dockerfile' # string. Required when command = Build an image || command = build. Dockerfile. Default: **/Dockerfile.
    #arguments: # string. Optional. Use when command != login && command != logout. Arguments. 
    #pushMultipleImages: false # boolean. Optional. Use when command = Push an image || command = push. Push multiple images. Default: false.
    #tagMultipleImages: false # boolean. Optional. Use when command = Tag image || command = tag. Tag multiple images. Default: false.
    #imageName: '$(Build.Repository.Name):$(Build.BuildId)' # string. Required when command = Build an image || command = build || command = Run an image || command = run || pushMultipleImages = false || tagMultipleImages = false. Image name. Default: $(Build.Repository.Name):$(Build.BuildId).
    #imageNamesPath: # string. Required when tagMultipleImages = true || pushMultipleImages = true. Image names path. 
    #qualifyImageName: true # boolean. Optional. Use when command = Build an image || command = build || command = Tag image || command = tag || command = Push an image || command = push || command = Run an image || command = run. Qualify image name. Default: true.
    #qualifySourceImageName: false # boolean. Optional. Use when command = Tag image || command = tag. Qualify source image name. Default: false.
    #includeSourceTags: false # boolean. Optional. Use when command = Build an image || command = build || command = Tag image || command = tag  || command = Push an image || command = push. Include source tags. Default: false.
    #includeLatestTag: false # boolean. Optional. Use when command = Build an image || command = build. Include latest tag. Default: false.
    #addDefaultLabels: true # boolean. Optional. Use when addDefaultLabels = false. Add default labels. Default: true.
    #useDefaultContext: true # boolean. Optional. Use when command = Build an image || command = build. Use default build context. Default: true.
    #buildContext: # string. Optional. Use when useDefaultContext = false. Build context. 
    #imageDigestFile: # string. Optional. Use when command = Push an image || command = push. Image digest file. 
    #containerName: # string. Optional. Use when command = Run an image || command = run. Container name. 
    #ports: # string. Optional. Use when command = Run an image || command = run. Ports. 
    #volumes: # string. Optional. Use when command = Run an image || command = run. Volumes. 
    #envVars: # string. Optional. Use when command = Run an image || command = run. Environment variables. 
    #workingDirectory: # string. Optional. Use when command = Run an image || command = run. Working directory. 
    #entrypointOverride: # string. Optional. Use when command = Run an image || command = run. Entry point override. 
    #containerCommand: # string. Optional. Use when command = Run an image || command = run. Container command. 
    #runInBackground: true # boolean. Optional. Use when command = Run an image || command = run. Run in background. Default: true.
    restartPolicy: 'no' # 'no' | 'onFailure' | 'always' | 'unlessStopped'. Required when runInBackground = true. Restart policy. Default: no.
    #maxRestartRetries: # string. Optional. Use when runInBackground = true && restartPolicy = onFailure. Maximum restart retries. 
  # Advanced Options
    #dockerHostEndpoint: # string. Docker host service connection. 
    #enforceDockerNamingConvention: true # boolean. Force image name to follow Docker naming convention. Default: true.
    #memoryLimit: # string. Memory limit.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Docker v1
# Build, tag, push, or run Docker images, or run a Docker command.
- task: Docker@1
  inputs:
  # Container Registry
    containerregistrytype: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required. Container registry type. Default: Azure Container Registry.
    #dockerRegistryEndpoint: # string. Optional. Use when containerregistrytype = Container Registry. Docker registry service connection. 
    #azureSubscriptionEndpoint: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure container registry. 
  # Commands
    command: 'Build an image' # 'Build an image' | 'Tag image' | 'Push an image' | 'Run an image' | 'login' | 'logout'. Required. Command. Default: Build an image.
    #dockerFile: '**/Dockerfile' # string. Required when command = Build an image || command = build. Dockerfile. Default: **/Dockerfile.
    #arguments: # string. Optional. Use when command != login && command != logout. Arguments. 
    #pushMultipleImages: false # boolean. Optional. Use when command = Push an image || command = push. Push multiple images. Default: false.
    #tagMultipleImages: false # boolean. Optional. Use when command = Tag image || command = tag. Tag multiple images. Default: false.
    #imageName: '$(Build.Repository.Name):$(Build.BuildId)' # string. Required when command = Build an image || command = build || command = Run an image || command = run || pushMultipleImages = false || tagMultipleImages = false. Image name. Default: $(Build.Repository.Name):$(Build.BuildId).
    #imageNamesPath: # string. Required when tagMultipleImages = true || pushMultipleImages = true. Image names path. 
    #qualifyImageName: true # boolean. Optional. Use when command = Build an image || command = build || command = Tag image || command = tag || command = Push an image || command = push || command = Run an image || command = run. Qualify image name. Default: true.
    #includeSourceTags: false # boolean. Optional. Use when command = Build an image || command = build || command = Tag image || command = tag  || command = Push an image || command = push. Include source tags. Default: false.
    #includeLatestTag: false # boolean. Optional. Use when command = Build an image || command = build. Include latest tag. Default: false.
    #addDefaultLabels: true # boolean. Optional. Use when addDefaultLabels = false. Add default labels. Default: true.
    #useDefaultContext: true # boolean. Optional. Use when command = Build an image || command = build. Use default build context. Default: true.
    #buildContext: # string. Optional. Use when useDefaultContext = false. Build context. 
    #imageDigestFile: # string. Optional. Use when command = Push an image || command = push. Image digest file. 
    #containerName: # string. Optional. Use when command = Run an image || command = run. Container name. 
    #ports: # string. Optional. Use when command = Run an image || command = run. Ports. 
    #volumes: # string. Optional. Use when command = Run an image || command = run. Volumes. 
    #envVars: # string. Optional. Use when command = Run an image || command = run. Environment variables. 
    #workingDirectory: # string. Optional. Use when command = Run an image || command = run. Working directory. 
    #entrypointOverride: # string. Optional. Use when command = Run an image || command = run. Entry point override. 
    #containerCommand: # string. Optional. Use when command = Run an image || command = run. Container command. 
    #runInBackground: true # boolean. Optional. Use when command = Run an image || command = run. Run in background. Default: true.
    restartPolicy: 'no' # 'no' | 'onFailure' | 'always' | 'unlessStopped'. Required when runInBackground = true. Restart policy. Default: no.
    #maxRestartRetries: # string. Optional. Use when runInBackground = true && restartPolicy = onFailure. Maximum restart retries. 
  # Advanced Options
    #dockerHostEndpoint: # string. Docker host service connection. 
    #enforceDockerNamingConvention: true # boolean. Force image name to follow Docker naming convention. Default: true.
    #memoryLimit: # string. Memory limit.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Docker v1
# Build, tag, push, or run Docker images, or run a Docker command. Task can be used with Docker or Azure Container registry.
- task: Docker@1
  inputs:
  # Container Registry
    containerregistrytype: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required. Container registry type. Default: Azure Container Registry.
    #dockerRegistryEndpoint: # string. Optional. Use when containerregistrytype = Container Registry. Docker registry service connection. 
    #azureSubscriptionEndpoint: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure container registry. 
  # Commands
    command: 'Build an image' # 'Build an image' | 'Tag image' | 'Push an image' | 'Run an image' | 'login' | 'logout'. Required. Command. Default: Build an image.
    #dockerFile: '**/Dockerfile' # string. Required when command = Build an image || command = build. Dockerfile. Default: **/Dockerfile.
    #arguments: # string. Optional. Use when command != Run an image && command != run && command != login && command != logout. Arguments. 
    #useDefaultContext: true # boolean. Optional. Use when command = Build an image || command = build. Use default build context. Default: true.
    #buildContext: # string. Optional. Use when useDefaultContext = false. Build context. 
    #pushMultipleImages: false # boolean. Optional. Use when command = Push an image || command = push. Push multiple images. Default: false.
    #tagMultipleImages: false # boolean. Optional. Use when command = Tag image || command = tag. Tag multiple images. Default: false.
    #imageName: '$(Build.Repository.Name):$(Build.BuildId)' # string. Required when command = Build an image || command = build || command = Run an image || command = run || pushMultipleImages = false || tagMultipleImages = false. Image name. Default: $(Build.Repository.Name):$(Build.BuildId).
    #imageNamesPath: # string. Required when tagMultipleImages = true || pushMultipleImages = true. Image names path. 
    #qualifyImageName: true # boolean. Optional. Use when command = Build an image || command = build || command = Tag image || command = tag || command = Push an image || command = push || command = Run an image || command = run. Qualify image name. Default: true.
    #includeSourceTags: false # boolean. Optional. Use when command = Build an image || command = build || command = Tag image || command = tag  || command = Push an image || command = push. Include source tags. Default: false.
    #includeLatestTag: false # boolean. Optional. Use when command = Build an image || command = build. Include latest tag. Default: false.
    #addDefaultLabels: true # boolean. Optional. Use when command = Build an image || command = build. Add default labels. Default: true.
    #imageDigestFile: # string. Optional. Use when command = Push an image || command = push. Image digest file. 
    #containerName: # string. Optional. Use when command = Run an image || command = run. Container name. 
    #ports: # string. Optional. Use when command = Run an image || command = run. Ports. 
    #volumes: # string. Optional. Use when command = Run an image || command = run. Volumes. 
    #envVars: # string. Optional. Use when command = Run an image || command = run. Environment variables. 
    #workingDirectory: # string. Optional. Use when command = Run an image || command = run. Working directory. 
    #entrypointOverride: # string. Optional. Use when command = Run an image || command = run. Entry point override. 
    #containerCommand: # string. Optional. Use when command = Run an image || command = run. Command. 
    #runInBackground: true # boolean. Optional. Use when command = Run an image || command = run. Run in background. Default: true.
    restartPolicy: 'no' # 'no' | 'onFailure' | 'always' | 'unlessStopped'. Required when runInBackground = true. Restart policy. Default: no.
    #maxRestartRetries: # string. Optional. Use when runInBackground = true && restartPolicy = onFailure. Maximum restart retries. 
  # Advanced Options
    #dockerHostEndpoint: # string. Docker host service connection. 
    #enforceDockerNamingConvention: true # boolean. Force image name to follow Docker naming convention. Default: true.
    #memoryLimit: # string. Memory limit.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="containerregistrytype"::: -->
:::moniker range=">=azure-pipelines-2019"

**`containerregistrytype`** - **Container registry type**<br>
`string`. Required. Allowed values: `Azure Container Registry`, `Container Registry`. Default value: `Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select 'Azure Container Registry' to connect to it by using an Azure Service Connection. Select 'Container registry' to connect to Docker Hub or any other private container registry.
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
<!-- :::item name="dockerRegistryEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`dockerRegistryEndpoint`** - **Docker registry service connection**<br>
`string`. Optional. Use when `containerregistrytype = Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker registry service connection. Required for commands that need to authenticate with a registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscriptionEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureSubscriptionEndpoint`** - **Azure subscription**<br>
`string`. Optional. Use when `containerregistrytype = Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure subscription.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureContainerRegistry"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureContainerRegistry`** - **Azure container registry**<br>
`string`. Optional. Use when `containerregistrytype = Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure Container Registry in the selected Azure Subscription. The container image will be built and pushed to this container registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="command"::: -->
:::moniker range=">=azure-pipelines-2019"

**`command`** - **Command**<br>
`string`. Required. Allowed values: `Build an image` (build), `Tag image` (tag), `Push an image` (push), `Run an image` (run), `login`, `logout`. Default value: `Build an image`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The docker command to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`dockerFile`** - **Dockerfile**<br>
`string`. Required when `command = Build an image || command = build`. Default value: `**/Dockerfile`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the Dockerfile. The task will use the first dockerfile it finds to build the image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`arguments`** - **Arguments**<br>
`string`. Optional. Use when `command != login && command != logout`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments to be passed onto the docker client
Be aware that if you use value `buildAndPush` for the command parameter, the arguments property is ignored.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`arguments`** - **Arguments**<br>
`string`. Optional. Use when `command != Run an image && command != run && command != login && command != logout`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional arguments to be passed onto the docker client
Be aware that if you use value `buildAndPush` for the command parameter, the arguments property is ignored.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pushMultipleImages"::: -->
:::moniker range=">=azure-pipelines-2019"

**`pushMultipleImages`** - **Push multiple images**<br>
`boolean`. Optional. Use when `command = Push an image || command = push`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Push multiple images by using a text file that contains the names of the Docker images to push. Each image name is contained on its own line.<br>For example:<br>  Imagename1:tag1<br>  Imagename2:tag2<br>  Imagename3<br>In case only image name is provided,  all tags of the ImageName3 container image will be pushed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tagMultipleImages"::: -->
:::moniker range=">=azure-pipelines-2019"

**`tagMultipleImages`** - **Tag multiple images**<br>
`boolean`. Optional. Use when `command = Tag image || command = tag`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Tag multiple images by using a text file that contains the names of the Docker images to tag. Each image name is contained on its own line.<br>For example:<br>  Imagename1:tag1<br>  Imagename2:tag2<br>  Imagename3<br>In case only image name is provided, that image will be tagged as 'latest'.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`imageName`** - **Image name**<br>
`string`. Required when `command = Build an image || command = build || command = Run an image || command = run || pushMultipleImages = false || tagMultipleImages = false`. Default value: `$(Build.Repository.Name):$(Build.BuildId)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the Docker image to build, push, or run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageNamesPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`imageNamesPath`** - **Image names path**<br>
`string`. Required when `tagMultipleImages = true || pushMultipleImages = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to a text file that contains the names of the Docker images to tag or push. Each image name is contained on its own line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="qualifyImageName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`qualifyImageName`** - **Qualify image name**<br>
`boolean`. Optional. Use when `command = Build an image || command = build || command = Tag image || command = tag || command = Push an image || command = push || command = Run an image || command = run`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Qualify the image name with the Docker registry service connection's hostname if not otherwise specified.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="qualifySourceImageName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`qualifySourceImageName`** - **Qualify source image name**<br>
`boolean`. Optional. Use when `command = Tag image || command = tag`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Qualify the source image name with the Docker registry service connection's hostname if not otherwise specified.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeSourceTags"::: -->
:::moniker range=">=azure-pipelines-2019"

**`includeSourceTags`** - **Include source tags**<br>
`boolean`. Optional. Use when `command = Build an image || command = build || command = Tag image || command = tag  || command = Push an image || command = push`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Include Git tags when building or pushing the Docker image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeLatestTag"::: -->
:::moniker range=">=azure-pipelines-2019"

**`includeLatestTag`** - **Include latest tag**<br>
`boolean`. Optional. Use when `command = Build an image || command = build`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Include the 'latest' tag when building the Docker image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addDefaultLabels"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`addDefaultLabels`** - **Add default labels**<br>
`boolean`. Optional. Use when `addDefaultLabels = false`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Add CI/CD metadata like repository, commit, build and release information to the container image by using Docker labels.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`addDefaultLabels`** - **Add default labels**<br>
`boolean`. Optional. Use when `command = Build an image || command = build`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Add CI/CD metadata like repository, commit, build and release information to the container image by using Docker labels.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useDefaultContext"::: -->
:::moniker range=">=azure-pipelines-2019"

**`useDefaultContext`** - **Use default build context**<br>
`boolean`. Optional. Use when `command = Build an image || command = build`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set the build context to the directory that contains the Dockerfile.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildContext"::: -->
:::moniker range=">=azure-pipelines-2019"

**`buildContext`** - **Build context**<br>
`string`. Optional. Use when `useDefaultContext = false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the build context.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageDigestFile"::: -->
:::moniker range=">=azure-pipelines-2019"

**`imageDigestFile`** - **Image digest file**<br>
`string`. Optional. Use when `command = Push an image || command = push`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to a file that is created and populated with the full image repository digest of the Docker image that was pushed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`containerName`** - **Container name**<br>
`string`. Optional. Use when `command = Run an image || command = run`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the Docker container to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ports"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ports`** - **Ports**<br>
`string`. Optional. Use when `command = Run an image || command = run`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Ports in the Docker container to publish to the host. Specify each host-port:container-port binding on a new line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="volumes"::: -->
:::moniker range=">=azure-pipelines-2019"

**`volumes`** - **Volumes**<br>
`string`. Optional. Use when `command = Run an image || command = run`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Volumes to mount from the host. Specify each host-dir:container-dir on a new line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="envVars"::: -->
:::moniker range=">=azure-pipelines-2019"

**`envVars`** - **Environment variables**<br>
`string`. Optional. Use when `command = Run an image || command = run`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Environment variables for the Docker container. Specify each name=value pair on a new line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`workingDirectory`** - **Working directory**<br>
`string`. Optional. Use when `command = Run an image || command = run`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The working directory for the Docker container.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="entrypointOverride"::: -->
:::moniker range=">=azure-pipelines-2019"

**`entrypointOverride`** - **Entry point override**<br>
`string`. Optional. Use when `command = Run an image || command = run`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Override the default entry point for the Docker container.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerCommand"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`containerCommand`** - **Container command**<br>
`string`. Optional. Use when `command = Run an image || command = run`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The docker run command first creates a writeable container layer over the specified image, and then starts it by using the specified run command. For example, if the image contains a simple Python Flask web application you can specify 'python app.py' to launch the web application.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`containerCommand`** - **Command**<br>
`string`. Optional. Use when `command = Run an image || command = run`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The docker run command first creates a writeable container layer over the specified image, and then starts it by using the specified run command. For example, if the image contains a simple Python Flask web application you can specify 'python app.py' to launch the web application.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runInBackground"::: -->
:::moniker range=">=azure-pipelines-2019"

**`runInBackground`** - **Run in background**<br>
`boolean`. Optional. Use when `command = Run an image || command = run`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run the Docker container in the background.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="restartPolicy"::: -->
:::moniker range=">=azure-pipelines-2019"

**`restartPolicy`** - **Restart policy**<br>
`string`. Required when `runInBackground = true`. Allowed values: `no`, `onFailure` (On failure), `always`, `unlessStopped` (Unless stopped). Default value: `no`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a restart policy.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="maxRestartRetries"::: -->
:::moniker range=">=azure-pipelines-2019"

**`maxRestartRetries`** - **Maximum restart retries**<br>
`string`. Optional. Use when `runInBackground = true && restartPolicy = onFailure`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The maximum number of restart retries the Docker daemon attempts.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerHostEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`dockerHostEndpoint`** - **Docker host service connection**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker host service connection. Defaults to the agent's host.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enforceDockerNamingConvention"::: -->
:::moniker range=">=azure-pipelines-2019"

**`enforceDockerNamingConvention`** - **Force image name to follow Docker naming convention**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If enabled Docker image name will be modified to follow Docker naming convention. Converts upper case character to lower case and removes spaces in image name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="memoryLimit"::: -->
:::moniker range=">=azure-pipelines-2019"

**`memoryLimit`** - **Memory limit**<br>
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

:::moniker range=">=azure-pipelines-2019"

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