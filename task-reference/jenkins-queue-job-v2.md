---
title: JenkinsQueueJob@2 - Jenkins queue job v2 task
description: Queue a job on a Jenkins server.
ms.date: 08/18/2022
monikerRange: "<=azure-pipelines"
---

# JenkinsQueueJob@2 - Jenkins queue job v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Queue a job on a Jenkins server.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
## Syntax

:::moniker range=">=azure-pipelines-2022"

```yaml
# Jenkins queue job v2
# Queue a job on a Jenkins server.
- task: JenkinsQueueJob@2
  inputs:
    serverEndpoint: # string. Required. Jenkins service connection. 
    jobName: # string. Required. Job name. 
    #isMultibranchJob: false # boolean. Job is of multibranch pipeline type. Default: false.
    #multibranchPipelineBranch: # string. Required when isMultibranchJob = true. Multibranch pipeline branch. 
    captureConsole: true # boolean. Required. Capture console output and wait for completion. Default: true.
    capturePipeline: true # boolean. Required when captureConsole = true. Capture pipeline output and wait for pipeline completion. Default: true.
  # Advanced
    isParameterizedJob: false # boolean. Required. Parameterized job. Default: false.
    #jobParameters: # string. Optional. Use when parameterizedJob = true. Job parameters. 
    #failOnUnstableResult: false # boolean. Fail on unstable result. Default: false.
    #retryCount: '3' # string. Number of retries for failed connection. Default: '3'.
    #delayBetweenRetries: '60' # string. Time between retries. Default: '60'.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019.1 <=azure-pipelines-2020.1"

```yaml
# Jenkins queue job v2
# Queue a job on a Jenkins server.
- task: JenkinsQueueJob@2
  inputs:
    serverEndpoint: # string. Required. Jenkins service connection. 
    jobName: # string. Required. Job name. 
    #isMultibranchJob: false # boolean. Job is of multibranch pipeline type. Default: false.
    #multibranchPipelineBranch: # string. Required when isMultibranchJob = true. Multibranch pipeline branch. 
    captureConsole: true # boolean. Required. Capture console output and wait for completion. Default: true.
    capturePipeline: true # boolean. Required when captureConsole = true. Capture pipeline output and wait for pipeline completion. Default: true.
  # Advanced
    isParameterizedJob: false # boolean. Required. Parameterized job. Default: false.
    #jobParameters: # string. Optional. Use when parameterizedJob = true. Job parameters.
```

:::moniker-end

:::moniker range="=azure-pipelines-2019"

```yaml
# Jenkins Queue Job v2
# Queue a job on a Jenkins server.
- task: JenkinsQueueJob@2
  inputs:
    serverEndpoint: # string. Required. Jenkins service connection. 
    jobName: # string. Required. Job name. 
    #isMultibranchJob: false # boolean. Job is of multibranch pipeline type. Default: false.
    #multibranchPipelineBranch: # string. Required when isMultibranchJob = true. Multibranch pipeline branch. 
    captureConsole: true # boolean. Required. Capture console output and wait for completion. Default: true.
    capturePipeline: true # boolean. Required when captureConsole = true. Capture pipeline output and wait for pipeline completion. Default: true.
  # Advanced
    isParameterizedJob: false # boolean. Required. Parameterized job. Default: false.
    #jobParameters: # string. Optional. Use when parameterizedJob = true. Job parameters.
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

<!-- :::item name="serverEndpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`serverEndpoint`** - **Jenkins service connection**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the service connection for your Jenkins instance.  To create one, click the Manage link and create a new Jenkins service connection.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`serverEndpoint`** - **Jenkins service endpoint**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select the service connection for your Jenkins instance.  To create one, click the Manage link and create a new Jenkins service connection.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobName"::: -->
:::moniker range="<=azure-pipelines"

**`jobName`** - **Job name**<br>
Type: string. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Jenkins job to queue.  This must exactly match the job name on the Jenkins server.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isMultibranchJob"::: -->
:::moniker range="<=azure-pipelines"

