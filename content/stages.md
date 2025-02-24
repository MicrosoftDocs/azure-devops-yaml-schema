---
title: stages definition
description: Stages are a collection of related jobs.
ms.date: 02/24/2025
monikerRange: ">=azure-pipelines-2020"
---

# stages definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Stages are a collection of related jobs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020"

```yaml
stages: [ stage | template ] # Stages are a collection of related jobs.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [pipeline](pipeline.md)

:::moniker-end
<!-- :::parents-end::: -->

## List types

<!-- :::list-types::: -->
:::moniker range=">=azure-pipelines-2020"

| Type | Description |
|---|---|
| [stages.stage](stages-stage.md) | A stage is a collection of related jobs. |
| [stages.template](stages-template.md) | You can define a set of stages in one file and use it multiple times in other files. |

:::moniker-end
<!-- :::list-types-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

By default, stages run sequentially. Each stage starts only after the preceding stage is complete unless otherwise specified via the `dependsOn` property.

Use [approval checks](/azure/devops/pipelines/process/approvals) to manually control when a stage should run.
These checks are commonly used to control deployments to production environments.

Checks are a mechanism available to the *resource owner*.
They control when a stage in a pipeline consumes a resource.
As an owner of a resource like an environment, you can define checks that are required before a stage that consumes the resource can start.

Currently, manual approval checks are supported on [environments](/azure/devops/pipelines/process/environments).
For more information, see [Approvals](/azure/devops/pipelines/process/approvals).
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