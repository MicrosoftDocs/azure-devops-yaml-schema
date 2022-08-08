---
title: target.settableVariables definition
description: target.settableVariables definition reference.
ms.date: 08/08/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2022"
---

# target.settableVariables definition


Variables that can be set by a step.


:::moniker range="= azure-pipelines-2022"

Properties that use this definition: [target.settableVariables](target.md)

:::moniker-end

:::moniker range="= azure-pipelines"

Properties that use this definition: [target.settableVariables](target.md)

:::moniker-end

## Overloads

:::moniker range="= azure-pipelines-2022" 

| Overload | Description |
|----------|-------------|
| [settableVariables: none](#settablevariables-none) | Disable a step from setting any variables. |
| [settableVariables: string list](#settablevariables-string-list) | Restrict variable setting to a list of allowed variables. |

:::moniker-end

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [settableVariables: none](#settablevariables-none) | Disable a step from setting any variables. |
| [settableVariables: string list](#settablevariables-string-list) | Restrict variable setting to a list of allowed variables. |

:::moniker-end


## Remarks

You can disable setting all variables for a step, or restrict the settable variables to a list. If the `settableVariables` property is not set, the default allows all variables to be set by a step.

:::moniker range="= azure-pipelines || = azure-pipelines-2022"

## settableVariables: none

Disable a step from setting any variables.



:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="variableRestrictions(none)" version="azure-pipelines-2022"::: -->


```yaml
settableVariables: none # Disable a step from setting any variables.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variableRestrictions`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Acceptable values: none
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="variableRestrictions(none)" version="azure-pipelines"::: -->


```yaml
settableVariables: none # Disable a step from setting any variables.
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variableRestrictions`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Acceptable values: none
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


### Examples

```yaml
steps:
- script: echo This is a step
  target:
    settableVariables: none
```

:::moniker range="= azure-pipelines || = azure-pipelines-2022"

## settableVariables: string list

Restrict a step from setting any variables not in the specified list.



:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="variableRestrictions[string]" version="azure-pipelines-2022"::: -->


```yaml
settableVariables: [ string ] # Restrict variable setting to a list of allowed variables. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variableRestrictions`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
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

<!-- :::api-definition signature="variableRestrictions[string]" version="azure-pipelines"::: -->


```yaml
settableVariables: [ string ] # Restrict variable setting to a list of allowed variables. 
```

### Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variableRestrictions`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
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


## See also

- [Configure settable variables for steps](/azure/devops/pipelines/process/variables#configure-settable-variables-for-steps)

