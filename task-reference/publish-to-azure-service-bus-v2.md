---
title: PublishToAzureServiceBus@2 - Publish To Azure Service Bus v2 task
description: Sends a message to Azure Service Bus using a service connection (no agent is required).
ms.date: 06/11/2024
monikerRange: "=azure-pipelines"
---

# PublishToAzureServiceBus@2 - Publish To Azure Service Bus v2 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Sends a message to Azure Service Bus using a service connection (no agent is required).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Publish To Azure Service Bus v2
# Sends a message to Azure Service Bus using a service connection (no agent is required).
- task: PublishToAzureServiceBus@2
  inputs:
    azureSubscription: # string. Alias: connectedServiceName. Required. Azure Service Bus service connection. 
    serviceBusQueueName: # string. Required. Azure Service Bus Queue name. 
    serviceBusNamespace: # string. Required. Azure Service Bus Namespace. 
    #messageBody: # string. Message body. 
    #waitForCompletion: false # boolean. Wait for task completion. Default: false.
    #useDataContractSerializer: true # boolean. Use .NET data contract serializer. Default: true.
  # Advanced
    #sessionId: # string. Session Id. 
    #signPayload: false # boolean. Sign the Message. Default: false.
    #certificateString: # string. Required when signPayload = true. Certificate Variable. 
    #signatureKey: 'signature' # string. Optional. Use when signPayload = true. Signature Property Key. Default: signature.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscription`** - **Azure Service Bus service connection**<br>
Input alias: `connectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select an Azure Service Bus service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serviceBusQueueName"::: -->
:::moniker range="=azure-pipelines"

**`serviceBusQueueName`** - **Azure Service Bus Queue name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the name of the queue for which the message is intended.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serviceBusNamespace"::: -->
:::moniker range="=azure-pipelines"

**`serviceBusNamespace`** - **Azure Service Bus Namespace**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the namespace of your Azure Service Bus.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="messageBody"::: -->
:::moniker range="=azure-pipelines"

**`messageBody`** - **Message body**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the json messageBody.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sessionId"::: -->
:::moniker range="=azure-pipelines"

**`sessionId`** - **Session Id**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Session id with which message is published. For session based queues, publishing fails if value not specified. For Non Session Based Queues, it will not matter.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signPayload"::: -->
:::moniker range="=azure-pipelines"

**`signPayload`** - **Sign the Message**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is set to true, message will be signed provided a private certificate.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="certificateString"::: -->
:::moniker range="=azure-pipelines"

**`certificateString`** - **Certificate Variable**<br>
`string`. Required when `signPayload = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify the secret variable that contains the certificate content.  This can also be a certificate stored in an Azure key vault that is [linked](https://docs.microsoft.com/en-us/vsts/pipelines/library/variable-groups?view=vsts#link-secrets-from-an-azure-key-vault-as-variables) to a Variable Group used by this release pipeline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signatureKey"::: -->
:::moniker range="=azure-pipelines"

**`signatureKey`** - **Signature Property Key**<br>
`string`. Optional. Use when `signPayload = true`. Default value: `signature`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Key where you want signature to be in Message Properties. If left Empty, default is 'signature' in message properties.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="waitForCompletion"::: -->
:::moniker range="=azure-pipelines"

**`waitForCompletion`** - **Wait for task completion**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, this task will wait for TaskCompleted event for the specified task timeout.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useDataContractSerializer"::: -->
:::moniker range="=azure-pipelines"

**`useDataContractSerializer`** - **Use .NET data contract serializer**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
For more details go to task documentation.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Server |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->