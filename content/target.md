---
title: target definition
description: Tasks run in an execution context, which is either the agent host or a container.
ms.date: 11/17/2023
monikerRange: ">=azure-pipelines-2020"
---

# target definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Tasks run in an execution context, which is either the agent host or a container.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [steps.task](steps-task.md), [steps.script](steps-script.md), [steps.powershell](steps-powershell.md), [steps.pwsh](steps-pwsh.md), [steps.bash](steps-bash.md), [steps.checkout](steps-checkout.md), [steps.download](steps-download.md), [steps.downloadBuild](steps-download-build.md), [steps.getPackage](steps-get-package.md), [steps.publish](steps-publish.md), [steps.reviewApp](steps-review-app.md)

:::moniker-end
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range=">=azure-pipelines-2022"

| Implementation | Description |
|---|---|
| [target: string](#targetstring) | Environment in which to run this step or task. |
| [target: container, commands, settableVariables](#targetobjectproperties) | Configure step target with environment, and allowed list of commands and variables. |

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

| Implementation | Description |
|---|---|
| [target: string](#targetstring) | Environment in which to run this step or task. |
| [target: container, commands](#targetobjectproperties) | Configure step target with environment and allowed list of commands. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

An individual step may override its context by specifying a `target`, and optionally configure a container, commands, and settable variables.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="target: string"::: -->
<a name="targetstring"></a>
<!-- :::stringAnyOf::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## target: string
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Specify a step target by name.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
target: string # Environment in which to run this step or task.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-string-item::: -->
**`target`** string.<br>
<!-- :::editable-content name="description"::: -->
Available options are the word `host` to target the agent host plus any containers defined in the pipeline.
<!-- :::editable-content-end::: -->
<!-- :::implementation-string-item-end::: -->

:::moniker-end
<!-- :::stringAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="target: object properties"::: -->
<a name="targetobjectproperties"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::implementation-signature::: -->
## target: container, commands, settableVariables
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Configure step target using a container name, commands, and settable variables.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
target:
  container: string # Container to target (or 'host' for host machine).
  commands: string # Set of allowed logging commands ('any' or 'restricted').
  settableVariables: none | [ string ] # Restrictions on which variables that can be set.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="container"::: -->
**`container`** string.<br><!-- :::editable-content name="propDescription"::: -->
Container to target (or 'host' for host machine).
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="commands"::: -->
**`commands`** string.<br><!-- :::editable-content name="propDescription"::: -->
Set of allowed logging commands ('any' or 'restricted'). any | restricted.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="settableVariables"::: -->
**`settableVariables`** [target.settableVariables](target-settable-variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Restrictions on which variables that can be set.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

<!-- :::implementation-signature::: -->
## target: container, commands
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Configure step target with environment and allowed list of commands.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
target:
  container: string # Container to target (or 'host' for host machine).
  commands: string # Set of allowed logging commands ('any' or 'restricted').
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="container"::: -->
**`container`** string.<br><!-- :::editable-content name="propDescription"::: -->
Container to target (or 'host' for host machine).
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="commands"::: -->
**`commands`** string.<br><!-- :::editable-content name="propDescription"::: -->
Set of allowed logging commands ('any' or 'restricted'). any | restricted.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end
<!-- :::objectAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
### Remarks

You don't need to configure all of these properties when configuring a step target. If not specified, the default value for `container` is `host`, the default value of `commands` is `any`, and the default value for `settableVariables` allows all variables to be set by a step.

#### Step targeting and command isolation

Azure Pipelines supports running jobs either in containers or on the agent host. Previously, an entire job was set to one of those two targets. Now, individual steps (tasks or scripts) can run on the target you choose. Steps may also target other containers, so a pipeline could run each step in a specialized, purpose-built container. 

> [!NOTE]
> This feature is in public preview. If you have any feedback or questions about this feature, let us know in the [Developer Community](https://developercommunity.visualstudio.com/spaces/21/index.html).

Containers can act as isolation boundaries, preventing code from making unexpected changes on the host machine. The way steps [communicate with and access services from the agent](/azure/devops/pipelines/scripts/logging-commands) is not affected by isolating steps in a container. Therefore, we're also introducing a command restriction mode which you can use with step targets. Setting `commands` to `restricted` will restrict the services a step can request from the agent. It will no longer be able to attach logs, upload artifacts, and certain other operations.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

The following example shows running steps on the host in a job container, and in another container.

```yaml
resources:
  containers:
  - container: python
    image: python:3.8
  - container: node
    image: node:13.2

jobs:
- job: example
  container: python

  steps:
  - script: echo Running in the job container

  - script: echo Running on the host
    target: host

  - script: echo Running in another container, in restricted commands mode
    target:
      container: node
      commands: restricted
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Task types & usage - step target](/azure/devops/pipelines/process/tasks#step-target)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
