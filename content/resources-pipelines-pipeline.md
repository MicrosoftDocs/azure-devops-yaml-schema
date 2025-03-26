---
title: resources.pipelines.pipeline definition
description: A pipeline resource.
ms.date: 03/20/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# resources.pipelines.pipeline definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
If you have an Azure Pipeline that produces artifacts, your pipeline can consume the artifacts by defining a pipeline resource. In Azure DevOps Server 2020 and higher, you can also enable [pipeline completion triggers](/azure/devops/pipelines/process/pipeline-triggers) using a pipeline resource.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020.1"

```yaml
pipelines:
- pipeline: string # Required as first property. ID of the pipeline resource.
  project: string # Project for the source; defaults to current project.
  source: string # Name of the pipeline that produces the artifact.
  version: string # The pipeline run number to pick the artifact, defaults to latest pipeline successful across all stages; used only for manual or scheduled triggers.
  branch: string # Branch to pick the artifact. Optional; defaults to all branches, used only for manual or scheduled triggers.
  tags: [ string ] # List of tags required on the pipeline to pickup default artifacts. Optional; used only for manual or scheduled triggers.
  trigger:  # Specify none to disable, true to include all branches, or use the full syntax as described in the following examples.
    enabled: boolean # Whether the trigger is enabled; defaults to true.
    branches: branches # Branches to include or exclude for triggering a run.
    stages: [ string ] # List of stages that when matched will trigger the pipeline.
    tags: [ string ] # List of tags that when matched will trigger the pipeline.
```

:::moniker-end

:::moniker range="=azure-pipelines-2020"

```yaml
pipelines:
- pipeline: string # Required as first property. ID of the pipeline resource.
  project: string # Project for the source; defaults to current project.
  source: string # Name of the pipeline that produces the artifact.
  version: string # The pipeline run number to pick the artifact, defaults to latest pipeline successful across all stages; used only for manual or scheduled triggers.
  branch: string # Branch to pick the artifact. Optional; defaults to all branches, used only for manual or scheduled triggers.
  tags: [ string ] # List of tags required on the pipeline to pickup default artifacts. Optional; used only for manual or scheduled triggers.
  trigger:  # Specify none to disable, true to include all branches, or use the full syntax as described in the following examples.
    enabled: boolean # Whether the trigger is enabled; defaults to true.
    branches: branches # Branches to include or exclude for triggering a run.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [resources.pipelines](resources-pipelines.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="pipeline"::: -->
:::moniker range="<=azure-pipelines"

**`pipeline`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
ID of the pipeline resource. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="project"::: -->
:::moniker range="<=azure-pipelines"

**`project`** string.<br><!-- :::editable-content name="propDescription"::: -->
Project for the source; defaults to current project.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="source"::: -->
:::moniker range="<=azure-pipelines"

**`source`** string.<br><!-- :::editable-content name="propDescription"::: -->
Name of the pipeline that produces the artifact. If the pipeline is contained in a folder, include the folder name, including the leading `\`, for example `\security pipelines\security-lib-ci`. This property is not case sensitive and does not need quotes if the name include spaces. The folder path must be specified if there are multiple pipelines with the same name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="version"::: -->
:::moniker range="<=azure-pipelines"

**`version`** string.<br><!-- :::editable-content name="propDescription"::: -->
The pipeline run number to pick the artifact, defaults to latest pipeline successful across all stages; used only for manual or scheduled triggers.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="branch"::: -->
:::moniker range="<=azure-pipelines"

**`branch`** string.<br><!-- :::editable-content name="propDescription"::: -->
Branch to pick the artifact. Optional; defaults to all branches, used only for manual or scheduled triggers.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="tags"::: -->
:::moniker range="<=azure-pipelines"

**`tags`** string list.<br><!-- :::editable-content name="propDescription"::: -->
List of tags required on the pipeline to pickup default artifacts. Optional; used only for manual or scheduled triggers.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
:::moniker range="<=azure-pipelines"

**`trigger`** [resources.pipelines.pipeline.trigger](resources-pipelines-pipeline-trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
Specify none to disable, true to include all branches, or use the full syntax as described in the following examples.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

> [!NOTE]
> `pipeline:` specifies the name of the pipeline resource. Use the label defined here when referring to the pipeline resource from other parts of the pipeline, such as when using pipeline resource variables or downloading artifacts.

:::moniker range=">= azure-pipelines-2020.1"

For more information about `stages` and `tags` in the pipeline resource trigger, see [pipeline-completion triggers](/azure/devops/pipelines/process/pipeline-triggers).

:::moniker-end

:::moniker range="azure-pipelines-2020"

For more information about pipeline resource triggers, see [pipeline-completion triggers](/azure/devops/pipelines/process/pipeline-triggers).

:::moniker-end

:::moniker range=">= azure-pipelines-2020"

### Pipeline resource trigger syntax

> [!NOTE]
> Pipeline completion triggers use the [Default branch for manual and scheduled builds](/azure/devops/pipelines/process/pipeline-default-branch) setting to determine which branch's version of a YAML pipeline's branch filters to evaluate when determining whether to run a pipeline as the result of another pipeline completing. By default this setting points to the default branch of the repository. For more information, see [Pipeline completion triggers - branch considerations](/azure/devops/pipelines/process/pipeline-triggers#branch-considerations).

:::moniker-end

:::moniker range=">= azure-pipelines-2020"

There are several ways to define triggers in a pipeline resource. To trigger a run when any run of the referenced pipeline completes, use `trigger: true`.

```yaml
resources:
  pipelines:
  - pipeline: source-pipeline
    source: TriggeringPipeline
    trigger: true
