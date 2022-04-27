---
ms.topic: include
ms.date: 04/26/2022
---

:::moniker range=" = azure-pipelines-2019"
:::row:::
:::column:::
[pipeline](../pipeline.md)
:::column-end:::
:::column span="3":::
A pipeline is one or more jobs that describe a CI/CD process.
:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs](../jobs.md)
:::column-end:::
:::column span="3":::
The jobs list specifies the jobs that make up the work of a stage.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.job](../jobs-job.md)
:::column-end:::
:::column span="3":::
A [job](/azure/devops/pipelines/process/phases) is a collection of steps run by an [agent](/azure/devops/pipelines/agents/agents) or on a [server](/azure/devops/pipelines/process/phases#server-jobs).

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.job.strategy](../jobs-job-strategy.md)
:::column-end:::
:::column span="3":::

The `matrix` and `parallel` keywords specify mutually exclusive strategies for duplicating a job.


:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[pool](../pool.md)
:::column-end:::
:::column span="3":::

The `pool` keyword specifies which [pool](/azure/devops/pipelines/agents/pools-queues) to use for a job of the pipeline.
A `pool` specification also holds information about the job's strategy for running.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[pr](../pr.md)
:::column-end:::
:::column span="3":::

A pull request trigger specifies which branches cause a pull request build to run.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources](../resources.md)
:::column-end:::
:::column span="3":::
Resources specifies builds, repositories, pipelines, and other resources used by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.builds](../resources-builds.md)
:::column-end:::
:::column span="3":::
List of build resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.builds.build](../resources-builds-build.md)
:::column-end:::
:::column span="3":::
If you have an external CI build system that produces artifacts, you can consume artifacts with a build resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.containers](../resources-containers.md)
:::column-end:::
:::column span="3":::
List of container resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.containers.container](../resources-containers-container.md)
:::column-end:::
:::column span="3":::
A container resource references a container image.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.pipelines](../resources-pipelines.md)
:::column-end:::
:::column span="3":::
List of pipeline resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.pipelines.pipeline](../resources-pipelines-pipeline.md)
:::column-end:::
:::column span="3":::
If you have an Azure pipeline that produces artifacts, your pipeline can consume the artifacts by defining a pipeline resource. In Azure DevOps Server 2020 and higher, you can also enable [pipeline completion triggers](/azure/devops/pipelines/process/pipeline-triggers) using a pipeline resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.repositories](../resources-repositories.md)
:::column-end:::
:::column span="3":::
List of repository resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.repositories.repository](../resources-repositories-repository.md)
:::column-end:::
:::column span="3":::
The `repository` keyword lets you specify an external repository.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps](../steps.md)
:::column-end:::
:::column span="3":::
Steps are a linear sequence of operations that make up a job.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.bash](../steps-bash.md)
:::column-end:::
:::column span="3":::
The `bash` step runs a script in Bash on Windows, macOS, and Linux.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.checkout](../steps-checkout.md)
:::column-end:::
:::column span="3":::
Use `checkout` to configure how the pipeline checks out source code.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.download](../steps-download.md)
:::column-end:::
:::column span="3":::
The `download` step downloads artifacts associated with the current run or from another Azure pipeline that is associated as a pipeline resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.downloadBuild](../steps-download-build.md)
:::column-end:::
:::column span="3":::
The `downloadBuild` step downloads build artifacts.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.powershell](../steps-powershell.md)
:::column-end:::
:::column span="3":::
The `powershell` step runs a script in Windows PowerShell.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.publish](../steps-publish.md)
:::column-end:::
:::column span="3":::
The `publish` keyword publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.pwsh](../steps-pwsh.md)
:::column-end:::
:::column span="3":::
The `pwsh` step runs a script in PowerShell Core on Windows, macOS, and Linux.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.restoreCache](../steps-restore-cache.md)
:::column-end:::
:::column span="3":::
The `restoreCache` step restores a cache.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.saveCache](../steps-save-cache.md)
:::column-end:::
:::column span="3":::
The `saveCache` step saves a cache.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.script](../steps-script.md)
:::column-end:::
:::column span="3":::
The `script` step runs a script using cmd.exe on Windows and Bash on other platforms.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.task](../steps-task.md)
:::column-end:::
:::column span="3":::
A `task` step runs a task.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.template](../steps-template.md)
:::column-end:::
:::column span="3":::
You can define a set of steps in one file and use it multiple times in another file.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[trigger](../trigger.md)
:::column-end:::
:::column span="3":::

