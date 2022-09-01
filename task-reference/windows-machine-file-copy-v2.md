---
title: WindowsMachineFileCopy@2 - Windows machine file copy v2 task
description: Copy files to remote Windows machines.
ms.date: 09/01/2022
monikerRange: "<=azure-pipelines"
---

# WindowsMachineFileCopy@2 - Windows machine file copy v2 task

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

:::moniker range=">=azure-pipelines-2022"

```yaml
# Windows machine file copy v2
# Copy files to remote Windows machines.
- task: WindowsMachineFileCopy@2
  inputs:
    SourcePath: # string. Required. Source. 
    MachineNames: # string. Required. Machines. 
    AdminUserName: # string. Required. Admin Login. 
    AdminPassword: # string. Required. Password. 
    TargetPath: # string. Required. Destination Folder. 
  # Advanced Options
    #CleanTargetBeforeCopy: false # boolean. Clean Target. Default: false.
    #CopyFilesInParallel: true # boolean. Copy Files in Parallel. Default: true.
    #AdditionalArguments: # string. Additional Arguments.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

```yaml
# Windows machine file copy v2
# Copy files to remote Windows machines.
- task: WindowsMachineFileCopy@2
  inputs:
    SourcePath: # string. Required. Source. 
    #MachineNames: # string. Machines. 
    #AdminUserName: # string. Admin Login. 
    #AdminPassword: # string. Password. 
    TargetPath: # string. Required. Destination Folder. 
  # Advanced Options
    #CleanTargetBeforeCopy: false # boolean. Clean Target. Default: false.
    #CopyFilesInParallel: true # boolean. Copy Files in Parallel. Default: true.
    #AdditionalArguments: # string. Additional Arguments.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Windows Machine File Copy v2
# Copy files to remote machine(s).
- task: WindowsMachineFileCopy@2
  inputs:
    SourcePath: # string. Required. Source. 
    #MachineNames: # string. Machines. 
    #AdminUserName: # string. Admin Login. 
    #AdminPassword: # string. Password. 
    TargetPath: # string. Required. Destination Folder. 
  # Advanced Options
    #CleanTargetBeforeCopy: false # boolean. Clean Target. Default: false.
    #CopyFilesInParallel: true # boolean. Copy Files in Parallel. Default: true.
    #AdditionalArguments: # string. Additional Arguments.
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
<!-- :::item name="MachineNames"::: -->
:::moniker range=">=azure-pipelines-2022"

**`MachineNames`** - **Machines**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a comma separated list of machine IP addresses or FQDNs. <br>Eg: dbserver.fabrikam.com,192.168.12.34 <br>Or provide output variable of other tasks. Eg: $(variableName).
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

**`MachineNames`** - **Machines**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Provide a comma separated list of machine IP addresses or FQDNs. <br>Eg: dbserver.fabrikam.com,192.168.12.34 <br>Or provide output variable of other tasks. Eg: $(variableName).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminUserName"::: -->
:::moniker range=">=azure-pipelines-2022"

**`AdminUserName`** - **Admin Login**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator login for the target machines.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

**`AdminUserName`** - **Admin Login**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Administrator login for the target machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminPassword"::: -->
:::moniker range=">=azure-pipelines-2022"

**`AdminPassword`** - **Password**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password for administrator login for the target machines. <br>It can accept a variable defined in build or release pipelines as '$(passwordVariable)'. <br>You may mark the variable as 'secret' to secure it.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

**`AdminPassword`** - **Password**<br>
Type: string.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Password for administrator login for the target machines. <br>It can accept a variable defined in build or release pipelines as '$(passwordVariable)'. <br>You may mark the variable as 'secret' to secure it.
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

What's new in Version 2.0.
* Proxy support is being added.
* Removed support of legacy DTL machines.
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
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->