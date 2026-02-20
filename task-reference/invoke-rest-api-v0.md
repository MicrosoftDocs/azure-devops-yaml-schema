---
title: InvokeRESTAPI@0 - Invoke REST API v0 task
description: Invoke REST API as a part of your process (task version 0).
ms.date: 01/27/2026
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022"
---

# InvokeRESTAPI@0 - Invoke REST API v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to invoke a REST API as a part of your pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Invoke REST API v0
# Invoke REST API as a part of your process.
- task: InvokeRESTAPI@0
  inputs:
    serviceConnection: # string. Alias: connectedServiceName. Required. Generic endpoint. 
    method: 'POST' # 'OPTIONS' | 'GET' | 'HEAD' | 'POST' | 'PUT' | 'DELETE' | 'TRACE' | 'PATCH'. Required. Method. Default: POST.
    #headers: # string. Headers. 
    #body: '{"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}' # string. Optional. Use when method != GET && method != HEAD. Body. Default: {"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}.
    #urlSuffix: # string. Url suffix string. 
  # Completion Options
    waitForCompletion: 'false' # 'true' | 'false'. Required. Complete based on. Default: false.
    #successCriteria: # string. Optional. Use when waitForCompletion = false. Success criteria.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="serviceConnection"::: -->
:::moniker range="<=azure-pipelines"

**`serviceConnection`** - **Generic endpoint**<br>
[Input alias](index.md#what-are-task-input-aliases): `connectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the generic service connection that provides the `baseURL` for the call and the authorization to use for the task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="method"::: -->
:::moniker range="<=azure-pipelines"

**`method`** - **Method**<br>
`string`. Required. Allowed values: `OPTIONS`, `GET`, `HEAD`, `POST`, `PUT`, `DELETE`, `TRACE`, `PATCH`. Default value: `POST`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the HTTP method that invokes the API.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="headers"::: -->
:::moniker range="<=azure-pipelines"

**`headers`** - **Headers**<br>
`string`. Default value: `{\n"Content-Type":"application/json"\n}`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Defines the header in JSON format. The header is attached with the request sent to the API.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="body"::: -->
:::moniker range="<=azure-pipelines"

**`body`** - **Body**<br>
`string`. Optional. Use when `method != GET && method != HEAD`. Default value: `{"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the request body for the function call in JSON format.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="urlSuffix"::: -->
:::moniker range="<=azure-pipelines"

**`urlSuffix`** - **Url suffix string**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the string to append to the baseUrl from the generic service connection while making the HTTP call.

Example: If the service connection URL is `https:...TestProj/_apis/Release/releases` and the URL suffix is `/2/environments/1`, the service connection URL becomes `https:.../TestProj/_apis/Release/releases/2/environments/1`. If the URL suffix is `?definitionId=1&releaseCount=1`, then the service connection URL becomes `https//...TestProj/_apis/Release/releases?definitionId=1&releaseCount=1`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="waitForCompletion"::: -->
:::moniker range="<=azure-pipelines"

**`waitForCompletion`** - **Complete based on**<br>
`string`. Required. Allowed values: `true` (Callback), `false` (ApiResponse). Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies how the task reports completion. The allowed values are:

- `false` - **API response**: Reports completion when the function returns success within 20 seconds, and the success criteria evaluates to true.
- `true` - **Callback**: Reports completion when the external service makes a callback to update the timeline record.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="successCriteria"::: -->
:::moniker range="<=azure-pipelines"

**`successCriteria`** - **Success criteria**<br>
`string`. Optional. Use when `waitForCompletion = false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the task's criteria for success. The response content does not influence the result if no criteria is defined. By default, the task passes when the call returns `200 OK`.

Example: For response `{"status" : "successful"}`, the expression can be `eq(root['status'], 'successful')`. Learn more about [specifying conditions](/azure/devops/pipelines/process/conditions).
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

Succeeds if the API returns success and the response body parsing is successful, or when the API updates the timeline record with success.

The **Invoke REST API task** does not perform deployment actions directly.
Instead, it allows you to invoke any generic HTTP REST API as part of the automated
pipeline and, optionally, wait for it to be completed.

![Configuring an Invoke REST API task](media/invoke-rest-api-task.png)

For more information about using this task, see [Approvals and gates overview](/azure/devops/pipelines/release/approvals/).

### What base URLs are used when invoking Azure Management APIs?

Azure management APIs are invoked using *ResourceManagerEndpoint* of the selected environment. For example `https://management.Azure.com` is used when the subscription is in an **AzureCloud** environment.

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