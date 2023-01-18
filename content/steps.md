---
title: steps list definition
description: steps list definition reference.
ms.date: 01/18/2023
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"
---

# steps list definition


Steps are a linear sequence of operations that make up a job.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="steps[step]" version="azure-pipelines-2019"::: -->

```yaml
steps: [ step ] # 
```


Properties that use this definition: [pipeline.steps](pipeline.md), [jobs.job.steps](jobs-job.md)

## List types

| Type     | Description |
|----------|-------------|
| [steps.task](steps-task.md) | Run a task. |
| [steps.script](steps-script.md) | The script step is a shortcut for the command-line task, and runs a script using cmd.exe on Windows and Bash on other platforms. |
| [steps.powershell](steps-powershell.md) | The powershell step is a shortcut for the PowerShell task, and runs a script in Windows PowerShell. |
| [steps.pwsh](steps-pwsh.md) | The pwsh step is a shortcut for the PowerShell task when that task's pwsh value is set to true, and runs a script in PowerShell Core on Windows, macOS, and Linux. |
| [steps.bash](steps-bash.md) | The bash step is a shortcut for the shell script task, and runs a script in Bash on Windows, macOS, and Linux. |
| [steps.checkout](steps-checkout.md) | Checkout repositories. |
| [steps.download](steps-download.md) | The download step is a shortcut for the Download Pipeline Artifact task, and downloads artifacts associated with the current run or from another Azure pipeline that is associated as a pipeline resource. |
| [steps.downloadBuild](steps-download-build.md) | The download step is a shortcut for the Download Build Artifact task, and downloads build artifacts |
| [steps.publish](steps-publish.md) | The publish step is a shortcut for the Publish Pipeline Artifact task, and publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume. |
| [steps.template](steps-template.md) | Run the steps in a template file for this step. |
| [steps.restoreCache](steps-restore-cache.md) | The restoreCache step is a shortcut for the Cache task, and restores a cache. |
| [steps.saveCache](steps-save-cache.md) | The saveCache step is a shortcut for the Cache task, and saves a cache. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="steps[step]" version="azure-pipelines-2019.1"::: -->

```yaml
steps: [ step ] # 
```


Properties that use this definition: [pipeline.steps](pipeline.md), [jobs.job.steps](jobs-job.md)

## List types

| Type     | Description |
|----------|-------------|
| [steps.task](steps-task.md) | Run a task. |
| [steps.script](steps-script.md) | The script step is a shortcut for the command-line task, and runs a script using cmd.exe on Windows and Bash on other platforms. |
| [steps.powershell](steps-powershell.md) | The powershell step is a shortcut for the PowerShell task, and runs a script in Windows PowerShell. |
| [steps.pwsh](steps-pwsh.md) | The pwsh step is a shortcut for the PowerShell task when that task's pwsh value is set to true, and runs a script in PowerShell Core on Windows, macOS, and Linux. |
| [steps.bash](steps-bash.md) | The bash step is a shortcut for the shell script task, and runs a script in Bash on Windows, macOS, and Linux. |
| [steps.checkout](steps-checkout.md) | Checkout repositories. |
| [steps.download](steps-download.md) | The download step is a shortcut for the Download Pipeline Artifact task, and downloads artifacts associated with the current run or from another Azure pipeline that is associated as a pipeline resource. |
| [steps.downloadBuild](steps-download-build.md) | The download step is a shortcut for the Download Build Artifact task, and downloads build artifacts |
| [steps.publish](steps-publish.md) | The publish step is a shortcut for the Publish Pipeline Artifact task, and publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume. |
| [steps.template](steps-template.md) | Run the steps in a template file for this step. |
| [steps.restoreCache](steps-restore-cache.md) | The restoreCache step is a shortcut for the Cache task, and restores a cache. |
| [steps.saveCache](steps-save-cache.md) | The saveCache step is a shortcut for the Cache task, and saves a cache. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="steps[step]" version="azure-pipelines-2020"::: -->

```yaml
steps: [ step ] # 
```


Properties that use this definition: [pipeline.steps](pipeline.md), [jobs.job.steps](jobs-job.md)

## List types

