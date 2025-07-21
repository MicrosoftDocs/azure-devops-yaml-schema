---
title: AdvancedSecurity-Publish@1 - Advanced Security Publish Results v1 task
description: Combines SARIF file(s) produced by code scanning tool(s), enhances the combined SARIF file, and publishes the enhanced SARIF file to the Advanced Security service.
ms.date: 07/21/2025
monikerRange: "=azure-pipelines"
author: juliakm
ms.author: jukullam
---

# AdvancedSecurity-Publish@1 - Advanced Security Publish Results v1 task

<!-- :::description::: -->
:::moniker range="=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Combines SARIF file(s) produced by code scanning tool(s), enhances the combined SARIF file, and publishes the enhanced SARIF file to the Advanced Security service.

> [!NOTE]
> This task publishes the SARIF files produced by non-Microsoft tasks to [Code Scanning for GitHub Advanced Security](/azure/devops/repos/security/github-advanced-security-code-scanning). Currently, this task works with the [Infrastructure-as-Code Scanning Tasks Extension](https://marketplace.visualstudio.com/items?itemName=advancedsecurity.iac-tasks) tasks. For more information, see [Infrastructure‐as‐Code Scanning](https://github.com/microsoft/advancedsecurity/wiki/Infrastructure%E2%80%90as%E2%80%90Code-Scanning).
>
> This task isn't needed when using [GitHub Advanced Security for Azure DevOps](/azure/devops/repos/security/configure-github-advanced-security-features) tasks like [AdvancedSecurity-Dependency-Scanning@1](./advanced-security-dependency-scanning-v1.md) or [AdvancedSecurity-Codeql-Analyze@1](./advanced-security-codeql-analyze-v1.md).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range="=azure-pipelines"

```yaml
# Advanced Security Publish Results v1
# Combines SARIF file(s) produced by code scanning tool(s), enhances the combined SARIF file, and publishes the enhanced SARIF file to the Advanced Security service.
- task: AdvancedSecurity-Publish@1
  inputs:
    #SarifsInputDirectory: # string. SARIF(s) Input Directory. 
    #Category: # string. Category. 
    #WaitForProcessing: false # boolean. Enable Wait for Processing. Default: false.
    #WaitForProcessingInterval: '5' # string. Optional. Use when WaitForProcessing = true. Wait for Processing Time Interval. Default: 5.
    #WaitForProcessingTimeout: '120' # string. Optional. Use when WaitForProcessing = true. Wait for Processing Timeout. Default: 120.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::inputs::: -->
## Inputs

<!-- :::item name="SarifsInputDirectory"::: -->
:::moniker range="=azure-pipelines"

**`SarifsInputDirectory`** - **SARIF(s) Input Directory**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Path to the directory containing the SARIF file(s) that need to be combined, enhanced, and published to Advanced Security. When not specified, the task will look for SARIF file(s) in pre-determined locations.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="Category"::: -->
:::moniker range="=azure-pipelines"

**`Category`** - **Category**<br>
`string`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Category to associate scan results with when enhancing the SARIF file(s) before publishing to Advanced Security. The category of scan results helps distinguish between different types of scan results. Use this field when publishing SARIF file(s) produced by tools other than CodeQL. When publishing SARIF file(s) produced by CodeQL, there is no need to specify a category, and if one is specified, it will be ignored by the task.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WaitForProcessing"::: -->
:::moniker range="=azure-pipelines"

**`WaitForProcessing`** - **Enable Wait for Processing**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Wait for Advanced Security to process published SARIF file before completing.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WaitForProcessingInterval"::: -->
:::moniker range="=azure-pipelines"

**`WaitForProcessingInterval`** - **Wait for Processing Time Interval**<br>
`string`. Optional. Use when `WaitForProcessing = true`. Default value: `5`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Time, in seconds, to wait between each call to Advanced Security to check SARIF processing status.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="WaitForProcessingTimeout"::: -->
:::moniker range="=azure-pipelines"

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

:::moniker range="=azure-pipelines"

None.

:::moniker-end
<!-- :::outputVariables-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

This task publishes the SARIF files produced by non-Microsoft tasks to [Code Scanning for GitHub Advanced Security](/azure/devops/repos/security/github-advanced-security-code-scanning). Currently, this task works with the [Infrastructure-as-Code Scanning Tasks Extension](https://marketplace.visualstudio.com/items?itemName=advancedsecurity.iac-tasks) tasks. For more information, see [Infrastructure‐as‐Code Scanning](https://github.com/microsoft/advancedsecurity/wiki/Infrastructure%E2%80%90as%E2%80%90Code-Scanning).

This task isn't needed when using [GitHub Advanced Security for Azure DevOps](/azure/devops/repos/security/configure-github-advanced-security-features) tasks like [AdvancedSecurity-Dependency-Scanning@1](./advanced-security-dependency-scanning-v1.md) or [AdvancedSecurity-Codeql-Analyze@1](./advanced-security-codeql-analyze-v1.md).
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
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->