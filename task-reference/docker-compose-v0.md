---
title: DockerCompose@0 - Docker Compose v0 task
description: Build, push or run multi-container Docker applications with Docker or from the Azure Container registry.
ms.date: 05/14/2024
monikerRange: "<=azure-pipelines"
---

# DockerCompose@0 - Docker Compose v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Build, push or run multi-container Docker applications. Use this task with Docker or the Azure Container registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2020.1"

```yaml
# Docker Compose v0
# Build, push or run multi-container Docker applications. Task can be used with Docker or Azure Container registry.
- task: DockerCompose@0
  inputs:
    containerregistrytype: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required. Container Registry Type. Default: Azure Container Registry.
    #dockerRegistryEndpoint: # string. Optional. Use when containerregistrytype = Container Registry. Docker Registry Service Connection. 
    #azureSubscription: # string. Alias: azureSubscriptionEndpoint. Optional. Use when containerregistrytype = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure Container Registry. 
    dockerComposeFile: '**/docker-compose.yml' # string. Required. Docker Compose File. Default: **/docker-compose.yml.
    #additionalDockerComposeFiles: # string. Additional Docker Compose Files. 
    #dockerComposeFileArgs: # string. Environment Variables. 
    #projectName: '$(Build.Repository.Name)' # string. Project Name. Default: $(Build.Repository.Name).
    #qualifyImageNames: true # boolean. Qualify Image Names. Default: true.
    action: 'Run a Docker Compose command' # 'Build services' | 'Push services' | 'Run services' | 'Run a specific service' | 'Lock services' | 'Write service image digests' | 'Combine configuration' | 'Run a Docker Compose command'. Required. Action. Default: Run a Docker Compose command.
    #additionalImageTags: # string. Optional. Use when action = Build services || action = Push services. Additional Image Tags. 
    #includeSourceTags: false # boolean. Optional. Use when action = Build services || action = Push services. Include Source Tags. Default: false.
    #includeLatestTag: false # boolean. Optional. Use when action = Build services || action = Push services. Include Latest Tag. Default: false.
    #buildImages: true # boolean. Optional. Use when action = Run services. Build Images. Default: true.
    #serviceName: # string. Required when action = Run a specific service. Service Name. 
    #containerName: # string. Optional. Use when action = Run a specific service. Container Name. 
    #ports: # string. Optional. Use when action = Run a specific service. Ports. 
    #workingDirectory: # string. Alias: workDir. Optional. Use when action = Run a specific service. Working Directory. 
    #entrypoint: # string. Optional. Use when action = Run a specific service. Entry Point Override. 
    #containerCommand: # string. Optional. Use when action = Run a specific service. Command. 
    #detached: true # boolean. Optional. Use when action = Run services || action = Run a specific service. Run in Background. Default: true.
    #abortOnContainerExit: true # boolean. Optional. Use when action = Run services && detached == false. Abort on Container Exit. Default: true.
    #imageDigestComposeFile: '$(Build.StagingDirectory)/docker-compose.images.yml' # string. Required when action = Write service image digests. Image Digest Compose File. Default: $(Build.StagingDirectory)/docker-compose.images.yml.
    #removeBuildOptions: false # boolean. Optional. Use when action = Lock services || action = Combine configuration. Remove Build Options. Default: false.
    #baseResolveDirectory: # string. Optional. Use when action = Lock services || action = Combine configuration. Base Resolve Directory. 
    #outputDockerComposeFile: '$(Build.StagingDirectory)/docker-compose.yml' # string. Required when action = Lock services || action = Combine configuration. Output Docker Compose File. Default: $(Build.StagingDirectory)/docker-compose.yml.
    #dockerComposeCommand: # string. Required when action = Run a Docker Compose command. Command. 
    #arguments: # string. Optional. Use when action != Lock services && action != Combine configuration && action != Write service image digests. Arguments. 
  # Advanced Options
    #dockerHostEndpoint: # string. Docker Host Service Connection. 
    #nopIfNoDockerComposeFile: false # boolean. No-op if no Docker Compose File. Default: false.
    #requireAdditionalDockerComposeFiles: false # boolean. Require Additional Docker Compose Files. Default: false.
    #currentWorkingDirectory: '$(System.DefaultWorkingDirectory)' # string. Alias: cwd. Working Directory. Default: $(System.DefaultWorkingDirectory).
    #dockerComposePath: # string. Docker Compose executable Path.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Docker Compose v0
# Build, push or run multi-container Docker applications. Task can be used with Docker or Azure Container registry.
- task: DockerCompose@0
  inputs:
    containerregistrytype: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required. Container Registry Type. Default: Azure Container Registry.
    #dockerRegistryEndpoint: # string. Optional. Use when containerregistrytype = Container Registry. Docker Registry Service Connection. 
    #azureSubscription: # string. Alias: azureSubscriptionEndpoint. Optional. Use when containerregistrytype = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure Container Registry. 
    dockerComposeFile: '**/docker-compose.yml' # string. Required. Docker Compose File. Default: **/docker-compose.yml.
    #additionalDockerComposeFiles: # string. Additional Docker Compose Files. 
    #dockerComposeFileArgs: # string. Environment Variables. 
    #projectName: '$(Build.Repository.Name)' # string. Project Name. Default: $(Build.Repository.Name).
    #qualifyImageNames: true # boolean. Qualify Image Names. Default: true.
    action: 'Run a Docker Compose command' # 'Build services' | 'Push services' | 'Run services' | 'Run a specific service' | 'Lock services' | 'Write service image digests' | 'Combine configuration' | 'Run a Docker Compose command'. Required. Action. Default: Run a Docker Compose command.
    #additionalImageTags: # string. Optional. Use when action = Build services || action = Push services. Additional Image Tags. 
    #includeSourceTags: false # boolean. Optional. Use when action = Build services || action = Push services. Include Source Tags. Default: false.
    #includeLatestTag: false # boolean. Optional. Use when action = Build services || action = Push services. Include Latest Tag. Default: false.
    #buildImages: true # boolean. Optional. Use when action = Run services. Build Images. Default: true.
    #serviceName: # string. Required when action = Run a specific service. Service Name. 
    #containerName: # string. Optional. Use when action = Run a specific service. Container Name. 
    #ports: # string. Optional. Use when action = Run a specific service. Ports. 
    #workingDirectory: # string. Alias: workDir. Optional. Use when action = Run a specific service. Working Directory. 
    #entrypoint: # string. Optional. Use when action = Run a specific service. Entry Point Override. 
    #containerCommand: # string. Optional. Use when action = Run a specific service. Command. 
    #detached: true # boolean. Optional. Use when action = Run services || action = Run a specific service. Run in Background. Default: true.
    #abortOnContainerExit: true # boolean. Optional. Use when action = Run services && detached == false. Abort on Container Exit. Default: true.
    #imageDigestComposeFile: '$(Build.StagingDirectory)/docker-compose.images.yml' # string. Required when action = Write service image digests. Image Digest Compose File. Default: $(Build.StagingDirectory)/docker-compose.images.yml.
    #removeBuildOptions: false # boolean. Optional. Use when action = Lock services || action = Combine configuration. Remove Build Options. Default: false.
    #baseResolveDirectory: # string. Optional. Use when action = Lock services || action = Combine configuration. Base Resolve Directory. 
    #outputDockerComposeFile: '$(Build.StagingDirectory)/docker-compose.yml' # string. Required when action = Lock services || action = Combine configuration. Output Docker Compose File. Default: $(Build.StagingDirectory)/docker-compose.yml.
    #dockerComposeCommand: # string. Required when action = Run a Docker Compose command. Command. 
    #arguments: # string. Optional. Use when action != Lock services && action != Combine configuration && action != Write service image digests. Arguments. 
  # Advanced Options
    #dockerHostEndpoint: # string. Docker Host Service Connection. 
    #nopIfNoDockerComposeFile: false # boolean. No-op if no Docker Compose File. Default: false.
    #requireAdditionalDockerComposeFiles: false # boolean. Require Additional Docker Compose Files. Default: false.
    #currentWorkingDirectory: '$(System.DefaultWorkingDirectory)' # string. Alias: cwd. Working Directory. Default: $(System.DefaultWorkingDirectory).
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
# Docker Compose v0
# Build, push or run multi-container Docker applications. Task can be used with Docker or Azure Container registry.
- task: DockerCompose@0
  inputs:
    containerregistrytype: 'Azure Container Registry' # 'Azure Container Registry' | 'Container Registry'. Required. Container Registry Type. Default: Azure Container Registry.
    #dockerRegistryEndpoint: # string. Optional. Use when containerregistrytype = Container Registry. Docker Registry Service Connection. 
    #azureSubscription: # string. Alias: azureSubscriptionEndpoint. Optional. Use when containerregistrytype = Azure Container Registry. Azure subscription. 
    #azureContainerRegistry: # string. Optional. Use when containerregistrytype = Azure Container Registry. Azure Container Registry. 
    dockerComposeFile: '**/docker-compose.yml' # string. Required. Docker Compose File. Default: **/docker-compose.yml.
    #additionalDockerComposeFiles: # string. Additional Docker Compose Files. 
    #dockerComposeFileArgs: # string. Environment Variables. 
    #projectName: '$(Build.Repository.Name)' # string. Project Name. Default: $(Build.Repository.Name).
    #qualifyImageNames: true # boolean. Qualify Image Names. Default: true.
    action: 'Run a Docker Compose command' # 'Build services' | 'Push services' | 'Run services' | 'Run a specific service' | 'Lock services' | 'Write service image digests' | 'Combine configuration' | 'Run a Docker Compose command'. Required. Action. Default: Run a Docker Compose command.
    #additionalImageTags: # string. Optional. Use when action = Build services || action = Push services. Additional Image Tags. 
    #includeSourceTags: false # boolean. Optional. Use when action = Build services || action = Push services. Include Source Tags. Default: false.
    #includeLatestTag: false # boolean. Optional. Use when action = Build services || action = Push services. Include Latest Tag. Default: false.
    #buildImages: true # boolean. Optional. Use when action = Run services. Build Images. Default: true.
    #serviceName: # string. Required when action = Run a specific service. Service Name. 
    #containerName: # string. Optional. Use when action = Run a specific service. Container Name. 
    #ports: # string. Optional. Use when action = Run a specific service. Ports. 
    #workingDirectory: # string. Alias: workDir. Optional. Use when action = Run a specific service. Working Directory. 
    #entrypoint: # string. Optional. Use when action = Run a specific service. Entry Point Override. 
    #containerCommand: # string. Optional. Use when action = Run a specific service. Command. 
    #detached: true # boolean. Optional. Use when action = Run services || action = Run a specific service. Run in Background. Default: true.
    #abortOnContainerExit: true # boolean. Optional. Use when action = Run services && detached == false. Abort on Container Exit. Default: true.
    #imageDigestComposeFile: '$(Build.StagingDirectory)/docker-compose.images.yml' # string. Required when action = Write service image digests. Image Digest Compose File. Default: $(Build.StagingDirectory)/docker-compose.images.yml.
    #removeBuildOptions: false # boolean. Optional. Use when action = Lock services || action = Combine configuration. Remove Build Options. Default: false.
    #baseResolveDirectory: # string. Optional. Use when action = Lock services || action = Combine configuration. Base Resolve Directory. 
    #outputDockerComposeFile: '$(Build.StagingDirectory)/docker-compose.yml' # string. Required when action = Lock services || action = Combine configuration. Output Docker Compose File. Default: $(Build.StagingDirectory)/docker-compose.yml.
    #dockerComposeCommand: # string. Required when action = Run a Docker Compose command. Command. 
  # Advanced Options
    #dockerHostEndpoint: # string. Docker Host Service Connection. 
    #nopIfNoDockerComposeFile: false # boolean. No-op if no Docker Compose File. Default: false.
    #requireAdditionalDockerComposeFiles: false # boolean. Require Additional Docker Compose Files. Default: false.
    #currentWorkingDirectory: '$(System.DefaultWorkingDirectory)' # string. Alias: cwd. Working Directory. Default: $(System.DefaultWorkingDirectory).
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
Specifies an Azure Container Registry type if using ACR. Specify a Container Registry type if using any other container registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerRegistryEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`dockerRegistryEndpoint`** - **Docker Registry Service Connection**<br>
`string`. Optional. Use when `containerregistrytype = Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a Docker registry service connection. Required when commands need to authenticate using a registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `azureSubscriptionEndpoint`. `string`. Optional. Use when `containerregistrytype = Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an Azure subscription. Name of the Azure Service Connection. To manually set up the connection, see [Azure Resource Manager service connection](/azure/devops/pipelines/library/connect-to-azure).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureContainerRegistry"::: -->
:::moniker range="<=azure-pipelines"

**`azureContainerRegistry`** - **Azure Container Registry**<br>
`string`. Optional. Use when `containerregistrytype = Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an Azure Container Registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerComposeFile"::: -->
:::moniker range="<=azure-pipelines"

