---
title: AdvancedSecurity-Codeql-Analyze@1 - Advanced Security Perform CodeQL analysis v1 task
description: Finalizes the CodeQL database and runs the analysis queries.
ms.date: 11/11/2025
monikerRange: "=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# AdvancedSecurity-Codeql-Analyze@1 - Advanced Security Perform CodeQL analysis v1 task

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-server"

<!-- :::editable-content name="description"::: -->
Analyzes the code in an Azure Repos Git repository to find security vulnerabilities and coding errors. You must have [GitHub Advanced Security for Azure DevOps](/azure/devops/repos/security/configure-github-advanced-security-features) enabled for the repository being scanned.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Advanced Security Perform CodeQL analysis v1
# Finalizes the CodeQL database and runs the analysis queries.
- task: AdvancedSecurity-Codeql-Analyze@1
  inputs:
    #WaitForProcessing: false # boolean. Enable Wait for Processing. Default: false.
    #WaitForProcessingInterval: '5' # string. Optional. Use when WaitForProcessing = true. Wait for Processing Time Interval. Default: 5.
    #WaitForProcessingTimeout: '120' # string. Optional. Use when WaitForProcessing = true. Wait for Processing Timeout. Default: 120.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="WaitForProcessing"::: -->
:::moniker range=">azure-pipelines-server"

**`WaitForProcessing`** - **Enable Wait for Processing**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Wait for Advanced Security to process published SARIF file before completing.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WaitForProcessingInterval"::: -->
:::moniker range=">azure-pipelines-server"

**`WaitForProcessingInterval`** - **Wait for Processing Time Interval**<br>
`string`. Optional. Use when `WaitForProcessing = true`. Default value: `5`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Time, in seconds, to wait between each call to Advanced Security to check SARIF processing status.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WaitForProcessingTimeout"::: -->
:::moniker range=">azure-pipelines-server"

**`WaitForProcessingTimeout`** - **Wait for Processing Timeout**<br>
`string`. Optional. Use when `WaitForProcessing = true`. Default value: `120`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Time, in seconds, to wait for Advanced Security to process SARIF file before completing.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range=">=azure-pipelines-server"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

> [!IMPORTANT]
> This task is supported with Azure Repos Git repositories only.

### Prerequisites  

For the task to successfully complete and populate the Advanced Security tab for the scanned repository, [Advanced Security](/azure/devops/repos/security/configure-github-advanced-security-features) must be enabled for that repository prior to running a build with the dependency scanning task included.

The task is available to run on self-hosted agents as well as Microsoft-hosted agents. For self-hosted agents, see [additional self-hosted agent set-up instructions](/azure/devops/repos/security/configure-github-advanced-security-features#extra-prerequisites-for-self-hosted-agents).


#### Task Order
The analysis task must appear after the initialize task for successful completion. 

##### Interpreted Languages
For interpreted languages, no build mode customization is required. See [Code scanning build mode customization](/azure/devops/repos/security/github-advanced-security-code-scanning#code-scanning-build-mode-customization) for more details.

1. Initialize CodeQL
1. Perform CodeQL analysis

```YAML
# Initialize CodeQL database
- task: AdvancedSecurity-Codeql-Init@1
  inputs: 
    languages: 'javascript'
  displayName: 'Advanced Security Initialize CodeQL' 

# Run analysis 
- task: AdvancedSecurity-Codeql-Analyze@1 
  displayName: 'Advanced Security Code Scanning' 
```

##### Compiled Languages

For compiled languages, either `buildtype: None` or custom build tasks that invoke the compiler must be configured for your project to be analyzed. For more information on the different build modes, including a comparison on the benefits of each build mode, see [Initialize CodeQL buildtype input](../advanced-security-codeql-init-v1.md#inputs).


1. Initialize CodeQL (buildtype: None)
1. Perform CodeQL analysis

```YAML
# Initialize CodeQL database
- task: AdvancedSecurity-Codeql-Init@1
  inputs: 
    languages: 'csharp'
    buildtype: 'None'
  displayName: 'Advanced Security Initialize CodeQL' 

# Run analysis 
- task: AdvancedSecurity-Codeql-Analyze@1 
  displayName: 'Advanced Security Code Scanning' 
```

Alternatively,

1. Initialize CodeQL (by default or with buildtype: Manual)
1. custom build tasks
1. Perform CodeQL analysis


```YAML
# Initialize CodeQL database 
- task: AdvancedSecurity-Codeql-Init@1
  inputs: 
    languages: 'csharp' 
  displayName: 'Advanced Security Initialize CodeQL' 

# Restore/Build project using your own custom build steps 
- task: DotNetCoreCLI@2
  displayName: Build
  inputs:
    command: build
    projects: '**/*.sln'

# Run analysis 
- task: AdvancedSecurity-Codeql-Analyze@1 
  displayName: 'Advanced Security Code Scanning' 
```
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::properties::: -->
## Requirements

:::moniker range="=azure-pipelines"

| Requirement | Description |
|-------------|-------------|
| Pipeline types | YAML, Classic build, Classic release |
| Runs on | Agent, DeploymentGroup |
| [Demands](/azure/devops/pipelines/process/demands) | None |
| [Capabilities](/azure/devops/pipelines/agents/agents#capabilities) | This task does not satisfy any demands for subsequent tasks in the job. |
| [Command restrictions](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| [Settable variables](/azure/devops/pipelines/security/templates#agent-logging-command-restrictions) | Any |
| Agent version | All supported agent versions. |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Code scanning for GitHub Advanced Security](/azure/devops/repos/security/github-advanced-security-code-scanning)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
