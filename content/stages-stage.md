---
title: stages.stage definition
description: A stage is a collection of related jobs.
ms.date: 11/17/2023
monikerRange: ">=azure-pipelines-2020"
---

# stages.stage definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Stages are a collection of related jobs. By default, stages run sequentially. Each stage starts only after the preceding stage is complete unless otherwise specified via the `dependsOn` property.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2022"

```yaml
stages:
- stage: string # Required as first property. ID of the stage.
  displayName: string # Human-readable name for the stage.
  pool: string | pool # Pool where jobs in this stage will run unless otherwise specified.
  dependsOn: string | [ string ] # Any stages which must complete before this one.
  condition: string # Evaluate this condition expression to determine whether to run this stage.
  variables: variables | [ variable ] # Stage-specific variables.
  jobs: [ job | deployment | template ] # Jobs which make up the stage.
  lockBehavior: string # Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests.
  templateContext: # Stage related information passed from a pipeline when extending a template.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2020.1"

```yaml
stages:
- stage: string # Required as first property. ID of the stage.
  displayName: string # Human-readable name for the stage.
  pool: string | pool # Pool where jobs in this stage will run unless otherwise specified.
  dependsOn: string | [ string ] # Any stages which must complete before this one.
  condition: string # Evaluate this condition expression to determine whether to run this stage.
  variables: variables | [ variable ] # Stage-specific variables.
  jobs: [ job | deployment | template ] # Jobs which make up the stage.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [stages](stages.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="stage"::: -->
:::moniker range=">=azure-pipelines-2020"

**`stage`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
ID of the stage.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`displayName`** string.<br><!-- :::editable-content name="propDescription"::: -->
Human-readable name for the stage.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
:::moniker range=">=azure-pipelines-2020"

**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this stage will run unless otherwise specified.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dependsOn"::: -->
:::moniker range=">=azure-pipelines-2020"

**`dependsOn`** string | string list.<br><!-- :::editable-content name="propDescription"::: -->
Any stages which must complete before this one. By default stages are run sequentially in the order defined in the pipeline. Specify `dependsOn: []` for a stage if it shouldn't depend on the previous stage in the pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="condition"::: -->
:::moniker range=">=azure-pipelines-2020"

**`condition`** string.<br><!-- :::editable-content name="propDescription"::: -->
Evaluate this condition expression to determine whether to run this stage.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
:::moniker range=">=azure-pipelines-2020"

**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Stage-specific variables.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobs"::: -->
:::moniker range=">=azure-pipelines-2020"

**`jobs`** [jobs](jobs.md).<br><!-- :::editable-content name="propDescription"::: -->
Jobs which make up the stage.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="lockBehavior"::: -->
:::moniker range=">=azure-pipelines-2022"

**`lockBehavior`** string.<br><!-- :::editable-content name="propDescription"::: -->
Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests. sequential | runLatest.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="templateContext"::: -->
:::moniker range=">=azure-pipelines-2022"

**`templateContext`** templateContext.<br><!-- :::editable-content name="propDescription"::: -->
Stage related information passed from a pipeline when extending a template. For more information about `templateContext`, see [Extended YAML Pipelines templates can now be passed context information for stages, jobs, and deployments](/azure/devops/release-notes/2022/sprint-202-update#extended-yaml-pipelines-templates-can-now-be-passed-context-information-for-stages-jobs-and-deployments) and [Templates - Use templateContext to pass properties to templates](/azure/devops/pipelines/process/templates#use-templatecontext-to-pass-properties-to-templates).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

:::moniker range="azure-pipelines"

For more information about `templateContext`, see [Extended YAML Pipelines templates can now be passed context information for stages, jobs, and deployments](/azure/devops/release-notes/2022/sprint-202-update#extended-yaml-pipelines-templates-can-now-be-passed-context-information-for-stages-jobs-and-deployments) and [Templates - Use templateContext to pass properties to templates](/azure/devops/pipelines/process/templates#use-templatecontext-to-pass-properties-to-templates).

:::moniker-end

Use [approval checks](/azure/devops/pipelines/process/approvals) to manually control when a stage should run.
These checks are commonly used to control deployments to production environments.

Checks are a mechanism available to the *resource owner*.
They control when a stage in a pipeline consumes a resource.
As an owner of a resource like an environment, you can define checks that are required before a stage that consumes the resource can start.

Currently, manual approval checks are supported on [environments](/azure/devops/pipelines/process/environments).
For more information, see [Approvals](/azure/devops/pipelines/process/approvals).

:::moniker range="> azure-pipelines-2020.1"

### Exclusive lock

In YAML pipelines, checks are used to control the execution of stages on [protected resources](/azure/devops/pipelines/security/resources). One of the common checks that you can use is an [exclusive lock check](/azure/devops/pipelines/process/approvals). This check lets only a single run from the pipeline proceed. When multiple runs attempt to deploy to an environment at the same time, the check cancels all the old runs and permits the latest run to be deployed.

You can configure the behavior of the exclusive lock check using the `lockBehavior` property, which has two values:

- `runLatest` - Only the latest run acquires the lock to the resource. This is the default value if no `lockBehavior` is specified.
- `sequential` - All runs acquire the lock sequentially to the protected resource.

Canceling old runs is a good approach when your releases are cumulative and contain all the code changes from previous runs. However, there are some pipelines in which code changes are not cumulative. By configuring the `lockBehavior` property, you can choose to allow all runs to proceed and deploy sequentially to an environment, or preserve the previous behavior of canceling old runs and allowing just the latest. A value of `sequential` implies that all runs acquire the lock sequentially to the protected resource. A value of `runLatest` implies that only the latest run acquires the lock to the resource.

To use exclusive lock check with `sequential` deployments or `runLatest`, follow these steps:

 1. Enable the exclusive lock check on the environment (or another protected resource).
 2. In the YAML file for the pipeline, specify a new property called `lockBehavior`. This can be specified for the whole pipeline or for a given stage:

Set on a stage:

```yaml
stages:
- stage: A
  lockBehavior: sequential
  jobs:
  - job: Job
    steps:
    - script: Hey!
```
Set on the pipeline:

```yaml
lockBehavior: runLatest
stages:
- stage: A
  jobs:
  - job: Job
    steps:
    - script: Hey!
```

:::moniker-end
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

This example runs three stages, one after another.
The middle stage runs two jobs in parallel.

```yaml
stages:
- stage: Build
  jobs:
  - job: BuildJob
    steps:
    - script: echo Building!
- stage: Test
  jobs:
  - job: TestOnWindows
    steps:
    - script: echo Testing on Windows!
  - job: TestOnLinux
    steps:
    - script: echo Testing on Linux!
- stage: Deploy
  jobs:
  - job: Deploy
    steps:
    - script: echo Deploying the code!
```

This example runs two stages in parallel.
For brevity, the jobs and steps are omitted.

```yaml
stages:
- stage: BuildWin
  displayName: Build for Windows
- stage: BuildMac
  displayName: Build for Mac
  dependsOn: [] # by specifying an empty array, this stage doesn't depend on the stage before it
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

Learn more about [stages](/azure/devops/pipelines/process/stages), [conditions](/azure/devops/pipelines/process/conditions), and [variables](/azure/devops/pipelines/process/variables).
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->