**`dockerComposeFile`** - **Docker Compose File**<br>
`string`. Required. Default value: `**/docker-compose.yml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the file path to the primary Docker Compose file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="additionalDockerComposeFiles"::: -->
:::moniker range="<=azure-pipelines"

**`additionalDockerComposeFiles`** - **Additional Docker Compose Files**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional Docker Compose files that are combined with the primary Docker Compose file. Relative paths are resolved relative to the directory containing the primary Docker Compose file. If a specified file is not found, it is ignored. Specify each file path on a new line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerComposeFileArgs"::: -->
:::moniker range="<=azure-pipelines"

**`dockerComposeFileArgs`** - **Environment Variables**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies any environment variables that are set.

Format as follows:

- List each `name=value` pair on a new line.
- Use the `|` operator in YAML to preserve new lines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="projectName"::: -->
:::moniker range="<=azure-pipelines"

**`projectName`** - **Project Name**<br>
`string`. Default value: `$(Build.Repository.Name)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the project name to use by default to name images and containers.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="qualifyImageNames"::: -->
:::moniker range="<=azure-pipelines"

**`qualifyImageNames`** - **Qualify Image Names**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
By default, specifies the Docker registry service connection's hostname.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="action"::: -->
:::moniker range="<=azure-pipelines"

