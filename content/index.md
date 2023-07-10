---
title: YAML schema reference
description: Azure Pipelines YAML schema reference
ms.date: 07/10/2023
monikerRange: ">=azure-pipelines-2019"
---

# YAML schema reference for Azure Pipelines

The YAML schema reference for Azure Pipelines is a detailed reference for YAML pipelines that lists all supported YAML syntax and their available options.

To create a YAML pipeline, start with the [pipeline](pipeline.md#remarks) definition. For more information about building YAML pipelines, see [Customize your pipeline](/azure/devops/pipelines/customize-pipeline).

The YAML schema reference does not cover tasks. For more information about tasks, see the [Azure Pipelines tasks index](/azure/devops/pipelines/tasks/reference).

## Definitions

<!-- :::definitionIndex::: -->
<!-- :::item name="pipeline"::: -->
:::moniker range=">=azure-pipelines-2020"

[**pipeline**](pipeline.md)<br><!-- :::editable-content name="description"::: -->
A pipeline is one or more stages that describe a CI/CD process.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

[**pipeline**](pipeline.md)<br><!-- :::editable-content name="description"::: -->
A pipeline is one or more jobs that describe a CI/CD process.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="extends"::: -->
:::moniker range=">=azure-pipelines-2020"

[**extends**](extends.md)<br><!-- :::editable-content name="description"::: -->
Extends a pipeline using a template.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobs"::: -->
:::moniker range=">=azure-pipelines-2020"

[**jobs**](jobs.md)<br><!-- :::editable-content name="description"::: -->
Specifies the jobs that make up the work of a stage.
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

[**jobs**](jobs.md)<br><!-- :::editable-content name="description"::: -->
Specifies the jobs that make up the work of a pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobs.deployment"::: -->
:::moniker range=">=azure-pipelines-2020"

[**jobs.deployment**](jobs-deployment.md)<br><!-- :::editable-content name="description"::: -->
A deployment job is a special type of job. It's a collection of steps to run sequentially against the environment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobs.deployment.environment"::: -->
:::moniker range=">=azure-pipelines-2020"

[**jobs.deployment.environment**](jobs-deployment-environment.md)<br><!-- :::editable-content name="description"::: -->
Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobs.deployment.strategy"::: -->
:::moniker range=">=azure-pipelines-2020"

[**jobs.deployment.strategy**](jobs-deployment-strategy.md)<br><!-- :::editable-content name="description"::: -->
Execution strategy for this deployment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobs.deployment.strategy.canary"::: -->
:::moniker range=">=azure-pipelines-2020"

[**jobs.deployment.strategy.canary**](jobs-deployment-strategy-canary.md)<br><!-- :::editable-content name="description"::: -->
Canary Deployment strategy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobs.deployment.strategy.rolling"::: -->
:::moniker range=">=azure-pipelines-2020"

[**jobs.deployment.strategy.rolling**](jobs-deployment-strategy-rolling.md)<br><!-- :::editable-content name="description"::: -->
Rolling Deployment strategy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobs.deployment.strategy.runOnce"::: -->
:::moniker range=">=azure-pipelines-2020"

[**jobs.deployment.strategy.runOnce**](jobs-deployment-strategy-run-once.md)<br><!-- :::editable-content name="description"::: -->
RunOnce Deployment strategy.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobs.job"::: -->
:::moniker range=">=azure-pipelines-2019"

[**jobs.job**](jobs-job.md)<br><!-- :::editable-content name="description"::: -->
A job is a collection of steps run by an agent or on a server.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobs.job.container"::: -->
:::moniker range=">=azure-pipelines-2019.1"

[**jobs.job.container**](jobs-job-container.md)<br><!-- :::editable-content name="description"::: -->
Container resource name.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobs.job.strategy"::: -->
:::moniker range=">=azure-pipelines-2019"

[**jobs.job.strategy**](jobs-job-strategy.md)<br><!-- :::editable-content name="description"::: -->
Execution strategy for this job.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobs.job.uses"::: -->
:::moniker range=">=azure-pipelines-2020.1"

[**jobs.job.uses**](jobs-job-uses.md)<br><!-- :::editable-content name="description"::: -->
Any resources required by this job that are not already referenced.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="jobs.template"::: -->
:::moniker range=">=azure-pipelines-2020"

[**jobs.template**](jobs-template.md)<br><!-- :::editable-content name="description"::: -->
A set of jobs defined in a template.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parameters"::: -->
:::moniker range=">=azure-pipelines-2020"

[**parameters**](parameters.md)<br><!-- :::editable-content name="description"::: -->
Specifies the runtime parameters passed to a pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="parameters.parameter"::: -->
:::moniker range=">=azure-pipelines-2020"

[**parameters.parameter**](parameters-parameter.md)<br><!-- :::editable-content name="description"::: -->
Pipeline template parameters.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pool"::: -->
:::moniker range=">=azure-pipelines-2019"

[**pool**](pool.md)<br><!-- :::editable-content name="description"::: -->
Which pool to use for a job of the pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pool.demands"::: -->
:::moniker range=">=azure-pipelines-2019"

[**pool.demands**](pool-demands.md)<br><!-- :::editable-content name="description"::: -->
Demands (for a private pool).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="pr"::: -->
:::moniker range=">=azure-pipelines-2019"

[**pr**](pr.md)<br><!-- :::editable-content name="description"::: -->
Pull request trigger.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources"::: -->
:::moniker range=">=azure-pipelines-2019"

[**resources**](resources.md)<br><!-- :::editable-content name="description"::: -->
Resources specifies builds, repositories, pipelines, and other resources used by the pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.builds"::: -->
:::moniker range=">=azure-pipelines-2019"

[**resources.builds**](resources-builds.md)<br><!-- :::editable-content name="description"::: -->
List of build resources referenced by the pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.builds.build"::: -->
:::moniker range=">=azure-pipelines-2019"

[**resources.builds.build**](resources-builds-build.md)<br><!-- :::editable-content name="description"::: -->
A build resource used to reference artifacts from a run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.containers"::: -->
:::moniker range=">=azure-pipelines-2019"

[**resources.containers**](resources-containers.md)<br><!-- :::editable-content name="description"::: -->
List of container images.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.containers.container"::: -->
:::moniker range=">=azure-pipelines-2019"

[**resources.containers.container**](resources-containers-container.md)<br><!-- :::editable-content name="description"::: -->
A container resource used to reference a container image.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.containers.container.trigger"::: -->
:::moniker range=">=azure-pipelines-2020"

[**resources.containers.container.trigger**](resources-containers-container-trigger.md)<br><!-- :::editable-content name="description"::: -->
Specify none to disable, true to trigger on all image tags, or use the full syntax as described in the following examples.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.packages"::: -->
:::moniker range=">=azure-pipelines-2020"

[**resources.packages**](resources-packages.md)<br><!-- :::editable-content name="description"::: -->
List of package resources.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.packages.package"::: -->
:::moniker range=">=azure-pipelines-2020"

[**resources.packages.package**](resources-packages-package.md)<br><!-- :::editable-content name="description"::: -->
A package resource used to reference a NuGet or npm GitHub package.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.pipelines"::: -->
:::moniker range=">=azure-pipelines-2019"

[**resources.pipelines**](resources-pipelines.md)<br><!-- :::editable-content name="description"::: -->
List of pipeline resources.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.pipelines.pipeline"::: -->
:::moniker range=">=azure-pipelines-2019"

[**resources.pipelines.pipeline**](resources-pipelines-pipeline.md)<br><!-- :::editable-content name="description"::: -->
A pipeline resource.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.pipelines.pipeline.trigger"::: -->
:::moniker range=">=azure-pipelines-2020"

[**resources.pipelines.pipeline.trigger**](resources-pipelines-pipeline-trigger.md)<br><!-- :::editable-content name="description"::: -->
Specify none to disable, true to include all branches, or use the full syntax as described in the following examples.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.pipelines.pipeline.trigger.branches"::: -->
:::moniker range=">=azure-pipelines-2020"

[**resources.pipelines.pipeline.trigger.branches**](resources-pipelines-pipeline-trigger-branches.md)<br><!-- :::editable-content name="description"::: -->
Branches to include or exclude for triggering a run.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.repositories"::: -->
:::moniker range=">=azure-pipelines-2019"

[**resources.repositories**](resources-repositories.md)<br><!-- :::editable-content name="description"::: -->
List of repository resources.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.repositories.repository"::: -->
:::moniker range=">=azure-pipelines-2019"

[**resources.repositories.repository**](resources-repositories-repository.md)<br><!-- :::editable-content name="description"::: -->
A repository resource is used to reference an additional repository in your pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.webhooks"::: -->
:::moniker range=">=azure-pipelines-2020.1"

[**resources.webhooks**](resources-webhooks.md)<br><!-- :::editable-content name="description"::: -->
List of webhooks.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.webhooks.webhook"::: -->
:::moniker range=">=azure-pipelines-2020.1"

[**resources.webhooks.webhook**](resources-webhooks-webhook.md)<br><!-- :::editable-content name="description"::: -->
A webhook resource enables you to integrate your pipeline with an external service to automate the workflow.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.webhooks.webhook.filters"::: -->
:::moniker range=">=azure-pipelines-2020.1"

[**resources.webhooks.webhook.filters**](resources-webhooks-webhook-filters.md)<br><!-- :::editable-content name="description"::: -->
List of trigger filters.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="resources.webhooks.webhook.filters.filter"::: -->
:::moniker range=">=azure-pipelines-2020.1"

[**resources.webhooks.webhook.filters.filter**](resources-webhooks-webhook-filters-filter.md)<br><!-- :::editable-content name="description"::: -->
Webhook resource trigger filter.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="schedules"::: -->
:::moniker range=">=azure-pipelines-2020"

[**schedules**](schedules.md)<br><!-- :::editable-content name="description"::: -->
The schedules list specifies the scheduled triggers for the pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="schedules.cron"::: -->
:::moniker range=">=azure-pipelines-2020"

[**schedules.cron**](schedules-cron.md)<br><!-- :::editable-content name="description"::: -->
A scheduled trigger specifies a schedule on which branches are built.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="stages"::: -->
:::moniker range=">=azure-pipelines-2020"

[**stages**](stages.md)<br><!-- :::editable-content name="description"::: -->
Stages are a collection of related jobs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="stages.stage"::: -->
:::moniker range=">=azure-pipelines-2020"

[**stages.stage**](stages-stage.md)<br><!-- :::editable-content name="description"::: -->
A stage is a collection of related jobs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="stages.template"::: -->
:::moniker range=">=azure-pipelines-2020"

[**stages.template**](stages-template.md)<br><!-- :::editable-content name="description"::: -->
You can define a set of stages in one file and use it multiple times in other files.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="steps"::: -->
:::moniker range=">=azure-pipelines-2019"

[**steps**](steps.md)<br><!-- :::editable-content name="description"::: -->
Steps are a linear sequence of operations that make up a job.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="steps.bash"::: -->
:::moniker range=">=azure-pipelines-2019"

[**steps.bash**](steps-bash.md)<br><!-- :::editable-content name="description"::: -->
Runs a script in Bash on Windows, macOS, and Linux.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="steps.checkout"::: -->
:::moniker range=">=azure-pipelines-2019"

[**steps.checkout**](steps-checkout.md)<br><!-- :::editable-content name="description"::: -->
Configure how the pipeline checks out source code.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="steps.download"::: -->
:::moniker range=">=azure-pipelines-2019"

[**steps.download**](steps-download.md)<br><!-- :::editable-content name="description"::: -->
Downloads artifacts associated with the current run or from another Azure Pipeline that is associated as a pipeline resource.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="steps.downloadBuild"::: -->
:::moniker range=">=azure-pipelines-2019"

[**steps.downloadBuild**](steps-download-build.md)<br><!-- :::editable-content name="description"::: -->
Downloads build artifacts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="steps.getPackage"::: -->
:::moniker range=">=azure-pipelines-2020"

[**steps.getPackage**](steps-get-package.md)<br><!-- :::editable-content name="description"::: -->
Downloads a package from a package management feed in Azure Artifacts or Azure DevOps Server.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="steps.powershell"::: -->
:::moniker range=">=azure-pipelines-2019"

[**steps.powershell**](steps-powershell.md)<br><!-- :::editable-content name="description"::: -->
Runs a script using either Windows PowerShell (on Windows) or pwsh (Linux and macOS).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="steps.publish"::: -->
:::moniker range=">=azure-pipelines-2019"

[**steps.publish**](steps-publish.md)<br><!-- :::editable-content name="description"::: -->
Publishes (uploads) a file or folder as a pipeline artifact that other jobs and pipelines can consume.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="steps.pwsh"::: -->
:::moniker range=">=azure-pipelines-2019"

[**steps.pwsh**](steps-pwsh.md)<br><!-- :::editable-content name="description"::: -->
Runs a script in PowerShell Core on Windows, macOS, and Linux.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="steps.reviewApp"::: -->
:::moniker range=">=azure-pipelines-2020"

[**steps.reviewApp**](steps-review-app.md)<br><!-- :::editable-content name="description"::: -->
Downloads creates a resource dynamically under a deploy phase provider.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="steps.script"::: -->
:::moniker range=">=azure-pipelines-2019"

[**steps.script**](steps-script.md)<br><!-- :::editable-content name="description"::: -->
Runs a script using cmd.exe on Windows and Bash on other platforms.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="steps.task"::: -->
:::moniker range=">=azure-pipelines-2019"

[**steps.task**](steps-task.md)<br><!-- :::editable-content name="description"::: -->
Runs a task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="steps.template"::: -->
:::moniker range=">=azure-pipelines-2019"

[**steps.template**](steps-template.md)<br><!-- :::editable-content name="description"::: -->
Define a set of steps in one file and use it multiple times in another file.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="target"::: -->
:::moniker range=">=azure-pipelines-2020"

[**target**](target.md)<br><!-- :::editable-content name="description"::: -->
Tasks run in an execution context, which is either the agent host or a container.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="target.settableVariables"::: -->
:::moniker range=">=azure-pipelines-2022"

[**target.settableVariables**](target-settable-variables.md)<br><!-- :::editable-content name="description"::: -->
Restrictions on which variables that can be set.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
:::moniker range=">=azure-pipelines-2019"

[**trigger**](trigger.md)<br><!-- :::editable-content name="description"::: -->
Continuous integration (push) trigger.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="variables"::: -->
:::moniker range=">=azure-pipelines-2019"

[**variables**](variables.md)<br><!-- :::editable-content name="description"::: -->
Define variables using name/value pairs.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="variables.group"::: -->
:::moniker range=">=azure-pipelines-2019"

[**variables.group**](variables-group.md)<br><!-- :::editable-content name="description"::: -->
Reference variables from a variable group.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="variables.name"::: -->
:::moniker range=">=azure-pipelines-2019"

[**variables.name**](variables-name.md)<br><!-- :::editable-content name="description"::: -->
Define variables using name and full syntax.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="variables.template"::: -->
:::moniker range=">=azure-pipelines-2019"

[**variables.template**](variables-template.md)<br><!-- :::editable-content name="description"::: -->
Define variables in a template.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::definitionIndex-end::: -->

## Supporting definitions

> [!NOTE]
> Supporting definitions are not intended for use directly in a pipeline. Supporting definitions are used only as part of other definitions, and are included here for reference.

<!-- :::supportingDefinitionIndex::: -->
<!-- :::item name="deployHook"::: -->
:::moniker range=">=azure-pipelines-2020"

[**deployHook**](deploy-hook.md)<br><!-- :::editable-content name="description"::: -->
Used to run steps that deploy your application.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeExcludeFilters"::: -->
:::moniker range=">=azure-pipelines-2019"

[**includeExcludeFilters**](include-exclude-filters.md)<br><!-- :::editable-content name="description"::: -->
Lists of items to include or exclude.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="includeExcludeStringFilters"::: -->
:::moniker range=">=azure-pipelines-2020"

[**includeExcludeStringFilters**](include-exclude-string-filters.md)<br><!-- :::editable-content name="description"::: -->
Items to include or exclude.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="mountReadOnly"::: -->
:::moniker range=">=azure-pipelines-2020.1"

[**mountReadOnly**](mount-read-only.md)<br><!-- :::editable-content name="description"::: -->
Volumes to mount read-only, the default is all false.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="onFailureHook"::: -->
:::moniker range=">=azure-pipelines-2020"

[**onFailureHook**](on-failure-hook.md)<br><!-- :::editable-content name="description"::: -->
Used to run steps for rollback actions or clean-up.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="onSuccessHook"::: -->
:::moniker range=">=azure-pipelines-2020"

[**onSuccessHook**](on-success-hook.md)<br><!-- :::editable-content name="description"::: -->
Used to run steps for rollback actions or clean-up.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="onSuccessOrFailureHook"::: -->
:::moniker range=">=azure-pipelines-2020"

[**onSuccessOrFailureHook**](on-success-or-failure-hook.md)<br><!-- :::editable-content name="description"::: -->
Used to run steps for rollback actions or clean-up.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="postRouteTrafficHook"::: -->
:::moniker range=">=azure-pipelines-2020"

[**postRouteTrafficHook**](post-route-traffic-hook.md)<br><!-- :::editable-content name="description"::: -->
Used to run the steps after the traffic is routed. Typically, these tasks monitor the health of the updated version for defined interval.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="preDeployHook"::: -->
:::moniker range=">=azure-pipelines-2020"

[**preDeployHook**](pre-deploy-hook.md)<br><!-- :::editable-content name="description"::: -->
Used to run steps that initialize resources before application deployment starts.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="routeTrafficHook"::: -->
:::moniker range=">=azure-pipelines-2020"

[**routeTrafficHook**](route-traffic-hook.md)<br><!-- :::editable-content name="description"::: -->
Used to run steps that serve the traffic to the updated version.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workspace"::: -->
:::moniker range=">=azure-pipelines-2019"

[**workspace**](workspace.md)<br><!-- :::editable-content name="description"::: -->
Workspace options on the agent.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::supportingDefinitionIndex-end::: -->

## YAML schema documentation conventions

The YAML schema reference is a detailed reference guide to Azure Pipelines YAML pipelines.
It includes a catalog of all supported YAML capabilities and the available options.

Here are the syntax conventions used in the YAML schema reference.

* To the left of `:` is a literal keyword used in pipeline definitions.
* To the right of `:` is a data type.
  The data type can be a primitive type like **string** or a reference to a rich structure defined elsewhere in this reference.
* The notation `[` *datatype* `]` indicates an array of the mentioned definition type.
  For instance, `[ string ]` is an array of strings.
* The notation `{` *datatype* `:` *datatype* `}` indicates a mapping of one data type to another.
  For instance, `{ string: string }` is a mapping of strings to strings.
* The symbol `|` indicates there are multiple data types available for the keyword.
  For instance, `job | template` means either a job definition or a template reference is allowed.

## See also

This reference covers the schema of an Azure Pipelines YAML file.
To learn the basics of YAML, see [Learn YAML in Y Minutes](https://learnxinyminutes.com/docs/yaml/).
Azure Pipelines doesn't support all YAML features.
Unsupported features include anchors, complex keys, and sets.
Also, unlike standard YAML, Azure Pipelines depends on seeing `stage`, `job`, `task`, or a task shortcut like `script` as the first key in a mapping.

