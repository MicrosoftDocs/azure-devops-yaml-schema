---
title: resources.containers.container definition
description: A container resource used to reference a container image.
ms.date: 01/27/2026
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# resources.containers.container definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
A container resource references a container image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-server"

```yaml
containers:
- container: string # Required as first property. Alias of the container.
  image: string # Required. Container image tag.
  type: string # Type of the registry like ACR or GCR.
  trigger: trigger | none | true # Specify none to disable, true to trigger on all image tags, or use the full syntax as described in the following examples.
  azureSubscription: string # Azure subscription (ARM service connection) for container registry.
  resourceGroup: string # Resource group for your ACR.
  registry: string # Registry for container images.
  repository: string # Name of the container image repository in ACR.
  localImage: boolean # When true, uses a locally tagged image instead of using docker pull to get the image; the default is false.
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
```

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

```yaml
containers:
- container: string # Required as first property. Alias of the container.
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
  localImage: boolean # When true, uses a locally tagged image instead of using docker pull to get the image. The default is false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [resources.containers](resources-containers.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="container"::: -->
:::moniker range="<=azure-pipelines"

**`container`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
ID for the container. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="image"::: -->
:::moniker range="<=azure-pipelines"

**`image`** string. Required.<br><!-- :::editable-content name="propDescription"::: -->
Container image tag.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="type"::: -->
:::moniker range="<=azure-pipelines"

**`type`** string.<br><!-- :::editable-content name="propDescription"::: -->
Type of the registry like ACR or GCR.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
:::moniker range="<=azure-pipelines"

**`trigger`** [resources.containers.container.trigger](resources-containers-container-trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Specify none to disable, true to trigger on all image tags, or use the full syntax as described in the following examples.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureSubscription"::: -->
:::moniker range="<=azure-pipelines"

**`azureSubscription`** string.<br><!-- :::editable-content name="propDescription"::: -->
Azure subscription (ARM service connection) for container registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroup"::: -->
:::moniker range="<=azure-pipelines"

**`resourceGroup`** string.<br><!-- :::editable-content name="propDescription"::: -->
Resource group for your ACR.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="registry"::: -->
:::moniker range="<=azure-pipelines"

**`registry`** string.<br><!-- :::editable-content name="propDescription"::: -->
Registry for container images.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="repository"::: -->
:::moniker range="<=azure-pipelines"

**`repository`** string.<br><!-- :::editable-content name="propDescription"::: -->
Name of the container image repository in ACR.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="localImage"::: -->
:::moniker range="<=azure-pipelines"

**`localImage`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
When true, uses a locally tagged image instead of using docker pull to get the image. The default is false.

This property is useful only for self-hosted agents where the image is already present on the agent machine.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="endpoint"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`endpoint`** string.<br><!-- :::editable-content name="propDescription"::: -->
ID of the service endpoint connecting to a private container registry.  [Template expressions are supported](/azure/devops/release-notes/2022/sprint-212-update#template-expressions-in-container-resource-definition).
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2022"

**`endpoint`** string.<br><!-- :::editable-content name="propDescription"::: -->
ID of the service endpoint connecting to a private container registry.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="env"::: -->
:::moniker range="<=azure-pipelines"

**`env`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Variables to map into the container's environment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mapDockerSocket"::: -->
:::moniker range="<=azure-pipelines"

**`mapDockerSocket`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Set this flag to false to force the agent not to setup the /var/run/docker.sock volume on container jobs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="options"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`options`** string.<br><!-- :::editable-content name="propDescription"::: -->
Options to pass into container host. [Template expressions are supported](/azure/devops/release-notes/2022/sprint-212-update#template-expressions-in-container-resource-definition).
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2022"

**`options`** string.<br><!-- :::editable-content name="propDescription"::: -->
Options to pass into container host.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ports"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`ports`** string list.<br><!-- :::editable-content name="propDescription"::: -->
Ports to expose on the container. [Template expressions are supported](/azure/devops/release-notes/2022/sprint-212-update#template-expressions-in-container-resource-definition).
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2022"

**`ports`** string list.<br><!-- :::editable-content name="propDescription"::: -->
Ports to expose on the container.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="volumes"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`volumes`** string list.<br><!-- :::editable-content name="propDescription"::: -->
Volumes to mount on the container. [Template expressions are supported](/azure/devops/release-notes/2022/sprint-212-update#template-expressions-in-container-resource-definition).
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2022"

**`volumes`** string list.<br><!-- :::editable-content name="propDescription"::: -->
Volumes to mount on the container.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mountReadOnly"::: -->
:::moniker range="<=azure-pipelines"

**`mountReadOnly`** [mountReadOnly](mount-read-only.md).<br><!-- :::editable-content name="propDescription"::: -->
Volumes to mount read-only, the default is all false.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

[Container jobs](/azure/devops/pipelines/process/container-phases) let you isolate your tools and dependencies inside a container.

The agent launches an instance of your specified container then runs steps inside it.
The `container` keyword lets you specify your container images.

[Service containers](/azure/devops/pipelines/process/service-containers) run alongside a job to provide various dependencies like databases.

::: moniker range=">=azure-pipelines-2022.1"

[Template expressions](/azure/devops/release-notes/2022/sprint-212-update#template-expressions-in-container-resource-definition) are supported for `endpoint`, `volumes`, `ports`, and `options` properties of a container resource in a YAML pipeline.

::: moniker-end
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

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