A push trigger specifies which branches cause a continuous integration build to run.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables](../variables.md)
:::column-end:::
:::column span="3":::
Define variables to use in your pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.group](../variables-group.md)
:::column-end:::
:::column span="3":::
Reference variables from a variable group.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.name](../variables-name.md)
:::column-end:::
:::column span="3":::
Define variables using the full syntax.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.template](../variables-template.md)
:::column-end:::
:::column span="3":::
You can define a set of variables in one file and use it multiple times in other files.

:::column-end:::
:::row-end:::
___
:::moniker-end

:::moniker range=" = azure-pipelines-2019.1"
:::row:::
:::column:::
[pipeline](../pipeline.md)
:::column-end:::
:::column span="3":::
A pipeline is one or more jobs that describe a CI/CD process.
:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs](../jobs.md)
:::column-end:::
:::column span="3":::
The jobs list specifies the jobs that make up the work of a stage.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.job](../jobs-job.md)
:::column-end:::
:::column span="3":::
A [job](/azure/devops/pipelines/process/phases) is a collection of steps run by an [agent](/azure/devops/pipelines/agents/agents) or on a [server](/azure/devops/pipelines/process/phases#server-jobs).

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.job.container](../jobs-job-container.md)
:::column-end:::
:::column span="3":::
Container jobs allow you to run jobs on a container instead of the agent host.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.job.strategy](../jobs-job-strategy.md)
:::column-end:::
:::column span="3":::

The `matrix` and `parallel` keywords specify mutually exclusive strategies for duplicating a job.


:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[pool](../pool.md)
:::column-end:::
:::column span="3":::

The `pool` keyword specifies which [pool](/azure/devops/pipelines/agents/pools-queues) to use for a job of the pipeline.
A `pool` specification also holds information about the job's strategy for running.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[pr](../pr.md)
:::column-end:::
:::column span="3":::

A pull request trigger specifies which branches cause a pull request build to run.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources](../resources.md)
:::column-end:::
:::column span="3":::
Resources specifies builds, repositories, pipelines, and other resources used by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.builds](../resources-builds.md)
:::column-end:::
:::column span="3":::
List of build resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.builds.build](../resources-builds-build.md)
:::column-end:::
:::column span="3":::
If you have an external CI build system that produces artifacts, you can consume artifacts with a build resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.containers](../resources-containers.md)
:::column-end:::
:::column span="3":::
List of container resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.containers.container](../resources-containers-container.md)
:::column-end:::
:::column span="3":::
A container resource references a container image.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.pipelines](../resources-pipelines.md)
:::column-end:::
:::column span="3":::
List of pipeline resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.pipelines.pipeline](../resources-pipelines-pipeline.md)
:::column-end:::
:::column span="3":::
If you have an Azure pipeline that produces artifacts, your pipeline can consume the artifacts by defining a pipeline resource. In Azure DevOps Server 2020 and higher, you can also enable [pipeline completion triggers](/azure/devops/pipelines/process/pipeline-triggers) using a pipeline resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.repositories](../resources-repositories.md)
:::column-end:::
:::column span="3":::
List of repository resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.repositories.repository](../resources-repositories-repository.md)
:::column-end:::
:::column span="3":::
The `repository` keyword lets you specify an external repository.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps](../steps.md)
:::column-end:::
:::column span="3":::
Steps are a linear sequence of operations that make up a job.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.bash](../steps-bash.md)
:::column-end:::
:::column span="3":::
The `bash` step runs a script in Bash on Windows, macOS, and Linux.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.checkout](../steps-checkout.md)
:::column-end:::
:::column span="3":::
Use `checkout` to configure how the pipeline checks out source code.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.download](../steps-download.md)
:::column-end:::
:::column span="3":::
The `download` step downloads artifacts associated with the current run or from another Azure pipeline that is associated as a pipeline resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.downloadBuild](../steps-download-build.md)
:::column-end:::
:::column span="3":::
The `downloadBuild` step downloads build artifacts.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.powershell](../steps-powershell.md)
:::column-end:::
:::column span="3":::
The `powershell` step runs a script in Windows PowerShell.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.publish](../steps-publish.md)
:::column-end:::
:::column span="3":::
The `publish` keyword publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.pwsh](../steps-pwsh.md)
:::column-end:::
:::column span="3":::
The `pwsh` step runs a script in PowerShell Core on Windows, macOS, and Linux.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.restoreCache](../steps-restore-cache.md)
:::column-end:::
:::column span="3":::
The `restoreCache` step restores a cache.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.saveCache](../steps-save-cache.md)
:::column-end:::
:::column span="3":::
The `saveCache` step saves a cache.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.script](../steps-script.md)
:::column-end:::
:::column span="3":::
The `script` step runs a script using cmd.exe on Windows and Bash on other platforms.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.task](../steps-task.md)
:::column-end:::
:::column span="3":::
A `task` step runs a task.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.template](../steps-template.md)
:::column-end:::
:::column span="3":::
You can define a set of steps in one file and use it multiple times in another file.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[trigger](../trigger.md)
:::column-end:::
:::column span="3":::

