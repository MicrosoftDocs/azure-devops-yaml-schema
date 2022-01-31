---
title: resources.webhooks.webhook definition
description: resources.webhooks.webhook definition reference.
ms.date: 01/31/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020.1"
---

# resources.webhooks.webhook definition


A webhook resource enables you to integrate your pipeline with an external service to automate the workflow.


:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="webhookResource{webhook,connection}" version="azure-pipelines-2020.1"::: -->

```yaml
webhooks:
- webhook: string # Required as first property. Name of the webhook.  ([-_A-Za-z0-9]*)
  connection: string # Required. Name of the connection. In case of offline webhook this will be the type of Incoming Webhook otherwise it will be the type of the webhook extension.. 
  type: string # Name of the webhook extension. leave this empty if its offline webhook.. 
  filters: [ path ]
```


Properties that use this definition: [resources.webhooks](resources-webhooks.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `webhook`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Name of the webhook. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `connection`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required. Name of the connection. In case of offline webhook this will be the type of Incoming Webhook otherwise it will be the type of the webhook extension. 
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
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the webhook extension. leave this empty if its offline webhook. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `filters`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.webhooks.webhook.filters](resources-webhooks-webhook-filters.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of trigger filters. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="webhookResource{webhook,connection}" version="azure-pipelines"::: -->

```yaml
webhooks:
- webhook: string # Required as first property. Name of the webhook.  ([-_A-Za-z0-9]*)
  connection: string # Required. Name of the connection. In case of offline webhook this will be the type of Incoming Webhook otherwise it will be the type of the webhook extension.. 
  type: string # Name of the webhook extension. leave this empty if its offline webhook.. 
  filters: [ path ]
```


Properties that use this definition: [resources.webhooks](resources-webhooks.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `webhook`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Name of the webhook. Acceptable values: [-_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `connection`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required. Name of the connection. In case of offline webhook this will be the type of Incoming Webhook otherwise it will be the type of the webhook extension. 
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
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Name of the webhook extension. leave this empty if its offline webhook. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `filters`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[resources.webhooks.webhook.filters](resources-webhooks-webhook-filters.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->List of trigger filters. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


<!-- Examples -->


## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)
