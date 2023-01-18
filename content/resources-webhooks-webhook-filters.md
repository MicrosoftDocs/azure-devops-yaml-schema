---
title: resources.webhooks.webhook.filters list definition
description: resources.webhooks.webhook.filters list definition reference.
ms.date: 01/18/2023
monikerRange: "= azure-pipelines || = azure-pipelines-2020.1 || = azure-pipelines-2022"
---

# resources.webhooks.webhook.filters list definition


Filters used to customize the triggers for a webhook event.


:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="webhookFilters[webhookFilter]" version="azure-pipelines-2020.1"::: -->

```yaml
filters: [ path ] # 
```


Properties that use this definition: [resources.webhooks.webhook.filters](resources-webhooks-webhook.md)

## List types

| Type     | Description |
|----------|-------------|
| [resources.webhooks.webhook.filters.path](resources-webhooks-webhook-filters-path.md) | Filter the JSON payload data by path/value. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="webhookFilters[webhookFilter]" version="azure-pipelines-2022"::: -->

```yaml
filters: [ path ] # 
```


Properties that use this definition: [resources.webhooks.webhook.filters](resources-webhooks-webhook.md)

## List types

| Type     | Description |
|----------|-------------|
| [resources.webhooks.webhook.filters.path](resources-webhooks-webhook-filters-path.md) | Filter the JSON payload data by path/value. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="webhookFilters[webhookFilter]" version="azure-pipelines"::: -->

```yaml
filters: [ path ] # 
```


Properties that use this definition: [resources.webhooks.webhook.filters](resources-webhooks-webhook.md)

## List types

| Type     | Description |
|----------|-------------|
| [resources.webhooks.webhook.filters.path](resources-webhooks-webhook-filters-path.md) | Filter the JSON payload data by path/value. |

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