A push trigger specifies which branches cause a continuous integration build to run.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables](../variables.md)
:::column-end:::
:::column span="3":::
Define variables to use in your pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.group](../variables-group.md)
:::column-end:::
:::column span="3":::
Reference variables from a variable group.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.name](../variables-name.md)
:::column-end:::
:::column span="3":::
Define variables using the full syntax.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.template](../variables-template.md)
:::column-end:::
:::column span="3":::
You can define a set of variables in one file and use it multiple times in other files.

:::column-end:::
:::row-end:::
___
:::moniker-end

:::moniker range=" = azure-pipelines-2020"
:::row:::
:::column:::
[pipeline](../pipeline.md)
:::column-end:::
:::column span="3":::
A pipeline is one or more stages that describe a CI/CD process.
:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[extends](../extends.md)
:::column-end:::
:::column span="3":::
Extends a pipeline using a template.
:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs](../jobs.md)
:::column-end:::
:::column span="3":::
The jobs list specifies the jobs that make up the work of a stage.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment](../jobs-deployment.md)
:::column-end:::
:::column span="3":::

A [deployment job](/azure/devops/pipelines/process/deployment-jobs) is a special type of job.
It's a collection of steps to run sequentially against the environment.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.environment](../jobs-deployment-environment.md)
:::column-end:::
:::column span="3":::
The `environment` keyword specifies the [environment](/azure/devops/pipelines/process/environments) or its resource that is targeted by a deployment job of the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.strategy](../jobs-deployment-strategy.md)
:::column-end:::
:::column span="3":::
A deployment strategy enables you to configure how the update is delivered.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.strategy.canary](../jobs-deployment-strategy-canary.md)
:::column-end:::
:::column span="3":::
Canary deployment strategy rolls out changes to a small subset of servers.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.strategy.rolling](../jobs-deployment-strategy-rolling.md)
:::column-end:::
:::column span="3":::
A rolling deployment replaces instances of the previous version of an application with instances of the new version of the application on a fixed set of virtual machines (rolling set) in each iteration. 

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.strategy.runOnce](../jobs-deployment-strategy-run-once.md)
:::column-end:::
:::column span="3":::
The runOnce deployment strategy rolls out changes by executing each of its steps one time.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.job](../jobs-job.md)
:::column-end:::
:::column span="3":::
A [job](/azure/devops/pipelines/process/phases) is a collection of steps run by an [agent](/azure/devops/pipelines/agents/agents) or on a [server](/azure/devops/pipelines/process/phases#server-jobs).

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.job.container](../jobs-job-container.md)
:::column-end:::
:::column span="3":::
Container jobs allow you to run jobs on a container instead of the agent host.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.job.strategy](../jobs-job-strategy.md)
:::column-end:::
:::column span="3":::

The `matrix` and `parallel` keywords specify mutually exclusive strategies for duplicating a job.


:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.template](../jobs-template.md)
:::column-end:::
:::column span="3":::

You can define a set of jobs in one file and use it multiple times in other files. See [templates](/azure/devops/pipelines/process/templates) for more about working with job templates.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[parameters](../parameters.md)
:::column-end:::
:::column span="3":::
The parameters list specifies the runtime parameters passed to a pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[parameters.name](../parameters-name.md)
:::column-end:::
:::column span="3":::
A parameter represents a value passed to a pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[pool](../pool.md)
:::column-end:::
:::column span="3":::

The `pool` keyword specifies which [pool](/azure/devops/pipelines/agents/pools-queues) to use for a job of the pipeline.
A `pool` specification also holds information about the job's strategy for running.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[pr](../pr.md)
:::column-end:::
:::column span="3":::

