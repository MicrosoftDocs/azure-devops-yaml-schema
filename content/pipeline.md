---
title: pipeline definition
description: A pipeline is one or more stages that describe a CI/CD process.
ms.date: 06/11/2024
monikerRange: ">=azure-pipelines-2019"
---

# pipeline definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
A pipeline is one or more stages that describe a CI/CD process.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
A pipeline is one or more jobs that describe a CI/CD process.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range=">=azure-pipelines-2020"

| Implementation | Description |
|---|---|
| [pipeline: stages](#pipelinestages) | Pipeline with stages. |
| [pipeline: extends](#pipelineextends) | Pipeline that extends a template. |
| [pipeline: jobs](#pipelinejobs) | Pipeline with jobs and one implicit stage. |
| [pipeline: steps](#pipelinesteps) | Pipeline with steps and one implicit job. |

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

| Implementation | Description |
|---|---|
| [pipeline: jobs](#pipelinejobs) | Pipeline with jobs. |
| [pipeline: steps](#pipelinesteps) | Pipeline with steps and one implicit job. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

::: moniker range="> azure-pipelines-2019"

A pipeline is one or more stages that describe a CI/CD process.
Stages are the major divisions in a pipeline.
The stages "Build this app," "Run these tests," and "Deploy to preproduction" are good examples.

A stage is one or more jobs, which are units of work assignable to the same machine.
You can arrange both stages and jobs into dependency graphs.
Examples include "Run this stage before that one" and "This job depends on the output of that job."

A job is a linear series of steps.
Steps can be tasks, scripts, or references to external templates.

This hierarchy is reflected in the structure of a YAML file like:
```yaml
- Pipeline
  - Stage A
    - Job 1
      - Step 1.1
      - Step 1.2
      - ...
    - Job 2
      - Step 2.1
      - Step 2.2
      - ...
  - Stage B
    - ...
```

Simple pipelines don't require all of these levels.
For example, in a single-job build, you can omit the containers for stages and jobs because there are only steps.
And because many options shown in this article aren't required and have good defaults, your YAML definitions are unlikely to include all of them.

::: moniker-end

::: moniker range="azure-pipelines-2019"

A pipeline is one or more jobs that describe a CI/CD process.
A job is a unit of work assignable to the same machine.
You can arrange jobs into dependency graphs like "This job depends on the output of that job."

A job is a linear series of steps.
Steps can be tasks, scripts, or references to external templates.

This hierarchy is reflected in the structure of a YAML file like:
```yaml
- Pipeline
  - Job 1
    - Step 1.1
    - Step 1.2
    - ...
  - Job 2
    - Step 2.1
    - Step 2.2
    - ...
```

For single-job pipelines, you can omit the jobs container because there are only steps.
And because many options shown in this article aren't required and have good defaults, your YAML definitions are unlikely to include all of them.

::: moniker-end

::: moniker range=">= azure-pipelines-2020"

If you have a single stage, you can omit the `stages` keyword and directly specify the [jobs](jobs.md) keyword:

```yaml
# ... other pipeline-level keywords
jobs: [ job | template ]
```

If you have a single stage and a single job, you can omit the `stages` and `jobs` keywords and directly specify the [steps](steps.md) keyword:

```yaml
# ... other pipeline-level keywords
steps: [ script | bash | pwsh | powershell | checkout | task | template | ... ]
```

::: moniker-end

::: moniker range=">= azure-pipelines-2019 < azure-pipelines-2020"

If you have a single job, you can omit the `jobs` keyword and directly specify the [steps](steps.md) keyword:

```yaml
# ... other pipeline-level keywords
steps: [ script | bash | pwsh | powershell | checkout | task | template | ... ]
```

::: moniker-end

Use the `name` property to configure the pipeline run number. For more information, see [Configure run or build numbers](/azure/devops/pipelines/process/run-number).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="pipeline: stages"::: -->
<a name="pipelinestages"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2022.1"

<!-- :::implementation-signature::: -->
## pipeline: stages
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with stages.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
stages: [ stage | template ] # Required. Stages are groups of jobs that can run without human intervention.
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
name: string # Pipeline run number.
appendCommitMessageToRunName: boolean # Append the commit message to the build number. The default is true.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  webhooks: [ webhook ] # List of webhooks.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
lockBehavior: string # Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="stages"::: -->
**`stages`** [stages](stages.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
Stages are groups of jobs that can run without human intervention.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="appendCommitMessageToRunName"::: -->
**`appendCommitMessageToRunName`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Append the commit message to the build number. The default is true.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="lockBehavior"::: -->
**`lockBehavior`** string.<br><!-- :::editable-content name="propDescription"::: -->
Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests. sequential | runLatest.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2022"

<!-- :::implementation-signature::: -->
## pipeline: stages
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with stages.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
stages: [ stage | template ] # Required. Stages are groups of jobs that can run without human intervention.
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  webhooks: [ webhook ] # List of webhooks.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
lockBehavior: string # Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="stages"::: -->
**`stages`** [stages](stages.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
Stages are groups of jobs that can run without human intervention.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.

See [Configure run or build numbers](/azure/devops/pipelines/process/run-number) for allowed placeholders.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="lockBehavior"::: -->
**`lockBehavior`** string.<br><!-- :::editable-content name="propDescription"::: -->
Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests. sequential | runLatest.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

<!-- :::implementation-signature::: -->
## pipeline: stages
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with stages.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
stages: [ stage | template ] # Required. Stages are groups of jobs that can run without human intervention.
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  webhooks: [ webhook ] # List of webhooks.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="stages"::: -->
**`stages`** [stages](stages.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
Stages are groups of jobs that can run without human intervention.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## pipeline: stages
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with stages.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
stages: [ stage | template ] # Required. Stages are groups of jobs that can run without human intervention.
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="stages"::: -->
**`stages`** [stages](stages.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
Stages are groups of jobs that can run without human intervention.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
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
### Examples

```yaml
trigger:
- main

pool: 
  vmImage: ubuntu-latest

stages:
- stage: CI
  jobs:
  - job: CIWork
    steps:
    - script: "Do CI work"

- stage: Test
  jobs:
  - job: TestWork
    steps:
    - script: "Do test work"
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="pipeline: extends"::: -->
<a name="pipelineextends"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2022.1"

<!-- :::implementation-signature::: -->
## pipeline: extends
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline that extends a template.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
extends: # Required. Extends a template.
  template: string # The template referenced by the pipeline to extend.
  parameters: # Parameters used in the extend.
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
name: string # Pipeline run number.
appendCommitMessageToRunName: boolean # Append the commit message to the build number. The default is true.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  webhooks: [ webhook ] # List of webhooks.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
lockBehavior: string # Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="extends"::: -->
**`extends`** [extends](extends.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
Extends a template.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="appendCommitMessageToRunName"::: -->
**`appendCommitMessageToRunName`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Append the commit message to the build number. The default is true.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="lockBehavior"::: -->
**`lockBehavior`** string.<br><!-- :::editable-content name="propDescription"::: -->
Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests. sequential | runLatest.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2022"

<!-- :::implementation-signature::: -->
## pipeline: extends
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline that extends a template.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
extends: # Required. Extends a template.
  template: string # The template referenced by the pipeline to extend.
  parameters: # Parameters used in the extend.
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  webhooks: [ webhook ] # List of webhooks.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
lockBehavior: string # Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="extends"::: -->
**`extends`** [extends](extends.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
Extends a template.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="lockBehavior"::: -->
**`lockBehavior`** string.<br><!-- :::editable-content name="propDescription"::: -->
Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests. sequential | runLatest.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

<!-- :::implementation-signature::: -->
## pipeline: extends
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline that extends a template.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
extends: # Required. Extends a template.
  template: string # The template referenced by the pipeline to extend.
  parameters: # Parameters used in the extend.
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  webhooks: [ webhook ] # List of webhooks.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="extends"::: -->
**`extends`** [extends](extends.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
Extends a template.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## pipeline: extends
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline that extends a template.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
extends: # Required. Extends a template.
  template: string # The template referenced by the pipeline to extend.
  parameters: # Parameters used in the extend.
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="extends"::: -->
**`extends`** [extends](extends.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
Extends a template.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
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
<!-- :::implementation-item name="pipeline: jobs"::: -->
<a name="pipelinejobs"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2022.1"

<!-- :::implementation-signature::: -->
## pipeline: jobs
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with jobs and one implicit stage.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
jobs: [ job | deployment | template ] # Required. Jobs represent units of work which can be assigned to a single agent or server.
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
name: string # Pipeline run number.
appendCommitMessageToRunName: boolean # Append the commit message to the build number. The default is true.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  webhooks: [ webhook ] # List of webhooks.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
lockBehavior: string # Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="jobs"::: -->
**`jobs`** [jobs](jobs.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
Jobs represent units of work which can be assigned to a single agent or server.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="appendCommitMessageToRunName"::: -->
**`appendCommitMessageToRunName`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Append the commit message to the build number. The default is true.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="lockBehavior"::: -->
**`lockBehavior`** string.<br><!-- :::editable-content name="propDescription"::: -->
Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests. sequential | runLatest.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2022"

<!-- :::implementation-signature::: -->
## pipeline: jobs
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with jobs and one implicit stage.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
jobs: [ job | deployment | template ] # Required. Jobs represent units of work which can be assigned to a single agent or server.
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  webhooks: [ webhook ] # List of webhooks.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
lockBehavior: string # Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="jobs"::: -->
**`jobs`** [jobs](jobs.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
Jobs represent units of work which can be assigned to a single agent or server.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="lockBehavior"::: -->
**`lockBehavior`** string.<br><!-- :::editable-content name="propDescription"::: -->
Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests. sequential | runLatest.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

<!-- :::implementation-signature::: -->
## pipeline: jobs
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with jobs and one implicit stage.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
jobs: [ job | deployment | template ] # Required. Jobs represent units of work which can be assigned to a single agent or server.
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  webhooks: [ webhook ] # List of webhooks.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="jobs"::: -->
**`jobs`** [jobs](jobs.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
Jobs represent units of work which can be assigned to a single agent or server.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## pipeline: jobs
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with jobs and one implicit stage.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
jobs: [ job | deployment | template ] # Required. Jobs represent units of work which can be assigned to a single agent or server.
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="jobs"::: -->
**`jobs`** [jobs](jobs.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
Jobs represent units of work which can be assigned to a single agent or server.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

<!-- :::implementation-signature::: -->
## pipeline: jobs
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with jobs.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
jobs: [ job ] # Required. Jobs represent units of work which can be assigned to a single agent or server.
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
pr: none | pr | [ string ] # Pull request triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
variables: variables | [ variable ] # Variables for this pipeline.
parameters: # Pipeline template parameters.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="jobs"::: -->
**`jobs`** [jobs](jobs.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
Jobs represent units of work which can be assigned to a single agent or server.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** template parameters.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
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
### Examples

```yaml
trigger:
- main

pool: 
  vmImage: ubuntu-latest

jobs:
- job: PreWork
  steps:
  - script: "Do pre-work"

- job: PostWork
  pool: windows-latest
  steps:
  - script: "Do post-work using a different hosted image"
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="pipeline: steps"::: -->
<a name="pipelinesteps"></a>
<!-- :::objectAnyOf::: -->
:::moniker range=">=azure-pipelines-2022.1"

<!-- :::implementation-signature::: -->
## pipeline: steps
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with steps and one implicit job.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # Required. A list of steps to run in this job.
strategy: strategy # Execution strategy for this job.
continueOnError: string # Continue running even on failure?
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
container: string | container # Container resource name.
services: # Container resources to run as a service container.
  string: string # Name/value pairs
workspace: # Workspace options on the agent.
  clean: string # Which parts of the workspace should be scorched before fetching.
name: string # Pipeline run number.
appendCommitMessageToRunName: boolean # Append the commit message to the build number. The default is true.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  webhooks: [ webhook ] # List of webhooks.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
lockBehavior: string # Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="steps"::: -->
**`steps`** [steps](steps.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
A list of steps to run in this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
**`strategy`** [jobs.job.strategy](jobs-job-strategy.md).<br><!-- :::editable-content name="propDescription"::: -->
Execution strategy for this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="continueOnError"::: -->
**`continueOnError`** string.<br><!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="container"::: -->
**`container`** [jobs.job.container](jobs-job-container.md).<br><!-- :::editable-content name="propDescription"::: -->
Container resource name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="services"::: -->
**`services`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Container resources to run as a service container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="workspace"::: -->
**`workspace`** [workspace](workspace.md).<br><!-- :::editable-content name="propDescription"::: -->
Workspace options on the agent.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="appendCommitMessageToRunName"::: -->
**`appendCommitMessageToRunName`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Append the commit message to the build number. The default is true.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="lockBehavior"::: -->
**`lockBehavior`** string.<br><!-- :::editable-content name="propDescription"::: -->
Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests. sequential | runLatest.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2022"

<!-- :::implementation-signature::: -->
## pipeline: steps
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with steps and one implicit job.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # Required. A list of steps to run in this job.
strategy: strategy # Execution strategy for this job.
continueOnError: string # Continue running even on failure?
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
container: string | container # Container resource name.
services: # Container resources to run as a service container.
  string: string # Name/value pairs
workspace: # Workspace options on the agent.
  clean: string # Which parts of the workspace should be scorched before fetching.
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  webhooks: [ webhook ] # List of webhooks.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
lockBehavior: string # Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="steps"::: -->
**`steps`** [steps](steps.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
A list of steps to run in this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
**`strategy`** [jobs.job.strategy](jobs-job-strategy.md).<br><!-- :::editable-content name="propDescription"::: -->
Execution strategy for this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="continueOnError"::: -->
**`continueOnError`** string.<br><!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="container"::: -->
**`container`** [jobs.job.container](jobs-job-container.md).<br><!-- :::editable-content name="propDescription"::: -->
Container resource name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="services"::: -->
**`services`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Container resources to run as a service container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="workspace"::: -->
**`workspace`** [workspace](workspace.md).<br><!-- :::editable-content name="propDescription"::: -->
Workspace options on the agent.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="lockBehavior"::: -->
**`lockBehavior`** string.<br><!-- :::editable-content name="propDescription"::: -->
Behavior lock requests from this stage should exhibit in relation to other exclusive lock requests. sequential | runLatest.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020.1"

<!-- :::implementation-signature::: -->
## pipeline: steps
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with steps and one implicit job.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # Required. A list of steps to run in this job.
strategy: strategy # Execution strategy for this job.
continueOnError: string # Continue running even on failure?
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
container: string | container # Container resource name.
services: # Container resources to run as a service container.
  string: string # Name/value pairs
workspace: # Workspace options on the agent.
  clean: string # Which parts of the workspace should be scorched before fetching.
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  webhooks: [ webhook ] # List of webhooks.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="steps"::: -->
**`steps`** [steps](steps.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
A list of steps to run in this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
**`strategy`** [jobs.job.strategy](jobs-job-strategy.md).<br><!-- :::editable-content name="propDescription"::: -->
Execution strategy for this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="continueOnError"::: -->
**`continueOnError`** string.<br><!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="container"::: -->
**`container`** [jobs.job.container](jobs-job-container.md).<br><!-- :::editable-content name="propDescription"::: -->
Container resource name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="services"::: -->
**`services`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Container resources to run as a service container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="workspace"::: -->
**`workspace`** [workspace](workspace.md).<br><!-- :::editable-content name="propDescription"::: -->
Workspace options on the agent.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020"

<!-- :::implementation-signature::: -->
## pipeline: steps
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with steps and one implicit job.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # Required. A list of steps to run in this job.
strategy: strategy # Execution strategy for this job.
continueOnError: string # Continue running even on failure?
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
container: string | container # Container resource name.
services: # Container resources to run as a service container.
  string: string # Name/value pairs
workspace: # Workspace options on the agent.
  clean: string # Which parts of the workspace should be scorched before fetching.
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
parameters: [ parameter ] # Pipeline template parameters.
pr: none | pr | [ string ] # Pull request triggers.
schedules: [ cron ] # Scheduled triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
  packages: [ package ] # List of package resources.
variables: variables | [ variable ] # Variables for this pipeline.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="steps"::: -->
**`steps`** [steps](steps.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
A list of steps to run in this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
**`strategy`** [jobs.job.strategy](jobs-job-strategy.md).<br><!-- :::editable-content name="propDescription"::: -->
Execution strategy for this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="continueOnError"::: -->
**`continueOnError`** string.<br><!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="container"::: -->
**`container`** [jobs.job.container](jobs-job-container.md).<br><!-- :::editable-content name="propDescription"::: -->
Container resource name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="services"::: -->
**`services`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Container resources to run as a service container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="workspace"::: -->
**`workspace`** [workspace](workspace.md).<br><!-- :::editable-content name="propDescription"::: -->
Workspace options on the agent.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** [parameters](parameters.md).<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
**`schedules`** [schedules](schedules.md).<br><!-- :::editable-content name="propDescription"::: -->
Scheduled triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019.1"

<!-- :::implementation-signature::: -->
## pipeline: steps
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with steps and one implicit job.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | publish | template ] # Required. A list of steps to run in this job.
strategy: strategy # Execution strategy for this job.
continueOnError: string # Continue running even on failure?
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
container: string | container # Container resource name.
services: # Container resources to run as a service container.
  string: string # Name/value pairs
workspace: # Workspace options on the agent.
  clean: string # Scorch the repo before fetching?
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
pr: none | pr | [ string ] # Pull request triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
variables: variables | [ variable ] # Variables for this pipeline.
parameters: # Pipeline template parameters.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="steps"::: -->
**`steps`** [steps](steps.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
A list of steps to run in this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
**`strategy`** [jobs.job.strategy](jobs-job-strategy.md).<br><!-- :::editable-content name="propDescription"::: -->
Execution strategy for this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="continueOnError"::: -->
**`continueOnError`** string.<br><!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="container"::: -->
**`container`** [jobs.job.container](jobs-job-container.md).<br><!-- :::editable-content name="propDescription"::: -->
Container resource name.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="services"::: -->
**`services`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Container resources to run as a service container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="workspace"::: -->
**`workspace`** [workspace](workspace.md).<br><!-- :::editable-content name="propDescription"::: -->
Workspace options on the agent.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** template parameters.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::implementation-properties-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::implementation-signature::: -->
## pipeline: steps
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Pipeline with steps and one implicit job.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | publish | template ] # Required. A list of steps to run in this job.
strategy: strategy # Execution strategy for this job.
continueOnError: string # Continue running even on failure?
pool: string | pool # Pool where jobs in this pipeline will run unless otherwise specified.
services: # Container resources to run as a service container.
  string: string # Name/value pairs
workspace: # Workspace options on the agent.
  clean: string # Scorch the repo before fetching?
name: string # Pipeline run number.
trigger: none | trigger | [ string ] # Continuous integration triggers.
pr: none | pr | [ string ] # Pull request triggers.
resources: # Containers and repositories used in the build.
  builds: [ build ] # List of build resources referenced by the pipeline.
  containers: [ container ] # List of container images.
  pipelines: [ pipeline ] # List of pipeline resources.
  repositories: [ repository ] # List of repository resources.
variables: variables | [ variable ] # Variables for this pipeline.
parameters: # Pipeline template parameters.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
### Properties

<!-- :::item name="steps"::: -->
**`steps`** [steps](steps.md). Required.<br><!-- :::editable-content name="propDescription"::: -->
A list of steps to run in this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="strategy"::: -->
**`strategy`** [jobs.job.strategy](jobs-job-strategy.md).<br><!-- :::editable-content name="propDescription"::: -->
Execution strategy for this job.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="continueOnError"::: -->
**`continueOnError`** string.<br><!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
**`pool`** [pool](pool.md).<br><!-- :::editable-content name="propDescription"::: -->
Pool where jobs in this pipeline will run unless otherwise specified.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="services"::: -->
**`services`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Container resources to run as a service container.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="workspace"::: -->
**`workspace`** [workspace](workspace.md).<br><!-- :::editable-content name="propDescription"::: -->
Workspace options on the agent.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline run number.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Continuous integration triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
**`pr`** [pr](pr.md).<br><!-- :::editable-content name="propDescription"::: -->
Pull request triggers.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
**`resources`** [resources](resources.md).<br><!-- :::editable-content name="propDescription"::: -->
Containers and repositories used in the build.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
**`variables`** [variables](variables.md).<br><!-- :::editable-content name="propDescription"::: -->
Variables for this pipeline.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
**`parameters`** template parameters.<br><!-- :::editable-content name="propDescription"::: -->
Pipeline template parameters.
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
### Examples

```yaml
trigger:
- main

pool: 
  vmImage: ubuntu-latest

steps:
- script: "Hello world!"
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Pipelines with multiple jobs](/azure/devops/pipelines/process/phases)
- [Triggers](/azure/devops/pipelines/build/triggers)
- [Variables](/azure/devops/pipelines/process/variables)
- [Build number formats](/azure/devops/pipelines/process/run-number)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
