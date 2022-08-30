---
title: DeployVisualStudioTestAgent@2 - Visual Studio test agent deployment v2 task
description: DeployVisualStudioTestAgent@2 is deprecated. Use the Visual Studio Test task to run unit and functional tests.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# DeployVisualStudioTestAgent@2 - Visual Studio test agent deployment v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
DeployVisualStudioTestAgent@2 is deprecated. Use the Visual Studio Test task to run unit and functional tests.
<!-- :::editable-content-end::: -->

This task is deprecated.

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Visual Studio test agent deployment v2
# DeployVisualStudioTestAgent@2 is deprecated. Use the Visual Studio Test task to run unit and functional tests.
- task: DeployVisualStudioTestAgent@2
  inputs:
  # Test Machines
    testMachines: # string. Required. Machines. 
    adminUserName: # string. Required. Admin login. 
    adminPassword: # string. Required. Admin password. 
    winRmProtocol: 'Http' # 'Http' | 'Https'. Required. Protocol. Default: 'Http'.
    #testCertificate: true # boolean. Optional. Use when winRmProtocol = Https. Test Certificate. Default: true.
  # Agent Configuration
    machineUserName: # string. Required. Username. 
    machinePassword: # string. Required. Password. 
    #runAsProcess: false # boolean. Run UI tests. Default: false.
    #isDataCollectionOnly: false # boolean. Enable data collection only. Default: false.
  # Advanced
    #testPlatform: '14.0' # '15.0' | '14.0'. Test agent version. Default: '14.0'.
    #agentLocation: # string. Test agent location. 
    #updateTestAgent: false # boolean. Update test agent. Default: false.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Visual Studio Test Agent Deployment v2
# DeployVisualStudioTestAgent@2 is deprecated. Use the Visual Studio Test task to run unit and functional tests.
- task: DeployVisualStudioTestAgent@2
  inputs:
  # Test Machines
    testMachines: # string. Required. Machines. 
    adminUserName: # string. Required. Admin login. 
    adminPassword: # string. Required. Admin password. 
    winRmProtocol: 'Http' # 'Http' | 'Https'. Required. Protocol. Default: 'Http'.
    #testCertificate: true # boolean. Optional. Use when winRmProtocol = Https. Test Certificate. Default: true.
  # Agent Configuration
    machineUserName: # string. Required. Username. 
    machinePassword: # string. Required. Password. 
    #runAsProcess: false # boolean. Run UI tests. Default: false.
    #isDataCollectionOnly: false # boolean. Enable data collection only. Default: false.
  # Advanced
    #testPlatform: '14.0' # '15.0' | '14.0'. Test agent version. Default: '14.0'.
    #agentLocation: # string. Test agent location. 
    #updateTestAgent: false # boolean. Update test agent. Default: false.
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

<!-- :::item name="testMachines"::: -->
:::moniker range="<=azure-pipelines"

**`testMachines`** - **Machines**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a comma separated list of machine IP addresses or FQDNs along with ports. Port is defaulted based on the selected protocol. Eg: `dbserver.fabrikam.com,dbserver_int.fabrikam.com:5986,192.168.12.34:5986` Or provide output variable of other tasks. Eg: `$(variableName)`. If you are using HTTPS, name/IP of machine should match the CN in the certificate.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="adminUserName"::: -->
:::moniker range="<=azure-pipelines"

**`adminUserName`** - **Admin login**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator login for the target machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="adminPassword"::: -->
:::moniker range="<=azure-pipelines"

**`adminPassword`** - **Admin password**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator password for the target machines. <br>It can accept variable defined in build or release pipelines as `$(passwordVariable)`. <br>You may mark a variable as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="winRmProtocol"::: -->
:::moniker range="<=azure-pipelines"

**`winRmProtocol`** - **Protocol**<br>
Type: string. Required. Allowed values: 'Http', 'Https'. Default value: 'Http'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the protocol to use for the WinRM service connection with the machine(s). Default is `HTTP`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testCertificate"::: -->
:::moniker range="<=azure-pipelines"

**`testCertificate`** - **Test Certificate**<br>
Type: boolean. Optional. Use when winRmProtocol = Https. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the option to skip validating the authenticity of the machine's certificate by a trusted certification authority. The parameter is required for the WinRM HTTPS protocol.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="machineUserName"::: -->
:::moniker range="<=azure-pipelines"

**`machineUserName`** - **Username**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Username with which test agent needs to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="machinePassword"::: -->
:::moniker range="<=azure-pipelines"

**`machinePassword`** - **Password**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password for the username given above.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="runAsProcess"::: -->
:::moniker range="<=azure-pipelines"

**`runAsProcess`** - **Run UI tests**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Denotes if test agent needs to run as an interactive process, needed for Coded UI Tests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isDataCollectionOnly"::: -->
:::moniker range="<=azure-pipelines"

**`isDataCollectionOnly`** - **Enable data collection only**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally specify if test agent needs to be used only for data collection and not for running tests. Typically done on application under test(AUT) machine group.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testPlatform"::: -->
:::moniker range="<=azure-pipelines"

**`testPlatform`** - **Test agent version**<br>
Type: string. Allowed values: '15.0', '14.0'. Default value: '14.0'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The version of Visual Studio test agent to use. Pick an appropriate version to match the VS version using which test binaries were built.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="agentLocation"::: -->
:::moniker range="<=azure-pipelines"

**`agentLocation`** - **Test agent location**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the path to vstf_testagent.exe from network or local location. If no path is provided, it will be automatically downloaded from the Download Center. Installer for Test Agent 2015 Update 3 from `https://go.microsoft.com/fwlink/?LinkId=827840`. Installer for Test Agent 2017 from `https://aka.ms/vs/15/release/vs_TestAgent.exe`. Refer to `https://aka.ms/testagentlocation` for details on how to use offline installers.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="updateTestAgent"::: -->
:::moniker range="<=azure-pipelines"

**`updateTestAgent`** - **Update test agent**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If Test Agent is already deployed on a machine, this option checks to see if an update is available for that version of the Test Agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
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

What's new in this task version.

* Support for Visual Studio Test Agent 2017: You can now deploy and run tests using multiple versions of Visual Studio Test Agent. Versions 2015 and 2017 are supported.
* Machine groups created from the Test hub are no longer supported. You can continue to use a list of machines or Azure resource groups.
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