A pull request trigger specifies which branches cause a pull request build to run.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources](../resources.md)
:::column-end:::
:::column span="3":::
Resources specifies builds, repositories, pipelines, and other resources used by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.builds](../resources-builds.md)
:::column-end:::
:::column span="3":::
List of build resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.builds.build](../resources-builds-build.md)
:::column-end:::
:::column span="3":::
If you have an external CI build system that produces artifacts, you can consume artifacts with a build resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.containers](../resources-containers.md)
:::column-end:::
:::column span="3":::
List of container resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.containers.container](../resources-containers-container.md)
:::column-end:::
:::column span="3":::
A container resource references a container image.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.packages](../resources-packages.md)
:::column-end:::
:::column span="3":::
List of package resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.packages.package](../resources-packages-package.md)
:::column-end:::
:::column span="3":::
You can consume NuGet and npm GitHub packages as a resource in YAML pipelines. When specifying package resources, set the package as `NuGet` or `npm`. 

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.pipelines](../resources-pipelines.md)
:::column-end:::
:::column span="3":::
List of pipeline resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.pipelines.pipeline](../resources-pipelines-pipeline.md)
:::column-end:::
:::column span="3":::
If you have an Azure pipeline that produces artifacts, your pipeline can consume the artifacts by defining a pipeline resource. In Azure DevOps Server 2020 and higher, you can also enable [pipeline completion triggers](/azure/devops/pipelines/process/pipeline-triggers) using a pipeline resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.repositories](../resources-repositories.md)
:::column-end:::
:::column span="3":::
List of repository resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.repositories.repository](../resources-repositories-repository.md)
:::column-end:::
:::column span="3":::
The `repository` keyword lets you specify an external repository.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[schedules](../schedules.md)
:::column-end:::
:::column span="3":::
The schedules list specifies the scheduled triggers for the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[schedules.cron](../schedules-cron.md)
:::column-end:::
:::column span="3":::
A scheduled trigger specifies a schedule on which branches are built.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[stages](../stages.md)
:::column-end:::
:::column span="3":::
Stages are a collection of related jobs. 

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[stages.stage](../stages-stage.md)
:::column-end:::
:::column span="3":::
Stages are a collection of related jobs. By default, stages run sequentially. Each stage starts only after the preceding stage is complete unless otherwise specified via the `dependsOn` property.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[stages.template](../stages-template.md)
:::column-end:::
:::column span="3":::
You can define a set of stages in one file and use it multiple times in other files.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps](../steps.md)
:::column-end:::
:::column span="3":::
Steps are a linear sequence of operations that make up a job.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.bash](../steps-bash.md)
:::column-end:::
:::column span="3":::
The `bash` step runs a script in Bash on Windows, macOS, and Linux.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.checkout](../steps-checkout.md)
:::column-end:::
:::column span="3":::
Use `checkout` to configure how the pipeline checks out source code.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.download](../steps-download.md)
:::column-end:::
:::column span="3":::
The `download` step downloads artifacts associated with the current run or from another Azure pipeline that is associated as a pipeline resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.downloadBuild](../steps-download-build.md)
:::column-end:::
:::column span="3":::
The `downloadBuild` step downloads build artifacts.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.getPackage](../steps-get-package.md)
:::column-end:::
:::column span="3":::
The `getPackage` step downloads a package from a package management feed in Azure Artifacts or Azure DevOps Server.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.powershell](../steps-powershell.md)
:::column-end:::
:::column span="3":::
The `powershell` step runs a script in Windows PowerShell.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.publish](../steps-publish.md)
:::column-end:::
:::column span="3":::
The `publish` keyword publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.pwsh](../steps-pwsh.md)
:::column-end:::
:::column span="3":::
The `pwsh` step runs a script in PowerShell Core on Windows, macOS, and Linux.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.restoreCache](../steps-restore-cache.md)
:::column-end:::
:::column span="3":::
The `restoreCache` step restores a cache.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.reviewApp](../steps-review-app.md)
:::column-end:::
:::column span="3":::
The `reviewApp` step downloads creates a resource dynamically under a deploy phase provider.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.saveCache](../steps-save-cache.md)
:::column-end:::
:::column span="3":::
The `saveCache` step saves a cache.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.script](../steps-script.md)
:::column-end:::
:::column span="3":::
The `script` step runs a script using cmd.exe on Windows and Bash on other platforms.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.task](../steps-task.md)
:::column-end:::
:::column span="3":::
A `task` step runs a task.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.template](../steps-template.md)
:::column-end:::
:::column span="3":::
You can define a set of steps in one file and use it multiple times in another file.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[target](../target.md)
:::column-end:::
:::column span="3":::
Tasks run in an execution context, which is either the agent host or a container.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[trigger](../trigger.md)
:::column-end:::
:::column span="3":::

A push trigger specifies which branches cause a continuous integration build to run.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables](../variables.md)
:::column-end:::
:::column span="3":::
Define variables to use in your pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.group](../variables-group.md)
:::column-end:::
:::column span="3":::
Reference variables from a variable group.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.name](../variables-name.md)
:::column-end:::
:::column span="3":::
Define variables using the full syntax.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.template](../variables-template.md)
:::column-end:::
:::column span="3":::
You can define a set of variables in one file and use it multiple times in other files.

