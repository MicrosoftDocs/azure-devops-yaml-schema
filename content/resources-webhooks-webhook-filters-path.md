---
title: resources.webhooks.webhook.filters.path definition
description: resources.webhooks.webhook.filters.path definition reference.
ms.date: 01/25/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020.1"
---

# resources.webhooks.webhook.filters.path definition


:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="webhookFilter{path,value}" version="azure-pipelines-2020.1"::: -->

```yaml
webhookFilters:
- path: string # Required as first property. json path to select data from event payload. 
  value: string # Required. Expected value for the filter to match. 
```


Properties that use this definition: [resources.webhooks.webhook.filters.webhookFilters](resources-webhooks-webhook-filters.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `path`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. json path to select data from event payload. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `value`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required. Expected value for the filter to match. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="webhookFilter{path,value}" version="azure-pipelines"::: -->

```yaml
webhookFilters:
- path: string # Required as first property. json path to select data from event payload. 
  value: string # Required. Expected value for the filter to match. 
```


Properties that use this definition: [resources.webhooks.webhook.filters.webhookFilters](resources-webhooks-webhook-filters.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `path`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. json path to select data from event payload. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `value`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required. Expected value for the filter to match. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


<!-- Examples -->

