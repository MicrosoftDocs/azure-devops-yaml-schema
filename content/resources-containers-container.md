---
title: resources.containers.container definition
description: A container resource used to reference a container image.
ms.date: 03/01/2023
monikerRange: ">=azure-pipelines-2019"
---

# resources.containers.container definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
A container resource references a container image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020.1"

```yaml
containers:
- container: string # Required as first property. ID for the container.
  image: string # Required. Container image tag.
  type: string # Type of the registry like ACR or GCR.
  trigger: trigger | none | true # Specify none to disable, true to trigger on all image tags, or use the full syntax as described in the following examples.
  endpoint: string # ID of the service endpoint connecting to a private container registry.
  env: # Variables to map into the container's environment.
    string: string # Name/value pairs
  mapDockerSocket: boolean # Set this flag to false to force the agent not to setup the /var/run/docker.sock volume on container jobs.
  options: string # Options to pass into container host.
  ports: [ string ] # Ports to expose on the container.
  volumes: [ string ] # Volumes to mount on the container.
  mountReadOnly: # Volumes to mount read-only, the default is all false.
    work: boolean # Mount the work directory as readonly.
    externals: boolean # Mount the externals directory as readonly.
    tools: boolean # Mount the tools directory as readonly.
    tasks: boolean # Mount the tasks directory as readonly.
  azureSubscription: string # Azure subscription (ARM service connection) for container registry.
  resourceGroup: string # Resource group for your ACR.
  registry: string # Registry for container images.
  repository: string # Name of the container image repository in ACR.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
containers:
- container: string # Required as first property. ID for the container.
  type: string # Type of the registry like ACR or GCR.
  endpoint: string # ID of the service endpoint connecting to a private container registry.
  trigger: trigger | none | true # Specify none to disable, true to trigger on all image tags, or use the full syntax as described in the following examples.
  azureSubscription: string # Azure subscription (ARM service connection) for container registry.
  resourceGroup: string # Resource group for your ACR.
  registry: string # Registry for container images.
  repository: string # Name of the container image repository in ACR.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
containers:
- container: string # Required as first property. ID for the container.
  endpoint: string # ID of the service endpoint connecting to a private container registry.
  azureSubscription: string # Azure subscription (ARM service connection) for container registry.
  resourceGroup: string # Resource group for your ACR.
  registry: string # Registry for container images.
  repository: string # Name of the container image repository in ACR.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2019"

Definitions that that reference this definition: [resources.containers](resources-containers.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
:::moniker range=">=azure-pipelines-2020.1"

<!-- :::item name="container"::: -->
**`container`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
ID for the container. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="image"::: -->
**`image`** string. Required.<br>
<!-- :::editable-content name="propDescription"::: -->
Container image tag.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="type"::: -->
**`type`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Type of the registry like ACR or GCR.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [resources.containers.container.trigger](resources-containers-container-trigger.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Specify none to disable, true to trigger on all image tags, or use the full syntax as described in the following examples.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="endpoint"::: -->
**`endpoint`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
ID of the service endpoint connecting to a private container registry.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="env"::: -->
**`env`** string dictionary.<br>
<!-- :::editable-content name="propDescription"::: -->
Variables to map into the container's environment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="mapDockerSocket"::: -->
**`mapDockerSocket`** [boolean](boolean.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Set this flag to false to force the agent not to setup the /var/run/docker.sock volume on container jobs.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="options"::: -->
**`options`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Options to pass into container host.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="ports"::: -->
**`ports`** string list.<br>
<!-- :::editable-content name="propDescription"::: -->
Ports to expose on the container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="volumes"::: -->
**`volumes`** string list.<br>
<!-- :::editable-content name="propDescription"::: -->
Volumes to mount on the container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="mountReadOnly"::: -->
**`mountReadOnly`** [mountReadOnly](mount-read-only.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Volumes to mount read-only, the default is all false.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
**`azureSubscription`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Azure subscription (ARM service connection) for container registry.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resourceGroup"::: -->
**`resourceGroup`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Resource group for your ACR.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="registry"::: -->
**`registry`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Registry for container images.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="repository"::: -->
**`repository`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Name of the container image repository in ACR.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020"

<!-- :::item name="container"::: -->
**`container`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
ID for the container. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="type"::: -->
**`type`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Type of the registry like ACR or GCR. ACR
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="endpoint"::: -->
**`endpoint`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
ID of the service endpoint connecting to a private container registry.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [resources.containers.container.trigger](resources-containers-container-trigger.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Specify none to disable, true to trigger on all image tags, or use the full syntax as described in the following examples.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
**`azureSubscription`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Azure subscription (ARM service connection) for container registry.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resourceGroup"::: -->
**`resourceGroup`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Resource group for your ACR.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="registry"::: -->
**`registry`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Registry for container images.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="repository"::: -->
**`repository`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Name of the container image repository in ACR.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

<!-- :::item name="container"::: -->
**`container`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
ID for the container. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="endpoint"::: -->
**`endpoint`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
ID of the service endpoint connecting to a private container registry.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
**`azureSubscription`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Azure subscription (ARM service connection) for container registry.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resourceGroup"::: -->
**`resourceGroup`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Resource group for your ACR.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="registry"::: -->
**`registry`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Registry for container images.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="repository"::: -->
**`repository`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Name of the container image repository in ACR.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

[Container jobs](/azure/devops/pipelines/process/container-phases) let you isolate your tools and dependencies inside a container.

The agent launches an instance of your specified container then runs steps inside it.
The `container` keyword lets you specify your container images.

[Service containers](/azure/devops/pipelines/process/service-containers) run alongside a job to provide various dependencies like databases.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

::: moniker range="azure-pipelines"

```yaml
resources:
  containers:
  - container: string  # identifier (A-Z, a-z, 0-9, and underscore)
    image: string  # container image name
    options: string  # arguments to pass to container at startup
    endpoint: string  # reference to a service connection for the private registry
    env: { string: string }  # list of environment variables to add
    ports: [ string ] # ports to expose on the container
    volumes: [ string ] # volumes to mount on the container
    mapDockerSocket: bool # whether to map in the Docker daemon socket; defaults to true
    mountReadOnly:  # volumes to mount read-only - all default to false
      externals: boolean  # components required to talk to the agent
      tasks: boolean  # tasks required by the job
      tools: boolean  # installable tools like Python and Ruby
      work: boolean # the work directory
