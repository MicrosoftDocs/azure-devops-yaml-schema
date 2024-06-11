---
title: jobs.job.container definition
description: Container resource name.
ms.date: 05/14/2024
monikerRange: ">=azure-pipelines-2019.1"
---

# jobs.job.container definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Container jobs allow you to run jobs on a container instead of the agent host.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [pipeline](pipeline.md), [jobs.job](jobs-job.md), [jobs.deployment](jobs-deployment.md)

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

Definitions that reference this definition: [pipeline](pipeline.md), [jobs.job](jobs-job.md)

:::moniker-end
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range=">=azure-pipelines-2019.1"

| Implementation | Description |
|---|---|
| [container: string](#containerstring) | Specify job container by alias. |
| [container: image](#containerimage) | Specify job container using image tag and options. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="container: string"::: -->
<a name="containerstring"></a>
<!-- :::stringAnyOf::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::implementation-signature::: -->
## container: string
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Specify job container by alias.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
container: string # Specify job container by alias.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-string-item::: -->
**`container`** string.<br>
<!-- :::editable-content name="description"::: -->
Specify job container by alias.
<!-- :::editable-content-end::: -->
<!-- :::implementation-string-item-end::: -->

:::moniker-end
<!-- :::stringAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
### Remarks

The alias can be the name of an image, or it can be a reference to a [container resource](resources-containers-container.md).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

The following example fetches the ubuntu image tagged 18.04 from [Docker Hub](https://hub.docker.com/) and then starts the container. When the `printenv` command runs, it happens inside the ubuntu:18.04 container.

```yaml
pool:
  vmImage: 'ubuntu-18.04'

container: ubuntu:18.04

steps:
- script: printenv
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="container: image"::: -->
<a name="containerimage"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2020.1"

<!-- :::implementation-signature::: -->
## container: image
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Specify job container using image tag and options.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
container:
  image: string # Required. Container image tag.
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
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="image"::: -->
**`image`** string. Required.<br><!-- :::editable-content name="propDescription"::: -->
Container image tag.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="endpoint"::: -->
**`endpoint`** string.<br><!-- :::editable-content name="propDescription"::: -->
ID of the service endpoint connecting to a private container registry.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="env"::: -->
**`env`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Variables to map into the container's environment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="mapDockerSocket"::: -->
**`mapDockerSocket`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Set this flag to false to force the agent not to setup the /var/run/docker.sock volume on container jobs.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="options"::: -->
**`options`** string.<br><!-- :::editable-content name="propDescription"::: -->
Options to pass into container host.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="ports"::: -->
**`ports`** string list.<br><!-- :::editable-content name="propDescription"::: -->
Ports to expose on the container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="volumes"::: -->
**`volumes`** string list.<br><!-- :::editable-content name="propDescription"::: -->
Volumes to mount on the container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="mountReadOnly"::: -->
**`mountReadOnly`** [mountReadOnly](mount-read-only.md).<br><!-- :::editable-content name="propDescription"::: -->
Volumes to mount read-only, the default is all false.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## container: image
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Specify job container using image tag and options.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
container:
  image: string # Required. Container image tag.
  endpoint: string # ID of the service endpoint connecting to a private container registry.
  env: # Variables to map into the container's environment.
    string: string # Name/value pairs
  mapDockerSocket: boolean # Set this flag to false to force the agent not to setup the /var/run/docker.sock volume on container jobs.
  options: string # Options to pass into container host.
  ports: [ string ] # Ports to expose on the container.
  volumes: [ string ] # Volumes to mount on the container.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="image"::: -->
**`image`** string. Required.<br><!-- :::editable-content name="propDescription"::: -->
Container image tag.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="endpoint"::: -->
**`endpoint`** string.<br><!-- :::editable-content name="propDescription"::: -->
ID of the service endpoint connecting to a private container registry.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="env"::: -->
**`env`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Variables to map into the container's environment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="mapDockerSocket"::: -->
**`mapDockerSocket`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Set this flag to false to force the agent not to setup the /var/run/docker.sock volume on container jobs.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="options"::: -->
**`options`** string.<br><!-- :::editable-content name="propDescription"::: -->
Options to pass into container host.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="ports"::: -->
**`ports`** string list.<br><!-- :::editable-content name="propDescription"::: -->
Ports to expose on the container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="volumes"::: -->
**`volumes`** string list.<br><!-- :::editable-content name="propDescription"::: -->
Volumes to mount on the container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

<!-- :::implementation-signature::: -->
## container: image
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Specify job container using image tag and options.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
container:
  image: string # Required. Container image tag.
  endpoint: string # ID of the service endpoint connecting to a private container registry.
  env: # Variables to map into the container's environment.
    string: string # Name/value pairs
  options: string # Options to pass into container host.
  ports: [ string ] # Ports to expose on the container.
  volumes: [ string ] # Volumes to mount on the container.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="image"::: -->
**`image`** string. Required.<br><!-- :::editable-content name="propDescription"::: -->
Container image tag.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="endpoint"::: -->
**`endpoint`** string.<br><!-- :::editable-content name="propDescription"::: -->
ID of the service endpoint connecting to a private container registry.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="env"::: -->
**`env`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Variables to map into the container's environment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="options"::: -->
**`options`** string.<br><!-- :::editable-content name="propDescription"::: -->
Options to pass into container host.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="ports"::: -->
**`ports`** string list.<br><!-- :::editable-content name="propDescription"::: -->
Ports to expose on the container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="volumes"::: -->
**`volumes`** string list.<br><!-- :::editable-content name="propDescription"::: -->
Volumes to mount on the container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end
<!-- :::objectAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

Use `options` to configure container startup.

```yaml
container:
  image: ubuntu:18.04
  options: --hostname container-test --ip 192.168.0.1

steps:
- script: echo hello
```

In the following example, the containers are defined in the resources section. Each container is then referenced later, by referring to its assigned alias.

```yaml
resources:
  containers:
  - container: u14
    image: ubuntu:14.04

  - container: u16
    image: ubuntu:16.04

  - container: u18
    image: ubuntu:18.04

jobs:
- job: RunInContainer
  pool:
    vmImage: 'ubuntu-18.04'

  strategy:
    matrix:
      ubuntu14:
        containerResource: u14
      ubuntu16:
        containerResource: u16
      ubuntu18:
        containerResource: u18

  container: $[ variables['containerResource'] ]

  steps:
  - script: printenv
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Define container jobs](/azure/devops/pipelines/process/container-phases)
- [Define resources](/azure/devops/pipelines/process/resources)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