**`action`** - **Action**<br>
`string`. Required. Allowed values: `Build services` (Build service images), `Push services` (Push service images), `Run services` (Run service images), `Run a specific service` (Run a specific service image), `Lock services` (Lock service images), `Write service image digests`, `Combine configuration`, `Run a Docker Compose command`. Default value: `Run a Docker Compose command`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a Docker Compose action from the list of allowed values.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="additionalImageTags"::: -->
:::moniker range="<=azure-pipelines"

**`additionalImageTags`** - **Additional Image Tags**<br>
`string`. Optional. Use when `action = Build services || action = Push services`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional tags for the Docker images being built or pushed.  You can specify multiple tags separating each with a line feed `\n`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeSourceTags"::: -->
:::moniker range="<=azure-pipelines"

**`includeSourceTags`** - **Include Source Tags**<br>
`boolean`. Optional. Use when `action = Build services || action = Push services`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies Git tags when building or pushing Docker images.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeLatestTag"::: -->
:::moniker range="<=azure-pipelines"

**`includeLatestTag`** - **Include Latest Tag**<br>
`boolean`. Optional. Use when `action = Build services || action = Push services`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the *latest* tag when building or pushing Docker images.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildImages"::: -->
:::moniker range="<=azure-pipelines"

**`buildImages`** - **Build Images**<br>
`boolean`. Optional. Use when `action = Run services`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies build images before starting service containers.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serviceName"::: -->
:::moniker range="<=azure-pipelines"

