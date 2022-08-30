---
title: WindowsMachineFileCopy@1 - Windows machine file copy v1 task
description: Copy files to remote Windows machines (task version 1).
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# WindowsMachineFileCopy@1 - Windows machine file copy v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Copy files to remote Windows machines.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Copy files to remote machine(s).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# Windows machine file copy v1
# Copy files to remote Windows machines.
- task: WindowsMachineFileCopy@1
  inputs:
    SourcePath: # string. Required. Source. 
    #EnvironmentName: # string. Machines. 
    #AdminUserName: # string. Admin Login. 
    #AdminPassword: # string. Password. 
    TargetPath: # string. Required. Destination Folder. 
  # Advanced Options
    #CleanTargetBeforeCopy: false # boolean. Clean Target. Default: false.
    #CopyFilesInParallel: true # boolean. Copy Files in Parallel. Default: true.
    #AdditionalArguments: # string. Additional Arguments. 
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Select Machines By. Default: 'machineNames'.
    #MachineNames: # string. Filter Criteria.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Windows Machine File Copy v1
# Copy files to remote machine(s).
- task: WindowsMachineFileCopy@1
  inputs:
    SourcePath: # string. Required. Source. 
    #EnvironmentName: # string. Machines. 
    #AdminUserName: # string. Admin Login. 
    #AdminPassword: # string. Password. 
    TargetPath: # string. Required. Destination Folder. 
  # Advanced Options
    #CleanTargetBeforeCopy: false # boolean. Clean Target. Default: false.
    #CopyFilesInParallel: true # boolean. Copy Files in Parallel. Default: true.
    #AdditionalArguments: # string. Additional Arguments. 
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Select Machines By. Default: 'machineNames'.
    #MachineNames: # string. Filter Criteria.
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

<!-- :::item name="SourcePath"::: -->
:::moniker range="<=azure-pipelines"

**`SourcePath`** - **Source**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Absolute path of the source folder or file on the local machine, or a UNC Share like c:\fabrikamfiber or \\\\fabrikamshare\fabrikamfiber.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="EnvironmentName"::: -->
:::moniker range="<=azure-pipelines"

**`EnvironmentName`** - **Machines**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a comma separated list of machine IP addresses or FQDNs. <br>Eg: dbserver.fabrikam.com,192.168.12.34 <br>Or provide output variable of other tasks. Eg: $(variableName).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminUserName"::: -->
:::moniker range="<=azure-pipelines"

**`AdminUserName`** - **Admin Login**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator login for the target machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminPassword"::: -->
:::moniker range="<=azure-pipelines"

**`AdminPassword`** - **Password**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password for administrator login for the target machines. <br>It can accept variable defined in Build/Release definitions as '$(passwordVariable)'. <br>You may mark variable type as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetPath"::: -->
:::moniker range="<=azure-pipelines"

**`TargetPath`** - **Destination Folder**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Local Path on the target machines or an accessible UNC path for copying the files from the source like d:\fabrikam or \\\\fabrikam\Web.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CleanTargetBeforeCopy"::: -->
:::moniker range="<=azure-pipelines"

**`CleanTargetBeforeCopy`** - **Clean Target**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selecting it will clean the destination folder before copying the files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CopyFilesInParallel"::: -->
:::moniker range="<=azure-pipelines"

**`CopyFilesInParallel`** - **Copy Files in Parallel**<br>
Type: boolean. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Selecting it will copy files in parallel to the machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`AdditionalArguments`** - **Additional Arguments**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Additional robocopy arguments that will be applied when copying files like, /min:33553332 /l.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceFilteringMethod"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceFilteringMethod`** - **Select Machines By**<br>
Type: string. Allowed values: 'machineNames', 'tags'. Default value: 'machineNames'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MachineNames"::: -->
:::moniker range="<=azure-pipelines"

**`MachineNames`** - **Filter Criteria**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This input is valid only for machine groups and is not supported for flat list of machines or output variables yet. Provide a list of machines like, dbserver.fabrikam.com, webserver.fabrikam.com, 192.168.12.34, or tags like, Role:DB; OS:Win8.1. If multiple tags are provided, then the task will run in all the machines with the specified tags. The default is to run the task in all machines.
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
| Task category | Deploy |

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
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->