| Type     | Description |
|----------|-------------|
| [steps.task](steps-task.md) | Run a task. |
| [steps.script](steps-script.md) | The script step is a shortcut for the command-line task, and runs a script using cmd.exe on Windows and Bash on other platforms. |
| [steps.powershell](steps-powershell.md) | The powershell step is a shortcut for the PowerShell task, and runs a script in Windows PowerShell. |
| [steps.pwsh](steps-pwsh.md) | The pwsh step is a shortcut for the PowerShell task when that task's pwsh value is set to true, and runs a script in PowerShell Core on Windows, macOS, and Linux. |
| [steps.bash](steps-bash.md) | The bash step is a shortcut for the shell script task, and runs a script in Bash on Windows, macOS, and Linux. |
| [steps.checkout](steps-checkout.md) | Checkout repositories. |
| [steps.download](steps-download.md) | The download step is a shortcut for the Download Pipeline Artifact task, and downloads artifacts associated with the current run or from another Azure pipeline that is associated as a pipeline resource. |
| [steps.downloadBuild](steps-download-build.md) | The download step is a shortcut for the Download Build Artifact task, and downloads build artifacts |
| [steps.getPackage](steps-get-package.md) | The getPackage step is a shortcut for the Download Package task, and downloads a package from a package management feed. |
| [steps.publish](steps-publish.md) | The publish step is a shortcut for the Publish Pipeline Artifact task, and publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume. |
| [steps.template](steps-template.md) | Run the steps in a template file for this step. |
| [steps.restoreCache](steps-restore-cache.md) | The restoreCache step is a shortcut for the Cache task, and restores a cache. |
| [steps.saveCache](steps-save-cache.md) | The saveCache step is a shortcut for the Cache task, and saves a cache. |
| [steps.reviewApp](steps-review-app.md) | The reviewApp step is a shortcut for the Review App task. Use this task under deploy phase provider to create a resource dynamically. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="steps[step]" version="azure-pipelines-2020.1"::: -->

```yaml
steps: [ step ] # 
```


Properties that use this definition: [pipeline.steps](pipeline.md), [jobs.job.steps](jobs-job.md)

## List types

| Type     | Description |
|----------|-------------|
| [steps.task](steps-task.md) | Run a task. |
| [steps.script](steps-script.md) | The script step is a shortcut for the command-line task, and runs a script using cmd.exe on Windows and Bash on other platforms. |
| [steps.powershell](steps-powershell.md) | The powershell step is a shortcut for the PowerShell task, and runs a script in Windows PowerShell. |
| [steps.pwsh](steps-pwsh.md) | The pwsh step is a shortcut for the PowerShell task when that task's pwsh value is set to true, and runs a script in PowerShell Core on Windows, macOS, and Linux. |
| [steps.bash](steps-bash.md) | The bash step is a shortcut for the shell script task, and runs a script in Bash on Windows, macOS, and Linux. |
| [steps.checkout](steps-checkout.md) | Checkout repositories. |
| [steps.download](steps-download.md) | The download step is a shortcut for the Download Pipeline Artifact task, and downloads artifacts associated with the current run or from another Azure pipeline that is associated as a pipeline resource. |
| [steps.downloadBuild](steps-download-build.md) | The download step is a shortcut for the Download Build Artifact task, and downloads build artifacts |
| [steps.getPackage](steps-get-package.md) | The getPackage step is a shortcut for the Download Package task, and downloads a package from a package management feed. |
| [steps.publish](steps-publish.md) | The publish step is a shortcut for the Publish Pipeline Artifact task, and publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume. |
| [steps.template](steps-template.md) | Run the steps in a template file for this step. |
| [steps.restoreCache](steps-restore-cache.md) | The restoreCache step is a shortcut for the Cache task, and restores a cache. |
| [steps.saveCache](steps-save-cache.md) | The saveCache step is a shortcut for the Cache task, and saves a cache. |
| [steps.reviewApp](steps-review-app.md) | The reviewApp step is a shortcut for the Review App task. Use this task under deploy phase provider to create a resource dynamically. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="steps[step]" version="azure-pipelines-2022"::: -->

```yaml
steps: [ step ] # 
```


Properties that use this definition: [pipeline.steps](pipeline.md), [jobs.job.steps](jobs-job.md)

## List types

| Type     | Description |
|----------|-------------|
| [steps.task](steps-task.md) | Run a task. |
| [steps.script](steps-script.md) | The script step is a shortcut for the command-line task, and runs a script using cmd.exe on Windows and Bash on other platforms. |
| [steps.powershell](steps-powershell.md) | The powershell step is a shortcut for the PowerShell task, and runs a script in Windows PowerShell. |
| [steps.pwsh](steps-pwsh.md) | The pwsh step is a shortcut for the PowerShell task when that task's pwsh value is set to true, and runs a script in PowerShell Core on Windows, macOS, and Linux. |
| [steps.bash](steps-bash.md) | The bash step is a shortcut for the shell script task, and runs a script in Bash on Windows, macOS, and Linux. |
| [steps.checkout](steps-checkout.md) | Checkout repositories. |
| [steps.download](steps-download.md) | The download step is a shortcut for the Download Pipeline Artifact task, and downloads artifacts associated with the current run or from another Azure pipeline that is associated as a pipeline resource. |
| [steps.downloadBuild](steps-download-build.md) | The download step is a shortcut for the Download Build Artifact task, and downloads build artifacts |
| [steps.getPackage](steps-get-package.md) | The getPackage step is a shortcut for the Download Package task, and downloads a package from a package management feed. |
| [steps.publish](steps-publish.md) | The publish step is a shortcut for the Publish Pipeline Artifact task, and publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume. |
| [steps.template](steps-template.md) | Run the steps in a template file for this step. |
| [steps.restoreCache](steps-restore-cache.md) | The restoreCache step is a shortcut for the Cache task, and restores a cache. |
| [steps.saveCache](steps-save-cache.md) | The saveCache step is a shortcut for the Cache task, and saves a cache. |
| [steps.reviewApp](steps-review-app.md) | The reviewApp step is a shortcut for the Review App task. Use this task under deploy phase provider to create a resource dynamically. |

