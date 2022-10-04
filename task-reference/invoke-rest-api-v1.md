---
title: InvokeRESTAPI@1 - Invoke REST API v1 task
description: Invoke a REST API as a part of your pipeline.
ms.date: 09/26/2022
monikerRange: "<=azure-pipelines"
---

# InvokeRESTAPI@1 - Invoke REST API v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Invoke a REST API as a part of your pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Invoke REST API v1
# Invoke a REST API as a part of your pipeline.
- task: InvokeRESTAPI@1
  inputs:
    connectionType: 'connectedServiceName' # 'connectedServiceName' | 'connectedServiceNameARM'. Required. Connection type. Default: connectedServiceName.
    serviceConnection: # string. Required when connectedServiceNameSelector = connectedServiceName. Generic service connection. 
    #azureServiceConnection: # string. Required when connectedServiceNameSelector = connectedServiceNameARM. Azure subscription. 
    method: 'POST' # 'OPTIONS' | 'GET' | 'HEAD' | 'POST' | 'PUT' | 'DELETE' | 'TRACE' | 'PATCH'. Required. Method. Default: POST.
    #headers: # string. Headers. 
    #body: # string. Optional. Use when method != GET && method != HEAD. Body. 
    #urlSuffix: # string. URL suffix and parameters. 
  # Advanced
    waitForCompletion: 'false' # 'true' | 'false'. Required. Completion event. Default: false.
    #successCriteria: # string. Optional. Use when waitForCompletion = false. Success criteria.
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

<!-- :::item name="connectionType"::: -->
:::moniker range=">=azure-pipelines-2019"

**`connectionType`** - **Connection type**<br>
Input alias: `connectedServiceNameSelector`. `string`. Required. Allowed values: `connectedServiceName` (Generic), `connectedServiceNameARM` (Azure Resource Manager). Default value: `connectedServiceName`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the service connection type to use to invoke the REST API. Select Azure Resource Manager to invoke an Azure management API or Generic for all other APIs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="serviceConnection"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`serviceConnection`** - **Generic service connection**<br>
Input alias: `connectedServiceName | genericService`. `string`. Required when `connectedServiceNameSelector = connectedServiceName`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Generic service connection that provides the baseUrl for the call and the authorization to use.
Select a generic service connection that should be used to pick the URL and construct authorization header for the http request.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`serviceConnection`** - **Generic service connection**<br>
Input alias: `connectedServiceName`. `string`. Required when `connectedServiceNameSelector = connectedServiceName`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Generic service connection that provides the baseUrl for the call and the authorization to use.
Select a generic service connection that should be used to pick the URL and construct authorization header for the http request.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`serviceConnection`** - **Generic endpoint**<br>
Input alias: `connectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a generic endpoint that should be used to pick the url and construct authorization header for the http request.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="azureServiceConnection"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azureServiceConnection`** - **Azure subscription**<br>
Input alias: `connectedServiceNameARM | azureSubscription`. `string`. Required when `connectedServiceNameSelector = connectedServiceNameARM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Resource Manager subscription to configure and use for invoking Azure management APIs.
Select an Azure Resource Manager subscription that should be used to pick the url and construct authorization header for the http request.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2019"

**`azureServiceConnection`** - **Azure subscription**<br>
Input alias: `connectedServiceNameARM`. `string`. Required when `connectedServiceNameSelector = connectedServiceNameARM`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Azure Resource Manager subscription to configure and use for invoking Azure management APIs.
Select an Azure Resource Manager subscription that should be used to pick the url and construct authorization header for the http request.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="method"::: -->
:::moniker range="<=azure-pipelines"

**`method`** - **Method**<br>
`string`. Required. Allowed values: `OPTIONS`, `GET`, `HEAD`, `POST`, `PUT`, `DELETE`, `TRACE`, `PATCH`. Default value: `POST`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The HTTP method with which the API will be invoked; for example, GET, PUT, or UPDATE.
Select the HTTP method with which the API should be invoked.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="headers"::: -->
:::moniker range="<=azure-pipelines"

**`headers`** - **Headers**<br>
`string`. Default value: `{\n"Content-Type":"application/json", \n"PlanUrl": "$(system.CollectionUri)", \n"ProjectId": "$(system.TeamProjectId)", \n"HubName": "$(system.HostType)", \n"PlanId": "$(system.PlanId)", \n"JobId": "$(system.JobId)", \n"TimelineId": "$(system.TimelineId)", \n"TaskInstanceId": "$(system.TaskInstanceId)", \n"AuthToken": "$(system.AccessToken)"\n}`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Define header in JSON format. The header shall be attached with request to be sent. The header in JSON format to be attached to the request sent to the API.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="body"::: -->
:::moniker range="<=azure-pipelines"

**`body`** - **Body**<br>
`string`. Optional. Use when `method != GET && method != HEAD`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The request body for the function call in JSON format.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="urlSuffix"::: -->
:::moniker range=">=azure-pipelines-2019"

**`urlSuffix`** - **URL suffix and parameters**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The string to append to the baseUrl from the Generic service connection while making the HTTP call.
Given string append to the URL. Example: If the service connection URL is https:...TestProj/_apis/Release/releases and the URL suffix is /2/environments/1, the service connection URL becomes https:.../TestProj/_apis/Release/releases/2/environments/1. If the URL suffix is ?definitionId=1&releaseCount=1 then the service connection URL becomes https//...TestProj/_apis/Release/releases?definitionId=1&releaseCount=1.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`urlSuffix`** - **Url suffix and parameters**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The string to append to the baseUrl from the Generic service connection while making the HTTP call.
Given string append to the URL. Example: If the service connection URL is https:...TestProj/_apis/Release/releases and the URL suffix is /2/environments/1, the service connection URL becomes https:.../TestProj/_apis/Release/releases/2/environments/1. If the URL suffix is ?definitionId=1&releaseCount=1 then the service connection URL becomes https//...TestProj/_apis/Release/releases?definitionId=1&releaseCount=1.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="waitForCompletion"::: -->
:::moniker range="<=azure-pipelines"

**`waitForCompletion`** - **Completion event**<br>
`string`. Required. Allowed values: `true` (Callback), `false` (ApiResponse). Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Default value "ApiResponse". Available values :  "ApiResponse", "Callback" call where the REST API calls back to update the timeline record​.
How the task reports completion. Can be API response (the default) - completion is when the function returns success within 20 seconds and the success criteria evaluates to true, or Callback - the external service makes a callback to update the timeline record.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="successCriteria"::: -->
:::moniker range="<=azure-pipelines"

**`successCriteria`** - **Success criteria**<br>
`string`. Optional. Use when `waitForCompletion = false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Criteria which defines when to pass the task. No criteria means response content does not influence the result. Example:- For response {"status" : "successful"}, the expression can be eq(root['status'], 'successful'). [More information](https://go.microsoft.com/fwlink/?linkid=842996)​.
How to parse the response body for success. By default, the task passes when 200 OK is returned from the call. Additionally, the success criteria - if specified - is evaluated.
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

> [!NOTE]
> This task can be used only in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs).

