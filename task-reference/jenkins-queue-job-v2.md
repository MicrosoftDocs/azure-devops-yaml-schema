---
title: JenkinsQueueJob@2 - Jenkins queue job v2 task
description: Queue a job on a Jenkins server.
ms.date: 07/31/2023
monikerRange: "<=azure-pipelines"
---

# JenkinsQueueJob@2 - Jenkins queue job v2 task

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use this task to queue a job on a Jenkins server.
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
    #captureConsole: true # boolean. Capture console output and wait for completion. Default: true.
    #capturePipeline: true # boolean. Optional. Use when captureConsole = true. Capture pipeline output and wait for pipeline completion. Default: true.
  # Advanced
    #isParameterizedJob: false # boolean. Alias: parameterizedJob. Parameterized job. Default: false.
    #jobParameters: # string. Optional. Use when parameterizedJob = true. Job parameters. 
    #failOnUnstableResult: false # boolean. Fail on unstable result. Default: false.
    #retryCount: '3' # string. Number of retries for failed connection. Default: 3.
    #delayBetweenRetries: '60' # string. Time between retries. Default: 60.
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
    #captureConsole: true # boolean. Capture console output and wait for completion. Default: true.
    #capturePipeline: true # boolean. Optional. Use when captureConsole = true. Capture pipeline output and wait for pipeline completion. Default: true.
  # Advanced
    #isParameterizedJob: false # boolean. Alias: parameterizedJob. Parameterized job. Default: false.
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
    #captureConsole: true # boolean. Capture console output and wait for completion. Default: true.
    #capturePipeline: true # boolean. Optional. Use when captureConsole = true. Capture pipeline output and wait for pipeline completion. Default: true.
  # Advanced
    #isParameterizedJob: false # boolean. Alias: parameterizedJob. Parameterized job. Default: false.
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
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the service connection for your Jenkins instance.  Click the Manage link to create a new Jenkins service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end

:::moniker range="=azure-pipelines-2018"

**`serverEndpoint`** - **Jenkins service endpoint**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the service connection for your Jenkins instance.  Click the Manage link to create a new Jenkins service connection.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobName"::: -->
:::moniker range="<=azure-pipelines"

**`jobName`** - **Job name**<br>
`string`. Required.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
The name of the Jenkins job to queue.  This must exactly match the job name on the Jenkins server.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isMultibranchJob"::: -->
:::moniker range="<=azure-pipelines"

**`isMultibranchJob`** - **Job is of multibranch pipeline type**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
This job is a multibranch pipeline. If specified, add the appropriate branch name. This input requires Team Foundation Server Plugin for Jenkins v5.3.4 or later.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="multibranchPipelineBranch"::: -->
:::moniker range="<=azure-pipelines"

**`multibranchPipelineBranch`** - **Multibranch pipeline branch**<br>
`string`. Required when `isMultibranchJob = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Queues this multibranch pipeline job on the specified branch. This input requires Team Foundation Server Plugin for Jenkins v5.3.4 or later.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="captureConsole"::: -->
:::moniker range="<=azure-pipelines"

**`captureConsole`** - **Capture console output and wait for completion**<br>
`boolean`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If specified, this input captures the Jenkins build console output, waits for the Jenkins build to complete, and succeeds/fails based on the Jenkins build result.  Otherwise, once the Jenkins job queues, this task successfully completes without waiting for the Jenkins build to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="capturePipeline"::: -->
:::moniker range="<=azure-pipelines"

**`capturePipeline`** - **Capture pipeline output and wait for pipeline completion**<br>
`boolean`. Optional. Use when `captureConsole = true`. Default value: `true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
If specified, this task captures the full Jenkins build pipeline console output, waits for the full Jenkins build pipeline to complete, and succeeds/fails based on the Jenkins build pipeline result. Otherwise, once the first Jenkins job completes, this task successfully completes without waiting for full Jenkins build pipeline to run.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="isParameterizedJob"::: -->
:::moniker range="<=azure-pipelines"

**`isParameterizedJob`** - **Parameterized job**<br>
Input alias: `parameterizedJob`. `boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies if the Jenkins job accepts parameters. Use this input even if all default parameter values are used and no parameters are actually specified.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobParameters"::: -->
:::moniker range="<=azure-pipelines"

**`jobParameters`** - **Job parameters**<br>
`string`. Optional. Use when `parameterizedJob = true`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies job parameters, with one per line, in the format of `<parameterName>=<parameterValue>`. 

To set a parameter to an empty value, which is useful for overriding a default value, leave off the parameter value. For example, specify `parameterName=`.

Variables are supported. To set a `commitId` parameter value to the Git commit ID of the build, for example, you can use: `commitId=$(Build.SourceVersion)`. For more information, see the [documentation on variables](/azure/devops/pipelines/build/variables). 

The supported Jenkins parameter types are:

* `Boolean`
* `Choice`
* `Password`
* `String`
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="failOnUnstableResult"::: -->
:::moniker range=">=azure-pipelines-2022"

**`failOnUnstableResult`** - **Fail on unstable result**<br>
`boolean`. Default value: `false`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies strictness of a success definition, or whether to consider unstable as a failure or not. The `false` value is for a non-strict version, and the `true` is for a strict version. If set to `true`, an unstable build result is treated as a failure. Otherwise, an unstable result is treated as a success.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="retryCount"::: -->
:::moniker range=">=azure-pipelines-2022"

**`retryCount`** - **Number of retries for failed connection**<br>
`string`. Default value: `3`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies the amount of connection retries when connection failure or error occurs.
<!-- :::editable-content-end::: -->
<br>

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="delayBetweenRetries"::: -->
:::moniker range=">=azure-pipelines-2022"

**`delayBetweenRetries`** - **Time between retries**<br>
`string`. Default value: `60`.<br>
<!-- :::editable-content name="helpMarkDown"::: -->
Specifies  the amount of time between connection retries when an error occurs. This value is specified in seconds.
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
## Remarks

Use this task to queue a job on a Jenkins server.

### Team Foundation Server Plug-in

You can use Team Foundation Server Plug-in (version 5.2.0 or newer) to automatically collect files from the Jenkins workspace and download them into the build.

To set it up:

1. Install the [Team Foundation Server Plug-in](https://www.jenkins.io/doc/pipeline/steps/tfs/) on the Jenkins server.

2. On the Jenkins server, for each job you would like to collect results from, add the **Collect results for Azure Pipelines/TFS** post-build action and then configure it with one or more pairs of result type and include file pattern.

3. On the Jenkins Queue Job, build task enable the **Capture console output and wait for completion** to collect results from the root level job, or the **Capture pipeline output and wait for pipeline completion** to collect results from all pipeline jobs. 

Results will be downloaded to the **$(Build.StagingDirectory)/jenkinsResults/Job Name/team-results.zip** and extracted to this location. Each set of result types collected by the plug-in, will be under the team-results directory, **$(Build.StagingDirectory)/jenkinsResults/Job Name/team-results/ResultType/**. This is the directory where build results can be published by downstream tasks (for example, Publish Test Results, and Publish Code Coverage Results).
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
| Agent version |  2.144.0 or greater |
| Task category | Build |

:::moniker-end

:::moniker range="<=azure-pipelines-2022"

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