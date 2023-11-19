---
title: WindowsMachineFileCopy@2 - Windows machine file copy v2 task
description: Copy files to remote Windows machines.
ms.date: 11/17/2023
monikerRange: "<=azure-pipelines"
---

# WindowsMachineFileCopy@2 - Windows machine file copy v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to copy files to remote Windows machines.
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
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The path to the files to copy. Specifies the absolute path of the source folder or file on the local machine or a UNC Share, like `c:\fabrikamfiber` or `\\fabrikamshare\fabrikamfiber`. You can use predefined system variables, such as `$(Build.Repository.LocalPath)` (the working folder on the agent computer), which makes it easy to specify the location of the build artifacts on the computer that hosts the automation agent.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MachineNames"::: -->
:::moniker range=">=azure-pipelines-2022"

**`MachineNames`** - **Machines**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a comma-separated list of machine IP addresses or FQDNs, optionally including the port number.  
For example: `dbserver.fabrikam.com, dbserver_int.fabrikam.com:5986, 192.168.12.34` You can also specify the output variable of other tasks, for example `$(variableName)`, or you can use the name of an [Azure Resource Group](/azure/azure-resource-manager/management/overview).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

**`MachineNames`** - **Machines**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a comma-separated list of machine IP addresses or FQDNs, optionally including the port number. For example: `dbserver.fabrikam.com, dbserver_int.fabrikam.com:5986, 192.168.12.34`. You can also specify the output variable of other tasks, for example `$(variableName)`, or you can use the name of an [Azure Resource Group](/azure/azure-resource-manager/management/overview).
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminUserName"::: -->
:::moniker range=">=azure-pipelines-2022"

**`AdminUserName`** - **Admin Login**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the username of a domain or a local administrative account on the target host(s). Formats such as **domain\username**, **username**, and **machine-name\username** are supported. UPN formats, such as `username@domain.com`, and built-in system accounts, such as **NT Authority\System**, are not supported.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

**`AdminUserName`** - **Admin Login**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the username of a domain or a local administrative account on the target host(s). Formats such as **domain\username**, **username**, and **machine-name\username** are supported. UPN formats, such as `username@domain.com`, and built-in system accounts, such as **NT Authority\System**, are not supported.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminPassword"::: -->
:::moniker range=">=azure-pipelines-2022"

**`AdminPassword`** - **Password**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the administrator login for the target machines. Variables defined in build or release pipelines, such as `$(passwordVariable)`, are accepted. You can mark the variable as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

**`AdminPassword`** - **Password**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the administrator login for the target machines. Variables defined in build or release pipelines, such as `$(passwordVariable)`, are accepted. You can mark the variable as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetPath"::: -->
:::moniker range="<=azure-pipelines"

**`TargetPath`** - **Destination Folder**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the local path on the target machines or an accessible UNC path for copying the files from the source, like `d:\fabrikam` or `\\fabrikam\Web`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CleanTargetBeforeCopy"::: -->
:::moniker range="<=azure-pipelines"

**`CleanTargetBeforeCopy`** - **Clean Target**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Deletes all files in the target folder before copying the new files to it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CopyFilesInParallel"::: -->
:::moniker range="<=azure-pipelines"

**`CopyFilesInParallel`** - **Copy Files in Parallel**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Copies files to all target machines in parallel, which can speed up the copying process.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`AdditionalArguments`** - **Additional Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional RoboCopy arguments that are applied when copying files, like `/min:33553332 /l`.
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

Use this task to copy application files and other artifacts, such as PowerShell scripts and PowerShell-DSC modules, which are required to install the application on Windows machines. It uses RoboCopy, the command-line utility built for fast copying of data.

### Why do I get a system error 53 when using this task?

Typically this occurs when the specified path cannot be located.
This may be due to a firewall blocking the necessary ports for file and printer sharing or an invalid path specification. For more details, see
[Error 53](/previous-versions/windows/it-pro/windows-2000-server/cc940100(v=technet.10)) on TechNet.

### What's new in Version 2.0

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