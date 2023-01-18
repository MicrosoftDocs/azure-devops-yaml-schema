---
title: jobs list definition
description: jobs list definition reference.
ms.date: 01/18/2023
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"
---

# jobs list definition


The jobs list specifies the jobs that make up the work of a stage.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="jobs[job]" version="azure-pipelines-2019"::: -->

```yaml
jobs: [ job ] # 
```


Properties that use this definition: [pipeline.jobs](pipeline.md)

## List types

| Type     | Description |
|----------|-------------|
| [jobs.job](jobs-job.md) | Agent pool job. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="jobs[job]" version="azure-pipelines-2019.1"::: -->

```yaml
jobs: [ job ] # 
```


Properties that use this definition: [pipeline.jobs](pipeline.md)

## List types

| Type     | Description |
|----------|-------------|
| [jobs.job](jobs-job.md) | Agent pool job. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="jobs[job]" version="azure-pipelines-2020"::: -->

```yaml
jobs: [ job | deployment | template ] # 
```


Properties that use this definition: [pipeline.jobs](pipeline.md), [stages.stage.jobs](stages-stage.md)

## List types

| Type     | Description |
|----------|-------------|
| [jobs.job](jobs-job.md) | Agent pool job. |
| [jobs.deployment](jobs-deployment.md) | Deployment job. |
| [jobs.template](jobs-template.md) | Jobs defined in a template file. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="jobs[job]" version="azure-pipelines-2020.1"::: -->

```yaml
jobs: [ job | deployment | template ] # 
```


Properties that use this definition: [pipeline.jobs](pipeline.md), [stages.stage.jobs](stages-stage.md)

## List types

| Type     | Description |
|----------|-------------|
| [jobs.job](jobs-job.md) | Agent pool job. |
| [jobs.deployment](jobs-deployment.md) | Deployment job. |
| [jobs.template](jobs-template.md) | Jobs defined in a template file. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="jobs[job]" version="azure-pipelines-2022"::: -->

```yaml
jobs: [ job | deployment | template ] # 
```


Properties that use this definition: [pipeline.jobs](pipeline.md), [stages.stage.jobs](stages-stage.md)

## List types

| Type     | Description |
|----------|-------------|
| [jobs.job](jobs-job.md) | Agent pool job. |
| [jobs.deployment](jobs-deployment.md) | Deployment job. |
| [jobs.template](jobs-template.md) | Jobs defined in a template file. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="jobs[job]" version="azure-pipelines"::: -->

```yaml
jobs: [ job | deployment | template ] # 
```


Properties that use this definition: [pipeline.jobs](pipeline.md), [stages.stage.jobs](stages-stage.md)

## List types

| Type     | Description |
|----------|-------------|
| [jobs.job](jobs-job.md) | Agent pool job. |
| [jobs.deployment](jobs-deployment.md) | Deployment job. |
| [jobs.template](jobs-template.md) | Jobs defined in a template file. |

<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

A [job](/azure/devops/pipelines/process/phases) is a collection of [steps](steps.md) run by an [agent](/azure/devops/pipelines/agents/agents) or on a [server](/azure/devops/pipelines/process/phases#server-jobs). Jobs can run [conditionally](/azure/devops/pipelines/process/phases#conditions) and  might [depend on earlier jobs](/azure/devops/pipelines/process/phases#dependencies).

> [!NOTE]
> If you have only one stage and one job, you can use [single-job syntax](/azure/devops/pipelines/process/phases) as a shorter way to describe the steps to run.


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


## See also

- For more information about `uses`, see [Limit job authorization scope to referenced Azure DevOps repositories](/azure/devops/pipelines/repos/azure-repos-git#limit-job-authorization-scope-to-referenced-azure-devops-repositories). For more information about workspaces, including clean options, see the [workspace](/azure/devops/pipelines/process/phases#workspace) topic in [Jobs](/azure/devops/pipelines/process/phases).
- Learn more about [variables](/azure/devops/pipelines/process/variables), [steps](steps.md), [pools](pool.md), and [server jobs](/azure/devops/pipelines/process/phases#server).





