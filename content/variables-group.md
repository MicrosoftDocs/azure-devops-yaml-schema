---
title: variables.group definition
description: Reference variables from a variable group.
ms.date: 02/24/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# variables.group definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Reference variables from a variable group.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
variables:
- group: string # Required as first property. Variable group name.
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
<!-- :::item name="group"::: -->
:::moniker range="<=azure-pipelines"

**`group`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Variable group name.
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

```yaml
variables:
- group: my-variable-group
```

Use a variable group and variables defined in the pipeline.

```yaml
variables:
- group: my-variable-group
- name: my-bare-variable
  value: 'value of my-bare-variable'
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Add & use variable groups](/azure/devops/pipelines/library/variable-groups)
- [Define variables](/azure/devops/pipelines/process/variables)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->