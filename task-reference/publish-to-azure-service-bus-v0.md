---
title: PublishToAzureServiceBus@0 - Publish To Azure Service Bus v0 task
description: Sends a message to azure service bus using a service connection (no agent required).
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# PublishToAzureServiceBus@0 - Publish To Azure Service Bus v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Sends a message to azure service bus using a service connection (no agent required).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

```yaml
# Publish To Azure Service Bus v0
# Sends a message to azure service bus using a service connection (no agent required).
- task: PublishToAzureServiceBus@0
  inputs:
    azureSubscription: # string. Required. Azure service bus connection. 
    messageBody: '{"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}' # string. Required. Message body. Default: '{"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}'.
    waitForCompletion: false # boolean. Required. Wait for task completion. Default: false.
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
:::moniker range="<=azure-pipelines"

**`azureSubscription`** - **Azure service bus connection**<br>
Input alias: `connectedServiceName`. Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select a Azure Service Bus connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="messageBody"::: -->
:::moniker range="<=azure-pipelines"

**`messageBody`** - **Message body**<br>
Type: string. Required. Default value: '{"JobId": "$(system.jobId)", "PlanId": "$(system.planId)", "TimelineId": "$(system.timelineId)", "ProjectId": "$(system.teamProjectId)", "VstsUrl": "$(system.CollectionUri)","AuthToken": "$(system.AccessToken)"}'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enter the json messageBody.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="waitForCompletion"::: -->
:::moniker range="<=azure-pipelines"

**`waitForCompletion`** - **Wait for task completion**<br>
Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If this is true, this task will wait for TaskCompleted event for the specified task timeout.
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