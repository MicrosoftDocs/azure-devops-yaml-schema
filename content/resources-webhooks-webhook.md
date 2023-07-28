---
title: resources.webhooks.webhook definition
description: A webhook resource enables you to integrate your pipeline with an external service to automate the workflow.
ms.date: 07/10/2023
monikerRange: ">=azure-pipelines-2020.1"
---

# resources.webhooks.webhook definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2020.1"

<!-- :::editable-content name="description"::: -->
A webhook resource enables you to integrate your pipeline with an external service to automate the workflow.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020.1"

```yaml
webhooks:
- webhook: string # Required as first property. Name of the webhook.
  connection: string # Required. Name of the connection. In case of offline webhook this will be the type of Incoming Webhook otherwise it will be the type of the webhook extension.
  type: string # Name of the webhook extension. Leave this empty if it is an offline webhook.
  filters: [ filter ] # List of trigger filters.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020.1"

Definitions that reference this definition: [resources.webhooks](resources-webhooks.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="webhook"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`webhook`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Name of the webhook. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="connection"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`connection`** string. Required.<br><!-- :::editable-content name="propDescription"::: -->
Name of the connection. In case of offline webhook this will be the type of Incoming Webhook otherwise it will be the type of the webhook extension.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="type"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`type`** string.<br><!-- :::editable-content name="propDescription"::: -->
Name of the webhook extension. Leave this empty if it is an offline webhook.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="filters"::: -->
:::moniker range=">=azure-pipelines-2020.1"

**`filters`** [resources.webhooks.webhook.filters](resources-webhooks-webhook-filters.md).<br><!-- :::editable-content name="propDescription"::: -->
List of trigger filters.
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

You can define your pipeline as follows.
```yaml
resources:
  webhooks:
    - webhook: WebHook
      connection: IncomingWH

steps:  
- script: echo ${{ parameters.WebHook.resource.message.title }}
```

To trigger your pipeline using the webhook, you need to make a `POST` request to `https://dev.azure.com/<org_name>/_apis/public/distributedtask/webhooks/<webhook_connection_name>?api-version=6.0-preview`. This endpoint is publicly available, and no authorization is needed. The request should have the following body.
```json
{
    "resource": {
        "message": {
            "title": "Hello, world!",
            "subtitle": "I'm using WebHooks!"
        }
    }
}
```
When you access data from the webhook's request body, be mindful that it may lead to incorrect YAML. For example, if in the previous pipeline, your step reads `- script: echo ${{ parameters.WebHook.resource.message }}`, and you trigger the pipeline via a webhook, the pipeline doesn't run. This is because in the process of replacing `${{ parameters.WebHook.resource.message.title }}` with 
```json
{
  "title": "Hello, world!",
  "subtitle": "I'm using WebHooks!"
}
```
the generated YAML becomes invalid, and no pipeline run is queued in response.

<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
