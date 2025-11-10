---
title: variables.template definition
description: Define variables in a template.
ms.date: 11/10/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# variables.template definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
You can define a set of variables in one file and use it multiple times in other files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
variables:
- template: string # Required as first property. Template file with variables.
  parameters: # Parameters to map into the template.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [variables](variables.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="template"::: -->
:::moniker range="<=azure-pipelines"

**`template`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Template file with variables.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
:::moniker range="<=azure-pipelines"

**`parameters`** template parameters.<br><!-- :::editable-content name="propDescription"::: -->
Parameters to map into the template.
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

In this example, a set of variables is repeated across multiple pipelines.
The variables are specified only once.

```yaml
# File: variables/build.yml
variables:
- name: vmImage
  value: vs2017-win2016
- name: arch
  value: x64
- name: config
  value: debug
```

```yaml
# File: component-x-pipeline.yml
variables:
- template: variables/build.yml  # Template reference
pool:
  vmImage: ${{ variables.vmImage }}
steps:
- script: build x ${{ variables.arch }} ${{ variables.config }}
```

```yaml
# File: component-y-pipeline.yml
variables:
- template: variables/build.yml  # Template reference
pool:
  vmImage: ${{ variables.vmImage }}
steps:
- script: build y ${{ variables.arch }} ${{ variables.config }}
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Template usage reference](/azure/devops/pipelines/process/templates)
- [Template parameters](/azure/devops/pipelines/process/template-parameters)
- [Define variables](/azure/devops/pipelines/process/variables)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->