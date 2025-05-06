---
title: jobs.deployment.strategy.runOnce definition
description: RunOnce Deployment strategy.
ms.date: 04/30/2025
monikerRange: "<=azure-pipelines"
author: ramiMSFT
ms.author: rabououn
---

# jobs.deployment.strategy.runOnce definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
The runOnce deployment strategy rolls out changes by executing each of its steps one time.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
runOnce:
  preDeploy: # Pre deploy hook for runOnce deployment strategy.
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
    pool: string | pool # Pool where pre deploy steps will run.
  deploy: # Deploy hook for runOnce deployment strategy.
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
    pool: string | pool # Pool where deploy steps will run.
  routeTraffic: # Route traffic hook for runOnce deployment strategy.
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
    pool: string | pool # Pool where route traffic steps will run.
  postRouteTraffic: # Post route traffic hook for runOnce deployment strategy.
    steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
    pool: string | pool # Pool where post route traffic steps will run.
  on: # On success or failure hook for runOnce deployment strategy.
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
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [jobs.deployment.strategy](jobs-deployment-strategy.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="preDeploy"::: -->
:::moniker range="<=azure-pipelines"

**`preDeploy`** [preDeployHook](pre-deploy-hook.md).<br><!-- :::editable-content name="propDescription"::: -->
Pre deploy hook for runOnce deployment strategy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="deploy"::: -->
:::moniker range="<=azure-pipelines"

**`deploy`** [deployHook](deploy-hook.md).<br><!-- :::editable-content name="propDescription"::: -->
Deploy hook for runOnce deployment strategy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="routeTraffic"::: -->
:::moniker range="<=azure-pipelines"

**`routeTraffic`** [routeTrafficHook](route-traffic-hook.md).<br><!-- :::editable-content name="propDescription"::: -->
Route traffic hook for runOnce deployment strategy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="postRouteTraffic"::: -->
:::moniker range="<=azure-pipelines"

**`postRouteTraffic`** [postRouteTrafficHook](post-route-traffic-hook.md).<br><!-- :::editable-content name="propDescription"::: -->
Post route traffic hook for runOnce deployment strategy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="on"::: -->
:::moniker range="<=azure-pipelines"

**`on`** [onSuccessOrFailureHook](on-success-or-failure-hook.md).<br><!-- :::editable-content name="propDescription"::: -->
On success or failure hook for runOnce deployment strategy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

`runOnce` is the simplest deployment strategy wherein all the lifecycle hooks, namely `preDeploy` `deploy`, `routeTraffic`, and `postRouteTraffic`, are executed once. Then, either `on:` `success` or `on:` `failure` is executed.

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
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Deployment jobs](/azure/devops/pipelines/process/deployment-jobs)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->