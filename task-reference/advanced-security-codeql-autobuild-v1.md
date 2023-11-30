---
title: AdvancedSecurity-Codeql-Autobuild@1 - Advanced Security AutoBuild v1 task
description: Attempts to build the repository by finding and building project files in the source folder.
ms.date: 11/30/2023
monikerRange: "=azure-pipelines"
---

# AdvancedSecurity-Codeql-Autobuild@1 - Advanced Security AutoBuild v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Attempts to automatically build your project for CodeQL analysis by finding and building project files in the source folder. This task is not required if you have your own custom build steps, or if you are not using `cpp`, `java`, `csharp`, or `swift`. You must have [GitHub Advanced Security for Azure DevOps](/azure/devops/repos/security/configure-github-advanced-security-features) enabled for the repository being scanned.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Advanced Security AutoBuild v1
# Attempts to build the repository by finding and building project files in the source folder.
- task: AdvancedSecurity-Codeql-Autobuild@1
  inputs: # none
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="emptyCollectionValue"::: -->
:::moniker range="=azure-pipelines"

None.

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

> [!IMPORTANT]
> This task is supported with Azure Repos Git repositories only.

The `AdvancedSecurity-Codeql-Autobuild@1` task attempts to build the project file in your repository. If `AdvancedSecurity-Codeql-Autobuild@1` cannot build your project, remove the `AdvancedSecurity-Codeql-Autobuild@1` task and replace it with your custom build steps.

This task is not required if you have your own custom build steps, or if you are not using `cpp`, `java`, `csharp`, or `swift`. You must have [GitHub Advanced Security for Azure DevOps](/azure/devops/repos/security/configure-github-advanced-security-features) enabled for the repository being scanned.

The pipeline must call the tasks in the following order.

1. Initialize CodeQL
1. AutoBuild (or your custom build tasks)
1. Perform CodeQL analysis

The AutoBuild task is optional and may be replaced with your custom build tasks. Either AutoBuild or your custom build tasks must be run for your project to be analyzed.

The `AdvancedSecurity-Codeql-Autobuild@1` task must appear after the initialize step for successful completion.

```YAML
# Initialize CodeQL database 
- task: AdvancedSecurity-Codeql-Init@1
  inputs: 
    language: csharp 
  displayName: 'Advanced Security Initialize CodeQL' 

# Build project using Autobuild or your own custom build steps 
- task: AdvancedSecurity-Codeql-Autobuild@1
  displayName: 'Advanced Security Autobuild' 

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