---
title: jobs.deployment.strategy definition
description: jobs.deployment.strategy definition reference.
ms.date: 01/24/2022
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
| [deploymentStrategy: runOnce](#deploymentstrategy-runonce) | Run once deployment strategy. |
| [deploymentStrategy: rolling](#deploymentstrategy-rolling) | Rolling deployment strategy. |
| [deploymentStrategy: canary](#deploymentstrategy-canary) | Canary deployment strategy. |

:::moniker-end

:::moniker range="= azure-pipelines-2020.1" 

| Overload | Description |
|----------|-------------|
| [deploymentStrategy: runOnce](#deploymentstrategy-runonce) | Run once deployment strategy. |
| [deploymentStrategy: rolling](#deploymentstrategy-rolling) | Rolling deployment strategy. |
| [deploymentStrategy: canary](#deploymentstrategy-canary) | Canary deployment strategy. |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [deploymentStrategy: runOnce](#deploymentstrategy-runonce) | Run once deployment strategy. |
| [deploymentStrategy: rolling](#deploymentstrategy-rolling) | Rolling deployment strategy. |
| [deploymentStrategy: canary](#deploymentstrategy-canary) | Canary deployment strategy. |

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

:::moniker range="= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## deploymentStrategy: runOnce

:::moniker-end

`runOnce` is the simplest deployment strategy wherein all the lifecycle hooks, namely `preDeploy` `deploy`, `routeTraffic`, and `postRouteTraffic`, are executed once. Then,  either `on:` `success` or `on:` `failure` is executed.  


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

If you are using self-hosted agents, you can use the workspace clean options to clean your deployment workspace.

```yaml
  jobs:
  - deployment: deploy
    pool:
      vmImage: 'ubuntu-latest'
      workspace:
        clean: all
    environment: staging
```


### Examples

The following example YAML snippet showcases a simple use of a deploy job by using the `runOnce` deployment strategy. The example includes a checkout step. 

```YAML

jobs:
  # Track deployments on the environment.
- deployment: DeployWeb
  displayName: deploy Web App
  pool:
    vmImage: 'ubuntu-latest'
  # Creates an environment if it doesn't exist.
  environment: 'smarthotel-dev'
  strategy:
    # Default deployment strategy, more coming...
    runOnce:
      deploy:
        steps:
        - checkout: self 
        - script: echo my first deployment
```

With each run of this job, deployment history is recorded against the `smarthotel-dev` environment.

> [!NOTE]
> - It's also possible to create an environment with empty resources and use that as an abstract shell to record deployment history, as shown in the previous example.

The next example demonstrates how a pipeline can refer both an environment and a resource to be used as the target for a deployment job.

```YAML
jobs:
- deployment: DeployWeb
  displayName: deploy Web App
  pool:
    vmImage: 'ubuntu-latest'
  # Records deployment against bookings resource - Kubernetes namespace.
  environment: 'smarthotel-dev.bookings'
  strategy: 
    runOnce:
      deploy:
        steps:
          # No need to explicitly pass the connection details.
        - task: KubernetesManifest@0
          displayName: Deploy to Kubernetes cluster
          inputs:
            action: deploy
            namespace: $(k8sNamespace)
            manifests: |
              $(System.ArtifactsDirectory)/manifests/*
            imagePullSecrets: |
              $(imagePullSecret)
            containers: |
              $(containerRegistry)/$(imageRepository):$(tag)
```

This approach has the following benefits:
- Records deployment history on a specific resource within the environment, as opposed to recording the history on all resources within the environment.
- Steps in the deployment job **automatically inherit** the connection details of the resource (in this case, a Kubernetes namespace, `smarthotel-dev.bookings`), because the deployment job is linked to the environment. 
This is useful in the cases where the same connection detail is set for multiple steps of the job.

:::moniker range="= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## deploymentStrategy: rolling

:::moniker-end

A rolling deployment replaces instances of the previous version of an application with instances of the new version of the application on a fixed set of virtual machines (rolling set) in each iteration. 


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


### Remarks

We currently only support the rolling strategy to VM resources.

For example, a rolling deployment typically waits for deployments on each set of virtual machines to complete before proceeding to the next set of deployments. You could do a health check after each iteration and if a significant issue occurs, the rolling deployment can be stopped.

Rolling deployments can be configured by specifying the keyword `rolling:` under the `strategy:` node. 
The `strategy.name` variable is available in this strategy block, which takes the name of the strategy. In this case, rolling.

All the lifecycle hooks are supported and lifecycle hook jobs are created to run on each VM.

`preDeploy`, `deploy`, `routeTraffic`, and `postRouteTraffic` are executed once per batch size defined by `maxParallel`. 
Then, either `on: success` or `on: failure` is executed.

With `maxParallel: <# or % of VMs>`, you can control the number/percentage of virtual machine targets to deploy to in parallel. This ensures that the app is running on these machines and is capable of handling requests while the deployment is taking place on the rest of the machines, which reduces overall downtime.

 > [!NOTE]
 > There are a few known gaps in this feature. For example, when you retry a stage, it will re-run the deployment on all VMs not just failed targets. 


### Examples

The following rolling strategy  example for VMs updates up to five targets in each iteration. `maxParallel` will determine the number of targets that can be deployed to, in parallel. The selection accounts for absolute number or percentage of targets that must remain available at any time excluding the targets that are being deployed to. It is also used to determine the success and failure conditions during deployment.

```YAML
jobs: 
- deployment: VMDeploy
  displayName: web
  environment:
    name: smarthotel-dev
    resourceType: VirtualMachine
  strategy:
    rolling:
      maxParallel: 5  #for percentages, mention as x%
      preDeploy:
        steps:
        - download: current
          artifact: drop
        - script: echo initialize, cleanup, backup, install certs
      deploy:
        steps:
        - task: IISWebAppDeploymentOnMachineGroup@0
          displayName: 'Deploy application to Website'
          inputs:
            WebSiteName: 'Default Web Site'
            Package: '$(Pipeline.Workspace)/drop/**/*.zip'
      routeTraffic:
        steps:
        - script: echo routing traffic
      postRouteTraffic:
        steps:
        - script: echo health check post-route traffic
      on:
        failure:
          steps:
          - script: echo Restore from backup! This is on failure
        success:
          steps:
          - script: echo Notify! This is on success
```


:::moniker range="= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## deploymentStrategy: canary

:::moniker-end

Canary deployment strategy rolls out changes to a small subset of servers.


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

Canary deployment strategy supports the `preDeploy` lifecycle hook (executed once) and iterates with the `deploy`, `routeTraffic`, and `postRouteTraffic` lifecycle hooks. It then exits with either the `success` or `failure` hook.

 
The following variables are available in this strategy:

`strategy.name`: Name of the strategy. For example, canary.
<br>`strategy.action`: The action to be performed on the Kubernetes cluster. For example, deploy, promote, or reject.
<br>`strategy.increment`: The increment value used in the current interaction. This variable is available only in `deploy`, `routeTraffic`, and `postRouteTraffic` lifecycle hooks.


### Examples

In the following example, the canary strategy for AKS will first deploy the changes with 10 percent pods, followed by 20 percent, while monitoring the health during `postRouteTraffic`. If all goes well, it will promote to 100 percent.  

```YAML
jobs: 
- deployment: 
  environment: smarthotel-dev.bookings
  pool: 
    name: smarthotel-devPool
  strategy:                  
    canary:      
      increments: [10,20]  
      preDeploy:                                     
        steps:           
        - script: initialize, cleanup....   
      deploy:             
        steps: 
        - script: echo deploy updates... 
        - task: KubernetesManifest@0 
          inputs: 
            action: $(strategy.action)       
            namespace: 'default' 
            strategy: $(strategy.name) 
            percentage: $(strategy.increment) 
            manifests: 'manifest.yml' 
      postRouteTraffic: 
        pool: server 
        steps:           
        - script: echo monitor application health...   
      on: 
        failure: 
          steps: 
          - script: echo clean-up, rollback...   
        success: 
          steps: 
          - script: echo checks passed, notify... 
```



## See also

* [Deployment jobs](/azure/devops/pipelines/process/deployment-jobs)