::: moniker range="azure-pipelines-2018"

> [!NOTE]
> This task is available in both classic build and release pipelines starting with TFS 2018.2 In TFS 2018 RTM, this task is available only in classic release pipeines.

::: moniker-end

Succeeds if the API returns success and the response body parsing is successful, or when the API updates the timeline record with success.

The **Invoke REST API task** does not perform deployment actions directly.
Instead, it allows you to invoke any generic HTTP REST API as part of the automated
pipeline and, optionally, wait for it to be completed.

![Configuring an Invoke REST API task](media/invoke-rest-api-task.png)

For more information about using this task, see [Approvals and gates overview](/azure/devops/pipelines/release/approvals/).

### What base URLs are used when invoking Azure Management APIs?

Azure management APIs are invoked using *ResourceManagerEndpoint* of the selected environment. For example `https://management.Azure.com` is used when the subscription is in **AzureCloud** environment.

### Where should a task signal completion when **Callback** is chosen as the completion event?

To signal completion, the external service should POST completion data to the following pipelines REST endpoint.
```
{planUri}/{projectId}/_apis/distributedtask/hubs/{hubName}/plans/{planId}/events?api-version=2.0-preview.1

**Request Body**
 { "name": "TaskCompleted", "taskId": "taskInstanceId", "jobId": "jobId", "result": "succeeded" }
 ```
 
See [this simple cmdline application](https://github.com/Microsoft/azure-pipelines-extensions/tree/master/ServerTaskHelper/HttpRequestSampleWithoutHandler) for specifics. 
 
In addition, a C# helper library is available to enable live logging and managing task status for agentless tasks. [Learn more](/archive/blogs/aseemb/async-http-agentless-task) 

### Can I use the response body as the input for another task?

No, as this task is an agentless task and uses TFS's internal HttpRequest, which doesn't return the content of the HTTP request.
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
| Runs on | Server, ServerGate |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->