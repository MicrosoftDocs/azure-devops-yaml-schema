---
title: DeployVisualStudioTestAgent@1 - Visual Studio Test Agent Deployment v1 task
description: Deploy and configure Test Agent to run tests on a set of machines.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# DeployVisualStudioTestAgent@1 - Visual Studio Test Agent Deployment v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Deploy and configure Test Agent to run tests on a set of machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019"

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
    #resourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Select Machines By. Default: 'machineNames'.
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

<!-- :::item name="testMachineGroup"::: -->
:::moniker range="<=azure-pipelines"

**`testMachineGroup`** - **Machines**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a comma separated list of machine IP addresses or FQDNs along with ports. Port is defaulted based on the selected protocol. Eg: `dbserver.fabrikam.com,dbserver_int.fabrikam.com:5986,192.168.12.34:5986` Or provide output variable of other tasks. Eg: `$(variableName)` Or provide a Machine Group Name.` If you are using HTTPS, name/IP of machine should match the CN in the certificate.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="adminUserName"::: -->
:::moniker range="<=azure-pipelines"

**`adminUserName`** - **Admin Login**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator login for the target machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="adminPassword"::: -->
:::moniker range="<=azure-pipelines"

**`adminPassword`** - **Admin Password**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator password for the target machines. <br>It can accept variable defined in Build/Release definitions as `$(passwordVariable)`. <br>You may mark variable type as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="winRmProtocol"::: -->
:::moniker range="<=azure-pipelines"

**`winRmProtocol`** - **Protocol**<br>
Type: string. Allowed values: 'Http', 'Https'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the protocol to use for the WinRM connection with the machine(s). Default is `HTTPS`.
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
<!-- :::item name="resourceFilteringMethod"::: -->
:::moniker range="<=azure-pipelines"

**`resourceFilteringMethod`** - **Select Machines By**<br>
Type: string. Allowed values: 'machineNames', 'tags'. Default value: 'machineNames'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="testMachines"::: -->
:::moniker range="<=azure-pipelines"

**`testMachines`** - **Filter Criteria**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a list of machines like `dbserver.fabrikam.com, dbserver_int.fabrikam.com, 192.168.12.34 or tags like Role:DB;OS:Win8.1`. Returns machines with either of the tags. For Azure Resource Group provide the VM Host Name for the machine name. The default is to deploy agent on all machines represented in the Machines field.
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

**`runAsProcess`** - **Interactive Process**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Denotes if test agent needs to run as an interactive process, needed for Coded UI Tests.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="agentLocation"::: -->
:::moniker range="<=azure-pipelines"

**`agentLocation`** - **Test Agent Location**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally supply the path to vstf_testagent.exe from network or local location. If no path is provided, it will be downloaded from `https://go.microsoft.com/fwlink/?LinkId=827840`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="updateTestAgent"::: -->
:::moniker range="<=azure-pipelines"

**`updateTestAgent`** - **Update Test Agent**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally specify if test agent needs to be updated.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isDataCollectionOnly"::: -->
:::moniker range="<=azure-pipelines"

**`isDataCollectionOnly`** - **Enable Data Collection Only**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Optionally specify if test agent needs to be used only for datacollection and not for running tests. Typically done on application under test(AUT) machine group.
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

:::moniker range=">=azure-pipelines-2019"

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

:::moniker range="=azure-pipelines-2018"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | All |
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