```

::: moniker-end

::: moniker range=">= azure-pipelines-2020 <= azure-pipelines-2020.1"

```yaml
resources:
  containers:
  - container: string  # identifier (A-Z, a-z, 0-9, and underscore)
    image: string  # container image name
    options: string  # arguments to pass to container at startup
    endpoint: string  # reference to a service connection for the private registry
    env: { string: string }  # list of environment variables to add
    ports: [ string ] # ports to expose on the container
    volumes: [ string ] # volumes to mount on the container
    mapDockerSocket: bool # whether to map in the Docker daemon socket; defaults to true
```

::: moniker-end

::: moniker range=">= azure-pipelines-2019 <= azure-pipelines-2019.1"

```yaml
resources:
  containers:
  - container: string  # identifier (A-Z, a-z, 0-9, and underscore)
    image: string  # container image name
    options: string  # arguments to pass to container at startup
    endpoint: string  # reference to a service connection for the private registry
    env: { string: string }  # list of environment variables to add
    ports: [ string ] # ports to expose on the container
    volumes: [ string ] # volumes to mount on the container
```

::: moniker-end

```yaml
resources:
  containers:
  - container: linux
    image: ubuntu:16.04
  - container: windows
    image: myprivate.azurecr.io/windowsservercore:1803
    endpoint: my_acr_connection
  - container: my_service
    image: my_service:tag
    ports:
    - 8080:80 # bind container port 80 to 8080 on the host machine
    - 6379 # bind container port 6379 to a random available port on the host machine
    volumes:
    - /src/dir:/dst/dir # mount /src/dir on the host into /dst/dir in the container
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

[Define resources in YAML](/azure/devops/pipelines/process/resources)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->