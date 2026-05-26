---
title: AzureFunction@2 - Invoke Azure Function v2 task
description: Invoke an Azure Function.
ms.date: 04/09/2026
monikerRange: "=azure-pipelines"
---

# AzureFunction@2 - Invoke Azure Function v2 task

<!-- :::description::: -->
:::moniker range=">azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Use this task in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) of a release pipeline to invoke an HTTP triggered function in a function app and parse the response. The function app must be created and hosted in Azure Functions.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Invoke Azure Function v2
# Invoke an Azure Function.
- task: AzureFunction@2
  inputs:
    #azureSubscription: # string. Alias: azureServiceConnection | connectedServiceARM. Azure Service Connection. 
    function: # string. Required. Azure function URL. 
    #key: # string. Function key. 
    method: 'POST' # 'OPTIONS' | 'GET' | 'HEAD' | 'POST' | 'PUT' | 'DELETE' | 'TRACE' | 'PATCH'. Required. Method. Default: POST.
    #headers: # string. Headers. 
    #queryParameters: # string. Query parameters. 
    #body: # string. Optional. Use when method != GET && method != HEAD. Body. 
  # Advanced
    waitForCompletion: 'false' # 'true' | 'false'. Required. Completion event. Default: false.
    #successCriteria: # string. Optional. Use when waitForCompletion = false. Success criteria.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range=">azure-pipelines-server"

**`azureSubscription`** - **Azure Service Connection**<br>
[Input alias](index.md#what-are-task-input-aliases): `azureServiceConnection | connectedServiceARM`. `string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Service connection used to authenticate when invoking the Azure Function. Provides an Entra Access Token for Service Principal or Managed Identity access.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="function"::: -->
:::moniker range=">azure-pipelines-server"

**`function`** - **Azure function URL**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
URL of the Azure function that needs to be invoked​. Example: `https://azurefunctionapp.azurewebsites.net/api/HttpTriggerJS1`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="key"::: -->
:::moniker range=">azure-pipelines-server"

**`key`** - **Function key**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The function or the host key used to access and invoke the function. To keep the key secure, use a secret pipeline variable to store the function key. Example: `$(myFunctionKey)`. `myFunctionKey` is an environment-level secret variable with a value as the secret key.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="method"::: -->
:::moniker range=">azure-pipelines-server"

**`method`** - **Method**<br>
`string`. Required. Allowed values: `OPTIONS`, `GET`, `HEAD`, `POST`, `PUT`, `DELETE`, `TRACE`, `PATCH`. Default value: `POST`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The HTTP method with which the function will be invoked.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="headers"::: -->
:::moniker range=">azure-pipelines-server"

**`headers`** - **Headers**<br>
`string`. Default value: `{\n"Content-Type":"application/json", \n"PlanUrl": "$(system.CollectionUri)", \n"ProjectId": "$(system.TeamProjectId)", \n"HubName": "$(system.HostType)", \n"PlanId": "$(system.PlanId)", \n"JobId": "$(system.JobId)", \n"TimelineId": "$(system.TimelineId)", \n"TaskInstanceId": "$(system.TaskInstanceId)", \n"AuthToken": "$(system.AccessToken)"\n}`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The header in JSON format to be attached to the request sent to the function.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="queryParameters"::: -->
:::moniker range=">azure-pipelines-server"

**`queryParameters`** - **Query parameters**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The string query to append to the function URL. Must not start with `?` or `&`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="body"::: -->
:::moniker range=">azure-pipelines-server"

**`body`** - **Body**<br>
`string`. Optional. Use when `method != GET && method != HEAD`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
JSON-formatted message body for the request.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="waitForCompletion"::: -->
:::moniker range=">azure-pipelines-server"

**`waitForCompletion`** - **Completion event**<br>
`string`. Required. Allowed values: `true` (Callback), `false` (ApiResponse). Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
How the task reports completion.

- **`false` - API response** - the function returns success and success criteria evaluates to true.
- **`true` - Callback** - the function makes a callback to update the timeline record.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="successCriteria"::: -->
:::moniker range=">azure-pipelines-server"

**`successCriteria`** - **Success criteria**<br>
`string`. Optional. Use when `waitForCompletion = false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The criteria for a successful task. By default, the task returns `200 OK` status when successful. If this input is not specified, the response content does not influence the result.

Example: For response `{"status" : "successful"}`, the expression can be `eq(root['status'], 'successful')`. Learn more about [specifying conditions](/azure/devops/pipelines/process/conditions)​.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">azure-pipelines-server"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) of a release pipeline to invoke an HTTP triggered function in a function app that is created and hosted in Azure Functions and parse the response.

### Where should a task signal completion when **Callback** is chosen as the completion event?

To signal completion, the function should POST completion data to the following pipelines REST endpoint.

```
{planUri}/{projectId}/_apis/distributedtask/hubs/{hubName}/plans/{planId}/events?api-version=2.0-preview.1

**Request Body**
{ "name": "TaskCompleted", "taskId": "taskInstanceId", "jobId": "jobId", "result": "succeeded" }
```
See [this simple cmdline application](https://github.com/Microsoft/azure-pipelines-extensions/tree/master/ServerTaskHelper/HttpRequestSampleWithoutHandler) for specifics. 
In addition, a C# helper library is available to enable live logging and managing task status for agentless tasks. [Learn more](/archive/blogs/aseemb/async-http-agentless-task) 

### Why does the task fail within 1 minute when the timeout is longer?

If the function executes for more than 1 minute, use the **Callback** completion event. The API Response completion option is supported for requests that complete within 60 seconds.
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

The following two examples are functionally equivalent. The first example uses an Azure Resource Manager service connection for authentication, while the second example directly uses a function key for authentication.

```yml
trigger: none
 
pool: server
 
steps:
- task: AzureFunction@2
  inputs:
    # Authenticate using Azure Resource Manager service connection
    authenticationType: 'azureServiceConnection'
    azureServiceConnection: 'working-app-registration'
    function: 'https://myfuction.azurewebsites.net/api/my-test-trigger-function'
    method: 'GET'
    waitForCompletion: 'false'
```

```yml
trigger: none
 
pool: server
 
steps:
- task: AzureFunction@2
  inputs:
    # Authenticate using function key
    authenticationType: 'functionKey'
    key: 'aaaaaaaa-0b0b-1c1c-2d2d-333333333333'
    function: 'https://myfuction.azurewebsites.net/api/my-test-trigger-function'
    method: 'GET'
    waitForCompletion: 'false'
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Server, ServerGate |
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