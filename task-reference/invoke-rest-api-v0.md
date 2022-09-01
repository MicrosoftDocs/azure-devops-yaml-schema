---
title: InvokeRESTAPI@0 - Invoke REST API v0 task
description: Invoke REST API as a part of your process (task version 0).
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# InvokeRESTAPI@0 - Invoke REST API v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Invoke REST API as a part of your process.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Invoke REST API v0
# Invoke REST API as a part of your process.
- task: InvokeRESTAPI@0
  inputs:
    serviceConnection: # string. Required. Generic endpoint. 
    method: 'POST' # 'OPTIONS' | 'GET' | 'HEAD' | 'POST' | 'PUT' | 'DELETE' | 'TRACE' | 'PATCH'. Required. Method. Default: 'POST'.
    #headers: # string. Headers. 
    #body: '{"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}' # string. Optional. Use when method != GET && method != HEAD. Body. Default: '{"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}'.
    #urlSuffix: # string. Url suffix string. 
  # Completion Options
    waitForCompletion: 'false' # 'true' | 'false'. Required. Complete based on. Default: 'false'.
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

<!-- :::item name="serviceConnection"::: -->
:::moniker range="<=azure-pipelines"

**`serviceConnection`** - **Generic endpoint**<br>
Input alias: `connectedServiceName`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a generic endpoint that should be used to pick the url and construct authorization header for the http request.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="method"::: -->
:::moniker range="<=azure-pipelines"

**`method`** - **Method**<br>
Type: string. Required. Allowed values: 'OPTIONS', 'GET', 'HEAD', 'POST', 'PUT', 'DELETE', 'TRACE', 'PATCH'. Default value: 'POST'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the http method with which the API should be invoked with.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="headers"::: -->
:::moniker range="<=azure-pipelines"

**`headers`** - **Headers**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Define header in JSON format. The header shall be attached with request to be sent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="body"::: -->
:::moniker range="<=azure-pipelines"

**`body`** - **Body**<br>
Type: string. Optional. Use when method != GET && method != HEAD. Default value: '{"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="urlSuffix"::: -->
:::moniker range="<=azure-pipelines"

**`urlSuffix`** - **Url suffix string**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Given string append to the url. Example: If endpoint url is https:...TestProj/_apis/Release/releases and url suffix is /2/environments/1, endpoint url becomes https:.../TestProj/_apis/Release/releases/2/environments/1. If url suffix is ?definitionId=1&releaseCount=1 then endpoint url becomes https//...TestProj/_apis/Release/releases?definitionId=1&releaseCount=1.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="waitForCompletion"::: -->
:::moniker range="<=azure-pipelines"

**`waitForCompletion`** - **Complete based on**<br>
Type: string. Required. Allowed values: 'true', 'false'. Default value: 'false'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Default value "ApiResponse". Available values :  "ApiResponse", "Callback" call where the REST API calls back to update the timeline record​.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="successCriteria"::: -->
:::moniker range="<=azure-pipelines"

**`successCriteria`** - **Success criteria**<br>
Type: string. Optional. Use when waitForCompletion = false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Criteria which defines when to pass the task. No criteria means response content does not influence the result. Example:- For response {"status" : "successful"}, the expression can be eq(root['status'], 'successful'). [More Information](https://go.microsoft.com/fwlink/?linkid=842996)​.
<!-- :::editable-content-end::: -->

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