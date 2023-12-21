---
title: extends definition
description: Extends a pipeline using a template.
ms.date: 12/21/2023
monikerRange: ">=azure-pipelines-2020"
---

# extends definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
Extend a pipeline using a template.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020"

```yaml
extends:
  template: string # The template referenced by the pipeline to extend.
  parameters: # Parameters used in the extend.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [pipeline](pipeline.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="template"::: -->
:::moniker range=">=azure-pipelines-2020"

**`template`** string.<br><!-- :::editable-content name="propDescription"::: -->
The template referenced by the pipeline to extend.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
:::moniker range=">=azure-pipelines-2020"

**`parameters`** template parameters.<br><!-- :::editable-content name="propDescription"::: -->
Parameters used in the extend.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

Templates and their parameters are turned into constants before the pipeline runs.
Template parameters provide type safety to input parameters.
In this example, templates restrict which pools can be used in a pipeline by offering an enumeration of possible options rather than a freeform string.

```yaml
# template.yml
parameters:
- name: userpool
  type: string
  default: Azure Pipelines
  values:
  - Azure Pipelines
  - private-pool-1
  - private-pool-2

pool: ${{ parameters.userpool }}
steps:
- script: # ... removed for clarity
```

```yaml
# azure-pipelines.yml
extends:
  template: template.yml
  parameters:
    userpool: private-pool-1
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Template types & usage](/azure/devops/pipelines/process/templates)
- [Security through templates](/azure/devops/pipelines/security/templates)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->