---
title: variables definition
description: variables definition reference.
ms.date: 08/08/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"
---

# variables definition


Define variables to use in your pipeline.


:::moniker range="= azure-pipelines-2019"

Properties that use this definition: [pipeline.variables](pipeline.md), [jobs.job.variables](jobs-job.md)

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

Properties that use this definition: [pipeline.variables](pipeline.md), [jobs.job.variables](jobs-job.md)

:::moniker-end

:::moniker range="= azure-pipelines-2020"

Properties that use this definition: [pipeline.variables](pipeline.md), [stages.stage.variables](stages-stage.md), [jobs.job.variables](jobs-job.md), [jobs.deployment.variables](jobs-deployment.md)

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

Properties that use this definition: [pipeline.variables](pipeline.md), [stages.stage.variables](stages-stage.md), [jobs.job.variables](jobs-job.md), [jobs.deployment.variables](jobs-deployment.md)

:::moniker-end

:::moniker range="= azure-pipelines-2022"

Properties that use this definition: [pipeline.variables](pipeline.md), [stages.stage.variables](stages-stage.md), [jobs.job.variables](jobs-job.md), [jobs.deployment.variables](jobs-deployment.md)

:::moniker-end

:::moniker range="= azure-pipelines"

Properties that use this definition: [pipeline.variables](pipeline.md), [stages.stage.variables](stages-stage.md), [jobs.job.variables](jobs-job.md), [jobs.deployment.variables](jobs-deployment.md)

:::moniker-end

## Overloads

:::moniker range="= azure-pipelines-2019" 

| Overload | Description |
|----------|-------------|
| [variables: string pairs](#variables-string-pairs) | Define variables using name/value pairs. |
| [variables: variable list](#variables-variable-list) | Define variables by name, variable group, or in a template. |

:::moniker-end

:::moniker range="= azure-pipelines-2019.1" 

| Overload | Description |
|----------|-------------|
| [variables: string pairs](#variables-string-pairs) | Define variables using name/value pairs. |
| [variables: variable list](#variables-variable-list) | Define variables by name, variable group, or in a template. |

:::moniker-end

:::moniker range="= azure-pipelines-2020" 

| Overload | Description |
|----------|-------------|
| [variables: string pairs](#variables-string-pairs) | Define variables using name/value pairs. |
| [variables: variable list](#variables-variable-list) | Define variables by name, variable group, or in a template. |

:::moniker-end

:::moniker range="= azure-pipelines-2020.1" 

| Overload | Description |
|----------|-------------|
| [variables: string pairs](#variables-string-pairs) | Define variables using name/value pairs. |
| [variables: variable list](#variables-variable-list) | Define variables by name, variable group, or in a template. |

:::moniker-end

:::moniker range="= azure-pipelines-2022" 

| Overload | Description |
|----------|-------------|
| [variables: string pairs](#variables-string-pairs) | Define variables using name/value pairs. |
| [variables: variable list](#variables-variable-list) | Define variables by name, variable group, or in a template. |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [variables: string pairs](#variables-string-pairs) | Define variables using name/value pairs. |
| [variables: variable list](#variables-variable-list) | Define variables by name, variable group, or in a template. |

:::moniker-end


## Remarks

The `variables` keyword uses two syntax forms: list and mapping.

In mapping syntax, all keys are variable names and their values are variable values. To use variable templates, you must use list syntax. List syntax requires you to specify whether you're mentioning a variable (`name`), a variable group (`group`), or a template (`template`).

You can't use list and mapping variables in the same variables section, but you can combine `name`, `group`, and `template` when using list syntax.

You can specify variables at the pipeline, stage, or job level.

:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"

## variables: string pairs

You can specify variables as string/value pairs.



:::moniker-end

:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="variables" version="azure-pipelines-2019"::: -->


```yaml
variables:
  string: string # Name/value pairs.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `mapping`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="variables" version="azure-pipelines-2019.1"::: -->


```yaml
variables:
  string: string # Name/value pairs.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `mapping`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="variables" version="azure-pipelines-2020"::: -->


```yaml
variables:
  string: string # Name/value pairs.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `mapping`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="variables" version="azure-pipelines-2020.1"::: -->


```yaml
variables:
  string: string # Name/value pairs.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `mapping`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="variables" version="azure-pipelines-2022"::: -->


```yaml
variables:
  string: string # Name/value pairs.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `mapping`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="variables" version="azure-pipelines"::: -->


```yaml
variables:
  string: string # Name/value pairs.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `mapping`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


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

::: moniker range=">= azure-pipelines-2019 <= azure-pipelines-2019.1"

```yaml
variables:      # pipeline-level
  MY_VAR: 'my value'
  ANOTHER_VAR: 'another value'

jobs:
- job: FirstJob
  variables:  # job-level
    JOB_VAR: 'a job var'
  steps:
  - script: echo $(MY_VAR) $(STAGE_VAR) $(JOB_VAR)
```

::: moniker-end


:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"

## variables: variable list

Specify variables using the full syntax.



:::moniker-end

:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="variables[variable]" version="azure-pipelines-2019"::: -->


```yaml
variables: [ name | group | template ] # Define variables by name, variable group, or in a template. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[variables.name](variables-name.md) | [variables.group](variables-group.md) | [variables.template](variables-template.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="variables[variable]" version="azure-pipelines-2019.1"::: -->


```yaml
variables: [ name | group | template ] # Define variables by name, variable group, or in a template. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[variables.name](variables-name.md) | [variables.group](variables-group.md) | [variables.template](variables-template.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="variables[variable]" version="azure-pipelines-2020"::: -->


```yaml
variables: [ name | group | template ] # Define variables by name, variable group, or in a template. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[variables.name](variables-name.md) | [variables.group](variables-group.md) | [variables.template](variables-template.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="variables[variable]" version="azure-pipelines-2020.1"::: -->


```yaml
variables: [ name | group | template ] # Define variables by name, variable group, or in a template. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[variables.name](variables-name.md) | [variables.group](variables-group.md) | [variables.template](variables-template.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="variables[variable]" version="azure-pipelines-2022"::: -->


```yaml
variables: [ name | group | template ] # Define variables by name, variable group, or in a template. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[variables.name](variables-name.md) | [variables.group](variables-group.md) | [variables.template](variables-template.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="variables[variable]" version="azure-pipelines"::: -->


```yaml
variables: [ name | group | template ] # Define variables by name, variable group, or in a template. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[variables.name](variables-name.md) | [variables.group](variables-group.md) | [variables.template](variables-template.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


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


## See also

- [Add & use variable groups](/azure/devops/pipelines/library/variable-groups)
- [Define variables](/azure/devops/pipelines/process/variables)



