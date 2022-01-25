---
title: jobs.deployment.strategy.runOnce definition
description: jobs.deployment.strategy.runOnce definition reference.
ms.date: 01/25/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# jobs.deployment.strategy.runOnce definition


The runOnce deployment strategy rolls out changes by executing each of its steps one time.


:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="runOnceDeploymentStrategy{preDeploy,deploy,routeTraffic,postRouteTraffic,on}" version="azure-pipelines-2020"::: -->

```yaml
runOnce:
  preDeploy:  # Pre deploy hook for runOnce deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where pre deploy steps will run
  deploy:  # Deploy hook for runOnce deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where deploy steps will run
  routeTraffic:  # Route traffic hook for runOnce deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where route traffic steps will run
  postRouteTraffic:  # Post route traffic hook for runOnce deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where post route traffic steps will run
  on:  # On success or failure hook for runOnce deployment strategy
    failure:  # Runs on failure of any step
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where post on failure steps will run
    success:  # Runs on success of all of the steps
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where on success steps will run
```


Properties that use this definition: [jobs.deployment.strategy.runOnce](jobs-deployment-strategy.md)

## Properties


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
<!-- :::api-desc type="property"::: -->Pre deploy hook for runOnce deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Deploy hook for runOnce deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Route traffic hook for runOnce deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Post route traffic hook for runOnce deployment strategy. 
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
<!-- :::api-desc type="property"::: -->On success or failure hook for runOnce deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="runOnceDeploymentStrategy{preDeploy,deploy,routeTraffic,postRouteTraffic,on}" version="azure-pipelines-2020.1"::: -->

```yaml
runOnce:
  preDeploy:  # Pre deploy hook for runOnce deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where pre deploy steps will run
  deploy:  # Deploy hook for runOnce deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where deploy steps will run
  routeTraffic:  # Route traffic hook for runOnce deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where route traffic steps will run
  postRouteTraffic:  # Post route traffic hook for runOnce deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where post route traffic steps will run
  on:  # On success or failure hook for runOnce deployment strategy
    failure:  # Runs on failure of any step
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where post on failure steps will run
    success:  # Runs on success of all of the steps
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where on success steps will run
```


Properties that use this definition: [jobs.deployment.strategy.runOnce](jobs-deployment-strategy.md)

## Properties


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
<!-- :::api-desc type="property"::: -->Pre deploy hook for runOnce deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Deploy hook for runOnce deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Route traffic hook for runOnce deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Post route traffic hook for runOnce deployment strategy. 
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
<!-- :::api-desc type="property"::: -->On success or failure hook for runOnce deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="runOnceDeploymentStrategy{preDeploy,deploy,routeTraffic,postRouteTraffic,on}" version="azure-pipelines"::: -->

```yaml
runOnce:
  preDeploy:  # Pre deploy hook for runOnce deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where pre deploy steps will run
  deploy:  # Deploy hook for runOnce deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where deploy steps will run
  routeTraffic:  # Route traffic hook for runOnce deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where route traffic steps will run
  postRouteTraffic:  # Post route traffic hook for runOnce deployment strategy
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
    pool: pool # Pool where post route traffic steps will run
  on:  # On success or failure hook for runOnce deployment strategy
    failure:  # Runs on failure of any step
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where post on failure steps will run
    success:  # Runs on success of all of the steps
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | restoreCache | saveCache | reviewApp ]
      pool: pool # Pool where on success steps will run
```


Properties that use this definition: [jobs.deployment.strategy.runOnce](jobs-deployment-strategy.md)

## Properties


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
<!-- :::api-desc type="property"::: -->Pre deploy hook for runOnce deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Deploy hook for runOnce deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Route traffic hook for runOnce deployment strategy. 
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
<!-- :::api-desc type="property"::: -->Post route traffic hook for runOnce deployment strategy. 
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
<!-- :::api-desc type="property"::: -->On success or failure hook for runOnce deployment strategy. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

`runOnce` is the simplest deployment strategy wherein all the lifecycle hooks, namely `preDeploy` `deploy`, `routeTraffic`, and `postRouteTraffic`, are executed once. Then, either `on:` `success` or `on:` `failure` is executed.

```

### Descriptions of lifecycle hooks

`preDeploy`: Used to run steps that initialize resources before application deployment starts. 

`deploy`: Used to run steps that deploy your application. Download artifact task will be auto injected only in the `deploy` hook for deployment jobs. To stop downloading artifacts, use `- download: none` or choose specific artifacts to download by specifying [Download Pipeline Artifact task](steps.download.md).

`routeTraffic`: Used to run steps that serve the traffic to the updated version. 

`postRouteTraffic`: Used to run the steps after the traffic is routed. Typically, these tasks monitor the health of the updated version for defined interval. 

`on: failure` or `on: success`: Used to run steps for rollback actions or clean-up. 


## Examples

The following example YAML snippet showcases a simple use of a deployment job by using the `runOnce` deployment strategy. The example includes a checkout step. 

```YAML

jobs:
  # Track deployments on the environment.
- deployment: DeployWeb
  displayName: deploy Web App
  pool:
    vmImage: ubuntu-latest
  # Creates an environment if it doesn't exist.
  environment: 'smarthotel-dev'
  strategy:
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
    vmImage: ubuntu-latest
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


## See also

* [Deployment jobs](/azure/devops/pipelines/process/deployment-jobs)
