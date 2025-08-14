---
title: variables.name definition
description: Define variables using name and full syntax.
ms.date: 08/14/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# variables.name definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Define variables using name and full syntax.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
variables:
- name: string # Required as first property. Variable name.
  value: string # Variable value.
  readonly: boolean # Whether a YAML variable is read-only; default is false.
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
<!-- :::item name="name"::: -->
:::moniker range="<=azure-pipelines"

**`name`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Variable name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="value"::: -->
:::moniker range="<=azure-pipelines"

**`value`** string.<br><!-- :::editable-content name="propDescription"::: -->
Variable value.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="readonly"::: -->
:::moniker range="<=azure-pipelines"

**`readonly`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Whether a YAML variable is read-only; default is false.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

If you want to reference a variable group and define variables in the same variables section, you must use define your variables using name and full syntax.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yaml
variables:
- name: one
  value: initialValue
- name: two
  value: value2
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