---
title: stages.stage definition
description: A stage is a collection of related jobs.
ms.date: 11/10/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# stages.stage definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Stages are a collection of related jobs. By default, stages run sequentially. Each stage starts only after the preceding stage is complete unless otherwise specified via the `dependsOn` property.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="=azure-pipelines"

```yaml
stages:
- stage: string # Required as first property. ID of the stage.
  displayName: string # Human-readable name for the stage.
  pool: string | pool # Pool where jobs in this stage will run unless otherwise specified.
  dependsOn: string | [ string ] # Any stages which must complete before this one.
  condition: string # Evaluate this condition expression to determine whether to run this stage.
  variables: variables | [ variable ] # Stage-specific variables.
  jobs: [ job | deployment | template ] # Jobs which make up the stage.
  lockBehavior: sequential | runLatest # Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests.
  trigger: manual | automatic # Stage trigger manual or automatic (default).
  isSkippable: boolean # Setting false prevents the stage from being skipped. By default it's always true.
  templateContext: # Stage related information passed from a pipeline when extending a template.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2022 <=azure-pipelines-server"

```yaml
stages:
- stage: string # Required as first property. ID of the stage.
  displayName: string # Human-readable name for the stage.
  pool: string | pool # Pool where jobs in this stage will run unless otherwise specified.
  dependsOn: string | [ string ] # Any stages which must complete before this one.
  condition: string # Evaluate this condition expression to determine whether to run this stage.
  variables: variables | [ variable ] # Stage-specific variables.
  jobs: [ job | deployment | template ] # Jobs which make up the stage.
  lockBehavior: sequential | runLatest # Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests.
  templateContext: # Stage related information passed from a pipeline when extending a template.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [stages](stages.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="stage"::: -->
:::moniker range="<=azure-pipelines"

**`stage`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
ID of the stage.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
:::moniker range="<=azure-pipelines"

**`displayName`** string.<br><!-- :::editable-content name="propDescription"::: -->
Human-readable name for the stage.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
:::moniker range="<=azure-pipelines"

**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this stage will run unless otherwise specified.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="dependsOn"::: -->
:::moniker range="<=azure-pipelines"

**`dependsOn`** string | string list.<br><!-- :::editable-content name="propDescription"::: -->
Any stages which must complete before this one. By default stages are run sequentially in the order defined in the pipeline. Specify `dependsOn: []` for a stage if it shouldn't depend on the previous stage in the pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="condition"::: -->
:::moniker range="<=azure-pipelines"

**`condition`** string.<br><!-- :::editable-content name="propDescription"::: -->
Evaluate this condition expression to determine whether to run this stage.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
:::moniker range="<=azure-pipelines"

**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Stage-specific variables.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobs"::: -->
:::moniker range="<=azure-pipelines"

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
<!-- :::item name="trigger"::: -->
:::moniker range="=azure-pipelines"

**`trigger`** string.<br><!-- :::editable-content name="propDescription"::: -->
Stage trigger manual or automatic (default). manual | automatic.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isSkippable"::: -->
:::moniker range="=azure-pipelines"

**`isSkippable`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Setting false prevents the stage from being skipped. By default it's always true.
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

:::moniker range="<=azure-pipelines"

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

:::moniker range="> azure-pipelines-2022.2"

### Exclusive lock at stage level

Some use cases require a pipeline to access a specific resource only once at any given time. To support this case, we have the exclusive lock check described in the previous section..

A similar situation arises when only one pipeline run should access a stage at any point in time. For instance, if you have a stage that deploys to an Azure resource group, you may want to prevent multiple pipeline runs from simultaneously updating the same resource group. Currently, achieving this requires using a proxy resource, such as an environment, and placing the exclusive lock check on that environment. This approach can be time-consuming, add complexity, and increase maintenance efforts.

If you need to ensure only a single pipeline run at a time can access a stage, you can specify the exclusive lock at the stage level. If you have a stage with an ID and specify its `lockBehavior` property, a lock is automatically created for that stage. The sequential behavior remains consistent for both resource-level and stage-level locks. However, the `runLatest` behavior differs, as it only cancels `runLatest` builds for the same branch, not for all branches of the pipeline.

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