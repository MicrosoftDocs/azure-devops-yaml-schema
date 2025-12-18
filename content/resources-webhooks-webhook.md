---
title: resources.webhooks.webhook definition
description: A webhook resource enables you to integrate your pipeline with an external service to automate the workflow.
ms.date: 12/18/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# resources.webhooks.webhook definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
A webhook resource enables you to integrate your pipeline with an external service to automate the workflow.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

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
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [resources.webhooks](resources-webhooks.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="webhook"::: -->
:::moniker range="<=azure-pipelines"

**`webhook`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Name of the webhook. Acceptable values: [-_A-Za-z0-9]*.
For Azure DevOps webhook, `webhook` must always be a `WebHook`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="connection"::: -->
:::moniker range="<=azure-pipelines"

**`connection`** string. Required.<br><!-- :::editable-content name="propDescription"::: -->
Name of the connection. In case of offline webhook this will be the type of Incoming Webhook otherwise it will be the type of the webhook extension.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="type"::: -->
:::moniker range="<=azure-pipelines"

**`type`** string.<br><!-- :::editable-content name="propDescription"::: -->
Name of the webhook extension. Leave this empty if it is an offline webhook.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="filters"::: -->
:::moniker range="<=azure-pipelines"

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

### Basic example
You can define your pipeline as follows.

```yaml
resources:
  webhooks:
    - webhook: WebHook
      connection: IncomingWH

steps:  
- script: echo ${{ parameters.WebHook.resource.message.title }}
```

To trigger your pipeline using the webhook, you need to make a `POST` request to `https://dev.azure.com/<org_name>/_apis/public/distributedtask/webhooks/<WebHook Name>?api-version=6.0-preview`. 
The WebHook Name must match that of the Incoming WebHook Service Connection.
This endpoint is publicly available, and no authorization is needed. The request should have the following body.

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

When you access data from the webhook's request body, be mindful that it may lead to incorrect YAML. For example, if in the previous pipeline, your step reads `- script: echo ${{ parameters.WebHook.resource.message }}`, and you trigger the pipeline via a webhook, the pipeline doesn't run. This is because in the process of replacing `${{ parameters.WebHook.resource.message.title }}` with `message`, which contains the following JSON, the generated YAML becomes invalid.

```json
{
  "title": "Hello, world!",
  "subtitle": "I'm using WebHooks!"
}
```

Because the generated YAML becomes invalid, no pipeline run is queued in response.

### Prevent unauthorized pipeline runs

Webhooks allow anyone to trigger your pipeline, as long as they know the names of your organization and webhook service connection. 

You can prevent unauthorized pipeline runs by defining a _secret_ when creating an Incoming Webhook service connection. You need to also specify the name of HTTP header that contains the SHA-1 checksum of the webhook's body. 

To verify that an incoming webhook REST API call is authorized, Azure Pipelines computes the SHA-1 checksum of the request's body using the secret as key. It then compares it to the checksum passed in the request header. This way, the caller proves they know the secret.

Let's look at an example. Say you configured an Incoming Webhook service connection named `IncomingWH`, specified the secret is `secret`, and that the checksum is sent in the HTTP header named `X-WH-Checksum`. Imagine you have a pipeline that defines a Webhook resource.

Say you want to trigger the pipeline using the following request body:
```json
{"resource":{"message":{"title":"Hello, world!","subtitle":"I'm using WebHooks!"}}}
```

To do this, you need to make a `POST` request to `https://dev.azure.com/<org_name>/_apis/public/distributedtask/webhooks/IncomingWH?api-version=6.0-preview` and add the `X-WH-Checksum` header with the value of `750D33212D3AD4932CC390819050734831A0A94F`. You do not need to specify any username & password or any other type of authentication information. 

Azure Pipelines will independently compute the SHA-1 checksum of the body using `secret` as key and will generate the same `750D33212D3AD4932CC390819050734831A0A94F` value. Since the values match, the call is authorized, and pipeline queueing proceeds.

You compute the value of the `X-WH-Checksum` header, in pseudocode, as `SHA1(secret).ComputeHash(requestBody)`. You can use .NET's `System.Security.Cryptography.HMACSHA1` class for this purpose. 

To prevent validation failures due to new lines or whitespaces, we recommend you send the body in a minimized form. That is, send 
```json
{"resource":{"message":{"title":"Hello, world!","subtitle":"I'm using WebHooks!"}}}
```
instead of 
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

Even though the two JSON objects above represent the same object, they generate different SHA-1 checksums. This is because SHA-1 is computed on their string representation, which is different.
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
