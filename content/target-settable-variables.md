---
title: target.settableVariables definition
description: target.settableVariables definition reference.
ms.date: 01/28/2022
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
| [settableVariables: none](#settablevariables-none) | Disable variable restrictions and allow all variables. |
| [settableVariables: string list](#settablevariables-string-list) |  |

:::moniker-end

<!-- Remarks -->

:::moniker range="= azure-pipelines"

## settableVariables: none




:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="variableRestrictions(none)" version="azure-pipelines"::: -->


```yaml
settableVariables: none # Disable variable restrictions and allow all variables.
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

## settableVariables: string list




:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="variableRestrictions[string]" version="azure-pipelines"::: -->


```yaml
settableVariables: [ string ] # 
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


<!-- Examples -->

