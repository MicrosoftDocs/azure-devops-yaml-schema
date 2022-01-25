---
title: jobs.deployment.strategy.canary definition
description: jobs.deployment.strategy.canary definition reference.
ms.date: 01/24/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# jobs.deployment.strategy.canary definition


Canary deployment strategy rolls out changes to a small subset of servers.


:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="canaryDeploymentStrategy{increments,preDeploy,deploy,routeTraffic,postRouteTraffic,on}" version="azure-pipelines-2020"::: -->

```yaml
canary:
  increments: [ string ] # Maximum batch size for deployment 
  preDeploy:  # Pre deploy hook for canary deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where pre deploy steps will run
  deploy:  # Deploy hook for canary deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where deploy steps will run
  routeTraffic:  # Route traffic hook for canary deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where route traffic steps will run
  postRouteTraffic:  # Post route traffic hook for canary deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where post route traffic steps will run
  on:  # On success or failure hook for canary deployment strategy
    failure:  # Runs on failure of any step
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where post on failure steps will run
    success:  # Runs on success of all of the steps
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where on success steps will run
```


Properties that use this definition: [jobs.deployment.strategy.canary](jobs-deployment-strategy.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `increments`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Maximum batch size for deployment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `preDeploy`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
preDeployHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pre deploy hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `deploy`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
deployHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Deploy hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `routeTraffic`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
routeTrafficHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Route traffic hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `postRouteTraffic`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
postRouteTrafficHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Post route traffic hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `on`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
onSuccessOrFailureHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->On success or failure hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="canaryDeploymentStrategy{increments,preDeploy,deploy,routeTraffic,postRouteTraffic,on}" version="azure-pipelines-2020.1"::: -->

```yaml
canary:
  increments: [ string ] # Maximum batch size for deployment 
  preDeploy:  # Pre deploy hook for canary deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where pre deploy steps will run
  deploy:  # Deploy hook for canary deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where deploy steps will run
  routeTraffic:  # Route traffic hook for canary deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where route traffic steps will run
  postRouteTraffic:  # Post route traffic hook for canary deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where post route traffic steps will run
  on:  # On success or failure hook for canary deployment strategy
    failure:  # Runs on failure of any step
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where post on failure steps will run
    success:  # Runs on success of all of the steps
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where on success steps will run
```


Properties that use this definition: [jobs.deployment.strategy.canary](jobs-deployment-strategy.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `increments`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Maximum batch size for deployment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `preDeploy`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
preDeployHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pre deploy hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `deploy`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
deployHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Deploy hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `routeTraffic`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
routeTrafficHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Route traffic hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `postRouteTraffic`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
postRouteTrafficHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Post route traffic hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `on`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
onSuccessOrFailureHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->On success or failure hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="canaryDeploymentStrategy{increments,preDeploy,deploy,routeTraffic,postRouteTraffic,on}" version="azure-pipelines"::: -->

```yaml
canary:
  increments: [ string ] # Maximum batch size for deployment 
  preDeploy:  # Pre deploy hook for canary deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where pre deploy steps will run
  deploy:  # Deploy hook for canary deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where deploy steps will run
  routeTraffic:  # Route traffic hook for canary deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where route traffic steps will run
  postRouteTraffic:  # Post route traffic hook for canary deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where post route traffic steps will run
  on:  # On success or failure hook for canary deployment strategy
    failure:  # Runs on failure of any step
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where post on failure steps will run
    success:  # Runs on success of all of the steps
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where on success steps will run
```


Properties that use this definition: [jobs.deployment.strategy.canary](jobs-deployment-strategy.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `increments`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Maximum batch size for deployment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `preDeploy`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
preDeployHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pre deploy hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `deploy`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
deployHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Deploy hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `routeTraffic`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
routeTrafficHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Route traffic hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `postRouteTraffic`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
postRouteTrafficHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Post route traffic hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `on`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
onSuccessOrFailureHook
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->On success or failure hook for canary deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

Canary deployment strategy is an advanced deployment strategy that helps mitigate the risk involved in rolling out new versions of applications. By using this strategy, you can roll out the changes to a small subset of servers first. As you gain more confidence in the new version, you can release it to more servers in your infrastructure and route more traffic to it.

Canary deployment strategy supports the `preDeploy` lifecycle hook (executed once) and iterates with the `deploy`, `routeTraffic`, and `postRouteTraffic` lifecycle hooks. It then exits with either the `success` or `failure` hook.

 
The following variables are available in this strategy:

`strategy.name`: Name of the strategy. For example, canary.
<br>`strategy.action`: The action to be performed on the Kubernetes cluster. For example, deploy, promote, or reject.
<br>`strategy.increment`: The increment value used in the current interaction. This variable is available only in `deploy`, `routeTraffic`, and `postRouteTraffic` lifecycle hooks.


## Examples

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
