---
title: DeployVisualStudioTestAgent@2 - Visual Studio test agent deployment v2 task
description: DeployVisualStudioTestAgent@2 is deprecated. Use the Visual Studio Test task to run unit and functional tests.
ms.date: 01/27/2026
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022"
---

# DeployVisualStudioTestAgent@2 - Visual Studio test agent deployment v2 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
> [!IMPORTANT]
> [!INCLUDE [task-deprecation](includes/task-deprecation.md)] Use the [Visual Studio Test task](./vstest-v2.md) to run unit and functional tests.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end

:::moniker range="<=azure-pipelines-2022.2"

<!-- :::editable-content name="description"::: -->
> [!IMPORTANT]
> DeployVisualStudioTestAgent@2 is deprecated. Use the [Visual Studio Test task](./vstest-v2.md) to run unit and functional tests.
<!-- :::editable-content-end::: -->

<!-- This task is deprecated. -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

```yaml
# Visual Studio test agent deployment v2
# DeployVisualStudioTestAgent@2 is deprecated. Use the Visual Studio Test task to run unit and functional tests.
- task: DeployVisualStudioTestAgent@2
  inputs:
  # Test Machines
    testMachines: # string. Required. Machines. 
    adminUserName: # string. Required. Admin login. 
    adminPassword: # string. Required. Admin password. 
    winRmProtocol: 'Http' # 'Http' | 'Https'. Required. Protocol. Default: Http.
    #testCertificate: true # boolean. Optional. Use when winRmProtocol = Https. Test Certificate. Default: true.
  # Agent Configuration
    machineUserName: # string. Required. Username. 
    machinePassword: # string. Required. Password. 
    #runAsProcess: false # boolean. Run UI tests. Default: false.
    #isDataCollectionOnly: false # boolean. Enable data collection only. Default: false.
  # Advanced
    #testPlatform: '14.0' # '15.0' | '14.0'. Test agent version. Default: 14.0.
    #agentLocation: # string. Test agent location. 
    #updateTestAgent: false # boolean. Update test agent. Default: false.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="testMachines"::: -->
:::moniker range="<=azure-pipelines"

**`testMachines`** - **Machines**<br>
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

**`adminUserName`** - **Admin login**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the administrator login for the target machines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="adminPassword"::: -->
:::moniker range="<=azure-pipelines"

**`adminPassword`** - **Admin password**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the administrator password for the target machines. This input can accept a variable defined in build/release definitions as `$(passwordVariable)`. You may mark the variable type as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="winRmProtocol"::: -->
:::moniker range="<=azure-pipelines"

**`winRmProtocol`** - **Protocol**<br>
`string`. Required. Allowed values: `Http`, `Https`. Default value: `Http`.<br>
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
<!-- :::item name="machineUserName"::: -->
:::moniker range="<=azure-pipelines"

**`machineUserName`** - **Username**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the username with which test agent needs to run.
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

**`runAsProcess`** - **Run UI tests**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Denotes if the test agent needs to run as an interactive process. This input is needed for Coded UI Tests.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isDataCollectionOnly"::: -->
:::moniker range="<=azure-pipelines"

**`isDataCollectionOnly`** - **Enable data collection only**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Specifies if the test agent is used only for data collection and not for running tests. This can typically be found on the application under the test (AUT) machine group.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testPlatform"::: -->
:::moniker range="<=azure-pipelines"

**`testPlatform`** - **Test agent version**<br>
`string`. Allowed values: `15.0` (Visual Studio 2017), `14.0` (Visual Studio 2015). Default value: `14.0`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the version of Visual Studio test agent. Chooses an appropriate version to match the VS version using the test binaries that were built.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="agentLocation"::: -->
:::moniker range="<=azure-pipelines"

**`agentLocation`** - **Test agent location**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optional. Supplies the path to vstf_testagent.exe from the network or local location. If no path is provided, it will be automatically downloaded from the [download center](https://go.microsoft.com/fwlink/?LinkId=827840). [Install the Test Agent 2015 Update 3](https://go.microsoft.com/fwlink/?LinkId=827840).  
[Install Test Agent 2017](https://aka.ms/vs/15/release/vs_TestAgent.exe).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="updateTestAgent"::: -->
:::moniker range="<=azure-pipelines"

**`updateTestAgent`** - **Update test agent**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If the Test Agent is already deployed on a machine, this option checks to see if an update is available for that version.
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

What's new in this task version:

* Support for Visual Studio Test Agent 2017: You can now deploy and run tests using multiple versions of Visual Studio Test Agent. Versions 2015 and 2017 are supported.
* Machine groups created from the test hub are no longer supported. You can continue to use a list of machines or Azure resource groups.
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
| Runs on | Agent |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version |  2.0.0 or greater |
| Task category | Test |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
