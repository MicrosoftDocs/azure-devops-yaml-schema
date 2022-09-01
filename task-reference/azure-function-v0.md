---
title: AzureFunction@0 - Invoke Azure Function v0 task
description: Invoke Azure function as a part of your process.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# AzureFunction@0 - Invoke Azure Function v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Invoke Azure function as a part of your process.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Invoke Azure Function v0
# Invoke Azure function as a part of your process.
- task: AzureFunction@0
  inputs:
    function: # string. Required. Azure function url. 
    key: # string. Required. Function key. 
    method: 'POST' # 'OPTIONS' | 'GET' | 'HEAD' | 'POST' | 'PUT' | 'DELETE' | 'TRACE' | 'PATCH'. Required. Method. Default: 'POST'.
    #headers: # string. Headers. 
    #queryParameters: # string. Query parameters. 
    #body: '{"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}' # string. Optional. Use when method != GET && method != HEAD. Body. Default: '{"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}'.
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

<!-- :::item name="function"::: -->
:::moniker range="<=azure-pipelines"

**`function`** - **Azure function url**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
URL of the Azure function that needs to be invoked​. Example: `https://azurefunctionapp.azurewebsites.net/api/HttpTriggerJS1`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="key"::: -->
:::moniker range="<=azure-pipelines"

**`key`** - **Function key**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Function or Host key used to access this function. To keep the key secure, define a secret variable and use the variable here. Example: `$(myFunctionKey)` where `myFunctionKey` is an environment level secret variable with value as the secret key like `ZxPXnIEODXLRzYwCw1TgZ4osMfoKs9Zn6se6X/N0FnztfDvZbdOmYw==`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="method"::: -->
:::moniker range="<=azure-pipelines"

**`method`** - **Method**<br>
Type: string. Required. Allowed values: 'OPTIONS', 'GET', 'HEAD', 'POST', 'PUT', 'DELETE', 'TRACE', 'PATCH'. Default value: 'POST'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The http method with which the function should be invoked.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="headers"::: -->
:::moniker range="<=azure-pipelines"

**`headers`** - **Headers**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The header in JSON format to be attached to the request sent to the function.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="queryParameters"::: -->
:::moniker range="<=azure-pipelines"

**`queryParameters`** - **Query parameters**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The string query to append to the function URL. Must not start with `?` or `&`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="body"::: -->
:::moniker range="<=azure-pipelines"

**`body`** - **Body**<br>
Type: string. Optional. Use when method != GET && method != HEAD. Default value: '{"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The request body in JSON format.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="waitForCompletion"::: -->
:::moniker range="<=azure-pipelines"

**`waitForCompletion`** - **Complete based on**<br>
Type: string. Required. Allowed values: 'true', 'false'. Default value: 'false'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Default value "ApiResponse". Available values :  "ApiResponse", "Callback" call where the Azure function calls back to update the timeline record​.
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