**`isMultibranchJob`** - **Job is of multibranch pipeline type**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This job is of multibranch pipeline type.  If selected, enter the appropriate branch name. Requires Team Foundation Server Plugin for Jenkins v5.3.4 or later.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="multibranchPipelineBranch"::: -->
:::moniker range="<=azure-pipelines"

**`multibranchPipelineBranch`** - **Multibranch pipeline branch**<br>
Type: string. Required when isMultibranchJob = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Queue this multibranch pipeline job on the specified branch. This requires Team Foundation Server Plugin for Jenkins v5.3.4 or later.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="captureConsole"::: -->
:::moniker range="<=azure-pipelines"

**`captureConsole`** - **Capture console output and wait for completion**<br>
Type: boolean. Required. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If selected, this task will capture the Jenkins build console output, wait for the Jenkins build to complete, and succeed/fail based on the Jenkins build result.  Otherwise, once the Jenkins job is successfully queued, this task will successfully complete without waiting for the Jenkins build to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="capturePipeline"::: -->
:::moniker range="<=azure-pipelines"

**`capturePipeline`** - **Capture pipeline output and wait for pipeline completion**<br>
Type: boolean. Required when captureConsole = true. Default value: true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If selected, this task will capture the full Jenkins build pipeline console output, wait for the full Jenkins build pipeline to complete, and succeed/fail based on the Jenkins build pipeline result.  Otherwise, once the first Jenkins job completes, this task will successfully complete without waiting for full Jenkins build pipeline to run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isParameterizedJob"::: -->
:::moniker range="<=azure-pipelines"

**`isParameterizedJob`** - **Parameterized job**<br>
Input alias: `parameterizedJob`. Type: boolean. Required. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Select if the Jenkins job accepts parameters. This should be selected even if all default parameter values are used and no parameters are actually specified.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobParameters"::: -->
:::moniker range="<=azure-pipelines"

**`jobParameters`** - **Job parameters**<br>
Type: string. Optional. Use when parameterizedJob = true.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify job parameters, one per line, in the form <b>`<parameterName>=<parameterValue>`</b><p>To set a parameter to an empty value (useful for overriding a default value), leave off the parameter value. For example, specify <b>`<parameterName>=`</b><p>Variables are supported. For example, to set a <b>`commitId`</b> parameter value to the Git commit ID of the build, use: <b>`commitId=$(Build.SourceVersion)`</b>. See the [documentation on variables](https://go.microsoft.com/fwlink/?linkid=875288) for more details.<p>Supported Jenkins parameter types are: <ul><li>`Boolean`</li><li>`Choice`</li><li>`Password`</li><li>`String`</li></ul>.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnUnstableResult"::: -->
:::moniker range=">=azure-pipelines-2022"

**`failOnUnstableResult`** - **Fail on unstable result**<br>
Type: boolean. Default value: false.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies strictness of a success definition: whether to consider unstable as a failure or not. False for non-strict, and true for strict version.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="retryCount"::: -->
:::moniker range=">=azure-pipelines-2022"

**`retryCount`** - **Number of retries for failed connection**<br>
Type: string. Default value: '3'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify number of retries on errors or failures.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="delayBetweenRetries"::: -->
:::moniker range=">=azure-pipelines-2022"

**`delayBetweenRetries`** - **Time between retries**<br>
Type: string. Default value: '60'.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specify time between retries. This is specified in seconds.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::inputs-end::: -->

<!-- :::outputVariables::: -->
## Output variables

:::moniker range="<=azure-pipelines"

This task defines the following [output variables](/azure/devops/pipelines/process/variables#use-output-variables-from-tasks), which you can consume in downstream steps, jobs, and stages.

<!-- :::item name="JENKINS_JOB_ID"::: -->
**`JENKINS_JOB_ID`**<br><!-- :::editable-content name="Value"::: -->
The ID of the Jenkins job instance queued by this task. Use this variable in the Jenkins Download Artifacts task to download the artifacts for this particular job instance.
<!-- :::editable-content-end::: -->
<!-- :::item-end::: -->

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
| Agent version | All supported agent versions. |
| Task category | Build |

:::moniker-end
<!-- :::properties-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->