---
title: parameters.name definition
description: parameters.name definition reference.
ms.date: 08/08/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"
---

# parameters.name definition


A parameter represents a value passed to a pipeline.


:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="pipelineTemplateParameter{name}" version="azure-pipelines-2020"::: -->

```yaml
pipelineTemplateParameters:
- name: string # Required as first property. Parameter name.. 
  displayName: string # Human-readable name for the parameter. 
  type: string # Parameter type. Required..  (boolean,deployment,deploymentList,environment,filePath,job,jobList,number,object,pool,secureFile,serviceConnection,stage,stageList,step,stepList,string)
  default: any # Default value if none is specified.
  values: [ string ] # Allowed parameter values. 
```


Properties that use this definition: [parameters.pipelineTemplateParameters](parameters.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `name`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Parameter name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `displayName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Human-readable name for the parameter. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `type`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
pipelineTemplateParameterType
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Parameter type. Required. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `default`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
Depends on the type
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Default value if none is specified. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `values`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Allowed parameter values. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="pipelineTemplateParameter{name}" version="azure-pipelines-2020.1"::: -->

```yaml
pipelineTemplateParameters:
- name: string # Required as first property. Parameter name.. 
  displayName: string # Human-readable name for the parameter. 
  type: string # Parameter type. Required..  (boolean,container,containerList,deployment,deploymentList,environment,filePath,job,jobList,number,object,pool,secureFile,serviceConnection,stage,stageList,step,stepList,string)
  default: any # Default value if none is specified.
  values: [ string ] # Allowed parameter values. 
```


Properties that use this definition: [parameters.pipelineTemplateParameters](parameters.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `name`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Parameter name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `displayName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Human-readable name for the parameter. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `type`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
pipelineTemplateParameterType
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Parameter type. Required. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `default`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
Depends on the type
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Default value if none is specified. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `values`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Allowed parameter values. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="pipelineTemplateParameter{name}" version="azure-pipelines-2022"::: -->

```yaml
pipelineTemplateParameters:
- name: string # Required as first property. Parameter name.. 
  displayName: string # Human-readable name for the parameter. 
  type: string # Parameter type. Required..  (boolean,container,containerList,deployment,deploymentList,environment,filePath,job,jobList,number,object,pool,secureFile,serviceConnection,stage,stageList,step,stepList,string)
  default: any # Default value if none is specified.
  values: [ string ] # Allowed parameter values. 
```


Properties that use this definition: [parameters.pipelineTemplateParameters](parameters.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `name`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Parameter name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `displayName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Human-readable name for the parameter. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `type`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
pipelineTemplateParameterType
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Parameter type. Required. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `default`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
Depends on the type
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Default value if none is specified. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `values`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Allowed parameter values. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="pipelineTemplateParameter{name}" version="azure-pipelines"::: -->

```yaml
pipelineTemplateParameters:
- name: string # Required as first property. Parameter name.. 
  displayName: string # Human-readable name for the parameter. 
  type: string # Parameter type. Required..  (boolean,container,containerList,deployment,deploymentList,environment,filePath,job,jobList,number,object,pool,secureFile,serviceConnection,stage,stageList,step,stepList,string)
  default: any # Default value if none is specified.
  values: [ string ] # Allowed parameter values. 
```


Properties that use this definition: [parameters.pipelineTemplateParameters](parameters.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `name`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Parameter name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `displayName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Human-readable name for the parameter. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `type`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
pipelineTemplateParameterType
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Parameter type. Required. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `default`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
Depends on the type
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Default value if none is specified. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `values`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Allowed parameter values. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


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


## See also

See [templates](/azure/devops/pipelines/process/templates) for more about working with templates.




