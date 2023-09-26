---
title: PublishToAzureServiceBus@1 - Publish To Azure Service Bus v1 task
description: Sends a message to Azure Service Bus using a service connection (no agent is required).
ms.date: 09/26/2023
monikerRange: "<=azure-pipelines"
---

# PublishToAzureServiceBus@1 - Publish To Azure Service Bus v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to send a message to Azure Service Bus using a service connection (no agent is required).
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to send a message to Azure Service Bus using a service connection (no agent required).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.1"

```yaml
# Publish To Azure Service Bus v1
# Sends a message to Azure Service Bus using a service connection (no agent is required).
- task: PublishToAzureServiceBus@1
  inputs:
    azureSubscription: # string. Alias: connectedServiceName. Required. Azure Service Bus service connection. 
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

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2022"

```yaml
# Publish To Azure Service Bus v1
# Sends a message to Azure Service Bus using a service connection (no agent is required).
- task: PublishToAzureServiceBus@1
  inputs:
    azureSubscription: # string. Alias: connectedServiceName. Required. Azure Service Bus service connection. 
    #messageBody: # string. Message body. 
    #waitForCompletion: false # boolean. Wait for task completion. Default: false.
  # Advanced
    #sessionId: # string. Session Id. 
    #signPayload: false # boolean. Sign the Message. Default: false.
    #certificateString: # string. Required when signPayload = true. Certificate Variable. 
    #signatureKey: 'signature' # string. Optional. Use when signPayload = true. Signature Property Key. Default: signature.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Publish To Azure Service Bus v1
# Sends a message to azure service bus using a service connection (no agent required).
- task: PublishToAzureServiceBus@1
  inputs:
    azureSubscription: # string. Alias: connectedServiceName. Required. Azure Service Bus service connection. 
    #messageBody: # string. Message body. 
    #waitForCompletion: false # boolean. Wait for task completion. Default: false.
  # Signing Properties
    #signPayload: false # boolean. Sign the Message. Default: false.
    #certificateString: # string. Required when signPayload = true. Certificate Variable. 
    #signatureKey: 'signature' # string. Optional. Use when signPayload = true. Signature Property Key. Default: signature.
```

:::moniker-end

:::moniker range="=azure-pipelines-2018"

```yaml
# YAML Syntax is not supported in TFS 2018.
# Use the classic designer to add and configure tasks.
# See the following Inputs section for details on the inputs that this task supports.
```

:::moniker-end


<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2019"

**`azureSubscription`** - **Azure Service Bus service connection**<br>
Input alias: `connectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an [Azure Service Bus service connection](/azure/devops/pipelines/library/service-endpoints#azure-service-bus-service-connection).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`azureSubscription`** - **Azure service bus connection**<br>
Input alias: `connectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies an Azure Service Bus service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="messageBody"::: -->
:::moniker range="<=azure-pipelines"

**`messageBody`** - **Message body**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the JSON `messageBody`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sessionId"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`sessionId`** - **Session Id**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the session ID with which the message is published. For session-based queues, the publishing fails if a value is not specified. For non session-based queues, a value does not need to be specified.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signPayload"::: -->
:::moniker range="<=azure-pipelines"

**`signPayload`** - **Sign the Message**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, a private certificate will be added to the message.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="certificateString"::: -->
:::moniker range="<=azure-pipelines"

**`certificateString`** - **Certificate Variable**<br>
`string`. Required when `signPayload = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the secret variable that contains the certificate content. This can also be a certificate stored in an Azure key vault that is [linked](/azure/devops/pipelines/library/variable-groups#link-secrets-from-an-azure-key-vault-as-variables) to a variable group used by the release pipeline.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="signatureKey"::: -->
:::moniker range=">=azure-pipelines-2019"

**`signatureKey`** - **Signature Property Key**<br>
`string`. Optional. Use when `signPayload = true`. Default value: `signature`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In Message Properties, specifies the key where the signature is. If left empty, the default value is `signature`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`signatureKey`** - **Signature Property Key**<br>
`string`. Optional. Use when `signPayload = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
In Message Properties, specifies the key where the signature is. If left empty, the default value is `signature`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="waitForCompletion"::: -->
:::moniker range="<=azure-pipelines"

**`waitForCompletion`** - **Wait for task completion**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, this task will wait for the TaskCompleted event for the specified task timeout.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="useDataContractSerializer"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`useDataContractSerializer`** - **Use .NET data contract serializer.**<br>
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

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) of a release pipeline to send a message to an Azure Service Bus using a service connection (without using an agent).

> [!NOTE]
> Can only be used in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) of a release pipeline.

### Where should a task signal completion?

To signal completion, the external service should POST completion data to the following pipelines REST endpoint.

```
{planUri}/{projectId}/_apis/distributedtask/hubs/{hubName}/plans/{planId}/events?api-version=2.0-preview.1

**Request Body**
 { "name": "TaskCompleted", "taskId": "taskInstanceId", "jobId": "jobId", "result": "succeeded" }
```

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

:::moniker range="<=azure-pipelines"

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
