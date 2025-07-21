---
title: DeployVisualStudioTestAgent@1 - Visual Studio Test Agent Deployment v1 task
description: Deploy and configure Test Agent to run tests on a set of machines.
ms.date: 07/21/2025
monikerRange: "<=azure-pipelines"
---

# DeployVisualStudioTestAgent@1 - Visual Studio Test Agent Deployment v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
This task deploys and configures the Test Agent to run tests on a set of machines.

> [!IMPORTANT]
> This task is deprecated. Use the [Visual Studio Test task](./vstest-v2.md) to run unit and functional tests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Visual Studio Test Agent Deployment v1
# Deploy and configure Test Agent to run tests on a set of machines.
- task: DeployVisualStudioTestAgent@1
  inputs:
  # Test Machine Group
    testMachineGroup: # string. Required. Machines. 
    #adminUserName: # string. Admin Login. 
    #adminPassword: # string. Admin Password. 
    #winRmProtocol: # 'Http' | 'Https'. Protocol. 
    #testCertificate: true # boolean. Optional. Use when winRmProtocol = Https. Test Certificate. Default: true.
    #resourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Select Machines By. Default: machineNames.
    #testMachines: # string. Filter Criteria. 
  # Agent Configuration
    machineUserName: # string. Required. Username. 
    machinePassword: # string. Required. Password. 
    #runAsProcess: false # boolean. Interactive Process. Default: false.
  # Advanced
    #agentLocation: # string. Test Agent Location. 
    #updateTestAgent: true # boolean. Update Test Agent. Default: true.
    #isDataCollectionOnly: false # boolean. Enable Data Collection Only. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="testMachineGroup"::: -->
:::moniker range="<=azure-pipelines"

**`testMachineGroup`** - **Machines**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This input has three options:
* Provides a comma separated list of machine IP addresses or FQDNs along with ports. The default port is based on the selected protocol. For example, `dbserver.fabrikam.com,dbserver_int.fabrikam.com:5986,192.168.12.34:5986`.
* Provides the output variable of other tasks. For example, `$(variableName)`.
* Provides a machine group name. If you are using HTTPS, the name/IP of the machine should match the CN on the certificate.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="adminUserName"::: -->
:::moniker range="<=azure-pipelines"

**`adminUserName`** - **Admin Login**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the administrator login for the target machines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="adminPassword"::: -->
:::moniker range="<=azure-pipelines"

**`adminPassword`** - **Admin Password**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the administrator password for the target machines. This input can accept a variable defined in build/release definitions as `$(passwordVariable)`. You may mark the variable type as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="winRmProtocol"::: -->
:::moniker range="<=azure-pipelines"

**`winRmProtocol`** - **Protocol**<br>
`string`. Allowed values: `Http`, `Https`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the protocol to use for the WinRM connection with the machine(s). The default value is `HTTPS`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testCertificate"::: -->
:::moniker range="<=azure-pipelines"

**`testCertificate`** - **Test Certificate**<br>
`boolean`. Optional. Use when `winRmProtocol = Https`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides the option to skip the authenticity validation of the machine's certificate by a trusted certification authority. The parameter is required for the WinRM HTTPS protocol.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resourceFilteringMethod"::: -->
:::moniker range="<=azure-pipelines"

**`resourceFilteringMethod`** - **Select Machines By**<br>
`string`. Allowed values: `machineNames` (Machine Names), `tags`. Default value: `machineNames`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testMachines"::: -->
:::moniker range="<=azure-pipelines"

**`testMachines`** - **Filter Criteria**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provides a list of machines like `dbserver.fabrikam.com, dbserver_int.fabrikam.com, 192.168.12.34` or tags like `Role:DB;OS:Win8.1`. Returns machines that have either of the tags. For Azure Resource Group, provide the VM host name for the machine name. The default deploys an agent on all machines represented in the Machines field.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="machineUserName"::: -->
:::moniker range="<=azure-pipelines"

**`machineUserName`** - **Username**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the username with which the test agent needs to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="machinePassword"::: -->
:::moniker range="<=azure-pipelines"

**`machinePassword`** - **Password**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the username given above.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runAsProcess"::: -->
:::moniker range="<=azure-pipelines"

**`runAsProcess`** - **Interactive Process**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Denotes if the test agent needs to run as an interactive process. This input is needed for Coded UI Tests.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="agentLocation"::: -->
:::moniker range="<=azure-pipelines"

**`agentLocation`** - **Test Agent Location**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Supplies the path to vstf_testagent.exe from the network or local location. If no path is provided, it will be downloaded from [the download center](https://go.microsoft.com/fwlink/?LinkId=827840).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="updateTestAgent"::: -->
:::moniker range="<=azure-pipelines"

**`updateTestAgent`** - **Update Test Agent**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies if the test agent needs to be updated.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isDataCollectionOnly"::: -->
:::moniker range="<=azure-pipelines"

**`isDataCollectionOnly`** - **Enable Data Collection Only**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies if the test agent is used only for data collection and not for running tests. This can typically be found on the application under the test (AUT) machine group.
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
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  1.104.0 or greater |
| Task category | Test |

:::moniker-end

<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
