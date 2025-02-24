---
title: Docker@2 - Docker v2 task
description: Build or push Docker images, login or logout, start or stop containers, or run a Docker command.
ms.date: 02/24/2025
monikerRange: ">=azure-pipelines-2019.1"
---

# Docker@2 - Docker v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020.1"

<!-- :::editable-content name="description"::: -->
Build or push Docker images, log in or log out, start or stop containers, or run a Docker command.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Build or push Docker images, log in or log out, or run a Docker command.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Docker v2
# Build or push Docker images, login or logout, start or stop containers, or run a Docker command.
- task: Docker@2
  inputs:
  # Container Repository
    #containerRegistry: # string. Container registry. 
    #repository: # string. Optional. Use when command != login && command != logout && command != start && command != stop. Container repository. 
  # Commands
    command: 'buildAndPush' # 'buildAndPush' | 'build' | 'push' | 'login' | 'logout' | 'start' | 'stop'. Required. Command. Default: buildAndPush.
    Dockerfile: '**/Dockerfile' # string. Required when command = build || command = buildAndPush. Dockerfile. Default: **/Dockerfile.
    #buildContext: '**' # string. Optional. Use when command = build || command = buildAndPush. Build context. Default: **.
    #tags: '$(Build.BuildId)' # string. Optional. Use when command = build || command = push || command = buildAndPush. Tags. Default: $(Build.BuildId).
    #arguments: # string. Optional. Use when command != login && command != logout && command != buildAndPush. Arguments. 
    #addPipelineData: true # boolean. Add Pipeline metadata to image(s). Default: true.
    #addBaseImageData: true # boolean. Add base image metadata to image(s). Default: true.
    #container: # string. Optional. Use when command = start || command = stop. Container.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

```yaml
# Docker v2
# Build or push Docker images, login or logout, start or stop containers, or run a Docker command.
- task: Docker@2
  inputs:
  # Container Repository
    #containerRegistry: # string. Container registry. 
    #repository: # string. Optional. Use when command != login && command != logout && command != start && command != stop. Container repository. 
  # Commands
    command: 'buildAndPush' # 'buildAndPush' | 'build' | 'push' | 'login' | 'logout' | 'start' | 'stop'. Required. Command. Default: buildAndPush.
    Dockerfile: '**/Dockerfile' # string. Required when command = build || command = buildAndPush. Dockerfile. Default: **/Dockerfile.
    #buildContext: '**' # string. Optional. Use when command = build || command = buildAndPush. Build context. Default: **.
    #tags: '$(Build.BuildId)' # string. Optional. Use when command = build || command = push || command = buildAndPush. Tags. Default: $(Build.BuildId).
    #arguments: # string. Optional. Use when command != login && command != logout && command != buildAndPush. Arguments. 
    #addPipelineData: true # boolean. Add Pipeline metadata to image(s). Default: true.
    #container: # string. Optional. Use when command = start || command = stop. Container.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
# Docker v2
# Build or push Docker images, login or logout, or run a Docker command.
- task: Docker@2
  inputs:
  # Container Repository
    #containerRegistry: # string. Container registry. 
    #repository: # string. Optional. Use when command != login && command != logout. Container repository. 
  # Commands
    command: 'buildAndPush' # 'buildAndPush' | 'build' | 'push' | 'login' | 'logout'. Required. Command. Default: buildAndPush.
    Dockerfile: '**/Dockerfile' # string. Required when command = build || command = buildAndPush. Dockerfile. Default: **/Dockerfile.
    #buildContext: '**' # string. Optional. Use when command = build || command = buildAndPush. Build context. Default: **.
    #tags: '$(Build.BuildId)' # string. Optional. Use when command = build || command = push || command = buildAndPush. Tags. Default: $(Build.BuildId).
    #arguments: # string. Optional. Use when command != login && command != logout && command != buildAndPush. Arguments. 
    #addPipelineData: true # boolean. Add Pipeline metadata to image(s). Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
# Docker v2
# Build or push Docker images, login or logout, or run a Docker command.
- task: Docker@2
  inputs:
  # Container Repository
    #containerRegistry: # string. Container registry. 
    #repository: # string. Optional. Use when command != login && command != logout. Container repository. 
  # Commands
    command: 'buildAndPush' # 'buildAndPush' | 'build' | 'push' | 'login' | 'logout'. Required. Command. Default: buildAndPush.
    Dockerfile: '**/Dockerfile' # string. Required when command = build || command = buildAndPush. Dockerfile. Default: **/Dockerfile.
    #buildContext: '**' # string. Optional. Use when command = build || command = buildAndPush. Build context. Default: **.
    #tags: '$(Build.BuildId)' # string. Optional. Use when command = build || command = push || command = buildAndPush. Tags. Default: $(Build.BuildId).
    #arguments: # string. Optional. Use when command != login && command != logout && command != buildAndPush. Arguments.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="containerRegistry"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`containerRegistry`** - **Container registry**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Name of the [Docker registry service connection](/azure/devops/pipelines/library/service-endpoints#docker-registry-service-connection). Required for commands that perform authentication with a registry.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="repository"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`repository`** - **Container repository**<br>
`string`. Optional. Use when `command != login && command != logout && command != start && command != stop`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the repository.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

**`repository`** - **Container repository**<br>
`string`. Optional. Use when `command != login && command != logout`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the repository.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="command"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`command`** - **Command**<br>
`string`. Required. Allowed values: `buildAndPush`, `build`, `push`, `login`, `logout`, `start`, `stop`. Default value: `buildAndPush`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Docker command to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

**`command`** - **Command**<br>
`string`. Required. Allowed values: `buildAndPush`, `build`, `push`, `login`, `logout`. Default value: `buildAndPush`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the Docker command to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Dockerfile"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`Dockerfile`** - **Dockerfile**<br>
`string`. Required when `command = build || command = buildAndPush`. Default value: `**/Dockerfile`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the Docker file. The task uses the first Docker file it finds to build the image.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="buildContext"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`buildContext`** - **Build context**<br>
`string`. Optional. Use when `command = build || command = buildAndPush`. Default value: `**`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the path to the build context. Pass `**` to indicate the directory that contains the Docker file.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`tags`** - **Tags**<br>
`string`. Optional. Use when `command = build || command = push || command = buildAndPush`. Default value: `$(Build.BuildId)`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a list of comma-separated tags. These tags are used in `build`, `push` and `buildAndPush` commands.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="arguments"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`arguments`** - **Arguments**<br>
`string`. Optional. Use when `command != login && command != logout && command != buildAndPush`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional arguments to pass to the Docker client. If using the value `buildAndPush` for the command parameter, the arguments property is ignored.

Example: Using the build command, `--build-arg HTTP_PROXY=http://10.20.30.2:1234 --quiet`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addPipelineData"::: -->
:::moniker range=">=azure-pipelines-2020"

