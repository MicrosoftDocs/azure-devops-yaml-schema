---
title: target definition
description: target definition reference.
ms.date: 02/03/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# target definition


Tasks run in an execution context, which is either the agent host or a container.


:::moniker range="= azure-pipelines-2020"

Properties that use this definition: [steps.script.target](steps-script.md), [steps.powershell.target](steps-powershell.md), [steps.pwsh.target](steps-pwsh.md), [steps.bash.target](steps-bash.md), [steps.checkout.target](steps-checkout.md), [steps.download.target](steps-download.md), [steps.downloadBuild.target](steps-download-build.md), [steps.getPackage.target](steps-get-package.md), [steps.publish.target](steps-publish.md), [steps.restoreCache.target](steps-restore-cache.md), [steps.saveCache.target](steps-save-cache.md), [steps.reviewApp.target](steps-review-app.md)

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

Properties that use this definition: [steps.script.target](steps-script.md), [steps.powershell.target](steps-powershell.md), [steps.pwsh.target](steps-pwsh.md), [steps.bash.target](steps-bash.md), [steps.checkout.target](steps-checkout.md), [steps.download.target](steps-download.md), [steps.downloadBuild.target](steps-download-build.md), [steps.getPackage.target](steps-get-package.md), [steps.publish.target](steps-publish.md), [steps.restoreCache.target](steps-restore-cache.md), [steps.saveCache.target](steps-save-cache.md), [steps.reviewApp.target](steps-review-app.md)

:::moniker-end

:::moniker range="= azure-pipelines"

Properties that use this definition: [steps.script.target](steps-script.md), [steps.powershell.target](steps-powershell.md), [steps.pwsh.target](steps-pwsh.md), [steps.bash.target](steps-bash.md), [steps.checkout.target](steps-checkout.md), [steps.download.target](steps-download.md), [steps.downloadBuild.target](steps-download-build.md), [steps.getPackage.target](steps-get-package.md), [steps.publish.target](steps-publish.md), [steps.restoreCache.target](steps-restore-cache.md), [steps.saveCache.target](steps-save-cache.md), [steps.reviewApp.target](steps-review-app.md)

:::moniker-end

## Overloads

:::moniker range="= azure-pipelines-2020" 

| Overload | Description |
|----------|-------------|
| [target: string](#target-string) | Configure step target with environment. |
| [target: container, commands](#target-container-commands) | Configure step target with environment and allowed list of commands. |

:::moniker-end

:::moniker range="= azure-pipelines-2020.1" 

| Overload | Description |
|----------|-------------|
| [target: string](#target-string) | Configure step target with environment. |
| [target: container, commands](#target-container-commands) | Configure step target with environment and allowed list of commands. |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [target: string](#target-string) | Configure step target with environment. |
| [target: container, commands, settableVariables](#target-container-commands-settablevariables) | Configure step target with environment, and allowed list of commands and variables. |

:::moniker-end


## Remarks

An individual step may override its context by specifying a `target`, and optionally configure a container, commands, and settable variables.

:::moniker range="= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## target: string

Specify a step target by name.



:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="stepTarget{string}" version="azure-pipelines-2020"::: -->


```yaml
target: string # Environment in which to run this task.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `stepTarget`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="stepTarget{string}" version="azure-pipelines-2020.1"::: -->


```yaml
target: string # Environment in which to run this task.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `stepTarget`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="stepTarget{string}" version="azure-pipelines"::: -->


```yaml
target: string # Environment in which to run this task.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `stepTarget`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


### Remarks

Available options are the word `host` to target the agent host plus any containers defined in the pipeline.

<!-- Examples -->

:::moniker range="= azure-pipelines-2020 || = azure-pipelines-2020.1"

## target: container, commands

Configure step target with environment and allowed list of commands.


:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="stepTarget{container,commands}" version="azure-pipelines-2020"::: -->


```yaml
target:
  container: string # Container to target (or 'host' for host machine). 
  commands: string # Set of allowed logging commands ('any' or 'restricted').  (any, restricted)
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container to target (or 'host' for host machine). 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `commands`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Set of allowed logging commands ('any' or 'restricted'). Acceptable values: any, restricted
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="stepTarget{container,commands}" version="azure-pipelines-2020.1"::: -->


```yaml
target:
  container: string # Container to target (or 'host' for host machine). 
  commands: string # Set of allowed logging commands ('any' or 'restricted').  (any, restricted)
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container to target (or 'host' for host machine). 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `commands`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Set of allowed logging commands ('any' or 'restricted'). Acceptable values: any, restricted
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


<!-- Examples -->

:::moniker range="= azure-pipelines"

## target: container, commands, settableVariables

Configure step target using a container name, commands, and settable variables.



:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="stepTarget{container,commands,settableVariables}" version="azure-pipelines"::: -->


```yaml
target:
  container: string # Container to target (or 'host' for host machine). 
  commands: string # Set of allowed logging commands ('any' or 'restricted').  (any, restricted)
  settableVariables: string | [ string ]  # Restrictions on which variables that can be set
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container to target (or 'host' for host machine). 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `commands`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Set of allowed logging commands ('any' or 'restricted'). Acceptable values: any, restricted
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `settableVariables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[target.settableVariables](target-settable-variables.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Restrictions on which variables that can be set. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


### Remarks

You don't need to configure all of these properties when configuring a step target. If not specified, the default value for `container` is `host`, the default value of `commands` is `any`, and the default value for `settableVariables` allows all variables to be set by a step.

#### Step targeting and command isolation

Azure Pipelines supports running jobs either in containers or on the agent host. Previously, an entire job was set to one of those two targets. Now, individual steps (tasks or scripts) can run on the target you choose. Steps may also target other containers, so a pipeline could run each step in a specialized, purpose-built container. 

> [!NOTE]
> This feature is in public preview. If you have any feedback or questions about this feature, let us know in the [Developer Community](https://developercommunity.visualstudio.com/spaces/21/index.html). 

Containers can act as isolation boundaries, preventing code from making unexpected changes on the host machine. The way steps [communicate with and access services from the agent](/azure/devops/pipelines/scripts/logging-commands) is not affected by isolating steps in a container. Therefore, we're also introducing a command restriction mode which you can use with step targets. Setting `commands` to `restricted` will restrict the services a step can request from the agent. It will no longer be able to attach logs, upload artifacts, and certain other operations.


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



## See also

- [Task types & usage - step target](/azure/devops/pipelines/process/tasks#step-target)