**`serviceName`** - **Service Name**<br>
`string`. Required when `action = Run a specific service`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the service you want to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerName"::: -->
:::moniker range="<=azure-pipelines"

**`containerName`** - **Container Name**<br>
`string`. Optional. Use when `action = Run a specific service`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the service container you want to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ports"::: -->
:::moniker range="<=azure-pipelines"

**`ports`** - **Ports**<br>
`string`. Optional. Use when `action = Run a specific service`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies ports in the service container to publish to the host. Add each `host-port:container-port` binding on a new line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`workingDirectory`** - **Working Directory**<br>
Input alias: `workDir`. `string`. Optional. Use when `action = Run a specific service`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the working directory for the service container.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="entrypoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`entrypoint`** - **Entry Point Override**<br>
`string`. Optional. Use when `action = Run a specific service`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an override value for the default entry point of the service container.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerCommand"::: -->
:::moniker range="<=azure-pipelines"

**`containerCommand`** - **Command**<br>
`string`. Optional. Use when `action = Run a specific service`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the command to run in the service container. For example, if the image contains a simple Python Flask web application you can specify `python app.py` to launch the web application.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="detached"::: -->
:::moniker range=">=azure-pipelines-2019"

**`detached`** - **Run in Background**<br>
`boolean`. Optional. Use when `action = Run services || action = Run a specific service`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the service containers to run in the background.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="abortOnContainerExit"::: -->
:::moniker range="<=azure-pipelines"

**`abortOnContainerExit`** - **Abort on Container Exit**<br>
`boolean`. Optional. Use when `action = Run services && detached == false`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies all containers that should stop when any container exits.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageDigestComposeFile"::: -->
:::moniker range="<=azure-pipelines"

