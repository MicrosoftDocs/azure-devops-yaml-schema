---
title: steps definition
description: Steps are a linear sequence of operations that make up a job.
ms.date: 11/20/2024
monikerRange: "<=azure-pipelines"
---

# steps definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Steps are a linear sequence of operations that make up a job.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2020"

```yaml
steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | getPackage | publish | template | reviewApp ] # Steps are a linear sequence of operations that make up a job.
```

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

```yaml
steps: [ task | script | powershell | pwsh | bash | checkout | download | downloadBuild | publish | template ] # Steps are a linear sequence of operations that make up a job.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2020"

Definitions that reference this definition: [pipeline](pipeline.md), [jobs.job](jobs-job.md), [preDeployHook](pre-deploy-hook.md), [deployHook](deploy-hook.md), [routeTrafficHook](route-traffic-hook.md), [postRouteTrafficHook](post-route-traffic-hook.md), [onFailureHook](on-failure-hook.md), [onSuccessHook](on-success-hook.md)

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

Definitions that reference this definition: [pipeline](pipeline.md), [jobs.job](jobs-job.md)

:::moniker-end
<!-- :::parents-end::: -->

## List types

<!-- :::list-types::: -->
:::moniker range=">=azure-pipelines-2020"

| Type | Description |
|---|---|
| [steps.task](steps-task.md) | Runs a task. |
| [steps.script](steps-script.md) | Runs a script using cmd.exe on Windows and Bash on other platforms. |
| [steps.powershell](steps-powershell.md) | Runs a script using either Windows PowerShell (on Windows) or pwsh (Linux and macOS). |
| [steps.pwsh](steps-pwsh.md) | Runs a script in PowerShell Core on Windows, macOS, and Linux. |
| [steps.bash](steps-bash.md) | Runs a script in Bash on Windows, macOS, and Linux. |
| [steps.checkout](steps-checkout.md) | Configure how the pipeline checks out source code. |
| [steps.download](steps-download.md) | Downloads artifacts associated with the current run or from another Azure Pipeline that is associated as a pipeline resource. |
| [steps.downloadBuild](steps-download-build.md) | Downloads build artifacts. |
| [steps.getPackage](steps-get-package.md) | Downloads a package from a package management feed in Azure Artifacts or Azure DevOps Server. |
| [steps.publish](steps-publish.md) | Publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume. |
| [steps.template](steps-template.md) | Define a set of steps in one file and use it multiple times in another file. |
| [steps.reviewApp](steps-review-app.md) | Downloads creates a resource dynamically under a deploy phase provider. |

:::moniker-end

:::moniker range="<=azure-pipelines-2019.1"

| Type | Description |
|---|---|
| [steps.task](steps-task.md) | Runs a task. |
| [steps.script](steps-script.md) | Runs a script using cmd.exe on Windows and Bash on other platforms. |
| [steps.powershell](steps-powershell.md) | Runs a script using either Windows PowerShell (on Windows) or pwsh (Linux and macOS). |
| [steps.pwsh](steps-pwsh.md) | Runs a script in PowerShell Core on Windows, macOS, and Linux. |
| [steps.bash](steps-bash.md) | Runs a script in Bash on Windows, macOS, and Linux. |
| [steps.checkout](steps-checkout.md) | Configure how the pipeline checks out source code. |
| [steps.download](steps-download.md) | Downloads artifacts associated with the current run or from another Azure Pipeline that is associated as a pipeline resource. |
| [steps.downloadBuild](steps-download-build.md) | Downloads build artifacts. |
| [steps.publish](steps-publish.md) | Publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume. |
| [steps.template](steps-template.md) | Define a set of steps in one file and use it multiple times in another file. |

:::moniker-end
<!-- :::list-types-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

Each step runs in its own process on an agent and has access to the pipeline workspace on a local hard drive.
This behavior means environment variables aren't preserved between steps but file system changes are.

All tasks and steps support a set of common properties, such as `enabled` and `env`,in addition to their task or step specific properties. For more information on configuring these properties, see [Task control options](/azure/devops/pipelines/process/tasks#task-control-options) and [Task environment variables](/azure/devops/pipelines/process/tasks#environment-variables).
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yaml
steps:
- script: echo This runs in the default shell on any machine
- bash: |
    echo This multiline script always runs in Bash.
    echo Even on Windows machines!
- pwsh: |
    Write-Host "This multiline script always runs in PowerShell Core."
    Write-Host "Even on non-Windows machines!"
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Specify jobs in your pipeline](/azure/devops/pipelines/process/phases)
- [Task types and usage](/azure/devops/pipelines/process/tasks)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->