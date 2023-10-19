---
title: pipeline.parameters.parameter definition
description: Represents a value passed to a pipeline.
ms.date: 10/19/2023
monikerRange: ">=azure-pipelines-2020"
---

# pipeline.parameters.parameter definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020"

<!-- :::editable-content name="description"::: -->
A parameter represents a value passed to a pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020"

```yaml
parameters:
- name: string # Required as first property.
  displayName: string # Human-readable name for the parameter.
  type: string
  default: string | parameters | [ parameters ]
  values: [ string ]
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [parameters](parameters.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="name"::: -->
:::moniker range=">=azure-pipelines-2020"

**`name`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
:::moniker range=">=azure-pipelines-2020"

**`displayName`** string.<br><!-- :::editable-content name="propDescription"::: -->
Human-readable name for the parameter.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="type"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`type`** string.<br><!-- :::editable-content name="propDescription"::: -->
See [**types**](#types).
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2020"

**`type`** string.<br><!-- :::editable-content name="propDescription"::: -->
boolean | deployment | deploymentList | environment | filePath | job | jobList | number | object | pool | secureFile | serviceConnection | stage | stageList | step | stepList | string.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="default"::: -->
:::moniker range=">=azure-pipelines-2020"

**`default`** parameters.<br><!-- :::editable-content name="propDescription"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="values"::: -->
:::moniker range=">=azure-pipelines-2020"

**`values`** string list.<br><!-- :::editable-content name="propDescription"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

The type and name fields are required when defining parameters. See all [parameter data types](/azure/devops/pipelines/process/runtime-parameters#parameter-data-types).

```yaml
parameters:
- name: string          # name of the parameter; required
  type: enum            # see the enum data types in the following section
  default: any          # default value; if no default, then the parameter MUST be given by the user at runtime
  values: [ string ]    # allowed list of values (for some data types)
```

### Types

The `type` value must be one of the `enum` members from the following table.

| Data type | Notes |
|-----------|-------|
| `string` | string |
| `number` | may be restricted to `values:`, otherwise any number-like string is accepted |
| `boolean` | `true` or `false` |
| `object` | any YAML structure |
| `step` | a single step |
| `stepList` | sequence of steps |
| `job` | a single job |
| `jobList` | sequence of jobs |
| `deployment` | a single deployment job |
| `deploymentList` | sequence of deployment jobs |
| `stage` | a single stage |
| `stageList` | sequence of stages |

The step, stepList, job, jobList, deployment, deploymentList, stage, and stageList data types all use standard YAML schema format. This example includes string, number, boolean, object, step, and stepList. 


```yaml
parameters:
- name: myString
  type: string
  default: a string
- name: myMultiString
  type: string
  default: default
  values:
  - default
  - ubuntu
- name: myNumber
  type: number
  default: 2
  values:
  - 1
  - 2
  - 4
  - 8
  - 16
- name: myBoolean
  type: boolean
  default: true
- name: myObject
  type: object
  default:
    foo: FOO
    bar: BAR
    things:
    - one
    - two
    - three
    nested:
      one: apple
      two: pear
      count: 3
- name: myStep
  type: step
  default:
    script: echo my step
- name: mySteplist
  type: stepList
  default:
    - script: echo step one
    - script: echo step two

trigger: none

jobs: 
- job: stepList
  steps: ${{ parameters.mySteplist }}
- job: myStep
  steps:
    - ${{ parameters.myStep }}
```
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yaml
# File: azure-pipelines.yml
parameters:
- name: image
  displayName: Pool Image
  type: string
  default: ubuntu-latest
  values:
  - windows-latest
  - ubuntu-latest
  - macOS-latest

trigger: none

jobs:
- job: build
  displayName: build
  pool: 
    vmImage: ${{ parameters.image }}
  steps:
  - script: echo The image parameter is ${{ parameters.image }}```
```

You can use parameters to extend a template. In this example, the pipeline using the template supplies the values to fill into the template.

```yaml
# File: simple-param.yml
parameters:
- name: yesNo # name of the parameter; required
  type: boolean # data type of the parameter; required
  default: false

steps:
- script: echo ${{ parameters.yesNo }}
```

```yaml
# File: azure-pipelines.yml
trigger:
- main

extends:
    template: simple-param.yml
    parameters:
        yesNo: false # set to a non-boolean value to have the build fail
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

See [templates](/azure/devops/pipelines/process/templates) for more about working with templates.
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->