:::column-end:::
:::row-end:::
___
:::moniker-end

:::moniker range=" = azure-pipelines-2020.1"
:::row:::
:::column:::
[pipeline](../pipeline.md)
:::column-end:::
:::column span="3":::
A pipeline is one or more stages that describe a CI/CD process.
:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[extends](../extends.md)
:::column-end:::
:::column span="3":::
Extends a pipeline using a template.
:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs](../jobs.md)
:::column-end:::
:::column span="3":::
The jobs list specifies the jobs that make up the work of a stage.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment](../jobs-deployment.md)
:::column-end:::
:::column span="3":::

A [deployment job](/azure/devops/pipelines/process/deployment-jobs) is a special type of job.
It's a collection of steps to run sequentially against the environment.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.environment](../jobs-deployment-environment.md)
:::column-end:::
:::column span="3":::
The `environment` keyword specifies the [environment](/azure/devops/pipelines/process/environments) or its resource that is targeted by a deployment job of the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.strategy](../jobs-deployment-strategy.md)
:::column-end:::
:::column span="3":::
A deployment strategy enables you to configure how the update is delivered.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.strategy.canary](../jobs-deployment-strategy-canary.md)
:::column-end:::
:::column span="3":::
Canary deployment strategy rolls out changes to a small subset of servers.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.strategy.rolling](../jobs-deployment-strategy-rolling.md)
:::column-end:::
:::column span="3":::
A rolling deployment replaces instances of the previous version of an application with instances of the new version of the application on a fixed set of virtual machines (rolling set) in each iteration. 

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.strategy.runOnce](../jobs-deployment-strategy-run-once.md)
:::column-end:::
:::column span="3":::
The runOnce deployment strategy rolls out changes by executing each of its steps one time.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.job](../jobs-job.md)
:::column-end:::
:::column span="3":::
A [job](/azure/devops/pipelines/process/phases) is a collection of steps run by an [agent](/azure/devops/pipelines/agents/agents) or on a [server](/azure/devops/pipelines/process/phases#server-jobs).

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.job.container](../jobs-job-container.md)
:::column-end:::
:::column span="3":::
Container jobs allow you to run jobs on a container instead of the agent host.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.job.strategy](../jobs-job-strategy.md)
:::column-end:::
:::column span="3":::

The `matrix` and `parallel` keywords specify mutually exclusive strategies for duplicating a job.


:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.template](../jobs-template.md)
:::column-end:::
:::column span="3":::

You can define a set of jobs in one file and use it multiple times in other files. See [templates](/azure/devops/pipelines/process/templates) for more about working with job templates.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[parameters](../parameters.md)
:::column-end:::
:::column span="3":::
The parameters list specifies the runtime parameters passed to a pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[parameters.name](../parameters-name.md)
:::column-end:::
:::column span="3":::
A parameter represents a value passed to a pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[pool](../pool.md)
:::column-end:::
:::column span="3":::

The `pool` keyword specifies which [pool](/azure/devops/pipelines/agents/pools-queues) to use for a job of the pipeline.
A `pool` specification also holds information about the job's strategy for running.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[pr](../pr.md)
:::column-end:::
:::column span="3":::

