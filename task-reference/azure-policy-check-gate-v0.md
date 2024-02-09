---
title: AzurePolicyCheckGate@0 - Check Azure Policy compliance v0 task
description: Security and compliance assessment for Azure Policy.
ms.date: 02/09/2024
monikerRange: ">=azure-pipelines-2019.1"
---

# AzurePolicyCheckGate@0 - Check Azure Policy compliance v0 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to check the security and compliance assessment for Azure Policy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022.1"

```yaml
# Check Azure Policy compliance v0
# Security and compliance assessment for Azure Policy.
- task: AzurePolicyCheckGate@0
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    #ResourceGroupName: # string. Resource group. 
    #Resources: # string. Resource name. 
  # Advanced
    #RetryDuration: '00:02:00' # string. Retry duration. Default: 00:02:00.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2022"

```yaml
# Check Azure Policy compliance v0
# Security and compliance assessment for Azure Policy.
- task: AzurePolicyCheckGate@0
  inputs:
    azureSubscription: # string. Alias: ConnectedServiceName. Required. Azure subscription. 
    #ResourceGroupName: # string. Resource group. 
    #Resources: # string. Resource name.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `ConnectedServiceName`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the Azure Resource Manager subscription you want to use to enforce the policies.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceGroupName"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`ResourceGroupName`** - **Resource group**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides the resource group name.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Resources"::: -->
:::moniker range=">=azure-pipelines-2019.1"

**`Resources`** - **Resource name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects the name of Azure resources for which you want to check the policy compliance.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RetryDuration"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`RetryDuration`** - **Retry duration**<br>
`string`. Default value: `00:02:00`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The Check Azure Policy compliance task performs an asynchronous [On-demand evaluation scan](/azure/governance/policy/how-to/get-compliance-data#on-demand-evaluation-scan---rest) of your [compliance data of Azure resources](/azure/governance/policy/how-to/get-compliance-data). The call returns a **202 Accepted** status while the evaluation is ongoing. The `RetryDuration` input configures the intervals in which the task retries the REST API call to check for the completion of the policy evaluation. The format is **hours:minutes:seconds** in the following format: `hh:mm:ss`.

The default is `00:02:00` (two minutes), which is the minumum interval that may be configured.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019.1"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

[Azure Policy](/azure/governance/policy/) allows you to assess and enforce resource compliance against defined IT policies.
Use this task in a gate to identify, analyze and evaluate the security risks,
and determine the mitigation measures required to reduce the risks.

> [!NOTE]
> Can be used only as a [gate](/azure/devops/pipelines/release/approvals/gates). This task is not supported in a build or release pipeline.
>
> :::image type="content" source="media/gates.png" alt-text="Screenshot that shows using the task as a gate in a release pipeline.":::
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range=">=azure-pipelines-2019.1"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | Classic release |
| Runs on | ServerGate |
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