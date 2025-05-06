---
title: AzureFunction@0 - Invoke Azure Function v0 task
description: Invoke Azure function as a part of your process.
ms.date: 05/06/2025
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# AzureFunction@0 - Invoke Azure Function v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task in an [agentless job](/azure/devops/pipelines/process/phases#server-jobs) of a release pipeline to invoke an HTTP triggered function in a function app and parse the response. The function app must be created and hosted in Azure Functions.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Invoke Azure Function v0
# Invoke Azure function as a part of your process.
- task: AzureFunction@0
  inputs:
    function: # string. Required. Azure function url. 
    key: # string. Required. Function key. 
    method: 'POST' # 'OPTIONS' | 'GET' | 'HEAD' | 'POST' | 'PUT' | 'DELETE' | 'TRACE' | 'PATCH'. Required. Method. Default: POST.
    #headers: # string. Headers. 
    #queryParameters: # string. Query parameters. 
    #body: '{"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}' # string. Optional. Use when method != GET && method != HEAD. Body. Default: {"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}.
  # Completion Options
    waitForCompletion: 'false' # 'true' | 'false'. Required. Complete based on. Default: false.
    #successCriteria: # string. Optional. Use when waitForCompletion = false. Success criteria.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="function"::: -->
:::moniker range="<=azure-pipelines"

**`function`** - **Azure function url**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The URL of the Azure function to be invoked​. Example: `https://azurefunctionapp.azurewebsites.net/api/HttpTriggerJS1`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="key"::: -->
:::moniker range="<=azure-pipelines"

**`key`** - **Function key**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The function or the host key used to access and invoke the function. To keep the key secure, use a secret pipeline variable to store the function key. Example: `$(myFunctionKey)`. `myFunctionKey` is an environment-level secret variable with a value as the secret key.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="method"::: -->
:::moniker range="<=azure-pipelines"

**`method`** - **Method**<br>
`string`. Required. Allowed values: `OPTIONS`, `GET`, `HEAD`, `POST`, `PUT`, `DELETE`, `TRACE`, `PATCH`. Default value: `POST`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The HTTP method with which the function will be invoked.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="headers"::: -->
:::moniker range="<=azure-pipelines"

**`headers`** - **Headers**<br>
`string`. Default value: `{\n"Content-Type":"application/json"\n}`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The header in JSON format to be attached to the request sent to the function.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="queryParameters"::: -->
:::moniker range="<=azure-pipelines"

**`queryParameters`** - **Query parameters**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The string query to append to the function URL. Must not start with `?` or `&`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="body"::: -->
:::moniker range="<=azure-pipelines"

**`body`** - **Body**<br>
`string`. Optional. Use when `method != GET && method != HEAD`. Default value: `{"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The request body in JSON format.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="waitForCompletion"::: -->
:::moniker range="<=azure-pipelines"

**`waitForCompletion`** - **Complete based on**<br>
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
:::moniker range="<=azure-pipelines"

**`successCriteria`** - **Success criteria**<br>
`string`. Optional. Use when `waitForCompletion = false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The criteria for a successful task. By default, the task returns `200 OK` status when successful.

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

:::moniker range="<=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

[AzureFunction@2](azure-function-v1.md) is a newer version of the Invoke Azure Function task.
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
| Pipeline types | Classic release |
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
## See also

* [AzureFunction@2](azure-function-v1.md) is a newer version of the Invoke Azure Function task.
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->