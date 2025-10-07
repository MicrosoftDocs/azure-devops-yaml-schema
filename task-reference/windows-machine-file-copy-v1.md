---
title: WindowsMachineFileCopy@1 - Windows machine file copy v1 task
description: Copy files to remote Windows machines (task version 1).
ms.date: 10/07/2025
monikerRange: "=azure-pipelines || =azure-pipelines-server || =azure-pipelines-2022.2 || =azure-pipelines-2022.1 || =azure-pipelines-2022 || =azure-pipelines-2020.1 || =azure-pipelines-2020"
author: ramiMSFT
ms.author: rabououn
---

# WindowsMachineFileCopy@1 - Windows machine file copy v1 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to copy files to remote Windows machines.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="<=azure-pipelines"

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
    #ResourceFilteringMethod: 'machineNames' # 'machineNames' | 'tags'. Select Machines By. Default: machineNames.
    #MachineNames: # string. Filter Criteria.
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
Specifies the absolute path of the source folder or file on the local machine or a UNC Share, like `c:\fabrikamfiber` or `\\fabrikamshare\fabrikamfiber`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="EnvironmentName"::: -->
:::moniker range="<=azure-pipelines"

**`EnvironmentName`** - **Machines**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a comma-separated list of machine IP addresses or FQDNs, for example, `dbserver.fabrikam.com,192.168.12.34`. You can also specify the output variable of other tasks, for example `$(variableName)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminUserName"::: -->
:::moniker range="<=azure-pipelines"

**`AdminUserName`** - **Admin Login**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the administrator login for the target machines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdminPassword"::: -->
:::moniker range="<=azure-pipelines"

**`AdminPassword`** - **Password**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the administrator login for the target machines. Variables defined in build/release definitions as `$(passwordVariable)` are accepted. You can mark the variable type as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="TargetPath"::: -->
:::moniker range="<=azure-pipelines"

**`TargetPath`** - **Destination Folder**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the local path on the target machine or an accessible UNC path for copying the files from the source, like `d:\fabrikam` or `\\fabrikam\Web`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CleanTargetBeforeCopy"::: -->
:::moniker range="<=azure-pipelines"

**`CleanTargetBeforeCopy`** - **Clean Target**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Cleans the destination folder before copying the files.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CopyFilesInParallel"::: -->
:::moniker range="<=azure-pipelines"

**`CopyFilesInParallel`** - **Copy Files in Parallel**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Copies files in parallel to the machines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AdditionalArguments"::: -->
:::moniker range="<=azure-pipelines"

**`AdditionalArguments`** - **Additional Arguments**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies additional robocopy arguments that are applied when copying files, like `/min:33553332 /l`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ResourceFilteringMethod"::: -->
:::moniker range="<=azure-pipelines"

**`ResourceFilteringMethod`** - **Select Machines By**<br>
`string`. Allowed values: `machineNames` (Machine Names), `tags`. Default value: `machineNames`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="MachineNames"::: -->
:::moniker range="<=azure-pipelines"

**`MachineNames`** - **Filter Criteria**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This input is only valid for machine groups and is not supported for a flat list of machines or output variables yet.

Specifies a comma-separated list of machines, like `dbserver.fabrikam.com, webserver.fabrikam.com, 192.168.12.34`, or tags, like `Role:DB; OS:Win8.1`. If multiple tags are provided, the task will run in all machines with the specified tags. The default runs the task in all machines.
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
| Task category | Deploy |

:::moniker-end

<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->