```

To disable the pipeline resource trigger, specify a value of `none`.

```yaml
resources:
  pipelines:
  - pipeline: source-pipeline
    source: TriggeringPipeline
    trigger: none
```

To configure branch filters, use the full syntax. Branch filters can be specified as a list of branches to include, or as a list of branches to include combined with a list of branches to exclude.

To specify a list of branches to include and exclude, use the following `trigger` syntax.

```yaml
resources:
  pipelines:
  - pipeline: source-pipeline
    source: TriggeringPipeline
    trigger:
      branches:
        include:
        - main
        - develop
        - features/*
        exclude:
        - features/experimental/*
```

To specify a list of branches to include, with no excludes, omit the `exclude` value, or use the following syntax to specify the list of branches to include directly following `branches`.

```yaml
resources:
  pipelines:
  - pipeline: source-pipeline
    source: TriggeringPipeline
    trigger:
      branches:
      - main
      - develop
```

:::moniker-end

:::moniker range=">= azure-pipelines-2020.1"

To filter by stages or tags, use the following `trigger` syntax.

```yaml
resources:
  pipelines:
  - pipeline: source-pipeline
    source: TriggeringPipeline
    trigger:
      branches: # Branches to include
      tags: # List of tags that when matched will trigger the pipeline. 
      - release25
      stages: # List of stages that when complete will trigger the pipeline. 
      - build
```

:::moniker-end

:::moniker range=">= azure-pipelines-2020"

For more information, see [Pipeline completion triggers](/azure/devops/pipelines/process/pipeline-triggers).

:::moniker-end

:::moniker range=">= azure-pipelines-2020"

> [!IMPORTANT]
> When you define a resource trigger, if its pipeline resource is from the same repo as the current pipeline, triggering follows the same branch and commit on which the event is raised.
> But if the pipeline resource is from a different repo, the current pipeline is triggered on the branch specified by the **Default branch for manual and scheduled builds** setting. For more information, see [Branch considerations for pipeline completion triggers](/azure/devops/pipelines/process/pipeline-triggers#branch-considerations).

:::moniker-end

:::moniker range=">=azure-pipelines-2020"

### Pipeline resource metadata as predefined variables

In each run, the metadata for a pipeline resource is available to all jobs as the following predefined variables. These variables are available to your pipeline at runtime, and therefore can't be used in [template expressions](/azure/devops/pipelines/process/variables#template-expression-syntax), which are evaluated at pipeline compile time.

```yaml
resources.pipeline.<Alias>.projectName
resources.pipeline.<Alias>.projectID
resources.pipeline.<Alias>.pipelineName
resources.pipeline.<Alias>.pipelineID
resources.pipeline.<Alias>.runName
resources.pipeline.<Alias>.runID
resources.pipeline.<Alias>.runURI
resources.pipeline.<Alias>.sourceBranch
resources.pipeline.<Alias>.sourceCommit
resources.pipeline.<Alias>.sourceProvider
resources.pipeline.<Alias>.requestedFor
resources.pipeline.<Alias>.requestedForID
```

> [!IMPORTANT]
> `projectName` is not present in the variables if the pipeline resource does not have a `project` value specified. The `project` property is optional for pipeline resources that reference a pipeline in the same project, but may be specified if desired.

Replace `<Alias>` with the ID of the pipeline resource. For the following pipeline resource, the variable to access  `runID` is `resources.pipeline.source-pipeline.runID`.

```yaml
resources:
  pipelines:
  - pipeline: source-pipeline
    source: TriggeringPipeline
```

When a pipeline is triggered by one of its pipeline resources, the following variables are set in addition to the variables in the previous list.

| Variable | Value |
|----------|-------------|
| `Build.Reason` | `ResourceTrigger` |
| `Resources.TriggeringAlias` | The name of the pipeline resource, such as `source-pipeline` from the previous example. |
| `Resources.TriggeringCategory` | `pipeline` |

The following example has two pipeline resources.

```yml
resources:
 pipelines:
   - pipeline: source-pipeline
     source: PipelineTriggerSource
     project: FabrikamFiber
     trigger: true
   - pipeline: other-project-pipeline
     source: PipelineTriggerFromOtherProject
     project: FabrikamRepo
     trigger: true

trigger: none # Only trigger with pipeline resource trigger

pool:
  vmImage: ubuntu-latest

- bash: echo $(resources.pipeline.source-pipeline.projectName)
- bash: printenv | sort
```

Whe this pipeline is run, the first `bash` task outputs the `projectName` of the the pipeline resource named `source-pipeline`, which is `FabrikamFiber`.

The second `bash` task outputs all of the environment variables available to the task, including the pipeline resource variables described in this section. Listing environment variables isn't typically done in a production pipeline, but it can be useful for troubleshooting. In this example there are two pipeline resources, and the output contains the following two lines.

```
RESOURCES_PIPELINE_OTHER-PROJECT-PIPELINE_PROJECTNAME=FabrikamRepo
RESOURCES_PIPELINE_SOURCE-PIPELINE_PROJECTNAME=FabrikamFiber
```

> [!NOTE]
> System and user-defined variables get injected as environment variables for your platform. When variables convert into environment variables, variable names become uppercase, and periods turn into underscores. For example, the variable name `any.variable` becomes `ANY_VARIABLE`.
>
> For more information about using variables and variable syntax, see [Understand variable syntax](/azure/devops/pipelines/process/variables?#understand-variable-syntax), [Specify conditions](/azure/devops/pipelines/process/conditions), and [Expressions](/azure/devops/pipelines/process/expressions).

:::moniker-end

You can consume artifacts from a pipeline resource by using a `download` task. See the [steps.download](steps-download.md) keyword.

## Examples

```yaml
resources:
  pipelines:
  - pipeline: MyAppA
    source: MyCIPipelineA
  - pipeline: MyAppB
    source: MyCIPipelineB
    trigger: true
  - pipeline: MyAppC
    project:  DevOpsProject
    source: MyCIPipelineC
    branch: releases/M159
    version: 20190718.2
    trigger:
      branches:
        include:
        - main
        - releases/*
        exclude:
        - users/*
```
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
