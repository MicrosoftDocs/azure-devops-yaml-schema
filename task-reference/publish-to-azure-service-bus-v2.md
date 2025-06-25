---
title: PublishToAzureServiceBus@2 - Publish To Azure Service Bus v2 task
description: Sends a message to Azure Service Bus using a service connectionno, with no agent required.
ms.date: 06/24/2025
monikerRange: "=azure-pipelines"
---

# PublishToAzureServiceBus@2 - Publish To Azure Service Bus v2 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Sends a message to Azure Service Bus using a service connection (no agent is required).

This version of the task supports Entra ID and Workload identity federation through its [Azure Resource Manager service connection](/azure/devops/pipelines/library/connect-to-azure) input (`azureSubscription`). For more information, see the following [Remarks](#remarks) section.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Publish To Azure Service Bus v2
# Sends a message to Azure Service Bus using an Azure Resource Manager service connection (no agent is required).
- task: PublishToAzureServiceBus@2
  inputs:
    azureSubscription: # string. Alias: connectedServiceName. Required. Azure Resource Manager service connection. 
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

**`azureSubscription`** - **Azure Resource Manager service connection**<br>
[Input alias](index.md#what-are-task-input-aliases): `connectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an [Azure Resource Manager service connection](/azure/devops/pipelines/library/service-endpoints#azure-resource-manager-service-connection).
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
Specifies the JSON `messageBody`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sessionId"::: -->
:::moniker range="=azure-pipelines"

**`sessionId`** - **Session Id**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the session ID with which the message is published. For session-based queues, the publishing fails if a value is not specified. For non session-based queues, a value does not need to be specified.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signPayload"::: -->
:::moniker range="=azure-pipelines"

**`signPayload`** - **Sign the Message**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, a private certificate will be added to the message.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="certificateString"::: -->
:::moniker range="=azure-pipelines"

**`certificateString`** - **Certificate Variable**<br>
`string`. Required when `signPayload = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the secret variable that contains the certificate content. This can also be a certificate stored in an Azure key vault that is [linked](/azure/devops/pipelines/library/variable-groups#link-secrets-from-an-azure-key-vault-as-variables) to a variable group used by the release pipeline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signatureKey"::: -->
:::moniker range="=azure-pipelines"

**`signatureKey`** - **Signature Property Key**<br>
`string`. Optional. Use when `signPayload = true`. Default value: `signature`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In Message Properties, specifies the key where the signature is. If left empty, the default value is `signature`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="waitForCompletion"::: -->
:::moniker range="=azure-pipelines"

**`waitForCompletion`** - **Wait for task completion**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, this task will wait for the TaskCompleted event for the specified task timeout.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useDataContractSerializer"::: -->
:::moniker range="=azure-pipelines"

**`useDataContractSerializer`** - **Use .NET data contract serializer**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Set `useDataContractSerializer` to `false` if you want to pass your message as a stream instead of an object.
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
## Remarks

Use this task in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) of a release pipeline to send a message to an Azure Service Bus using a service connection (without using an agent).

> [!NOTE]
> Can only be used in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) of a release pipeline.

### Access Azure Service Bus from Pipelines using Entra ID authentication

You can now use [Entra ID authentication](/azure/service-bus-messaging/service-bus-authentication-and-authorization#microsoft-entra-id) to access Azure Service Bus from Azure Pipelines. This allows you to take advantage of Workload identity federation to remove secrets management and Azure RBAC for fine grained access control.

Identities accessing Azure Service Bus will need to be granted one of the [Azure built-in roles for Azure Service Bus](/azure/service-bus-messaging/authenticate-application#azure-built-in-roles-for-azure-service-bus) on the Service Bus accessed.

The `PublishToAzureServiceBus@2` task can be configured using an Azure Resource Manager service connection. Create an [Azure Resource Manager service connection](/azure/devops/pipelines/library/connect-to-azure) and populate the `serviceBusQueueName` and `serviceBusNamespace` properties of the task:

```yaml
- task: PublishToAzureServiceBus@2
  inputs:
    azureSubscription: my-azure-service-connection
    serviceBusQueueName: my-service-bus-queue
    serviceBusNamespace: my-service-bus-namespace
    useDataContractSerializer: false
    messageBody: |
      {
        "property": "value"
      }
```

### Where should a task signal completion?

To signal completion, the external service should POST completion data to the following pipelines REST endpoint.

```
{planUri}/{projectId}/_apis/distributedtask/hubs/{hubName}/plans/{planId}/events?api-version=2.0-preview.1

**Request Body**
 { "name": "TaskCompleted", "taskId": "taskInstanceId", "jobId": "jobId", "result": "succeeded" }
```

Azure DevOps automatically populates the [ServiceBusReceivedMessage.ApplicationProperties](/dotnet/api/azure.messaging.servicebus.servicebusreceivedmessage.applicationproperties).

See [this simple cmdline application](https://github.com/Microsoft/azure-pipelines-extensions/tree/master/ServerTaskHelper/HttpRequestSampleWithoutHandler) for specifics.

In addition, a C# helper library is available to enable live logging and managing the task status for agentless tasks. Learn more about [Async HTTP agentless tasks](/archive/blogs/aseemb/async-http-agentless-task).
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