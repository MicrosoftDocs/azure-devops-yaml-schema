---
title: resources.webhooks.webhook definition
description: A webhook resource enables you to integrate your pipeline with an external service to automate the workflow.
ms.date: 03/02/2023
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

Definitions that that reference this definition: [resources.webhooks](resources-webhooks.md)

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
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->