**`addPipelineData`** - **Add Pipeline metadata to image(s)**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
By default, pipeline data like source branch name, or build ID are added and help with traceability. For example, you can inspect an image to find out which pipeline built the image. You can opt out of this default behavior.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="addBaseImageData"::: -->
:::moniker range=">=azure-pipelines-2022"

**`addBaseImageData`** - **Add base image metadata to image(s)**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
By default, base image data like base image name, or digest are added and help with traceability. You can opt out of this default behavior.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="container"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`container`** - **Container**<br>
`string`. Optional. Use when `command = start || command = stop`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of the container resource to start or stop. Use this command with `start` and `stop` commands.
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

<!-- :::item name="DockerOutput"::: -->
**`DockerOutput`**<br><!-- :::editable-content name="Value"::: -->
Specifies the path to the files that contain the command output. You can list two file paths on separate lines for the `buildAndPush` command, and one file path for any other command.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

The following are the key benefits of using the Docker task instead of directly using Docker client binary in a script. 

- **Integration with Docker registry service connection** - The task makes it easy to use a Docker registry service connection for connecting to any container registry. Once signed in, you can add follow up tasks that execute other tasks or scripts by leveraging the sign on used by the Docker task. For example, use the Docker task to sign in to any Azure Container Registry, and then use another task or script to build and push an image to the registry.

- **Metadata added as labels** - The task adds traceability-related metadata to the image in the following labels -  
  - com.azure.dev.image.build.buildnumber
  - com.azure.dev.image.build.builduri
  - com.azure.dev.image.build.definitionname
  - com.azure.dev.image.build.repository.name
  - com.azure.dev.image.build.repository.uri
  - com.azure.dev.image.build.sourcebranchname
  - com.azure.dev.image.build.sourceversion
  - com.azure.dev.image.release.definitionname
  - com.azure.dev.image.release.releaseid
  - com.azure.dev.image.release.releaseweburl
  - com.azure.dev.image.system.teamfoundationcollectionuri
  - com.azure.dev.image.system.teamproject

### Troubleshooting

#### Why does the Docker task ignore arguments passed to the buildAndPush command?

