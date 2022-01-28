---
title: jobs.deployment.strategy definition
description: jobs.deployment.strategy definition reference.
ms.date: 01/28/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# jobs.deployment.strategy definition


A deployment strategy enables you to configure how the update is delivered.


:::moniker range="= azure-pipelines-2020"

Properties that use this definition: [jobs.deployment.strategy](jobs-deployment.md)

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

Properties that use this definition: [jobs.deployment.strategy](jobs-deployment.md)

:::moniker-end

:::moniker range="= azure-pipelines"

Properties that use this definition: [jobs.deployment.strategy](jobs-deployment.md)

:::moniker-end

## Overloads

:::moniker range="= azure-pipelines-2020" 

| Overload | Description |
|----------|-------------|
| [strategy: runOnce](#strategy-runonce) | Run once deployment strategy. |
| [strategy: rolling](#strategy-rolling) | Rolling deployment strategy. |
| [strategy: canary](#strategy-canary) | Canary deployment strategy. |

:::moniker-end

:::moniker range="= azure-pipelines-2020.1" 

| Overload | Description |
|----------|-------------|
| [strategy: runOnce](#strategy-runonce) | Run once deployment strategy. |
| [strategy: rolling](#strategy-rolling) | Rolling deployment strategy. |
| [strategy: canary](#strategy-canary) | Canary deployment strategy. |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [strategy: runOnce](#strategy-runonce) | Run once deployment strategy. |
| [strategy: rolling](#strategy-rolling) | Rolling deployment strategy. |
| [strategy: canary](#strategy-canary) | Canary deployment strategy. |

:::moniker-end


## Remarks

When you're deploying application updates, it's important that the technique you use to deliver the update will:

* Enable initialization.
* Deploy the update.
* Route traffic to the updated version.
* Test the updated version after routing traffic.
* In case of failure, run steps to restore to the last known good version.

We achieve this by using lifecycle hooks that can run steps during deployment. Each of the lifecycle hooks resolves into an agent job or a server job (or a container or validation job in the future), depending on the pool attribute. By default, the lifecycle hooks will inherit the pool specified by the deployment job.

Deployment jobs use the `$(Pipeline.Workspace) system variable.`

If you are using self-hosted agents, you can use the workspace clean options to clean your deployment workspace.

```yaml
  jobs:
  - deployment: deploy
    pool:
      vmImage: ubuntu-latest
      workspace:
        clean: all
    environment: staging
```

:::moniker range="= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## strategy: runOnce

The runOnce deployment strategy rolls out changes by executing each of its steps one time.



:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="deploymentStrategy{runOnce}" version="azure-pipelines-2020"::: -->


```yaml
strategy:
  runOnce:  # RunOnce Deployment strategy
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `runOnce`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.strategy.runOnce](jobs-deployment-strategy-run-once.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->RunOnce Deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="deploymentStrategy{runOnce}" version="azure-pipelines-2020.1"::: -->


```yaml
strategy:
  runOnce:  # RunOnce Deployment strategy
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `runOnce`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.strategy.runOnce](jobs-deployment-strategy-run-once.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->RunOnce Deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="deploymentStrategy{runOnce}" version="azure-pipelines"::: -->


```yaml
strategy:
  runOnce:  # RunOnce Deployment strategy
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `runOnce`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.strategy.runOnce](jobs-deployment-strategy-run-once.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->RunOnce Deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


### Remarks

`runOnce` is the simplest deployment strategy wherein all the lifecycle hooks, namely `preDeploy` `deploy`, `routeTraffic`, and `postRouteTraffic`, are executed once. Then,  either `on:` `success` or `on:` `failure` is executed.  


<!-- Examples -->

:::moniker range="= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## strategy: rolling

A rolling deployment replaces instances of the previous version of an application with instances of the new version of the application on a fixed set of virtual machines (rolling set) in each iteration. 



:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="deploymentStrategy{rolling}" version="azure-pipelines-2020"::: -->


```yaml
strategy:
  rolling:  # Rolling Deployment strategy
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `rolling`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.strategy.rolling](jobs-deployment-strategy-rolling.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Rolling Deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="deploymentStrategy{rolling}" version="azure-pipelines-2020.1"::: -->


```yaml
strategy:
  rolling:  # Rolling Deployment strategy
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `rolling`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.strategy.rolling](jobs-deployment-strategy-rolling.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Rolling Deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="deploymentStrategy{rolling}" version="azure-pipelines"::: -->


```yaml
strategy:
  rolling:  # Rolling Deployment strategy
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `rolling`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.strategy.rolling](jobs-deployment-strategy-rolling.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Rolling Deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


<!-- Examples -->

:::moniker range="= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## strategy: canary

Canary deployment strategy rolls out changes to a small subset of servers.



:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="deploymentStrategy{canary}" version="azure-pipelines-2020"::: -->


```yaml
strategy:
  canary:  # Canary Deployment strategy
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `canary`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.strategy.canary](jobs-deployment-strategy-canary.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Canary Deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="deploymentStrategy{canary}" version="azure-pipelines-2020.1"::: -->


```yaml
strategy:
  canary:  # Canary Deployment strategy
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `canary`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.strategy.canary](jobs-deployment-strategy-canary.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Canary Deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="deploymentStrategy{canary}" version="azure-pipelines"::: -->


```yaml
strategy:
  canary:  # Canary Deployment strategy
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `canary`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.strategy.canary](jobs-deployment-strategy-canary.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Canary Deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


### Remarks

Canary deployment strategy is an advanced deployment strategy that helps mitigate the risk involved in rolling out new versions of applications. By using this strategy, you can roll out the changes to a small subset of servers first. As you gain more confidence in the new version, you can release it to more servers in your infrastructure and route more traffic to it.


<!-- Examples -->


## See also

* [Deployment jobs](/azure/devops/pipelines/process/deployment-jobs)


