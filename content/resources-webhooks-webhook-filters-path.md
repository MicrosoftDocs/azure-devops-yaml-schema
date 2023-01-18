---
title: resources.webhooks.webhook.filters.path definition
description: resources.webhooks.webhook.filters.path definition reference.
ms.date: 01/18/2023
monikerRange: "= azure-pipelines || = azure-pipelines-2020.1 || = azure-pipelines-2022"
---

# resources.webhooks.webhook.filters.path definition


A webhook filter is used to customize the triggers for a webhook event.


:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="webhookFilter{path,value}" version="azure-pipelines-2020.1"::: -->

```yaml
filters:
- path: string # Required as first property. json path to select data from event payload. 
  value: string # Required. Expected value for the filter to match. 
```


Properties that use this definition: [resources.webhooks.webhook.filters](resources-webhooks-webhook-filters.md)

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

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="webhookFilter{path,value}" version="azure-pipelines-2022"::: -->

```yaml
filters:
- path: string # Required as first property. json path to select data from event payload. 
  value: string # Required. Expected value for the filter to match. 
```


Properties that use this definition: [resources.webhooks.webhook.filters](resources-webhooks-webhook-filters.md)

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
filters:
- path: string # Required as first property. json path to select data from event payload. 
  value: string # Required. Expected value for the filter to match. 
```


Properties that use this definition: [resources.webhooks.webhook.filters](resources-webhooks-webhook-filters.md)

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


## Examples

For subscribing to a webhook event, you need to define a webhook resource in your pipeline and point it to the Incoming webhook service connection. You can also define additional filters on the webhook resource based on the JSON payload data to further customize the triggers for each pipeline, and you can consume the payload data in the form of variables in your jobs.

```yaml
resources:
  webhooks:
    - webhook: MyWebhookTrigger          ### Webhook alias
      connection: MyWebhookConnection    ### Incoming webhook service connection
      filters:
        - path: repositoryName      ### JSON path in the payload
          value: maven-releases     ### Expected value in the path provided
        - path: action
          value: CREATED
steps:
- task: PowerShell@2
  inputs:
    targetType: 'inline'
    ### JSON payload data is available in the form of ${{ parameters.<WebhookAlias>.<JSONPath>}}
    script: |
      Write-Host ${{ parameters.MyWebhookTrigger.repositoryName}}
      Write-Host ${{ parameters.MyWebhookTrigger.component.group}}
```


## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)
