---
title: target definition
description: target definition reference.
ms.date: 01/28/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# target definition


Tasks run in an execution context, which is either the agent host or a container. An individual step may override its context by specifying a `target`.


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
| [stepTarget: string](#steptarget-string) | Configure step target with environment. |
| [stepTarget: container, commands](#steptarget-container-commands) | Configure step target with environment and allowed list of commands. |

:::moniker-end

:::moniker range="= azure-pipelines-2020.1" 

| Overload | Description |
|----------|-------------|
| [stepTarget: string](#steptarget-string) | Configure step target with environment. |
| [stepTarget: container, commands](#steptarget-container-commands) | Configure step target with environment and allowed list of commands. |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [stepTarget: string](#steptarget-string) | Configure step target with environment. |
| [stepTarget: container, commands, settableVariables](#steptarget-container-commands-settablevariables) | Configure step target with environment, and allowed list of commands and variables. |

:::moniker-end


## Remarks

The available options are the word `host` to target the agent host, plus any containers defined in the pipeline.

:::moniker range="= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## stepTarget: string

:::moniker-end

Tasks run in an execution context, which is either the agent host or a container. An individual step may override its context by specifying a `target`. Available options are the word `host` to target the agent host plus any containers defined in the pipeline.

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


<!-- Remarks -->


<!-- Examples -->

:::moniker range="= azure-pipelines-2020 || = azure-pipelines-2020.1"

## stepTarget: container, commands

:::moniker-end

Configure step target with environment and allowed list of commands.

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

## stepTarget: container, commands, settableVariables

:::moniker-end

Tasks run in an execution context, which is either the agent host or a container. An individual step may override its context by specifying a `target`. Available options are the word `host` to target the agent host plus any containers defined in the pipeline.

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


<!-- Remarks -->


<!-- Examples -->

<!-- See also -->
