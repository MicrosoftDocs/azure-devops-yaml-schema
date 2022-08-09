---
title: resources.webhooks list definition
description: resources.webhooks list definition reference.
ms.date: 08/08/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020.1 || = azure-pipelines-2022"
---

# resources.webhooks list definition


List of webhook resources referenced by the pipeline.


:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="webhookResources[webhookResource]" version="azure-pipelines-2020.1"::: -->

```yaml
webhooks: [ webhook ] # 
```


Properties that use this definition: [resources.webhooks](resources.md)

## List types

| Type     | Description |
|----------|-------------|
| [resources.webhooks.webhook](resources-webhooks-webhook.md) | A webhook resource enables you to integrate your pipeline with an external service to automate the workflow. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="webhookResources[webhookResource]" version="azure-pipelines-2022"::: -->

```yaml
webhooks: [ webhook ] # 
```


Properties that use this definition: [resources.webhooks](resources.md)

## List types

| Type     | Description |
|----------|-------------|
| [resources.webhooks.webhook](resources-webhooks-webhook.md) | A webhook resource enables you to integrate your pipeline with an external service to automate the workflow. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="webhookResources[webhookResource]" version="azure-pipelines"::: -->

```yaml
webhooks: [ webhook ] # 
```


Properties that use this definition: [resources.webhooks](resources.md)

## List types

| Type     | Description |
|----------|-------------|
| [resources.webhooks.webhook](resources-webhooks-webhook.md) | A webhook resource enables you to integrate your pipeline with an external service to automate the workflow. |

<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


<!-- Examples -->


## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)
