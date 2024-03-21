---
title: PowerShellOnTargetMachines@3 - PowerShell on target machines v3 task
description: Execute PowerShell scripts on remote machines using PSSession and Invoke-Command for remoting.
ms.date: 03/21/2024
monikerRange: ">=azure-pipelines-2019"
---

# PowerShellOnTargetMachines@3 - PowerShell on target machines v3 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019.1"

<!-- :::editable-content name="description"::: -->
Use this task to execute PowerShell scripts on remote machines using PSSession and Invoke-Command for remoting.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
Use this task to execute PowerShell scripts on remote machine(s). This version of the task uses PSSession and Invoke-Command for remoting.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2019.1"

```yaml
# PowerShell on target machines v3
# Execute PowerShell scripts on remote machines using PSSession and Invoke-Command for remoting.
- task: PowerShellOnTargetMachines@3
  inputs:
    Machines: # string. Required. Machines. 
    #UserName: # string. Username. 
    #UserPassword: # string. Password. 
  # Script options
    #ScriptType: 'Inline' # 'FilePath' | 'Inline'. Script Type. Default: Inline.
    #ScriptPath: # string. Required when ScriptType = FilePath. Script File Path. 
    InlineScript: # string. Required when ScriptType = Inline. Script. 
    #ScriptArguments: # string. Optional. Use when ScriptType = FilePath. Script Arguments. 
    #InitializationScript: # string. Optional. Use when ScriptType = FilePath. Initialization script. 
    #SessionVariables: # string. Optional. Use when ScriptType = FilePath. Session Variables. 
  # PSSession options
    #CommunicationProtocol: 'Https' # 'Http' | 'Https'. Protocol. Default: Https.
    #AuthenticationMechanism: 'Default' # 'Default' | 'Credssp'. Authentication. Default: Default.
    #NewPsSessionOptionArguments: '-SkipCACheck -IdleTimeout 7200000 -OperationTimeout 0 -OutputBufferingMode Block' # string. Session Option parameters. Default: -SkipCACheck -IdleTimeout 7200000 -OperationTimeout 0 -OutputBufferingMode Block.
  # Error handling options
    #ErrorActionPreference: 'stop' # 'stop' | 'continue' | 'silentlyContinue'. ErrorActionPreference. Default: stop.
    #failOnStderr: false # boolean. Fail on Standard Error. Default: false.
    #ignoreLASTEXITCODE: false # boolean. Ignore $LASTEXITCODE. Default: false.
  # Advanced
    #WorkingDirectory: # string. Working Directory. 
    #RunPowershellInParallel: true # boolean. Run PowerShell in Parallel. Default: true.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# PowerShell on Target Machines v3
# Execute PowerShell scripts on remote machine(s). This version of the task uses PSSession and Invoke-Command for remoting.
- task: PowerShellOnTargetMachines@3
  inputs:
    Machines: # string. Required. Machines. 
    #UserName: # string. Username. 
    #UserPassword: # string. Password. 
  # Script options
    #ScriptType: 'Inline' # 'FilePath' | 'Inline'. Script Type. Default: Inline.
    #ScriptPath: # string. Required when ScriptType = FilePath. Script File Path. 
    InlineScript: # string. Required when ScriptType = Inline. Script. 
    #ScriptArguments: # string. Optional. Use when ScriptType = FilePath. Script Arguments. 
    #InitializationScript: # string. Optional. Use when ScriptType = FilePath. Initialization script. 
    #SessionVariables: # string. Optional. Use when ScriptType = FilePath. Session Variables. 
  # PSSession options
    #CommunicationProtocol: 'Https' # 'Http' | 'Https'. Protocol. Default: Https.
    #AuthenticationMechanism: 'Default' # 'Default' | 'Credssp'. Authentication. Default: Default.
    #NewPsSessionOptionArguments: '-SkipCACheck -IdleTimeout 7200000 -OperationTimeout 0 -OutputBufferingMode Block' # string. Session Option parameters. Default: -SkipCACheck -IdleTimeout 7200000 -OperationTimeout 0 -OutputBufferingMode Block.
  # Error handling options
    #ErrorActionPreference: 'stop' # 'stop' | 'continue' | 'silentlyContinue'. ErrorActionPreference. Default: stop.
    #failOnStderr: false # boolean. Fail on Standard Error. Default: false.
    #ignoreLASTEXITCODE: false # boolean. Ignore $LASTEXITCODE. Default: false.
  # Advanced
    #WorkingDirectory: # string. Working Directory. 
    #RunPowershellInParallel: true # boolean. Run PowerShell in Parallel. Default: true.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="Machines"::: -->
:::moniker range=">=azure-pipelines-2019"

**`Machines`** - **Machines**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies a comma-separated list of machine FQDNs or IP addresses, and optionally includes the port number. Can be:

- The name of an [Azure Resource Group](/azure/azure-resource-manager/management/overview).
- A comma-delimited list of machine names. Example: `dbserver.fabrikam.com,dbserver_int.fabrikam.com:5986,192.168.34:5986`
- An output variable from a previous task.

If you do not specify a port, the default WinRM port is used. This depends on the protocol you have configured. For WinRM 2.0, the default HTTP port is `5985` and the default HTTPS port is `5986`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="UserName"::: -->
:::moniker range=">=azure-pipelines-2019"

**`UserName`** - **Username**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the username of a domain or a local administrative account on the target host(s).

- Formats such as `username`, `domain\username`, `machine-name\username`, and `.\username` are supported.
- UPN formats such as `username@domain.com` and built-in system accounts such as `NT Authority\System` are not supported.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="UserPassword"::: -->
:::moniker range=">=azure-pipelines-2019"

**`UserPassword`** - **Password**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the password for the target machines. Variables defined in build/release definitions as `$(passwordVariable)` are accepted. You may mark the variable type as `secret` to secure it.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptType"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ScriptType`** - **Script Type**<br>
`string`. Allowed values: `FilePath` (File Path), `Inline`. Default value: `Inline`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the type of script to execute: Inline or File Path.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptPath"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ScriptPath`** - **Script File Path**<br>
`string`. Required when `ScriptType = FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the PowerShell script on the target machines or on a UNC path, like `C:\BudgetIT\Web\Deploy\Website.ps1`, which should be accessible from the target machine.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="InlineScript"::: -->
:::moniker range=">=azure-pipelines-2019"

**`InlineScript`** - **Script**<br>
`string`. Required when `ScriptType = Inline`. Default value: `# Write your powershell commands here.\n\nWrite-Output "Hello World"`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ScriptArguments"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ScriptArguments`** - **Script Arguments**<br>
`string`. Optional. Use when `ScriptType = FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the arguments for the PowerShell script. Can be ordinal or named parameters, like `-testParam` test. For example: `-applicationPath $(applicationPath)`, `-username $(vmusername)`, `-password $(vmpassword)`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="InitializationScript"::: -->
:::moniker range=">=azure-pipelines-2019"

**`InitializationScript`** - **Initialization script**<br>
`string`. Optional. Use when `ScriptType = FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the location of the data script for the DSC on the target machines or on a UNC path, like `C:\BudgetIT\Web\Deploy\WebsiteConfiguration.ps1`. It's recommended to use arguments instead of an initialization script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="SessionVariables"::: -->
:::moniker range=">=azure-pipelines-2019"

