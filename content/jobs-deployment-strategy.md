---
title: jobs.deployment.strategy definition
description: Execution strategy for this deployment.
ms.date: 11/17/2023
monikerRange: ">=azure-pipelines-2020"
---

# jobs.deployment.strategy definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
A deployment strategy enables you to configure how the update is delivered.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [jobs.deployment](jobs-deployment.md)

:::moniker-end
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range=">=azure-pipelines-2020"

| Implementation | Description |
|---|---|
| [strategy: runOnce](#strategyrunonce) | Run once deployment strategy. |
| [strategy: rolling](#strategyrolling) | Rolling deployment strategy. |
| [strategy: canary](#strategycanary) | Canary deployment strategy. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
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
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="strategy: runOnce"::: -->
<a name="strategyrunonce"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## strategy: runOnce
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
The runOnce deployment strategy rolls out changes by executing each of its steps one time.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
strategy:
  runOnce: # RunOnce Deployment strategy.
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
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="runOnce"::: -->
**`runOnce`** [jobs.deployment.strategy.runOnce](jobs-deployment-strategy-run-once.md).<br><!-- :::editable-content name="propDescription"::: -->
RunOnce Deployment strategy.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end
<!-- :::objectAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
### Remarks

`runOnce` is the simplest deployment strategy wherein all the lifecycle hooks, namely `preDeploy` `deploy`, `routeTraffic`, and `postRouteTraffic`, are executed once. Then, either `on: success` or `on: failure` is executed.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="strategy: rolling"::: -->
<a name="strategyrolling"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## strategy: rolling
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
A rolling deployment replaces instances of the previous version of an application with instances of the new version of the application on a fixed set of virtual machines (rolling set) in each iteration.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
strategy:
  rolling: # Rolling Deployment strategy.
    maxParallel: string # Maximum number of jobs running in parallel.
    preDeploy: # Pre deploy hook for rolling deployment strategy.
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
      pool: string | pool # Pool where pre deploy steps will run.
    deploy: # Deploy hook for rolling deployment strategy.
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
      pool: string | pool # Pool where deploy steps will run.
    routeTraffic: # Route traffic hook for rolling deployment strategy.
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
      pool: string | pool # Pool where route traffic steps will run.
    postRouteTraffic: # Post route traffic hook for rolling deployment strategy.
      steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
      pool: string | pool # Pool where post route traffic steps will run.
    on: # On success or failure hook for rolling deployment strategy.
      failure: # Runs on failure of any step.
        steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
        pool: string | pool # Pool where post on failure steps will run.
      success: # Runs on success of all of the steps.
        steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
        pool: string | pool # Pool where on success steps will run.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="rolling"::: -->
**`rolling`** [jobs.deployment.strategy.rolling](jobs-deployment-strategy-rolling.md).<br><!-- :::editable-content name="propDescription"::: -->
Rolling Deployment strategy.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end
<!-- :::objectAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="strategy: canary"::: -->
<a name="strategycanary"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## strategy: canary
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Canary deployment strategy rolls out changes to a small subset of servers.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
strategy:
  canary: # Canary Deployment strategy.
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
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="canary"::: -->
**`canary`** [jobs.deployment.strategy.canary](jobs-deployment-strategy-canary.md).<br><!-- :::editable-content name="propDescription"::: -->
Canary Deployment strategy.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end
<!-- :::objectAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
### Remarks

Canary deployment strategy is an advanced deployment strategy that helps mitigate the risk involved in rolling out new versions of applications. By using this strategy, you can roll out the changes to a small subset of servers first. As you gain more confidence in the new version, you can release it to more servers in your infrastructure and route more traffic to it.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Deployment jobs](/azure/devops/pipelines/process/deployment-jobs)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
