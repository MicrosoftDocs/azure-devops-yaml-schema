---
title: jobs definition
description: Specifies the jobs that make up the work of a stage.
ms.date: 03/20/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# jobs definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Specifies the jobs that make up the work of a stage.
<!-- :::editable-content-end::: -->

:::moniker-end

<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
jobs: [ job | deployment | template ] # Specifies the jobs that make up the work of a stage.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [pipeline](pipeline.md), [stages.stage](stages-stage.md)

:::moniker-end

<!-- :::parents-end::: -->

## List types

<!-- :::list-types::: -->
:::moniker range="<=azure-pipelines"

| Type | Description |
|---|---|
| [jobs.job](jobs-job.md) | A job is a collection of steps run by an agent or on a server. |
| [jobs.deployment](jobs-deployment.md) | A deployment job is a special type of job. It's a collection of steps to run sequentially against the environment. |
| [jobs.template](jobs-template.md) | A set of jobs defined in a template. |

:::moniker-end

<!-- :::list-types-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

A [job](/azure/devops/pipelines/process/phases) is a collection of [steps](steps.md) run by an [agent](/azure/devops/pipelines/agents/agents) or on a [server](/azure/devops/pipelines/process/phases#server-jobs). Jobs can run [conditionally](/azure/devops/pipelines/process/phases#conditions) and  might [depend on earlier jobs](/azure/devops/pipelines/process/phases#dependencies).

> [!NOTE]
> If you have only one stage and one job, you can use [single-job syntax](/azure/devops/pipelines/process/phases) as a shorter way to describe the steps to run.
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

- For more information about `uses`, see [Limit job authorization scope to referenced Azure DevOps repositories](/azure/devops/pipelines/repos/azure-repos-git#limit-job-authorization-scope-to-referenced-azure-devops-repositories). For more information about workspaces, including clean options, see the [workspace](/azure/devops/pipelines/process/phases#workspace) topic in [Jobs](/azure/devops/pipelines/process/phases).
- Learn more about [variables](/azure/devops/pipelines/process/variables), [steps](steps.md), [pools](pool.md), and [server jobs](/azure/devops/pipelines/process/phases#server).
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->