A pull request trigger specifies which branches cause a pull request build to run.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources](../resources.md)
:::column-end:::
:::column span="3":::
Resources specifies builds, repositories, pipelines, and other resources used by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.builds](../resources-builds.md)
:::column-end:::
:::column span="3":::
List of build resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.builds.build](../resources-builds-build.md)
:::column-end:::
:::column span="3":::
If you have an external CI build system that produces artifacts, you can consume artifacts with a build resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.containers](../resources-containers.md)
:::column-end:::
:::column span="3":::
List of container resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.containers.container](../resources-containers-container.md)
:::column-end:::
:::column span="3":::
A container resource references a container image.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.packages](../resources-packages.md)
:::column-end:::
:::column span="3":::
List of package resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.packages.package](../resources-packages-package.md)
:::column-end:::
:::column span="3":::
You can consume NuGet and npm GitHub packages as a resource in YAML pipelines. When specifying package resources, set the package as `NuGet` or `npm`. 

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.pipelines](../resources-pipelines.md)
:::column-end:::
:::column span="3":::
List of pipeline resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.pipelines.pipeline](../resources-pipelines-pipeline.md)
:::column-end:::
:::column span="3":::
If you have an Azure pipeline that produces artifacts, your pipeline can consume the artifacts by defining a pipeline resource. In Azure DevOps Server 2020 and higher, you can also enable [pipeline completion triggers](/azure/devops/pipelines/process/pipeline-triggers) using a pipeline resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.repositories](../resources-repositories.md)
:::column-end:::
:::column span="3":::
List of repository resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.repositories.repository](../resources-repositories-repository.md)
:::column-end:::
:::column span="3":::
The `repository` keyword lets you specify an external repository.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.webhooks](../resources-webhooks.md)
:::column-end:::
:::column span="3":::
List of webhook resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.webhooks.webhook](../resources-webhooks-webhook.md)
:::column-end:::
:::column span="3":::
A webhook resource enables you to integrate your pipeline with an external service to automate the workflow.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.webhooks.webhook.filters](../resources-webhooks-webhook-filters.md)
:::column-end:::
:::column span="3":::
Filters used to customize the triggers for a webhook event.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.webhooks.webhook.filters.path](../resources-webhooks-webhook-filters-path.md)
:::column-end:::
:::column span="3":::
A webhook filter is used to customize the triggers for a webhook event.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[schedules](../schedules.md)
:::column-end:::
:::column span="3":::
The schedules list specifies the scheduled triggers for the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[schedules.cron](../schedules-cron.md)
:::column-end:::
:::column span="3":::
A scheduled trigger specifies a schedule on which branches are built.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[stages](../stages.md)
:::column-end:::
:::column span="3":::
Stages are a collection of related jobs. 

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[stages.stage](../stages-stage.md)
:::column-end:::
:::column span="3":::
Stages are a collection of related jobs. By default, stages run sequentially. Each stage starts only after the preceding stage is complete unless otherwise specified via the `dependsOn` property.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[stages.template](../stages-template.md)
:::column-end:::
:::column span="3":::
You can define a set of stages in one file and use it multiple times in other files.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps](../steps.md)
:::column-end:::
:::column span="3":::
Steps are a linear sequence of operations that make up a job.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.bash](../steps-bash.md)
:::column-end:::
:::column span="3":::
The `bash` step runs a script in Bash on Windows, macOS, and Linux.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.checkout](../steps-checkout.md)
:::column-end:::
:::column span="3":::
Use `checkout` to configure how the pipeline checks out source code.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.download](../steps-download.md)
:::column-end:::
:::column span="3":::
The `download` step downloads artifacts associated with the current run or from another Azure pipeline that is associated as a pipeline resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.downloadBuild](../steps-download-build.md)
:::column-end:::
:::column span="3":::
The `downloadBuild` step downloads build artifacts.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.getPackage](../steps-get-package.md)
:::column-end:::
:::column span="3":::
The `getPackage` step downloads a package from a package management feed in Azure Artifacts or Azure DevOps Server.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.powershell](../steps-powershell.md)
:::column-end:::
:::column span="3":::
The `powershell` step runs a script in Windows PowerShell.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.publish](../steps-publish.md)
:::column-end:::
:::column span="3":::
The `publish` keyword publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.pwsh](../steps-pwsh.md)
:::column-end:::
:::column span="3":::
The `pwsh` step runs a script in PowerShell Core on Windows, macOS, and Linux.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.restoreCache](../steps-restore-cache.md)
:::column-end:::
:::column span="3":::
The `restoreCache` step restores a cache.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.reviewApp](../steps-review-app.md)
:::column-end:::
:::column span="3":::
The `reviewApp` step downloads creates a resource dynamically under a deploy phase provider.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.saveCache](../steps-save-cache.md)
:::column-end:::
:::column span="3":::
The `saveCache` step saves a cache.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.script](../steps-script.md)
:::column-end:::
:::column span="3":::
The `script` step runs a script using cmd.exe on Windows and Bash on other platforms.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.task](../steps-task.md)
:::column-end:::
:::column span="3":::
A `task` step runs a task.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.template](../steps-template.md)
:::column-end:::
:::column span="3":::
You can define a set of steps in one file and use it multiple times in another file.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[target](../target.md)
:::column-end:::
:::column span="3":::
Tasks run in an execution context, which is either the agent host or a container.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[trigger](../trigger.md)
:::column-end:::
:::column span="3":::

A push trigger specifies which branches cause a continuous integration build to run.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables](../variables.md)
:::column-end:::
:::column span="3":::
Define variables to use in your pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.group](../variables-group.md)
:::column-end:::
:::column span="3":::
Reference variables from a variable group.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.name](../variables-name.md)
:::column-end:::
:::column span="3":::
Define variables using the full syntax.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.template](../variables-template.md)
:::column-end:::
:::column span="3":::
You can define a set of variables in one file and use it multiple times in other files.

:::column-end:::
:::row-end:::
___
:::moniker-end

