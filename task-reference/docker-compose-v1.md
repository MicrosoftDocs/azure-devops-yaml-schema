---
title: DockerCompose@1 - Docker Compose v1 task
description: Build, push or run multi-container Docker applications. Task can be used with Docker or Azure Container registry.
ms.date: 06/24/2025
monikerRange: "=azure-pipelines"
---

# DockerCompose@1 - Docker Compose v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Build, push or run multi-container Docker applications. Task can be used with Docker or Azure Container registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Docker Compose v1
# Build, push or run multi-container Docker applications. Task can be used with Docker or Azure Container registry.
- task: DockerCompose@1
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
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="containerregistrytype"::: -->
:::moniker range="=azure-pipelines"

**`containerregistrytype`** - **Container Registry Type**<br>
`string`. Required. Allowed values: `Azure Container Registry`, `Container Registry`. Default value: `Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Container Registry Type.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerRegistryEndpoint"::: -->
:::moniker range="=azure-pipelines"

**`dockerRegistryEndpoint`** - **Docker Registry Service Connection**<br>
`string`. Optional. Use when `containerregistrytype = Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker registry service connection. Required for commands that need to authenticate with a registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
[Input alias](index.md#what-are-task-input-aliases): `azureSubscriptionEndpoint`. `string`. Optional. Use when `containerregistrytype = Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure subscription.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureContainerRegistry"::: -->
:::moniker range="=azure-pipelines"

**`azureContainerRegistry`** - **Azure Container Registry**<br>
`string`. Optional. Use when `containerregistrytype = Azure Container Registry`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure Container Registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerComposeFile"::: -->
:::moniker range="=azure-pipelines"

**`dockerComposeFile`** - **Docker Compose File**<br>
`string`. Required. Default value: `**/docker-compose.yml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the primary Docker Compose file to use.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="additionalDockerComposeFiles"::: -->
:::moniker range="=azure-pipelines"

**`additionalDockerComposeFiles`** - **Additional Docker Compose Files**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional Docker Compose files to be combined with the primary Docker Compose file. Relative paths are resolved relative to the directory containing the primary Docker Compose file. If a specified file is not found, it is ignored. Specify each file path on a new line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerComposeFileArgs"::: -->
:::moniker range="=azure-pipelines"

**`dockerComposeFileArgs`** - **Environment Variables**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Environment variables to be set during the command. Specify each name=value pair on a new line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="projectName"::: -->
:::moniker range="=azure-pipelines"

**`projectName`** - **Project Name**<br>
`string`. Default value: `$(Build.Repository.Name)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Project name used for default naming of images and containers.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="qualifyImageNames"::: -->
:::moniker range="=azure-pipelines"

**`qualifyImageNames`** - **Qualify Image Names**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Qualify image names for built services with the Docker registry service connection's hostname if not otherwise specified.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="action"::: -->
:::moniker range="=azure-pipelines"

**`action`** - **Action**<br>
`string`. Required. Allowed values: `Build services` (Build service images), `Push services` (Push service images), `Run services` (Run service images), `Run a specific service` (Run a specific service image), `Lock services` (Lock service images), `Write service image digests`, `Combine configuration`, `Run a Docker Compose command`. Default value: `Run a Docker Compose command`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker Compose action.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="additionalImageTags"::: -->
:::moniker range="=azure-pipelines"

**`additionalImageTags`** - **Additional Image Tags**<br>
`string`. Optional. Use when `action = Build services || action = Push services`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional tags for the Docker images being built or pushed.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeSourceTags"::: -->
:::moniker range="=azure-pipelines"

**`includeSourceTags`** - **Include Source Tags**<br>
`boolean`. Optional. Use when `action = Build services || action = Push services`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Include Git tags when building or pushing Docker images.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeLatestTag"::: -->
:::moniker range="=azure-pipelines"

**`includeLatestTag`** - **Include Latest Tag**<br>
`boolean`. Optional. Use when `action = Build services || action = Push services`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Include the 'latest' tag when building or pushing Docker images.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildImages"::: -->
:::moniker range="=azure-pipelines"

**`buildImages`** - **Build Images**<br>
`boolean`. Optional. Use when `action = Run services`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Build images before starting service containers.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serviceName"::: -->
:::moniker range="=azure-pipelines"

**`serviceName`** - **Service Name**<br>
`string`. Required when `action = Run a specific service`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the specific service to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerName"::: -->
:::moniker range="=azure-pipelines"

**`containerName`** - **Container Name**<br>
`string`. Optional. Use when `action = Run a specific service`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the specific service container to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ports"::: -->
:::moniker range="=azure-pipelines"

**`ports`** - **Ports**<br>
`string`. Optional. Use when `action = Run a specific service`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Ports in the specific service container to publish to the host. Specify each host-port:container-port binding on a new line.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workingDirectory"::: -->
:::moniker range="=azure-pipelines"

**`workingDirectory`** - **Working Directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `workDir`. `string`. Optional. Use when `action = Run a specific service`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The working directory for the specific service container.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="entrypoint"::: -->
:::moniker range="=azure-pipelines"

**`entrypoint`** - **Entry Point Override**<br>
`string`. Optional. Use when `action = Run a specific service`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Override the default entry point for the specific service container.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="containerCommand"::: -->
:::moniker range="=azure-pipelines"

**`containerCommand`** - **Command**<br>
`string`. Optional. Use when `action = Run a specific service`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Command to run in the specific service container. For example, if the image contains a simple Python Flask web application you can specify 'python app.py' to launch the web application.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="detached"::: -->
:::moniker range="=azure-pipelines"

**`detached`** - **Run in Background**<br>
`boolean`. Optional. Use when `action = Run services || action = Run a specific service`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Run the service containers in the background.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="abortOnContainerExit"::: -->
:::moniker range="=azure-pipelines"

**`abortOnContainerExit`** - **Abort on Container Exit**<br>
`boolean`. Optional. Use when `action = Run services && detached == false`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Stop all containers when any container exits.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="imageDigestComposeFile"::: -->
:::moniker range="=azure-pipelines"

**`imageDigestComposeFile`** - **Image Digest Compose File**<br>
`string`. Required when `action = Write service image digests`. Default value: `$(Build.StagingDirectory)/docker-compose.images.yml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to a Docker Compose file that is created and populated with the full image repository digests of each service's Docker image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="removeBuildOptions"::: -->
:::moniker range="=azure-pipelines"

**`removeBuildOptions`** - **Remove Build Options**<br>
`boolean`. Optional. Use when `action = Lock services || action = Combine configuration`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Remove the build options from the output Docker Compose file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="baseResolveDirectory"::: -->
:::moniker range="=azure-pipelines"

**`baseResolveDirectory`** - **Base Resolve Directory**<br>
`string`. Optional. Use when `action = Lock services || action = Combine configuration`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The base directory from which relative paths in the output Docker Compose file should be resolved.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="outputDockerComposeFile"::: -->
:::moniker range="=azure-pipelines"

**`outputDockerComposeFile`** - **Output Docker Compose File**<br>
`string`. Required when `action = Lock services || action = Combine configuration`. Default value: `$(Build.StagingDirectory)/docker-compose.yml`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to an output Docker Compose file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerComposeCommand"::: -->
:::moniker range="=azure-pipelines"

**`dockerComposeCommand`** - **Command**<br>
`string`. Required when `action = Run a Docker Compose command`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Docker Compose command to execute with arguments. For example, 'rm --all' to remove all stopped service containers.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range="=azure-pipelines"

**`arguments`** - **Arguments**<br>
`string`. Optional. Use when `action != Lock services && action != Combine configuration && action != Write service image digests`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Docker Compose command options. Ex:<br> For build command,<br>--pull --compress --parallel.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerHostEndpoint"::: -->
:::moniker range="=azure-pipelines"

**`dockerHostEndpoint`** - **Docker Host Service Connection**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Docker host service connection. Defaults to the agent's host.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="nopIfNoDockerComposeFile"::: -->
:::moniker range="=azure-pipelines"

**`nopIfNoDockerComposeFile`** - **No-op if no Docker Compose File**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the Docker Compose file does not exist, skip this task. This is useful when the task offers optional behavior based on the existence of a Docker Compose file in the repository.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="requireAdditionalDockerComposeFiles"::: -->
:::moniker range="=azure-pipelines"

**`requireAdditionalDockerComposeFiles`** - **Require Additional Docker Compose Files**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Produces an error if the additional Docker Compose files do not exist. This overrides the default behavior which is to ignore a file if it does not exist.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="currentWorkingDirectory"::: -->
:::moniker range="=azure-pipelines"

**`currentWorkingDirectory`** - **Working Directory**<br>
[Input alias](index.md#what-are-task-input-aliases): `cwd`. `string`. Default value: `$(System.DefaultWorkingDirectory)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Working directory for the Docker Compose command.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dockerComposePath"::: -->
:::moniker range="=azure-pipelines"

**`dockerComposePath`** - **Docker Compose executable Path**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This docker-compose executable will be used if the path is provided.
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

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="DockerComposeOutput"::: -->
**`DockerComposeOutput`**<br><!-- :::editable-content name="Value"::: -->
The path of the file(s) which contains the output of the command. This can contain multiple file paths (separated by newline characters) in case of dockerComposeRun command (one for running and one for down), dockerPush (one for each image pushed), dockerBuild (the build itself and all the tag commands) and dockerDigest (one for each image pulled). The other commands only output one file.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

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
| Agent version | All supported agent versions. |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->