<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="steps[step]" version="azure-pipelines"::: -->

```yaml
steps: [ step ] # 
```


Properties that use this definition: [pipeline.steps](pipeline.md), [jobs.job.steps](jobs-job.md)

## List types

| Type     | Description |
|----------|-------------|
| [steps.task](steps-task.md) | Run a task. |
| [steps.script](steps-script.md) | The script step is a shortcut for the command-line task, and runs a script using cmd.exe on Windows and Bash on other platforms. |
| [steps.powershell](steps-powershell.md) | The powershell step is a shortcut for the PowerShell task, and runs a script in Windows PowerShell. |
| [steps.pwsh](steps-pwsh.md) | The pwsh step is a shortcut for the PowerShell task when that task's pwsh value is set to true, and runs a script in PowerShell Core on Windows, macOS, and Linux. |
| [steps.bash](steps-bash.md) | The bash step is a shortcut for the shell script task, and runs a script in Bash on Windows, macOS, and Linux. |
| [steps.checkout](steps-checkout.md) | Checkout repositories. |
| [steps.download](steps-download.md) | The download step is a shortcut for the Download Pipeline Artifact task, and downloads artifacts associated with the current run or from another Azure pipeline that is associated as a pipeline resource. |
| [steps.downloadBuild](steps-download-build.md) | The download step is a shortcut for the Download Build Artifact task, and downloads build artifacts |
| [steps.getPackage](steps-get-package.md) | The getPackage step is a shortcut for the Download Package task, and downloads a package from a package management feed. |
| [steps.publish](steps-publish.md) | The publish step is a shortcut for the Publish Pipeline Artifact task, and publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume. |
| [steps.template](steps-template.md) | Run the steps in a template file for this step. |
| [steps.restoreCache](steps-restore-cache.md) | The restoreCache step is a shortcut for the Cache task, and restores a cache. |
| [steps.saveCache](steps-save-cache.md) | The saveCache step is a shortcut for the Cache task, and saves a cache. |
| [steps.reviewApp](steps-review-app.md) | The reviewApp step is a shortcut for the Review App task. Use this task under deploy phase provider to create a resource dynamically. |

<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

Each step runs in its own process on an agent and has access to the pipeline workspace on a local hard drive.
This behavior means environment variables aren't preserved between steps but file system changes are.

All steps and tasks support the following properties in addition to their task or step specific properties.

:::moniker range=">azure-pipelines-2020.1"

```YAML
  condition: string # Evaluate this condition expression to determine whether to run this task. 
  continueOnError: boolean # Continue running even on failure?.  (false,n,no,off,on,true,y,yes)
  displayName: string # Human-readable name for the task. 
  target: # Environment in which to run this task
  enabled: boolean # Run this task when the job runs?.  (false,n,no,off,on,true,y,yes)
  env:  # Variables to map into the process's environment
    string: string # Name/value pairs.
  name: string # ID of the step.
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it. 
  retryCountOnTaskFailure: string # Number of retries if the task fails. 
```


:::moniker-end

:::moniker range=">= azure-pipelines-2020 <= azure-pipelines-2020.1"

```YAML
  condition: string # Evaluate this condition expression to determine whether to run this task. 
  continueOnError: boolean # Continue running even on failure?.  (false,n,no,off,on,true,y,yes)
  displayName: string # Human-readable name for the task. 
  target: # Environment in which to run this task
  enabled: boolean # Run this task when the job runs?.  (false,n,no,off,on,true,y,yes)
  env:  # Variables to map into the process's environment
    string: string # Name/value pairs.
  name: string # ID of the step.
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it. 
```

:::moniker-end

:::moniker range=">= azure-pipelines-2019 <= azure-pipelines-2019.1"

```YAML
  condition: string # Evaluate this condition expression to determine whether to run this task. 
  continueOnError: boolean # Continue running even on failure?.  (false,n,no,off,on,true,y,yes)
  displayName: string # Human-readable name for the step. 
  enabled: boolean # Run this task when the job runs?.  (false,n,no,off,on,true,y,yes)
  env:  # Variables to map into the process's environment
    string: string # Name/value pairs.
  name: string # ID of the step.
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it. 
```

:::moniker-end


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


## See also

- [Specify jobs in your pipeline](/azure/devops/pipelines/process/phases)
- [Task types and usage](/azure/devops/pipelines/process/tasks)





