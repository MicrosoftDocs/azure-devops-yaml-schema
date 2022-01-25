---
title: variables definition
description: variables definition reference.
ms.date: 01/25/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# variables definition



You can add hard-coded values directly, reference [variable groups](/azure/devops/pipelines/library/variable-groups), or insert via variable templates.


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

:::moniker range="= azure-pipelines"

Properties that use this definition: [pipeline.variables](pipeline.md), [stages.stage.variables](stages-stage.md), [jobs.job.variables](jobs-job.md), [jobs.deployment.variables](jobs-deployment.md)

:::moniker-end

## Overloads

:::moniker range="= azure-pipelines-2019" 

| Overload | Description |
|----------|-------------|
| [variables](#variables) |  |
| [variables: variable list](#variables-variable-list) |  |

:::moniker-end

:::moniker range="= azure-pipelines-2019.1" 

| Overload | Description |
|----------|-------------|
| [variables](#variables) |  |
| [variables: variable list](#variables-variable-list) |  |

:::moniker-end

:::moniker range="= azure-pipelines-2020" 

| Overload | Description |
|----------|-------------|
| [variables](#variables) |  |
| [variables: variable list](#variables-variable-list) |  |

:::moniker-end

:::moniker range="= azure-pipelines-2020.1" 

| Overload | Description |
|----------|-------------|
| [variables](#variables) |  |
| [variables: variable list](#variables-variable-list) |  |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [variables](#variables) |  |
| [variables: variable list](#variables-variable-list) |  |

:::moniker-end


## Remarks

Specify variables at the pipeline, stage, or job level.


:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## variables

:::moniker-end


You can add hard-coded values directly, reference [variable groups](/azure/devops/pipelines/library/variable-groups), or insert via variable templates.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="variables" version="azure-pipelines-2019"::: -->


```yaml
variables:
- ```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="variables" version="azure-pipelines-2019.1"::: -->


```yaml
variables:
- ```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="variables" version="azure-pipelines-2020"::: -->


```yaml
variables:
- ```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="variables" version="azure-pipelines-2020.1"::: -->


```yaml
variables:
- ```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="variables" version="azure-pipelines"::: -->


```yaml
variables:
- ```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end


### Remarks

Specify variables at the pipeline, stage, or job level.



### Examples


For a simple set of hard-coded variables, use this mapping syntax:

```yaml
variables: { string: string }
```

To include variable groups, switch to this sequence syntax:

```yaml
variables:
- name: string  # name of a variable
  value: string # value of the variable
- group: string # name of a variable group
```

You can repeat `name`/`value` pairs and `group`.

Variables can also be set as read only to [enhance security](/azure/devops/pipelines/security/inputs.md#variables). 

```yaml
variables:
- name: myReadOnlyVar
  value: myValue
  readonly: true
```

::: moniker range=">=azure-pipelines-2020"

You can also include [variables from templates](/azure/devops/pipelines/process/templates.md#variable-reuse).

::: moniker-end

Mapping syntax:

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

Sequence syntax:

```yaml
variables:
- name: MY_VARIABLE           # hard-coded value
  value: some value
- group: my-variable-group-1  # variable group
- group: my-variable-group-2  # another variable group
```


:::moniker range="= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"

## variables: variable list

:::moniker-end



:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="variables[variable]" version="azure-pipelines-2019"::: -->


```yaml
variables: [ name | group | template ] # 
```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="variables[variable]" version="azure-pipelines-2019.1"::: -->


```yaml
variables: [ name | group | template ] # 
```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="variables[variable]" version="azure-pipelines-2020"::: -->


```yaml
variables: [ name | group | template ] # 
```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="variables[variable]" version="azure-pipelines-2020.1"::: -->


```yaml
variables: [ name | group | template ] # 
```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="variables[variable]" version="azure-pipelines"::: -->


```yaml
variables: [ name | group | template ] # 
```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end


### Remarks

Specify variables at the pipeline, stage, or job level.



### Examples


For a simple set of hard-coded variables, use this mapping syntax:

```yaml
variables: { string: string }
```

To include variable groups, switch to this sequence syntax:

```yaml
variables:
- name: string  # name of a variable
  value: string # value of the variable
- group: string # name of a variable group
```

You can repeat `name`/`value` pairs and `group`.

Variables can also be set as read only to [enhance security](/azure/devops/pipelines/security/inputs.md#variables). 

```yaml
variables:
- name: myReadOnlyVar
  value: myValue
  readonly: true
```

::: moniker range=">=azure-pipelines-2020"

You can also include [variables from templates](/azure/devops/pipelines/process/templates.md#variable-reuse).

::: moniker-end

Mapping syntax:

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

Sequence syntax:

```yaml
variables:
- name: MY_VARIABLE           # hard-coded value
  value: some value
- group: my-variable-group-1  # variable group
- group: my-variable-group-2  # another variable group
```


<!-- See also -->
