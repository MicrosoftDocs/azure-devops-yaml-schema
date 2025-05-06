---
title: resources.webhooks.webhook.filters.filter definition
description: Filters used to customize the triggers for a webhook event.
ms.date: 04/30/2025
monikerRange: ">=azure-pipelines-2020.1"
author: juliakm
ms.author: jukullam
---

# resources.webhooks.webhook.filters.filter definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020.1"

<!-- :::editable-content name="description"::: -->
Filters used to customize the triggers for a webhook event.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020.1"

```yaml
filters:
- path: string # Required as first property. json path to select data from event payload.
  value: string # Required. Expected value for the filter to match.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020.1"

Definitions that reference this definition: [resources.webhooks.webhook.filters](resources-webhooks-webhook-filters.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="path"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`path`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
json path to select data from event payload.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="value"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`value`** string. Required.<br><!-- :::editable-content name="propDescription"::: -->
Expected value for the filter to match.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
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
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->