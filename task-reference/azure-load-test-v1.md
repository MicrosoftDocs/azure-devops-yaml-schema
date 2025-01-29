---
title: AzureLoadTest@1 - Azure Load Testing v1 task
description: Automate performance regression testing with Azure Load Testing.
ms.date: 01/29/2025
monikerRange: "=azure-pipelines"
---

# AzureLoadTest@1 - Azure Load Testing v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Automate performance regression testing with Azure Load Testing.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Azure Load Testing v1
# Automate performance regression testing with Azure Load Testing.
- task: AzureLoadTest@1
  inputs:
    azureSubscription: # string. Alias: connectedServiceNameARM. Required. Azure subscription. 
    loadTestConfigFile: # string. Required. Load Test File. 
    resourceGroup: # string. Required. Load Test Resource Group. 
    loadTestResource: # string. Required. Load Test Resource Name. 
    #loadTestRunName: # string. Load Test Run Name. 
    #loadTestRunDescription: # string. Load Test Run Description. 
    #secrets: # string. Secrets. 
    #env: # string. env.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="azureSubscription"::: -->
:::moniker range="=azure-pipelines"

**`azureSubscription`** - **Azure subscription**<br>
Input alias: `connectedServiceNameARM`. `string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selects an Azure Resource Manager subscription to run the load test.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="loadTestConfigFile"::: -->
:::moniker range="=azure-pipelines"

**`loadTestConfigFile`** - **Load Test File**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the load test YAML configuration file relative from the repo root.
See [Test configuration YAML reference](/azure/load-testing/reference-test-config-yaml). The path must be fully qualified or relative to the default working directory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceGroup"::: -->
:::moniker range="=azure-pipelines"

**`resourceGroup`** - **Load Test Resource Group**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters or selects the Azure Resource Group that contains the Load test resource.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="loadTestResource"::: -->
:::moniker range="=azure-pipelines"

**`loadTestResource`** - **Load Test Resource Name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Enters or selects the name of an existing Azure Load Testing resource.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="loadTestRunName"::: -->
:::moniker range="=azure-pipelines"

**`loadTestRunName`** - **Load Test Run Name**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Custom name for the load test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="loadTestRunDescription"::: -->
:::moniker range="=azure-pipelines"

**`loadTestRunDescription`** - **Load Test Run Description**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Custom description for the load test run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="secrets"::: -->
:::moniker range="=azure-pipelines"

**`secrets`** - **Secrets**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
An array of JSON objects that consist of the name and value for each secret. The name should match the secret name used in the Apache JMeter test script. Add or update the secret parameters using the json syntax as shown in the following example.

```json
[
   {
    "name": "key1",
    "value": $(secret1)
   },
   {
    "name": "key2",
    "value": $(secret2)
   }
]
```
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="env"::: -->
:::moniker range="=azure-pipelines"

**`env`** - **env**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
An array of JSON objects that consist of the name and value for each environment variable. The name should match the variable name used in the Apache JMeter test script. Add or update the environment variables using the JSON syntax as shown in the following example.

```json
[
   {
    "name": "env1",
    "value": "value1"
   },
   {
    "name": "env2",
    "value": "value2"
   }
]
```
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to run an Apache JMeter script by using Azure Load Testing. Azure Load Testing is a fully managed load testing service that enables you to generate high-scale load.

The task succeeds if the load test finishes successfully and all [test criteria](/azure/load-testing/how-to-define-test-criteria) pass.

Although Azure PowerShell isn't listed in the demands for `AzureLoadTest@1`, the agent must have Azure PowerShell installed. Azure PowerShell is installed on [Windows and Linux hosted agent images](/azure/devops/pipelines/agents/hosted#software).

> [!NOTE]
> `AzureLoadTest@1` is part of the Azure Load Testing marketplace extension. For more information on installing and using this task, see [Identify performance regressions with Azure Load Testing and Azure Pipelines](/azure/load-testing/tutorial-cicd-azure-pipelines).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

For an example using this task, see the Azure Load Testing documentation article [Continuous regression testing with Azure Pipelines](/azure/load-testing/tutorial-cicd-azure-pipelines).
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Azure Pipelines |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

For more information about using this task, see the Azure Load Testing documentation article [Continuous regression testing with Azure Pipelines](/azure/load-testing/tutorial-cicd-azure-pipelines).
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
