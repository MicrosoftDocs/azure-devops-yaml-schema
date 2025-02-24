---
title: target.settableVariables definition
description: Restrictions on which variables that can be set.
ms.date: 02/24/2025
monikerRange: ">=azure-pipelines-2022"
---

# target.settableVariables definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::editable-content name="description"::: -->
Restrictions on which variables that can be set by a step.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2022"

Definitions that reference this definition: [target](target.md)

:::moniker-end
<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range=">=azure-pipelines-2022"

| Implementation | Description |
|---|---|
| [settableVariables: none](#settablevariablesstring) | Disable a step from setting any variables. |
| [settableVariables: string list](#settablevariablesstringlist) | Restrict variable setting to a list of allowed variables. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

You can disable setting all variables for a step, or restrict the settable variables to a list. If the `settableVariables` property is not set, the default allows all variables to be set by a step.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="settableVariables: string"::: -->
<a name="settablevariablesstring"></a>
<!-- :::stringAnyOf::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::implementation-signature::: -->
## settableVariables: none
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Disable a step from setting any variables.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
settableVariables: none # Disable a step from setting any variables.
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-string-item::: -->
**`settableVariables`** string. Allowed values: none.<br>
<!-- :::editable-content name="description"::: -->
Disable a step from setting any variables.
<!-- :::editable-content-end::: -->
<!-- :::implementation-string-item-end::: -->

:::moniker-end
<!-- :::stringAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

```yaml
steps:
- script: echo This is a step
  target:
    settableVariables: none
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="settableVariables: string list"::: -->
<a name="settablevariablesstringlist"></a>
<!-- :::arrayAnyOf::: -->
:::moniker range=">=azure-pipelines-2022"

<!-- :::implementation-signature::: -->
## settableVariables: string list
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Restrict a step from setting any variables not in the specified list.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
settableVariables: [ string ] # Restrict variable setting to a list of allowed variables.
```
<!-- :::implementation-syntax-end::: -->

### List types

<!-- :::implementation-list-types::: -->
| Type | Description |
|---|---|
| string | Restrict variable setting to a list of allowed variables. |
<!-- :::implementation-list-types-end::: -->

:::moniker-end
<!-- :::arrayAnyOf-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
### Examples

In the following example, the `bash` step can only set the value of the `sauce` variable. When the pipeline runs, the `secretSauce` variable is not set, and a warning is displayed on the pipeline run page.

```yaml
steps:
  - bash: |
      echo "##vso[task.setvariable variable=sauce;]crushed tomatoes"
      echo "##vso[task.setvariable variable=secretSauce;]crushed tomatoes with garlic"
    target:
     settableVariables:
      - sauce
    name: SetVars
  - bash: 
      echo "Sauce is $(sauce)"
      echo "secretSauce is $(secretSauce)"
    name: OutputVars
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Configure settable variables for steps](/azure/devops/pipelines/process/variables#configure-settable-variables-for-steps)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
