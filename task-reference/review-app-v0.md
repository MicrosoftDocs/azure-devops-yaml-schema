---
title: ReviewApp@0 - Review App v0 task
description: Use this task under deploy phase provider to create a resource dynamically.
ms.date: 05/06/2025
monikerRange: "<=azure-pipelines"
---

# ReviewApp@0 - Review App v0 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
`ReviewApp` deploys every pull request from your Git repository to a dynamic environment resource.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Review App v0
# Use this task under deploy phase provider to create a resource dynamically.
- task: ReviewApp@0
  inputs:
    resourceName: # string. Required. Resource name. 
    #baseEnvironmentName: # string. Environment name. 
    #reviewResourceName: # string. Review Resource Name.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="resourceName"::: -->
:::moniker range="<=azure-pipelines"

**`resourceName`** - **Resource name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the name of an existing resource in the environment, which will be used for resource-type information.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="baseEnvironmentName"::: -->
:::moniker range="<=azure-pipelines"

**`baseEnvironmentName`** - **Environment name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="reviewResourceName"::: -->
:::moniker range="<=azure-pipelines"

**`reviewResourceName`** - **Review Resource Name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
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

`ReviewApp` deploys every pull request from your Git repository to a dynamic environment resource. Reviewers can see how those changes look as well as work with other dependent services before they’re merged into the main branch and deployed to production. This will make it easy for you to create and manage **reviewApp** resources and benefit from all the traceability and diagnosis capability of the environment features. By using the **reviewApp** keyword, you can create a clone of a resource (dynamically create a new resource based on an existing resource in an environment) and add the new resource to the environment.

For more information, see [Kubernetes resource - Set up Review App](/azure/devops/pipelines/process/environments-kubernetes#set-up-review-app) and [What’s new in Azure DevOps Sprint 160](https://devblogs.microsoft.com/devops/whats-new-in-azure-devops-sprint-160/).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

The following is a sample YAML snippet of using `reviewApp` under environments.

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

<!-- :::properties::: -->
## Requirements

:::moniker range="<=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build |
| Runs on | Agent, DeploymentGroup |
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

- [What’s new in Azure DevOps Sprint 160](https://devblogs.microsoft.com/devops/whats-new-in-azure-devops-sprint-160/)
- [Kubernetes resource - Set up Review App](/azure/devops/pipelines/process/environments-kubernetes#set-up-review-app)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->