**`SessionVariables`** - **Session Variables**<br>
`string`. Optional. Use when `ScriptType = FilePath`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Used to set up the session variables for the PowerShell scripts.  
Specifies a comma-separated list, such as `$varx=valuex, $vary=valuey`. Most commonly used for backward compatibility with earlier versions of the release service. It's recommended to use arguments instead of session variables.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="CommunicationProtocol"::: -->
:::moniker range=">=azure-pipelines-2019"

**`CommunicationProtocol`** - **Protocol**<br>
`string`. Allowed values: `Http`, `Https`. Default value: `Https`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the protocol to use for the WinRM service connection with the machine(s). The default value is `HTTPS`.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="AuthenticationMechanism"::: -->
:::moniker range=">=azure-pipelines-2019"

**`AuthenticationMechanism`** - **Authentication**<br>
`string`. Allowed values: `Default`, `Credssp`. Default value: `Default`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the authentication mechanism used for creating the PSSession. For `CredSSP` authentication, the username and password fields are mandatory.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="NewPsSessionOptionArguments"::: -->
:::moniker range=">=azure-pipelines-2019"

**`NewPsSessionOptionArguments`** - **Session Option parameters**<br>
`string`. Default value: `-SkipCACheck -IdleTimeout 7200000 -OperationTimeout 0 -OutputBufferingMode Block`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Advanced options for a remote session (New-PSSessionOption). For example, `-SkipCACheck`, `-SkipCNCheck`, `-SkipRevocationCheck`, etc. See a [complete list of all session options](https://aka.ms/Vsts_PS_TM_v3_NewPSSessionOptions) to learn more.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ErrorActionPreference"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ErrorActionPreference`** - **ErrorActionPreference**<br>
`string`. Allowed values: `stop`, `continue`, `silentlyContinue`. Default value: `stop`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Prepends the line `$ErrorActionPreference = 'VALUE'` at the top of your script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnStderr"::: -->
:::moniker range=">=azure-pipelines-2019"

**`failOnStderr`** - **Fail on Standard Error**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, fails if any errors are written to the error pipeline or if any data is written to the Standard Error stream. Otherwise, the task relies on the exit code to determine failure.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ignoreLASTEXITCODE"::: -->
:::moniker range=">=azure-pipelines-2019"

**`ignoreLASTEXITCODE`** - **Ignore $LASTEXITCODE**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `false`, the line `if ((Test-Path -LiteralPath variable:\LASTEXITCODE)) { exit $LASTEXITCODE }` is executed at the end of your script. This causes the last exit code from an external command to be propagated as the exit code of PowerShell. Otherwise, the line is not executed to the end of your script.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WorkingDirectory"::: -->
:::moniker range=">=azure-pipelines-2019"

**`WorkingDirectory`** - **Working Directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the working directory where the script is run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="RunPowershellInParallel"::: -->
:::moniker range=">=azure-pipelines-2019"

**`RunPowershellInParallel`** - **Run PowerShell in Parallel**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If set to `true`, runs the PowerShell scripts in parallel on the target machines.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-2019"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to execute PowerShell scripts on remote machine(s).

This task can run both PowerShell scripts and PowerShell-DSC scripts:

- For PowerShell scripts, the computers must have PowerShell 2.0 or higher installed.
- For PowerShell-DSC scripts, the computers must have [the latest version of the Windows Management Framework](https://www.microsoft.com/download/details.aspx?id=54616) installed. This is installed by default on Windows 8.1, Windows Server 2012 R2, and subsequent versions.

### Prerequisites

[!INCLUDE[deploy-winrm-setup](includes/deploy-winrm-setup.md)]

### What's new in this task version

- Uses PSSession and invoke-command to perform remoting on target machines.
- Added support for inline script execution.
- Default and CredSSP authentication are supported.
- Added options for error handling: `ErrorActionPreference`, `ignoreLASTEXITCODE` and **Fail on Standard Error**.
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
| Agent version |  2.134.0 or greater |
| Task category | Deploy |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->