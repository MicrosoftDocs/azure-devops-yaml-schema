---
title: resources.pipelines definition
description: List of pipeline resources.
ms.date: 06/18/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# resources.pipelines definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
List of pipeline resources referenced by the pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
pipelines: [ pipeline ] # List of pipeline resources.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [resources](resources.md)

:::moniker-end
<!-- :::parents-end::: -->

## List types

<!-- :::list-types::: -->
:::moniker range="<=azure-pipelines"

| Type | Description |
|---|---|
| [resources.pipelines.pipeline](resources-pipelines-pipeline.md) | A pipeline resource. |

:::moniker-end
<!-- :::list-types-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

The `resources.pipelines` definition represents a list of pipeline resources. For information and examples of the syntax for an individual pipeline resource in the `resources.pipelines` list, see [resources.pipelines.pipeline](./resources-pipelines-pipeline.md).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

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
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->