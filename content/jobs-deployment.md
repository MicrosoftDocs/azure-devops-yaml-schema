---
title: jobs.deployment definition
description: A deployment job is a special type of job. It's a collection of steps to run sequentially against the environment.
ms.date: 03/01/2023
monikerRange: ">=azure-pipelines-2020"
---

# jobs.deployment definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
A [deployment job](/azure/devops/pipelines/process/deployment-jobs) is a special type of job.
It's a collection of steps to run sequentially against the environment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2022"

```yaml
jobs:
- deployment: string # Required as first property. Name of the deployment job, A-Z, a-z, 0-9, and underscore. The word deploy is a keyword and is unsupported as the deployment name.
  displayName: string # Human-readable name for the deployment.
  dependsOn: string | [ string ] # Any jobs which must complete before this one.
  condition: string # Evaluate this condition expression to determine whether to run this deployment.
  continueOnError: string # Continue running even on failure?
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it.
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it.
  variables: variables | [ variable ] # Deployment-specific variables.
  pool: string | pool # Pool where this job will run.
  environment: string | environment # Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name.
  strategy: strategy # Execution strategy for this deployment.
  workspace: # Workspace options on the agent.
    clean: string # Which parts of the workspace should be scorched before fetching.
  uses: # Any resources required by this job that are not already referenced.
    repositories: [ string ] # Repository references.
    pools: [ string ] # Pool references.
  container: string | container # Container resource name.
  services: # Container resources to run as a service container.
    string: string # Name/value pairs
  templateContext: # Deployment related information passed from a pipeline when extending a template.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

```yaml
jobs:
- deployment: string # Required as first property. Name of the deployment job, A-Z, a-z, 0-9, and underscore. The word deploy is a keyword and is unsupported as the deployment name.
  displayName: string # Human-readable name for the deployment.
  dependsOn: string | [ string ] # Any jobs which must complete before this one.
  condition: string # Evaluate this condition expression to determine whether to run this deployment.
  continueOnError: string # Continue running even on failure?
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it.
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it.
  variables: variables | [ variable ] # Deployment-specific variables.
  pool: string | pool # Pool where this job will run.
  environment: string | environment # Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name.
  strategy: strategy # Execution strategy for this deployment.
  workspace: # Workspace options on the agent.
    clean: string # Which parts of the workspace should be scorched before fetching.
  uses: # Any resources required by this job that are not already referenced.
    repositories: [ string ] # Repository references.
    pools: [ string ] # Pool references.
  container: string | container # Container resource name.
  services: # Container resources to run as a service container.
    string: string # Name/value pairs
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
jobs:
- deployment: string # Required as first property. Name of the deployment job, A-Z, a-z, 0-9, and underscore. The word deploy is a keyword and is unsupported as the deployment name.
  displayName: string # Human-readable name for the deployment.
  dependsOn: string | [ string ] # Any jobs which must complete before this one.
  condition: string # Evaluate this condition expression to determine whether to run this deployment.
  continueOnError: string # Continue running even on failure?
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it.
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it.
  variables: variables | [ variable ] # Deployment-specific variables.
  pool: string | pool # Pool where this job will run.
  environment: string | environment # Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name.
  strategy: strategy # Execution strategy for this deployment.
  workspace: # Workspace options on the agent.
    clean: string # Which parts of the workspace should be scorched before fetching.
  container: string | container # Container resource name.
  services: # Container resources to run as a service container.
    string: string # Name/value pairs
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that that reference this definition: [jobs](jobs.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::item name="deployment"::: -->
**`deployment`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
Name of the deployment job, A-Z, a-z, 0-9, and underscore. The word deploy is a keyword and is unsupported as the deployment name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
**`displayName`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Human-readable name for the deployment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="dependsOn"::: -->
**`dependsOn`** string | string list.<br>
<!-- :::editable-content name="propDescription"::: -->
Any jobs which must complete before this one.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="condition"::: -->
**`condition`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Evaluate this condition expression to determine whether to run this deployment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="continueOnError"::: -->
**`continueOnError`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="timeoutInMinutes"::: -->
**`timeoutInMinutes`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Time to wait for this job to complete before the server kills it.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="cancelTimeoutInMinutes"::: -->
**`cancelTimeoutInMinutes`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Time to wait for the job to cancel before forcibly terminating it.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Deployment-specific variables.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Pool where this job will run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="environment"::: -->
**`environment`** [jobs.deployment.environment](jobs-deployment-environment.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
**`strategy`** [jobs.deployment.strategy](jobs-deployment-strategy.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Execution strategy for this deployment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="workspace"::: -->
**`workspace`** [workspace](workspace.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Workspace options on the agent.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="uses"::: -->
**`uses`** [jobs.job.uses](jobs-job-uses.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Any resources required by this job that are not already referenced.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="container"::: -->
**`container`** [jobs.job.container](jobs-job-container.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Container resource name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="services"::: -->
**`services`** string dictionary.<br>
<!-- :::editable-content name="propDescription"::: -->
Container resources to run as a service container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="templateContext"::: -->
**`templateContext`** templateContext.<br>
<!-- :::editable-content name="propDescription"::: -->
Deployment related information passed from a pipeline when extending a template. See remarks for more information.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

<!-- :::item name="deployment"::: -->
**`deployment`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
Name of the deployment job, A-Z, a-z, 0-9, and underscore. The word deploy is a keyword and is unsupported as the deployment name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
**`displayName`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Human-readable name for the deployment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="dependsOn"::: -->
**`dependsOn`** string | string list.<br>
<!-- :::editable-content name="propDescription"::: -->
Any jobs which must complete before this one.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="condition"::: -->
**`condition`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Evaluate this condition expression to determine whether to run this deployment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="continueOnError"::: -->
**`continueOnError`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="timeoutInMinutes"::: -->
**`timeoutInMinutes`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Time to wait for this job to complete before the server kills it.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="cancelTimeoutInMinutes"::: -->
**`cancelTimeoutInMinutes`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Time to wait for the job to cancel before forcibly terminating it.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Deployment-specific variables.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Pool where this job will run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="environment"::: -->
**`environment`** [jobs.deployment.environment](jobs-deployment-environment.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
**`strategy`** [jobs.deployment.strategy](jobs-deployment-strategy.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Execution strategy for this deployment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="workspace"::: -->
**`workspace`** [workspace](workspace.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Workspace options on the agent.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="uses"::: -->
**`uses`** [jobs.job.uses](jobs-job-uses.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Any resources required by this job that are not already referenced.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="container"::: -->
**`container`** [jobs.job.container](jobs-job-container.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Container resource name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="services"::: -->
**`services`** string dictionary.<br>
<!-- :::editable-content name="propDescription"::: -->
Container resources to run as a service container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020"

<!-- :::item name="deployment"::: -->
**`deployment`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
Name of the deployment job, A-Z, a-z, 0-9, and underscore. The word deploy is a keyword and is unsupported as the deployment name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
**`displayName`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Human-readable name for the deployment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="dependsOn"::: -->
**`dependsOn`** string | string list.<br>
<!-- :::editable-content name="propDescription"::: -->
Any jobs which must complete before this one.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="condition"::: -->
**`condition`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Evaluate this condition expression to determine whether to run this deployment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="continueOnError"::: -->
**`continueOnError`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="timeoutInMinutes"::: -->
**`timeoutInMinutes`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Time to wait for this job to complete before the server kills it.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="cancelTimeoutInMinutes"::: -->
**`cancelTimeoutInMinutes`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Time to wait for the job to cancel before forcibly terminating it.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Deployment-specific variables.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Pool where this job will run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="environment"::: -->
**`environment`** [jobs.deployment.environment](jobs-deployment-environment.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
**`strategy`** [jobs.deployment.strategy](jobs-deployment-strategy.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Execution strategy for this deployment.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="workspace"::: -->
**`workspace`** [workspace](workspace.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Workspace options on the agent.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="container"::: -->
**`container`** [jobs.job.container](jobs-job-container.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Container resource name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="services"::: -->
**`services`** string dictionary.<br>
<!-- :::editable-content name="propDescription"::: -->
Container resources to run as a service container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

In YAML pipelines, the pipelines team recommends that you put your deployment steps in a deployment job.

:::moniker range="azure-pipelines"

For more information about `templateContext`, see [Extended YAML Pipelines templates can now be passed context information for stages, jobs, and deployments](/azure/devops/release-notes/2022/sprint-202-update#extended-yaml-pipelines-templates-can-now-be-passed-context-information-for-stages-jobs-and-deployments) and [Templates - Use templateContext to pass properties to templates](/azure/devops/pipelines/process/templates#use-templatecontext-to-pass-properties-to-templates).

:::moniker-end
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```YAML
jobs:
  # track deployments on the environment
- deployment: DeployWeb
  displayName: deploy Web App
  pool:
    vmImage: ubuntu-latest
  # creates an environment if it doesn't exist
  environment: 'smarthotel-dev'
  strategy:
    # default deployment strategy, more coming...
    runOnce:
      deploy:
        steps:
        - script: echo my first deployment
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->