**`imageDigestComposeFile`** - **Image Digest Compose File**<br>
`string`. Required when `action = Write service image digests`. Default value: `$(Build.StagingDirectory)/docker-compose.images.yml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to a Docker Compose file that is created and populated with the full image repository digests of each service's Docker image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="removeBuildOptions"::: -->
:::moniker range="<=azure-pipelines"

**`removeBuildOptions`** - **Remove Build Options**<br>
`boolean`. Optional. Use when `action = Lock services || action = Combine configuration`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies if build options should be removed from the output Docker Compose file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="baseResolveDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`baseResolveDirectory`** - **Base Resolve Directory**<br>
`string`. Optional. Use when `action = Lock services || action = Combine configuration`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the base directory from which relative paths in the output Docker Compose file should be resolved.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputDockerComposeFile"::: -->
:::moniker range="<=azure-pipelines"

**`outputDockerComposeFile`** - **Output Docker Compose File**<br>
`string`. Required when `action = Lock services || action = Combine configuration`. Default value: `$(Build.StagingDirectory)/docker-compose.yml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to an output Docker Compose file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerComposeCommand"::: -->
:::moniker range="<=azure-pipelines"

**`dockerComposeCommand`** - **Command**<br>
`string`. Required when `action = Run a Docker Compose command`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Docker Compose command to execute with arguments. For example, `rm --all` to remove all stopped service containers.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range=">=azure-pipelines-2020"

**`arguments`** - **Arguments**<br>
`string`. Optional. Use when `action != Lock services && action != Combine configuration && action != Write service image digests`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies Docker Compose command options.

Example: For the build command, `--pull --compress --parallel`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerHostEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`dockerHostEndpoint`** - **Docker Host Service Connection**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a Docker host service connection. Defaults to the agent's host.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nopIfNoDockerComposeFile"::: -->
:::moniker range="<=azure-pipelines"

**`nopIfNoDockerComposeFile`** - **No-op if no Docker Compose File**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a value to skip the task if the Docker Compose file does not exist. This option is useful when the task offers optional behavior based on the existence of a Docker Compose file in the repository.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="requireAdditionalDockerComposeFiles"::: -->
:::moniker range="<=azure-pipelines"

**`requireAdditionalDockerComposeFiles`** - **Require Additional Docker Compose Files**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a value to produce an error if the additional Docker Compose files do not exist. This option overrides the default behavior that would ignore a file if it does not exist.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="currentWorkingDirectory"::: -->
:::moniker range="<=azure-pipelines"

**`currentWorkingDirectory`** - **Working Directory**<br>
Input alias: `cwd`. `string`. Default value: `$(System.DefaultWorkingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the working directory for the Docker Compose command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerComposePath"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`dockerComposePath`** - **Docker Compose executable Path**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a path to determine if the docker-compose executable is used.
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

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="DockerComposeOutput"::: -->
**`DockerComposeOutput`**<br><!-- :::editable-content name="Value"::: -->
The path to the files which contain the output of the command. This can contain multiple file paths (separated by newline characters) such as, dockerComposeRun command (one for running and one for down), dockerPush (one for each image pushed), dockerBuild (the build itself and all the tag commands) and dockerDigest (one for each image pulled). The other commands only output one file.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to build, push or run multi-container Docker applications. Use this task with a Docker registry or an Azure Container Registry.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

* [Azure Container Registry](#azure-container-registry)
* [Other container registries](#other-container-registries)
* [Build service images](#build-service-images)
* [Push service images](#push-service-images)
* [Run service images](#run-service-images)
* [Run a specific service image](#run-a-specific-service-image)
* [Lock service images](#lock-service-images)
* [Write service image digests](#write-service-image-digests)
* [Combine configuration](#combine-configuration)
* [Run a Docker Compose command](#run-a-docker-compose-command)

### Azure Container Registry

This YAML example specifies the inputs for Azure Container Registry:

```YAML
variables:
  azureContainerRegistry: Contoso.azurecr.io
  azureSubscriptionEndpoint: Contoso
steps:
- task: DockerCompose@0
  displayName: Container registry login
  inputs:
    containerregistrytype: Azure Container Registry
    azureSubscriptionEndpoint: $(azureSubscriptionEndpoint)
    azureContainerRegistry: $(azureContainerRegistry)
```

### Other container registries

The **containerregistrytype** value is required when using any container registry other than ACR. Use `containerregistrytype: Container Registry` in this case.

This YAML example specifies a container registry other than ACR where **Contoso**
is the name of the Docker registry service connection for the container registry:

```YAML
- task: DockerCompose@0
  displayName: Container registry login
  inputs:
    containerregistrytype: Container Registry
    dockerRegistryEndpoint: Contoso
