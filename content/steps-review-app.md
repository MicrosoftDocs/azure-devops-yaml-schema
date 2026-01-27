---
title: steps.reviewApp definition
description: Downloads creates a resource dynamically under a deploy phase provider.
ms.date: 01/27/2026
monikerRange: "<=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# steps.reviewApp definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
The `reviewApp` step deploys every pull request from your Git repository to a dynamic environment resource.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="<=azure-pipelines"

```yaml
steps:
- reviewApp: string # Required as first property. Use this task under deploy phase provider to create a resource dynamically.
  condition: string # Evaluate this condition expression to determine whether to run this task.
  continueOnError: boolean # Continue running even on failure?
  displayName: string # Human-readable name for the task.
  target: string | target # Environment in which to run this task.
  enabled: boolean # Run this task when the job runs?
  env: # Variables to map into the process's environment.
    string: string # Name/value pairs
  name: string # ID of the step.
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it.
  retryCountOnTaskFailure: string # Number of retries if the task fails.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [steps](steps.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<a name="reviewApp-property"></a>
<!-- :::item name="reviewApp"::: -->
:::moniker range="<=azure-pipelines"

**`reviewApp`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Use this task under deploy phase provider to create a resource dynamically.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="condition-property"></a>
<!-- :::item name="condition"::: -->
:::moniker range="<=azure-pipelines"

**`condition`** string.<br><!-- :::editable-content name="propDescription"::: -->
Evaluate this condition expression to determine whether to run this task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="continueOnError-property"></a>
<!-- :::item name="continueOnError"::: -->
:::moniker range="<=azure-pipelines"

**`continueOnError`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="displayName-property"></a>
<!-- :::item name="displayName"::: -->
:::moniker range="<=azure-pipelines"

**`displayName`** string.<br><!-- :::editable-content name="propDescription"::: -->
Human-readable name for the task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="target-property"></a>
<!-- :::item name="target"::: -->
:::moniker range="<=azure-pipelines"

**`target`** [target](target.md).<br><!-- :::editable-content name="propDescription"::: -->
Environment in which to run this task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="enabled-property"></a>
<!-- :::item name="enabled"::: -->
:::moniker range="<=azure-pipelines"

**`enabled`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Run this task when the job runs?
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="env-property"></a>
<!-- :::item name="env"::: -->
:::moniker range="<=azure-pipelines"

**`env`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Variables to map into the process's environment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="name-property"></a>
<!-- :::item name="name"::: -->
:::moniker range="<=azure-pipelines"

**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
ID of the step. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="timeoutInMinutes-property"></a>
<!-- :::item name="timeoutInMinutes"::: -->
:::moniker range="<=azure-pipelines"

**`timeoutInMinutes`** string.<br><!-- :::editable-content name="propDescription"::: -->
Time to wait for this task to complete before the server kills it.

[!INCLUDE [task-timeout](./includes/task-timeout.md)]
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<a name="retryCountOnTaskFailure-property"></a>
<!-- :::item name="retryCountOnTaskFailure"::: -->
:::moniker range="<=azure-pipelines"

**`retryCountOnTaskFailure`** string.<br><!-- :::editable-content name="propDescription"::: -->
Number of retries if the task fails.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

The `reviewApp` keyword is a shortcut for the [Review App task](/azure/devops/pipelines/tasks/reference/review-app-v0).

`ReviewApp` deploys every pull request from your Git repository to a dynamic environment resource. Reviewers can see how those changes look as well as work with other dependent services before they’re merged into the main branch and deployed to production. This will make it easy for you to create and manage **reviewApp** resources and benefit from all the traceability and diagnosis capability of the environment features. By using the **reviewApp** keyword, you can create a clone of a resource (dynamically create a new resource based on an existing resource in an environment) and add the new resource to the environment.

For more information, see [Kubernetes resource - Set up Review App](/azure/devops/pipelines/process/environments-kubernetes#set-up-review-app) and [What’s new in Azure DevOps Sprint 160](https://devblogs.microsoft.com/devops/whats-new-in-azure-devops-sprint-160/).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

The following is a sample YAML snippet of using reviewApp under environments.

```yaml
jobs:
- deployment:
  environment: 
     name: smarthotel-dev      
     resourceName: $(System.PullRequest.PullRequestId) 
  pool:
    name: 'ubuntu-latest'
  strategy:                 
    runOnce:            
      pre-deploy: 
        steps:       
        - reviewApp: MainNamespace
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Review App task](/azure/devops/pipelines/tasks/reference/review-app-v0)
- [What’s new in Azure DevOps Sprint 160](https://devblogs.microsoft.com/devops/whats-new-in-azure-devops-sprint-160/)
- [Kubernetes resource - Set up Review App](/azure/devops/pipelines/process/environments-kubernetes#set-up-review-app)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->