A Docker task configured using the `buildAndPush` command ignores the arguments passed because they become ambiguous to the internal build and push commands. You can split your command into separate build and push steps and pass the suitable arguments. For example, see this [stackoverflow post](https://stackoverflow.com/questions/60287354/i-am-using-azure-devops-to-build-and-push-my-docker-image-how-can-i-pass-argume).

#### DockerV2 only supports Docker registry service connection and not support ARM service connection. How can I use an existing Azure service principal (SPN) for authentication in Docker task?

You can create a Docker registry service connection using your Azure SPN credentials. Choose the others from Registry type and provide the details as follows:

```
Docker Registry:    Your container registry URL (eg. https://myacr.azurecr.io)
Docker ID:          Service principal client ID
Password:           Service principal key
```
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

### Login

# [YAML](#tab/yaml)

The following YAML snippet shows a container registry sign on using a Docker registry service connection.

```YAML
- task: Docker@2
  displayName: Login to ACR
  inputs:
    command: login
    containerRegistry: dockerRegistryServiceConnection1
```

# [Classic](#tab/classic)

Use a Docker registry connection with the Docker login command. Set the **Container Repository** to your Docker registry service connection.

:::image type="content" source="media/docker-classic-container-login.png" alt-text="Screenshot of Docker container registry task login. ":::

* * *

### Build and Push

A convenience command called `buildAndPush` allows the build and push of images to a container registry in a single command.

# [YAML](#tab/yaml)

The following YAML snippet is an example of building and pushing multiple tags of an image to multiple registries.

```YAML
steps:
- task: Docker@2
  displayName: Login to ACR
  inputs:
    command: login
    containerRegistry: dockerRegistryServiceConnection1
- task: Docker@2
  displayName: Login to Docker Hub
  inputs:
    command: login
    containerRegistry: dockerRegistryServiceConnection2
- task: Docker@2
  displayName: Build and Push
  inputs:
    command: buildAndPush
    repository: contosoRepository # username/contosoRepository for DockerHub
    tags: |
      tag1
      tag2
```

In the above snippet, the images ```contosoRepository:tag1``` and ```contosoRepository:tag2``` are built and pushed to the container registries corresponding to ```dockerRegistryServiceConnection1``` and ```dockerRegistryServiceConnection2```.

If you want to build and push to a specific authenticated container registry instead of building and pushing to all authenticated container registries at once, explicitly specify the ```containerRegistry``` input with ```command: buildAndPush``` as shown:

```YAML
steps:
- task: Docker@2
  displayName: Build and Push
  inputs:
    command: buildAndPush
    containerRegistry: dockerRegistryServiceConnection1
    repository: contosoRepository
    tags: |
      tag1
      tag2
```

# [Classic](#tab/classic)

Use the `buildAndPush` command to build and push images to a container registry in a single command. See the example for building and pushing multiple tags of an image with authentication to DockerHub.  

:::image type="content" source="media/docker-classic-build-push.png" alt-text="Screenshot of build and push Docker classic task.":::

You can build and push without authentication.  In the `buildAndPush` tasks, the images for `tag1` and `tag2` are built and pushed to the container registries corresponding to service connections set up in the previous two log on tasks.

:::image type="content" source="media/docker-classic-build-push-two-containers.png" alt-text="Screenshot of Classic pipeline with build and push to two Docker container registries.":::

* * *

### Logout

# [YAML](#tab/yaml)

The following YAML snippet shows how to log out from a container registry using a Docker registry service connection.

```YAML
- task: Docker@2
  displayName: Logout of ACR
  inputs:
    command: logout
    containerRegistry: dockerRegistryServiceConnection1
```
# [Classic](#tab/classic)

Log out from your Docker registry service connection with the Docker task.

:::image type="content" source="media/docker-classic-logout.png" alt-text="Screenshot of docker task logout.":::

* * *

### Start/stop

Use this task to control job and service containers. This usage is uncommon, but occasionally used in unique circumstances.

```yaml
resources:
  containers:
  - container: builder
    image: ubuntu:18.04
steps:
- script: echo "I can run inside the container (it starts by default)"
  target:
    container: builder
- task: Docker@2
  inputs:
    command: stop
    container: builder
# any task beyond this point would not be able to target the builder container
# because it's been stopped
```

### Other commands and arguments

The command and argument inputs are used to pass additional arguments for build or push commands using Docker client binary as shown in the example.

```yaml
steps:
- task: Docker@2
  displayName: Login to ACR
  inputs:
    command: login
    containerRegistry: dockerRegistryServiceConnection1
- task: Docker@2
  displayName: Build
  inputs:
    command: build
    repository: contosoRepository # username/contosoRepository for DockerHub
    tags: tag1
    arguments: --secret id=mysecret,src=mysecret.txt
```

> [!NOTE]
> The arguments input is evaluated for all commands except `buildAndPush`. `buildAndPush` is a convenience command (`build` followed by `push`), `arguments` input is ignored when it is used.
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2020.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.172.0 or greater |
| Task category | Build |

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

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