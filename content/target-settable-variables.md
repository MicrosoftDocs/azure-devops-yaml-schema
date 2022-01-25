---
title: target.settableVariables definition
description: target.settableVariables definition reference.
ms.date: 01/25/2022
monikerRange: "= azure-pipelines"
---

# target.settableVariables definition


:::moniker range="= azure-pipelines"

Properties that use this definition: [target.settableVariables](target.md)

:::moniker-end

## Overloads

:::moniker range="= azure-pipelines" 

| Overload | Description |
|----------|-------------|
| [variableRestrictions: none](#variablerestrictions-none) | Disable variable restrictions and allow all variables. |
| [variableRestrictions: string list](#variablerestrictions-string-list) |  |

:::moniker-end

<!-- Remarks -->

:::moniker range="= azure-pipelines"

## variableRestrictions: none

:::moniker-end



:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="variableRestrictions(none)" version="azure-pipelines"::: -->


```yaml
variableRestrictions: none # Disable variable restrictions and allow all variables.
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


<!-- Examples -->

:::moniker range="= azure-pipelines"

## variableRestrictions: string list

:::moniker-end



:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="variableRestrictions[string]" version="azure-pipelines"::: -->


```yaml
settableVariables: [ string ] # 
```

### Properties




<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


<!-- Examples -->

