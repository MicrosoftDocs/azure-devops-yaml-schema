---
title: stages list definition
description: stages list definition reference.
ms.date: 01/28/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# stages list definition


Stages are a collection of related jobs. 


:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="stages[stage]" version="azure-pipelines-2020"::: -->

```yaml
stages: [ stage | template ] # 
```


Properties that use this definition: [pipeline.stages](pipeline.md)

## List types

| Type     | Description |
|----------|-------------|
| [stages.stage](stages-stage.md) | Stages defined in a pipeline. |
| [stages.template](stages-template.md) | Stages defined in a template file. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="stages[stage]" version="azure-pipelines-2020.1"::: -->

```yaml
stages: [ stage | template ] # 
```


Properties that use this definition: [pipeline.stages](pipeline.md)

## List types

| Type     | Description |
|----------|-------------|
| [stages.stage](stages-stage.md) | Stages defined in a pipeline. |
| [stages.template](stages-template.md) | Stages defined in a template file. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="stages[stage]" version="azure-pipelines"::: -->

```yaml
stages: [ stage | template ] # 
```


Properties that use this definition: [pipeline.stages](pipeline.md)

## List types

| Type     | Description |
|----------|-------------|
| [stages.stage](stages-stage.md) | Stages defined in a pipeline. |
| [stages.template](stages-template.md) | Stages defined in a template file. |

<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

By default, stages run sequentially. Each stage starts only after the preceding stage is complete unless otherwise specified via the `dependsOn` property.

Use [approval checks](/azure/devops/pipelines/process/approvals) to manually control when a stage should run.
These checks are commonly used to control deployments to production environments.

Checks are a mechanism available to the *resource owner*.
They control when a stage in a pipeline consumes a resource.
As an owner of a resource like an environment, you can define checks that are required before a stage that consumes the resource can start.

Currently, manual approval checks are supported on [environments](/azure/devops/pipelines/process/environments).
For more information, see [Approvals](/azure/devops/pipelines/process/approvals).


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


## See also

Learn more about [stages](/azure/devops/pipelines/process/stages), [conditions](/azure/devops/pipelines/process/conditions), and [variables](/azure/devops/pipelines/process/variables).



