---
title: jobs.deployment.strategy.rolling definition
description: jobs.deployment.strategy.rolling definition reference.
ms.date: 08/08/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"
---

# jobs.deployment.strategy.rolling definition


A rolling deployment replaces instances of the previous version of an application with instances of the new version of the application on a fixed set of virtual machines (rolling set) in each iteration. 


:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="rollingDeploymentStrategy{maxParallel,preDeploy,deploy,routeTraffic,postRouteTraffic,on}" version="azure-pipelines-2020"::: -->

```yaml
rolling:
  maxParallel: string # Maximum number of jobs running in parallel. 
  preDeploy:  # Pre deploy hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where pre deploy steps will run
  deploy:  # Deploy hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where deploy steps will run
  routeTraffic:  # Route traffic hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where route traffic steps will run
  postRouteTraffic:  # Post route traffic hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where post route traffic steps will run
  on:  # On success or failure hook for rolling deployment strategy
    failure:  # Runs on failure of any step
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where post on failure steps will run
    success:  # Runs on success of all of the steps
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where on success steps will run
```


Properties that use this definition: [jobs.deployment.strategy.rolling](jobs-deployment-strategy.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `maxParallel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Maximum number of jobs running in parallel. 
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
<!-- :::api-desc type="property"::: -->Pre deploy hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Deploy hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Route traffic hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Post route traffic hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->On success or failure hook for rolling deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="rollingDeploymentStrategy{maxParallel,preDeploy,deploy,routeTraffic,postRouteTraffic,on}" version="azure-pipelines-2020.1"::: -->

```yaml
rolling:
  maxParallel: string # Maximum number of jobs running in parallel. 
  preDeploy:  # Pre deploy hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where pre deploy steps will run
  deploy:  # Deploy hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where deploy steps will run
  routeTraffic:  # Route traffic hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where route traffic steps will run
  postRouteTraffic:  # Post route traffic hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where post route traffic steps will run
  on:  # On success or failure hook for rolling deployment strategy
    failure:  # Runs on failure of any step
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where post on failure steps will run
    success:  # Runs on success of all of the steps
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where on success steps will run
```


Properties that use this definition: [jobs.deployment.strategy.rolling](jobs-deployment-strategy.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `maxParallel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Maximum number of jobs running in parallel. 
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
<!-- :::api-desc type="property"::: -->Pre deploy hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Deploy hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Route traffic hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Post route traffic hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->On success or failure hook for rolling deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="rollingDeploymentStrategy{maxParallel,preDeploy,deploy,routeTraffic,postRouteTraffic,on}" version="azure-pipelines-2022"::: -->

```yaml
rolling:
  maxParallel: string # Maximum number of jobs running in parallel. 
  preDeploy:  # Pre deploy hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where pre deploy steps will run
  deploy:  # Deploy hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where deploy steps will run
  routeTraffic:  # Route traffic hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where route traffic steps will run
  postRouteTraffic:  # Post route traffic hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where post route traffic steps will run
  on:  # On success or failure hook for rolling deployment strategy
    failure:  # Runs on failure of any step
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where post on failure steps will run
    success:  # Runs on success of all of the steps
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where on success steps will run
```


Properties that use this definition: [jobs.deployment.strategy.rolling](jobs-deployment-strategy.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `maxParallel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Maximum number of jobs running in parallel. 
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
<!-- :::api-desc type="property"::: -->Pre deploy hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Deploy hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Route traffic hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Post route traffic hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->On success or failure hook for rolling deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="rollingDeploymentStrategy{maxParallel,preDeploy,deploy,routeTraffic,postRouteTraffic,on}" version="azure-pipelines"::: -->

```yaml
rolling:
  maxParallel: string # Maximum number of jobs running in parallel. 
  preDeploy:  # Pre deploy hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where pre deploy steps will run
  deploy:  # Deploy hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where deploy steps will run
  routeTraffic:  # Route traffic hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where route traffic steps will run
  postRouteTraffic:  # Post route traffic hook for rolling deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where post route traffic steps will run
  on:  # On success or failure hook for rolling deployment strategy
    failure:  # Runs on failure of any step
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where post on failure steps will run
    success:  # Runs on success of all of the steps
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where on success steps will run
```


Properties that use this definition: [jobs.deployment.strategy.rolling](jobs-deployment-strategy.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `maxParallel`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Maximum number of jobs running in parallel. 
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
<!-- :::api-desc type="property"::: -->Pre deploy hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Deploy hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Route traffic hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Post route traffic hook for rolling deployment strategy. 
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
<!-- :::api-desc type="property"::: -->On success or failure hook for rolling deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

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

### Descriptions of lifecycle hooks

`preDeploy`: Used to run steps that initialize resources before application deployment starts. 

`deploy`: Used to run steps that deploy your application. Download artifact task will be auto injected only in the `deploy` hook for deployment jobs. To stop downloading artifacts, use `- download: none` or choose specific artifacts to download by specifying [Download Pipeline Artifact task](steps-download.md).

`routeTraffic`: Used to run steps that serve the traffic to the updated version. 

`postRouteTraffic`: Used to run the steps after the traffic is routed. Typically, these tasks monitor the health of the updated version for defined interval. 

`on: failure` or `on: success`: Used to run steps for rollback actions or clean-up. 


## Examples

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


## See also

* [Deployment jobs](/azure/devops/pipelines/process/deployment-jobs)