```

### Build service images

This YAML example builds the image where the image name is qualified on the basis of the inputs related to Azure Container Registry:

```YAML
- task: DockerCompose@0
  displayName: Build services
  inputs:
    action: Build services
    azureSubscriptionEndpoint: $(azureSubscriptionEndpoint)
    azureContainerRegistry: $(azureContainerRegistry)
    dockerComposeFile: docker-compose.yml
    projectName: $(Build.Repository.Name)
    qualifyImageNames: true
    additionalImageTags: $(Build.BuildId)
    dockerComposeFileArgs: |
      firstArg=$(firstArg)
      secondArg=$(secondArg)

```

### Push service images

This YAML example pushes an image to a container registry:

```YAML
- task: DockerCompose@0
  displayName: Push services
  inputs:
    action: Push services
    azureSubscriptionEndpoint: $(azureSubscriptionEndpoint)
    azureContainerRegistry: $(azureContainerRegistry)
    dockerComposeFile: docker-compose.yml
    projectName: $(Build.Repository.Name)
    qualifyImageNames: true
    additionalImageTags: $(Build.BuildId)
```

### Run service images

This YAML example runs services:

```YAML
- task: DockerCompose@0
  displayName: Run services
  inputs:
    action: Run services
    azureSubscriptionEndpoint: $(azureSubscriptionEndpoint)
    azureContainerRegistry: $(azureContainerRegistry)
    dockerComposeFile: docker-compose.ci.build.yml
    projectName: $(Build.Repository.Name)
    qualifyImageNames: true
    buildImages: true
    abortOnContainerExit: true
    detached: true
```

### Run a specific service image

This YAML example runs a specific service:

```YAML
- task: DockerCompose@0
  displayName: Run a specific service
  inputs:
    action: Run a specific service
    azureSubscriptionEndpoint: $(azureSubscriptionEndpoint)
    azureContainerRegistry: $(azureContainerRegistry)
    dockerComposeFile: docker-compose.yml
    projectName: $(Build.Repository.Name)
    qualifyImageNames: true
    serviceName: myhealth.web
    ports: 80:80
    detached: true
```

### Lock service images

This YAML example locks services:

```YAML
- task: DockerCompose@0
  displayName: Lock services
  inputs:
    action: Lock services
    azureSubscriptionEndpoint: $(azureSubscriptionEndpoint)
    azureContainerRegistry: $(azureContainerRegistry)
    dockerComposeFile: docker-compose.yml
    projectName: $(Build.Repository.Name)
    qualifyImageNames: true
    outputDockerComposeFile: $(Build.StagingDirectory)/docker-compose.yml
```

### Write service image digests

This YAML example writes service image digests:

```YAML
- task: DockerCompose@0
  displayName: Write service image digests
  inputs:
    action: Write service image digests
    azureSubscriptionEndpoint: $(azureSubscriptionEndpoint)
    azureContainerRegistry: $(azureContainerRegistry)
    dockerComposeFile: docker-compose.yml
    projectName: $(Build.Repository.Name)
    qualifyImageNames: true
    imageDigestComposeFile: $(Build.StagingDirectory)/docker-compose.images.yml 
```

### Combine configuration

This YAML example combines configurations:

```YAML
- task: DockerCompose@0
  displayName: Combine configuration
  inputs:
    action: Combine configuration
    azureSubscriptionEndpoint: $(azureSubscriptionEndpoint)
    azureContainerRegistry: $(azureContainerRegistry)
    dockerComposeFile: docker-compose.yml
    additionalDockerComposeFiles: docker-compose.override.yml
    projectName: $(Build.Repository.Name)
    qualifyImageNames: true
    outputDockerComposeFile: $(Build.StagingDirectory)/docker-compose.yml
```
### Run a Docker Compose command

This YAML example runs a docker Compose command:

```YAML
- task: DockerCompose@0
  displayName: Run a Docker Compose command
  inputs:
    action: Run a Docker Compose command
    azureSubscriptionEndpoint: $(azureSubscriptionEndpoint)
    azureContainerRegistry: $(azureContainerRegistry)
    dockerComposeFile: docker-compose.yml 
    projectName: $(Build.Repository.Name)
    qualifyImageNames: true
    dockerComposeCommand: rm
```
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
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
