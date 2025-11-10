---
title: variables definition
description: Define variables using name/value pairs.
ms.date: 11/10/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# variables definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Define variables using name/value pairs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [pipeline](pipeline.md), [stages.stage](stages-stage.md), [jobs.job](jobs-job.md), [jobs.deployment](jobs-deployment.md)

:::moniker-end

<!-- :::parents-end::: -->

## Implementations

<!-- :::implementations-list::: -->
:::moniker range="<=azure-pipelines"

| Implementation | Description |
|---|---|
| [variables: string dictionary](#variablesmapping) | Define variables using name/value pairs. |
| [variables: variable list](#variablesvariablelist) | Define variables by name, variable group, or in a template. |

:::moniker-end
<!-- :::implementations-list-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

The `variables` keyword uses two syntax forms: variable list and mapping (string dictionary).

In mapping syntax, all keys are variable names and their values are variable values. To use variable templates, you must use list syntax. List syntax requires you to specify whether you're mentioning a variable (`name`), a variable group (`group`), or a template (`template`).

You can't use list and mapping variables in the same variables section, but you can combine `name`, `group`, and `template` when using list syntax.

You can specify variables at the pipeline, stage, or job level.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::implementations::: -->
<!-- :::implementation-item name="variables: mapping"::: -->
<a name="variablesmapping"></a>
<!-- :::objectAnyOf::: -->
:::moniker range="<=azure-pipelines"

<!-- :::implementation-signature::: -->
## variables: string dictionary
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Define variables using name/value pairs.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
variables:
  string: string # Name/value pairs
```
<!-- :::implementation-syntax-end::: -->

<!-- :::implementation-properties::: -->
None.
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

For a simple set of hard-coded variables, use this mapping syntax:

```yaml
variables: { string: string }
```

Variables defined at different scopes:

::: moniker range=">= azure-pipelines-2020"

```yaml
variables:      # pipeline-level
  MY_VAR: 'my value'
  ANOTHER_VAR: 'another value'

stages:
- stage: Build
  variables:    # stage-level
    STAGE_VAR: 'that happened'

  jobs:
  - job: FirstJob
    variables:  # job-level
      JOB_VAR: 'a job var'
    steps:
    - script: echo $(MY_VAR) $(STAGE_VAR) $(JOB_VAR)
```

::: moniker-end
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementation-item name="variables: variable list"::: -->
<a name="variablesvariablelist"></a>
<!-- :::arrayAnyOf::: -->
:::moniker range="<=azure-pipelines"

<!-- :::implementation-signature::: -->
## variables: variable list
<!-- :::implementation-signature-end::: -->

<!-- :::implementation-description::: -->
<!-- :::editable-content name="description"::: -->
Define variables by name, variable group, or in a template.
<!-- :::editable-content-end::: -->
<!-- :::implementation-description-end::: -->

<!-- :::implementation-syntax::: -->
```yaml
variables: [ name | group | template ] # Define variables by name, variable group, or in a template.
```
<!-- :::implementation-syntax-end::: -->

### List types

<!-- :::implementation-list-types::: -->
| Type | Description |
|---|---|
| [variables.name](variables-name.md) | Define variables using name and full syntax. |
| [variables.group](variables-group.md) | Reference variables from a variable group. |
| [variables.template](variables-template.md) | Define variables in a template. |
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

To include variable groups, switch to this sequence syntax:

```yaml
variables:
- name: string  # name of a variable
  value: string # value of the variable
- group: string # name of a variable group
```

You can repeat `name`/`value` pairs and `group`.

Variables can also be set as read only to [enhance security](/azure/devops/pipelines/security/inputs#variables). 

```yaml
variables:
- name: myReadOnlyVar
  value: myValue
  readonly: true
```

::: moniker range=">=azure-pipelines-2020"

You can also include [variables from templates](/azure/devops/pipelines/process/templates#variable-reuse).

::: moniker-end

Sequence syntax:

```yaml
variables:
- name: MY_VARIABLE           # hard-coded value
  value: some value
- group: my-variable-group-1  # variable group
- group: my-variable-group-2  # another variable group
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->
<!-- :::implementation-item-end::: -->
<!-- :::implementations-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Add & use variable groups](/azure/devops/pipelines/library/variable-groups)
- [Define variables](/azure/devops/pipelines/process/variables)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
