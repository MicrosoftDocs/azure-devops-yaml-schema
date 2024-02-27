---
title: AdvancedSecurity-Dependency-Scanning@1 - Advanced Security Dependency Scanning v1 task
description: Scan for open source dependency vulnerabilities in your source code.
ms.date: 02/27/2024
monikerRange: "=azure-pipelines"
---

# AdvancedSecurity-Dependency-Scanning@1 - Advanced Security Dependency Scanning v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Scan your application for any vulnerabilities in open source components used in your source code. You must have [GitHub Advanced Security for Azure DevOps](/azure/devops/repos/security/configure-github-advanced-security-features) enabled for the repository being scanned.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Advanced Security Dependency Scanning v1
# Scan for open source dependency vulnerabilities in your source code.
- task: AdvancedSecurity-Dependency-Scanning@1
  inputs:
  # Advanced
    #directoryExclusionList: # string. Directory exclusion list.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="directoryExclusionList"::: -->
:::moniker range="=azure-pipelines"

**`directoryExclusionList`** - **Directory exclusion list**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
List of relative directory paths to ignore as a set of semi-colon separated values. If no paths are listed, everything under the source directory will be scanned. Filtering supports glob pattern matching of directories.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->

### Task control options

All tasks have control options in addition to their task inputs. For more information, see [Control options and common task properties](/azure/devops/pipelines/yaml-schema/steps-task#common-task-properties).
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Use this task to scan your application for any vulnerabilities in open source components used in your source code.

> [!IMPORTANT]
> This task is supported with Azure Repos Git repositories only.

You must have [GitHub Advanced Security for Azure DevOps](/azure/devops/repos/security/configure-github-advanced-security-features) enabled for the repository being scanned.

### Prerequisites  

For the task to successfully complete and populate the Advanced Security tab for the scanned repository, [Advanced Security](/azure/devops/repos/security/configure-github-advanced-security-features) must be enabled for that repository prior to running a build with the dependency scanning task included.

The task is available to run on self-hosted agents as well as Microsoft-hosted agents. For self-hosted agents, see [additional self-hosted agent set-up instructions](/azure/devops/repos/security/configure-github-advanced-security-features#extra-prerequisites-for-self-hosted-agents).

For the most accurate scanning results, add the Advanced Security dependency scanning task after your build steps but before any clean up of the build process, as shown in the following example.

```YAML
# Authenticate Azure DevOps NuGet feed 
- task: NuGetAuthenticate@1 
  displayName: 'Authenticate Azure DevOps NuGet feed' 

# Restore project 
- task: DotNetCoreCLI@2 
  inputs: 
    command: 'custom' 
    custom: 'restore' 

# Build project 
- task: DotNetCoreCLI@2 
  inputs: 
    command: 'custom' 
    custom: 'build' 
    arguments: '--no-restore' 

# Run dependency scanning 
- task: AdvancedSecurity-Dependency-Scanning@1 
  displayName: 'Advanced Security Dependency Scanning' 
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
| Agent version |  2.206.1 or greater |
| Task category | Utility |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

* [Dependency scanning for GitHub Advanced Security](/azure/devops/repos/security/github-advanced-security-dependency-scanning)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->