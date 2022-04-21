---
title: resources.pipelines.pipeline definition
description: resources.pipelines.pipeline definition reference.
ms.date: 04/21/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# resources.pipelines.pipeline definition


If you have an Azure pipeline that produces artifacts, your pipeline can consume the artifacts by defining a pipeline resource. In Azure DevOps Server 2020 and higher, you can also enable [pipeline-completion triggers](/azure/devops/pipelines/process/pipeline-triggers) using a pipeline resource.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="pipelineResource{pipeline}" version="azure-pipelines-2019"::: -->

```yaml
pipelines:
- pipeline: string # Required as first property. ID of the pipeline resource.  ([-_A-Za-z0-9]*)
  project: string # Project for the source; defaults to current project.. 
  source: string # Name of the pipeline that produces the artifact.. 
  version: string # The pipeline run number to pick the artifact, defaults to latest pipeline successful across all stages; used only for manual or scheduled triggers.. 
  branch: string # Branch to pick the artifact. Optional; defaults to all branches, used only for manual or scheduled triggers.. 
```


Properties that use this definition: [resources.pipelines](resources-pipelines.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pipeline`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the pipeline resource. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `project`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Project for the source; defaults to current project. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `source`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the pipeline that produces the artifact. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `version`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->The pipeline run number to pick the artifact, defaults to latest pipeline successful across all stages; used only for manual or scheduled triggers. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `branch`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Branch to pick the artifact. Optional; defaults to all branches, used only for manual or scheduled triggers. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="pipelineResource{pipeline}" version="azure-pipelines-2019.1"::: -->

```yaml
pipelines:
- pipeline: string # Required as first property. ID of the pipeline resource.  ([-_A-Za-z0-9]*)
  project: string # Project for the source; defaults to current project.. 
  source: string # Name of the pipeline that produces the artifact.. 
  version: string # The pipeline run number to pick the artifact, defaults to latest pipeline successful across all stages; used only for manual or scheduled triggers.. 
  branch: string # Branch to pick the artifact. Optional; defaults to all branches, used only for manual or scheduled triggers.. 
```


Properties that use this definition: [resources.pipelines](resources-pipelines.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pipeline`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the pipeline resource. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `project`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Project for the source; defaults to current project. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `source`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the pipeline that produces the artifact. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `version`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->The pipeline run number to pick the artifact, defaults to latest pipeline successful across all stages; used only for manual or scheduled triggers. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `branch`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Branch to pick the artifact. Optional; defaults to all branches, used only for manual or scheduled triggers. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="pipelineResource{pipeline}" version="azure-pipelines-2020"::: -->

```yaml
pipelines:
- pipeline: string # Required as first property. ID of the pipeline resource.  ([-_A-Za-z0-9]*)
  project: string # Project for the source; defaults to current project.. 
  source: string # Name of the pipeline that produces the artifact.. 
  version: string # The pipeline run number to pick the artifact, defaults to latest pipeline successful across all stages; used only for manual or scheduled triggers.. 
  branch: string # Branch to pick the artifact. Optional; defaults to all branches, used only for manual or scheduled triggers.. 
  tags: [ string ] # List of tags required on the pipeline to pickup default artifacts. Optional; used only for manual or scheduled triggers. 
  trigger:  # Specify none to disable, true to include all branches, or use the full syntax.
    enabled: boolean # Whether the trigger is enabled; defaults to true..  (false,n,no,off,on,true,y,yes)
    branches:  # Branch conditions to filter the events, optional; Defaults to all branches.
      include: [ branchFilter ] # List of branches to include. 
      exclude: [ branchFilter ] # List of branches to exclude. 
```


Properties that use this definition: [resources.pipelines](resources-pipelines.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pipeline`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the pipeline resource. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `project`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Project for the source; defaults to current project. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `source`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the pipeline that produces the artifact. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `version`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->The pipeline run number to pick the artifact, defaults to latest pipeline successful across all stages; used only for manual or scheduled triggers. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `branch`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Branch to pick the artifact. Optional; defaults to all branches, used only for manual or scheduled triggers. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `tags`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of tags required on the pipeline to pickup default artifacts. Optional; used only for manual or scheduled triggers. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string or trigger
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Specify none to disable, true to include all branches, or use the full syntax. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="pipelineResource{pipeline}" version="azure-pipelines-2020.1"::: -->

```yaml
pipelines:
- pipeline: string # Required as first property. ID of the pipeline resource.  ([-_A-Za-z0-9]*)
  project: string # Project for the source; defaults to current project.. 
  source: string # Name of the pipeline that produces the artifact.. 
  version: string # The pipeline run number to pick the artifact, defaults to latest pipeline successful across all stages; used only for manual or scheduled triggers.. 
  branch: string # Branch to pick the artifact. Optional; defaults to all branches, used only for manual or scheduled triggers.. 
  tags: [ string ] # List of tags required on the pipeline to pickup default artifacts. Optional; used only for manual or scheduled triggers. 
  trigger:  # Specify none to disable, true to include all branches, or use the full syntax.
    enabled: boolean # Whether the trigger is enabled; defaults to true..  (false,n,no,off,on,true,y,yes)
    branches:  # Branch conditions to filter the events, optional; Defaults to all branches.
      include: [ branchFilter ] # List of branches to include. 
      exclude: [ branchFilter ] # List of branches to exclude. 
    stages: [ string ] # List of stages that when complete will trigger the pipeline. 
    tags: [ string ] # List of tags that when matched will trigger the pipeline. 
```


Properties that use this definition: [resources.pipelines](resources-pipelines.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pipeline`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the pipeline resource. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `project`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Project for the source; defaults to current project. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `source`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the pipeline that produces the artifact. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `version`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->The pipeline run number to pick the artifact, defaults to latest pipeline successful across all stages; used only for manual or scheduled triggers. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `branch`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Branch to pick the artifact. Optional; defaults to all branches, used only for manual or scheduled triggers. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `tags`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of tags required on the pipeline to pickup default artifacts. Optional; used only for manual or scheduled triggers. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string or trigger
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Specify none to disable, true to include all branches, or use the full syntax. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="pipelineResource{pipeline}" version="azure-pipelines"::: -->

```yaml
pipelines:
- pipeline: string # Required as first property. ID of the pipeline resource.  ([-_A-Za-z0-9]*)
  project: string # Project for the source; defaults to current project.. 
  source: string # Name of the pipeline that produces the artifact.. 
  version: string # The pipeline run number to pick the artifact, defaults to latest pipeline successful across all stages; used only for manual or scheduled triggers.. 
  branch: string # Branch to pick the artifact. Optional; defaults to all branches, used only for manual or scheduled triggers.. 
  tags: [ string ] # List of tags required on the pipeline to pickup default artifacts. Optional; used only for manual or scheduled triggers. 
  trigger:  # Specify none to disable, true to include all branches, or use the full syntax.
    enabled: boolean # Whether the trigger is enabled; defaults to true..  (false,n,no,off,on,true,y,yes)
    branches:  # Branch conditions to filter the events, optional; Defaults to all branches.
      include: [ branchFilter ] # List of branches to include. 
      exclude: [ branchFilter ] # List of branches to exclude. 
    stages: [ string ] # List of stages that when complete will trigger the pipeline. 
    tags: [ string ] # List of tags that when matched will trigger the pipeline. 
```


Properties that use this definition: [resources.pipelines](resources-pipelines.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pipeline`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the pipeline resource. Acceptable values: [-_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `project`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Project for the source; defaults to current project. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `source`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the pipeline that produces the artifact. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `version`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->The pipeline run number to pick the artifact, defaults to latest pipeline successful across all stages; used only for manual or scheduled triggers. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `branch`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Branch to pick the artifact. Optional; defaults to all branches, used only for manual or scheduled triggers. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `tags`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of tags required on the pipeline to pickup default artifacts. Optional; used only for manual or scheduled triggers. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string or trigger
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Specify none to disable, true to include all branches, or use the full syntax. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

:::moniker range=">= azure-pipelines-2020.1"

For more information about `stages` and `tags` in the pipeline resource trigger, see [pipeline-completion triggers](/azure/devops/pipelines/process/pipeline-triggers).

:::moniker-end

:::moniker range="azure-pipelines-2020"

For more information about pipeline resource triggers, see [pipeline-completion triggers](/azure/devops/pipelines/process/pipeline-triggers).

:::moniker-end

> [!IMPORTANT]
> When you define a resource trigger, if its pipeline resource is from the same repo as the current pipeline, triggering follows the same branch and commit on which the event is raised.
> But if the pipeline resource is from a different repo, the current pipeline is triggered on the branch specified by the **Default branch for manual and scheduled builds** setting. For more information, see [Branch considerations for pipeline completion triggers](/azure/devops/pipelines/process/pipeline-triggers#branch-considerations).

#### The pipeline resource metadata as predefined variables

In each run, the metadata for a pipeline resource is available to all jobs as these predefined variables:

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

Replace `<Alias>` with the ID of the pipeline resource. For the following pipeline resource, the variable to access  `projectName` is `resources.pipeline.MyAppA.projectName`.

```yaml
resources:
  pipelines:
  - pipeline: MyAppA
    source: MyCIPipelineA
```

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


## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)