:::moniker range=" = azure-pipelines"
:::row:::
:::column:::
[pipeline](../pipeline.md)
:::column-end:::
:::column span="3":::
A pipeline is one or more stages that describe a CI/CD process.
:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[extends](../extends.md)
:::column-end:::
:::column span="3":::
Extends a pipeline using a template.
:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs](../jobs.md)
:::column-end:::
:::column span="3":::
The jobs list specifies the jobs that make up the work of a stage.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment](../jobs-deployment.md)
:::column-end:::
:::column span="3":::

A [deployment job](/azure/devops/pipelines/process/deployment-jobs) is a special type of job.
It's a collection of steps to run sequentially against the environment.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.environment](../jobs-deployment-environment.md)
:::column-end:::
:::column span="3":::
The `environment` keyword specifies the [environment](/azure/devops/pipelines/process/environments) or its resource that is targeted by a deployment job of the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.strategy](../jobs-deployment-strategy.md)
:::column-end:::
:::column span="3":::
A deployment strategy enables you to configure how the update is delivered.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.strategy.canary](../jobs-deployment-strategy-canary.md)
:::column-end:::
:::column span="3":::
Canary deployment strategy rolls out changes to a small subset of servers.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.strategy.rolling](../jobs-deployment-strategy-rolling.md)
:::column-end:::
:::column span="3":::
A rolling deployment replaces instances of the previous version of an application with instances of the new version of the application on a fixed set of virtual machines (rolling set) in each iteration. 

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.deployment.strategy.runOnce](../jobs-deployment-strategy-run-once.md)
:::column-end:::
:::column span="3":::
The runOnce deployment strategy rolls out changes by executing each of its steps one time.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.job](../jobs-job.md)
:::column-end:::
:::column span="3":::
A [job](/azure/devops/pipelines/process/phases) is a collection of steps run by an [agent](/azure/devops/pipelines/agents/agents) or on a [server](/azure/devops/pipelines/process/phases#server-jobs).

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.job.container](../jobs-job-container.md)
:::column-end:::
:::column span="3":::
Container jobs allow you to run jobs on a container instead of the agent host.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.job.strategy](../jobs-job-strategy.md)
:::column-end:::
:::column span="3":::

The `matrix` and `parallel` keywords specify mutually exclusive strategies for duplicating a job.


:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[jobs.template](../jobs-template.md)
:::column-end:::
:::column span="3":::

You can define a set of jobs in one file and use it multiple times in other files. See [templates](/azure/devops/pipelines/process/templates) for more about working with job templates.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[parameters](../parameters.md)
:::column-end:::
:::column span="3":::
The parameters list specifies the runtime parameters passed to a pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[parameters.name](../parameters-name.md)
:::column-end:::
:::column span="3":::
A parameter represents a value passed to a pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[pool](../pool.md)
:::column-end:::
:::column span="3":::

The `pool` keyword specifies which [pool](/azure/devops/pipelines/agents/pools-queues) to use for a job of the pipeline.
A `pool` specification also holds information about the job's strategy for running.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[pr](../pr.md)
:::column-end:::
:::column span="3":::

