---
title: jobs.job definition
description: A job is a collection of steps run by an agent or on a server.
ms.date: 03/01/2023
monikerRange: ">=azure-pipelines-2019"
---

# jobs.job definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
A [job](/azure/devops/pipelines/process/phases) is a collection of steps run by an [agent](/azure/devops/pipelines/agents/agents) or on a [server](/azure/devops/pipelines/process/phases#server-jobs).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2022"

```yaml
jobs:
- job: string # Required as first property. ID of the job.
  displayName: string # Human-readable name for the job.
  dependsOn: string | [ string ] # Any jobs which must complete before this one.
  condition: string # Evaluate this condition expression to determine whether to run this job.
  continueOnError: string # Continue running even on failure?
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it.
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it.
  variables: variables | [ variable ] # Job-specific variables.
  strategy: strategy # Execution strategy for this job.
  pool: string | pool # Pool where this job will run.
  container: string | container # Container resource name.
  services: # Container resources to run as a service container.
    string: string # Name/value pairs
  workspace: # Workspace options on the agent.
    clean: string # Which parts of the workspace should be scorched before fetching.
  uses: # Any resources required by this job that are not already referenced.
    repositories: [ string ] # Repository references.
    pools: [ string ] # Pool references.
  steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
  templateContext: # Job related information passed from a pipeline when extending a template.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

```yaml
jobs:
- job: string # Required as first property. ID of the job.
  displayName: string # Human-readable name for the job.
  dependsOn: string | [ string ] # Any jobs which must complete before this one.
  condition: string # Evaluate this condition expression to determine whether to run this job.
  continueOnError: string # Continue running even on failure?
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it.
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it.
  variables: variables | [ variable ] # Job-specific variables.
  strategy: strategy # Execution strategy for this job.
  pool: string | pool # Pool where this job will run.
  container: string | container # Container resource name.
  services: # Container resources to run as a service container.
    string: string # Name/value pairs
  workspace: # Workspace options on the agent.
    clean: string # Which parts of the workspace should be scorched before fetching.
  uses: # Any resources required by this job that are not already referenced.
    repositories: [ string ] # Repository references.
    pools: [ string ] # Pool references.
  steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
jobs:
- job: string # Required as first property. ID of the job.
  displayName: string # Human-readable name for the job.
  dependsOn: string | [ string ] # Any jobs which must complete before this one.
  condition: string # Evaluate this condition expression to determine whether to run this job.
  continueOnError: string # Continue running even on failure?
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it.
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it.
  variables: variables | [ variable ] # Job-specific variables.
  strategy: strategy # Execution strategy for this job.
  pool: string | pool # Pool where this job will run.
  container: string | container # Container resource name.
  services: # Container resources to run as a service container.
    string: string # Name/value pairs
  workspace: # Workspace options on the agent.
    clean: string # Which parts of the workspace should be scorched before fetching.
  steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # A list of steps to run.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

```yaml
jobs:
- job: string # Required as first property. ID of the job.
  displayName: string # Human-readable name for the job.
  dependsOn: string | [ string ] # Any jobs which must complete before this one.
  condition: string # Evaluate this condition expression to determine whether to run this job.
  continueOnError: string # Continue running even on failure?
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it.
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it.
  variables: variables | [ variable ] # Job-specific variables.
  strategy: strategy # Execution strategy for this job.
  pool: string | pool # Pool where this job will run.
  container: string | container # Container resource name.
  services: # Container resources to run as a service container.
    string: string # Name/value pairs
  workspace: # Workspace options on the agent.
    clean: string # Scorch the repo before fetching?
  steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | publish | template ] # A list of steps to run.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
jobs:
- job: string # Required as first property. ID of the job.
  displayName: string # Human-readable name for the job.
  dependsOn: string | [ string ] # Any jobs which must complete before this one.
  condition: string # Evaluate this condition expression to determine whether to run this job.
  continueOnError: string # Continue running even on failure?
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it.
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it.
  variables: variables | [ variable ] # Job-specific variables.
  strategy: strategy # Execution strategy for this job.
  pool: string | pool # Pool where this job will run.
  services: # Container resources to run as a service container.
    string: string # Name/value pairs
  workspace: # Workspace options on the agent.
    clean: string # Scorch the repo before fetching?
  steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | publish | template ] # A list of steps to run.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2019"

Definitions that that reference this definition: [jobs](jobs.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::item name="job"::: -->
**`job`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
ID of the job. Acceptable values: Valid names may only contain alphanumeric characters and '_' and may not start with a number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
**`displayName`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Human-readable name for the job.
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
Evaluate this condition expression to determine whether to run this job.
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
Job-specific variables.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
**`strategy`** [jobs.job.strategy](jobs-job-strategy.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Execution strategy for this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Pool where this job will run.
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
<!-- :::item name="workspace"::: -->
**`workspace`** [workspace](workspace.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Workspace options on the agent. For more information about workspaces, including clean options, see the [workspace](/azure/devops/pipelines/process/phases#workspace) topic in [Jobs](/azure/devops/pipelines/process/phases).
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="uses"::: -->
**`uses`** [jobs.job.uses](jobs-job-uses.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Any resources required by this job that are not already referenced. For more information about `uses`, see [Limit job authorization scope to referenced Azure DevOps repositories](/azure/devops/pipelines/repos/azure-repos-git#limit-job-authorization-scope-to-referenced-azure-devops-repositories).
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="steps"::: -->
**`steps`** [steps](steps.md).<br>
<!-- :::editable-content name="propDescription"::: -->
A list of steps to run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="templateContext"::: -->
**`templateContext`** templateContext.<br>
<!-- :::editable-content name="propDescription"::: -->
Job related information passed from a pipeline when extending a template. See remarks for more information. For more information about `templateContext`, see [Extended YAML Pipelines templates can now be passed context information for stages, jobs, and deployments](/azure/devops/release-notes/2022/sprint-202-update#extended-yaml-pipelines-templates-can-now-be-passed-context-information-for-stages-jobs-and-deployments) and [Templates - Use templateContext to pass properties to templates](/azure/devops/pipelines/process/templates#use-templatecontext-to-pass-properties-to-templates).
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

<!-- :::item name="job"::: -->
**`job`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
ID of the job. Acceptable values: Valid names may only contain alphanumeric characters and '_' and may not start with a number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
**`displayName`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Human-readable name for the job.
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
Evaluate this condition expression to determine whether to run this job.
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
Job-specific variables.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
**`strategy`** [jobs.job.strategy](jobs-job-strategy.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Execution strategy for this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Pool where this job will run.
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
<!-- :::item name="workspace"::: -->
**`workspace`** [workspace](workspace.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Workspace options on the agent. For more information about workspaces, including clean options, see the [workspace](/azure/devops/pipelines/process/phases#workspace) topic in [Jobs](/azure/devops/pipelines/process/phases).
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="uses"::: -->
**`uses`** [jobs.job.uses](jobs-job-uses.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Any resources required by this job that are not already referenced.

For more information about `uses`, see [Limit job authorization scope to referenced Azure DevOps repositories](/azure/devops/pipelines/repos/azure-repos-git#limit-job-authorization-scope-to-referenced-azure-devops-repositories).
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="steps"::: -->
**`steps`** [steps](steps.md).<br>
<!-- :::editable-content name="propDescription"::: -->
A list of steps to run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020"

<!-- :::item name="job"::: -->
**`job`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
ID of the job. Acceptable values: Valid names may only contain alphanumeric characters and '_' and may not start with a number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
**`displayName`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Human-readable name for the job.
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
Evaluate this condition expression to determine whether to run this job.
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
Job-specific variables.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
**`strategy`** [jobs.job.strategy](jobs-job-strategy.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Execution strategy for this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Pool where this job will run.
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
<!-- :::item name="workspace"::: -->
**`workspace`** [workspace](workspace.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Workspace options on the agent. For more information about workspaces, including clean options, see the [workspace](/azure/devops/pipelines/process/phases#workspace) topic in [Jobs](/azure/devops/pipelines/process/phases).
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="steps"::: -->
**`steps`** [steps](steps.md).<br>
<!-- :::editable-content name="propDescription"::: -->
A list of steps to run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::item name="job"::: -->
**`job`** string. Required as first property.<br>
<!-- :::editable-content name="propDescription"::: -->
ID of the job. Acceptable values: Valid names may only contain alphanumeric characters and '_' and may not start with a number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
**`displayName`** string.<br>
<!-- :::editable-content name="propDescription"::: -->
Human-readable name for the job.
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
Evaluate this condition expression to determine whether to run this job.
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
Job-specific variables.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
**`strategy`** [jobs.job.strategy](jobs-job-strategy.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Execution strategy for this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Pool where this job will run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="services"::: -->
**`services`** string dictionary.<br>
<!-- :::editable-content name="propDescription"::: -->
Container resources to run as a service container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="workspace"::: -->
**`workspace`** [workspace](workspace.md).<br>
<!-- :::editable-content name="propDescription"::: -->
Workspace options on the agent. For more information about workspaces, including clean options, see the [workspace](/azure/devops/pipelines/process/phases#workspace) topic in [Jobs](/azure/devops/pipelines/process/phases).
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="steps"::: -->
**`steps`** [steps](steps.md).<br>
<!-- :::editable-content name="propDescription"::: -->
A list of steps to run.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

The default `timeoutInMinutes` is set to 60 minutes. For more information, see [Timeouts](/azure/devops/pipelines/process/phases#timeouts).

Jobs can run [conditionally](/azure/devops/pipelines/process/phases#conditions) and might [depend on earlier jobs](/azure/devops/pipelines/process/phases#dependencies).

> [!NOTE]
> If you have only one stage and one job, you can use [single-job syntax](/azure/devops/pipelines/process/phases) as a shorter way to describe the steps to run.

:::moniker range="azure-pipelines"

For more information about `templateContext`, see [Extended YAML Pipelines templates can now be passed context information for stages, jobs, and deployments](/azure/devops/release-notes/2022/sprint-202-update#extended-yaml-pipelines-templates-can-now-be-passed-context-information-for-stages-jobs-and-deployments) and [Templates - Use templateContext to pass properties to templates](/azure/devops/pipelines/process/templates#use-templatecontext-to-pass-properties-to-templates).

:::moniker-end
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yaml
jobs:
- job: MyJob
  displayName: My First Job
  continueOnError: true
  workspace:
    clean: outputs
  steps:
  - script: echo My first job
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- For more information about `uses`, see [Limit job authorization scope to referenced Azure DevOps repositories](/azure/devops/pipelines/repos/azure-repos-git#limit-job-authorization-scope-to-referenced-azure-devops-repositories).
- For more information about workspaces, including clean options, see the [workspace](/azure/devops/pipelines/process/phases#workspace) topic in [Jobs](/azure/devops/pipelines/process/phases).
- Learn more about [variables](/azure/devops/pipelines/process/variables), [steps](steps.md), [pools](pool.md), and [server jobs](/azure/devops/pipelines/process/phases#server).
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->