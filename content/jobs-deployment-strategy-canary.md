---
title: jobs.deployment.strategy.canary definition
description: Canary Deployment strategy.
ms.date: 05/14/2024
monikerRange: ">=azure-pipelines-2020"
---

# jobs.deployment.strategy.canary definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Canary deployment strategy rolls out changes to a small subset of servers.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020"

```yaml
canary:
  increments: [ string ] # Maximum batch size for deployment.
  preDeploy: # Pre deploy hook for canary deployment strategy.
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
    pool: string | pool # Pool where pre deploy steps will run.
  deploy: # Deploy hook for canary deployment strategy.
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
    pool: string | pool # Pool where deploy steps will run.
  routeTraffic: # Route traffic hook for canary deployment strategy.
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
    pool: string | pool # Pool where route traffic steps will run.
  postRouteTraffic: # Post route traffic hook for canary deployment strategy.
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
    pool: string | pool # Pool where post route traffic steps will run.
  on: # On success or failure hook for canary deployment strategy.
    failure: # Runs on failure of any step.
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
      pool: string | pool # Pool where post on failure steps will run.
    success: # Runs on success of all of the steps.
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
      pool: string | pool # Pool where on success steps will run.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [jobs.deployment.strategy](jobs-deployment-strategy.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="increments"::: -->
:::moniker range=">=azure-pipelines-2020"

**`increments`** string list.<br><!-- :::editable-content name="propDescription"::: -->
Maximum batch size for deployment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="preDeploy"::: -->
:::moniker range=">=azure-pipelines-2020"

**`preDeploy`** [preDeployHook](pre-deploy-hook.md).<br><!-- :::editable-content name="propDescription"::: -->
Pre deploy hook for canary deployment strategy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploy"::: -->
:::moniker range=">=azure-pipelines-2020"

**`deploy`** [deployHook](deploy-hook.md).<br><!-- :::editable-content name="propDescription"::: -->
Deploy hook for canary deployment strategy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="routeTraffic"::: -->
:::moniker range=">=azure-pipelines-2020"

**`routeTraffic`** [routeTrafficHook](route-traffic-hook.md).<br><!-- :::editable-content name="propDescription"::: -->
Route traffic hook for canary deployment strategy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="postRouteTraffic"::: -->
:::moniker range=">=azure-pipelines-2020"

**`postRouteTraffic`** [postRouteTrafficHook](post-route-traffic-hook.md).<br><!-- :::editable-content name="propDescription"::: -->
Post route traffic hook for canary deployment strategy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="on"::: -->
:::moniker range=">=azure-pipelines-2020"

**`on`** [onSuccessOrFailureHook](on-success-or-failure-hook.md).<br><!-- :::editable-content name="propDescription"::: -->
On success or failure hook for canary deployment strategy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Canary deployment strategy is an advanced deployment strategy that helps mitigate the risk involved in rolling out new versions of applications. By using this strategy, you can roll out the changes to a small subset of servers first. As you gain more confidence in the new version, you can release it to more servers in your infrastructure and route more traffic to it.

Canary deployment strategy supports the `preDeploy` lifecycle hook (executed once) and iterates with the `deploy`, `routeTraffic`, and `postRouteTraffic` lifecycle hooks. It then exits with either the `success` or `failure` hook.
 
The following variables are available in this strategy:

`strategy.name`: Name of the strategy. For example, canary.
<br>`strategy.action`: The action to be performed on the Kubernetes cluster. For example, deploy, promote, or reject.
<br>`strategy.increment`: The increment value used in the current interaction. This variable is available only in `deploy`, `routeTraffic`, and `postRouteTraffic` lifecycle hooks.

### Descriptions of lifecycle hooks

`preDeploy`: Used to run steps that initialize resources before application deployment starts. 

`deploy`: Used to run steps that deploy your application. Download artifact task will be auto injected only in the `deploy` hook for deployment jobs. To stop downloading artifacts, use `- download: none` or choose specific artifacts to download by specifying [Download Pipeline Artifact task](steps-download.md).

`routeTraffic`: Used to run steps that serve the traffic to the updated version. 

`postRouteTraffic`: Used to run the steps after the traffic is routed. Typically, these tasks monitor the health of the updated version for defined interval. 

`on: failure` or `on: success`: Used to run steps for rollback actions or clean-up.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
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
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Deployment jobs](/azure/devops/pipelines/process/deployment-jobs)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->