A pull request trigger specifies which branches cause a pull request build to run.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources](../resources.md)
:::column-end:::
:::column span="3":::
Resources specifies builds, repositories, pipelines, and other resources used by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.builds](../resources-builds.md)
:::column-end:::
:::column span="3":::
List of build resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.builds.build](../resources-builds-build.md)
:::column-end:::
:::column span="3":::
If you have an external CI build system that produces artifacts, you can consume artifacts with a build resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.containers](../resources-containers.md)
:::column-end:::
:::column span="3":::
List of container resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.containers.container](../resources-containers-container.md)
:::column-end:::
:::column span="3":::
A container resource references a container image.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.packages](../resources-packages.md)
:::column-end:::
:::column span="3":::
List of package resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.packages.package](../resources-packages-package.md)
:::column-end:::
:::column span="3":::
You can consume NuGet and npm GitHub packages as a resource in YAML pipelines. When specifying package resources, set the package as `NuGet` or `npm`. 

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.pipelines](../resources-pipelines.md)
:::column-end:::
:::column span="3":::
List of pipeline resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.pipelines.pipeline](../resources-pipelines-pipeline.md)
:::column-end:::
:::column span="3":::
If you have an Azure pipeline that produces artifacts, your pipeline can consume the artifacts by defining a pipeline resource. In Azure DevOps Server 2020 and higher, you can also enable [pipeline completion triggers](/azure/devops/pipelines/process/pipeline-triggers) using a pipeline resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.repositories](../resources-repositories.md)
:::column-end:::
:::column span="3":::
List of repository resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.repositories.repository](../resources-repositories-repository.md)
:::column-end:::
:::column span="3":::
The `repository` keyword lets you specify an external repository.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.webhooks](../resources-webhooks.md)
:::column-end:::
:::column span="3":::
List of webhook resources referenced by the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.webhooks.webhook](../resources-webhooks-webhook.md)
:::column-end:::
:::column span="3":::
A webhook resource enables you to integrate your pipeline with an external service to automate the workflow.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.webhooks.webhook.filters](../resources-webhooks-webhook-filters.md)
:::column-end:::
:::column span="3":::
Filters used to customize the triggers for a webhook event.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[resources.webhooks.webhook.filters.path](../resources-webhooks-webhook-filters-path.md)
:::column-end:::
:::column span="3":::
A webhook filter is used to customize the triggers for a webhook event.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[schedules](../schedules.md)
:::column-end:::
:::column span="3":::
The schedules list specifies the scheduled triggers for the pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[schedules.cron](../schedules-cron.md)
:::column-end:::
:::column span="3":::
A scheduled trigger specifies a schedule on which branches are built.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[stages](../stages.md)
:::column-end:::
:::column span="3":::
Stages are a collection of related jobs. 

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[stages.stage](../stages-stage.md)
:::column-end:::
:::column span="3":::
Stages are a collection of related jobs. By default, stages run sequentially. Each stage starts only after the preceding stage is complete unless otherwise specified via the `dependsOn` property.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[stages.template](../stages-template.md)
:::column-end:::
:::column span="3":::
You can define a set of stages in one file and use it multiple times in other files.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps](../steps.md)
:::column-end:::
:::column span="3":::
Steps are a linear sequence of operations that make up a job.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.bash](../steps-bash.md)
:::column-end:::
:::column span="3":::
The `bash` step runs a script in Bash on Windows, macOS, and Linux.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.checkout](../steps-checkout.md)
:::column-end:::
:::column span="3":::
Use `checkout` to configure how the pipeline checks out source code.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.download](../steps-download.md)
:::column-end:::
:::column span="3":::
The `download` step downloads artifacts associated with the current run or from another Azure pipeline that is associated as a pipeline resource.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.downloadBuild](../steps-download-build.md)
:::column-end:::
:::column span="3":::
The `downloadBuild` step downloads build artifacts.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.getPackage](../steps-get-package.md)
:::column-end:::
:::column span="3":::
The `getPackage` step downloads a package from a package management feed in Azure Artifacts or Azure DevOps Server.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.powershell](../steps-powershell.md)
:::column-end:::
:::column span="3":::
The `powershell` step runs a script in Windows PowerShell.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.publish](../steps-publish.md)
:::column-end:::
:::column span="3":::
The `publish` keyword publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.pwsh](../steps-pwsh.md)
:::column-end:::
:::column span="3":::
The `pwsh` step runs a script in PowerShell Core on Windows, macOS, and Linux.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.restoreCache](../steps-restore-cache.md)
:::column-end:::
:::column span="3":::
The `restoreCache` step restores a cache.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.reviewApp](../steps-review-app.md)
:::column-end:::
:::column span="3":::
The `reviewApp` step downloads creates a resource dynamically under a deploy phase provider.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.saveCache](../steps-save-cache.md)
:::column-end:::
:::column span="3":::
The `saveCache` step saves a cache.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.script](../steps-script.md)
:::column-end:::
:::column span="3":::
The `script` step runs a script using cmd.exe on Windows and Bash on other platforms.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.task](../steps-task.md)
:::column-end:::
:::column span="3":::
A `task` step runs a task.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[steps.template](../steps-template.md)
:::column-end:::
:::column span="3":::
You can define a set of steps in one file and use it multiple times in another file.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[target](../target.md)
:::column-end:::
:::column span="3":::
Tasks run in an execution context, which is either the agent host or a container.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[target.settableVariables](../target-settable-variables.md)
:::column-end:::
:::column span="3":::
Variables that can be set by a step.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[trigger](../trigger.md)
:::column-end:::
:::column span="3":::

A push trigger specifies which branches cause a continuous integration build to run.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables](../variables.md)
:::column-end:::
:::column span="3":::
Define variables to use in your pipeline.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.group](../variables-group.md)
:::column-end:::
:::column span="3":::
Reference variables from a variable group.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.name](../variables-name.md)
:::column-end:::
:::column span="3":::
Define variables using the full syntax.

:::column-end:::
:::row-end:::
___
:::row:::
:::column:::
[variables.template](../variables-template.md)
:::column-end:::
:::column span="3":::
You can define a set of variables in one file and use it multiple times in other files.

:::column-end:::
:::row-end:::
___
:::moniker-end

