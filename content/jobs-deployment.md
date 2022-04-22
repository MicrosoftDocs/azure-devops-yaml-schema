---
title: jobs.deployment definition
description: jobs.deployment definition reference.
ms.date: 04/22/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# jobs.deployment definition



A [deployment job](/azure/devops/pipelines/process/deployment-jobs) is a special type of job.
It's a collection of steps to run sequentially against the environment.
In YAML pipelines, we recommend that you put your deployment steps in a deployment job.


:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="job{deployment}" version="azure-pipelines-2020"::: -->

```yaml
jobs:
- deployment: string # Required as first property. Name of the deployment job, A-Z, a-z, 0-9, and underscore. The word deploy is a keyword and is unsupported as the deployment name.. 
  displayName: string # Human-readable name for the deployment. 
  dependsOn: string | [ string ]  # Any jobs which must complete before this one
  condition: string # Evaluate this condition expression to determine whether to run this deployment. 
  continueOnError: string # Continue running even on failure?. 
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it. 
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it. 
  variables: variables # Deployment-specific variables
  pool: pool # Pool where this job will run
  environment: deploymentEnvironment # Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name.
  strategy: deploymentStrategy # Execution strategy for this deployment
  workspace:  # Workspace options on the agent.
    clean: string # Which parts of the workspace should be scorched before fetching.  (outputs, resources, all)
  container: jobContainer # Container resource name
  services:  # Container resources to run as a service container.
    string: string # Name/value pairs.
```


Properties that use this definition: [jobs](jobs.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `deployment`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Name of the deployment job, A-Z, a-z, 0-9, and underscore. The word deploy is a keyword and is unsupported as the deployment name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `displayName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Human-readable name for the deployment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `dependsOn`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string or string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Any jobs which must complete before this one. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `condition`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this deployment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `continueOnError`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Continue running even on failure? 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `timeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for this job to complete before the server kills it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `cancelTimeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for the job to cancel before forcibly terminating it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[variables](variables.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Deployment-specific variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pool`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[pool](pool.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pool where this job will run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `environment`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.environment](jobs-deployment-environment.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `strategy`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.strategy](jobs-deployment-strategy.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Execution strategy for this deployment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `workspace`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
workspace options
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Workspace options on the agent. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.job.container](jobs-job-container.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resource name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `services`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resources to run as a service container. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="job{deployment}" version="azure-pipelines-2020.1"::: -->

```yaml
jobs:
- deployment: string # Required as first property. Name of the deployment job, A-Z, a-z, 0-9, and underscore. The word deploy is a keyword and is unsupported as the deployment name.. 
  displayName: string # Human-readable name for the deployment. 
  dependsOn: string | [ string ]  # Any jobs which must complete before this one
  condition: string # Evaluate this condition expression to determine whether to run this deployment. 
  continueOnError: string # Continue running even on failure?. 
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it. 
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it. 
  variables: variables # Deployment-specific variables
  pool: pool # Pool where this job will run
  environment: deploymentEnvironment # Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name.
  strategy: deploymentStrategy # Execution strategy for this deployment
  workspace:  # Workspace options on the agent.
    clean: string # Which parts of the workspace should be scorched before fetching.  (outputs, resources, all)
  uses:  # Any resources required by this job that are not already referenced
    repositories: [ string ] # Repository references 
    pools: [ string ] # Pool references 
  container: jobContainer # Container resource name
  services:  # Container resources to run as a service container.
    string: string # Name/value pairs.
```


Properties that use this definition: [jobs](jobs.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `deployment`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Name of the deployment job, A-Z, a-z, 0-9, and underscore. The word deploy is a keyword and is unsupported as the deployment name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `displayName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Human-readable name for the deployment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `dependsOn`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string or string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Any jobs which must complete before this one. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `condition`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this deployment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `continueOnError`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Continue running even on failure? 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `timeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for this job to complete before the server kills it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `cancelTimeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for the job to cancel before forcibly terminating it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[variables](variables.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Deployment-specific variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pool`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[pool](pool.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pool where this job will run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `environment`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.environment](jobs-deployment-environment.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `strategy`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.strategy](jobs-deployment-strategy.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Execution strategy for this deployment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `workspace`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
workspace options
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Workspace options on the agent. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `uses`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
pools and repositories
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Any resources required by this job that are not already referenced. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.job.container](jobs-job-container.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resource name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `services`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resources to run as a service container. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="job{deployment}" version="azure-pipelines"::: -->

```yaml
jobs:
- deployment: string # Required as first property. Name of the deployment job, A-Z, a-z, 0-9, and underscore. The word deploy is a keyword and is unsupported as the deployment name.. 
  displayName: string # Human-readable name for the deployment. 
  dependsOn: string | [ string ]  # Any jobs which must complete before this one
  condition: string # Evaluate this condition expression to determine whether to run this deployment. 
  continueOnError: string # Continue running even on failure?. 
  timeoutInMinutes: string # Time to wait for this job to complete before the server kills it. 
  cancelTimeoutInMinutes: string # Time to wait for the job to cancel before forcibly terminating it. 
  variables: variables # Deployment-specific variables
  pool: pool # Pool where this job will run
  environment: deploymentEnvironment # Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name.
  strategy: deploymentStrategy # Execution strategy for this deployment
  workspace:  # Workspace options on the agent.
    clean: string # Which parts of the workspace should be scorched before fetching.  (outputs, resources, all)
  uses:  # Any resources required by this job that are not already referenced
    repositories: [ string ] # Repository references 
    pools: [ string ] # Pool references 
  container: jobContainer # Container resource name
  services:  # Container resources to run as a service container.
    string: string # Name/value pairs.
  templateContext: 
     # Job, stage, or deployment related information passed from a pipeline when extending a template.```


Properties that use this definition: [jobs](jobs.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `deployment`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Name of the deployment job, A-Z, a-z, 0-9, and underscore. The word deploy is a keyword and is unsupported as the deployment name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `displayName`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Human-readable name for the deployment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `dependsOn`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string or string list
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Any jobs which must complete before this one. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `condition`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Evaluate this condition expression to determine whether to run this deployment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `continueOnError`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
boolean
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Continue running even on failure? 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `timeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for this job to complete before the server kills it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `cancelTimeoutInMinutes`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Time to wait for the job to cancel before forcibly terminating it. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `variables`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[variables](variables.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Deployment-specific variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `pool`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[pool](pool.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Pool where this job will run. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `environment`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.environment](jobs-deployment-environment.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Target environment name and optionally a resource name to record the deployment history; format: environment-name.resource-name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `strategy`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.deployment.strategy](jobs-deployment-strategy.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Execution strategy for this deployment. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `workspace`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
workspace options
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Workspace options on the agent. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `uses`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
pools and repositories
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Any resources required by this job that are not already referenced. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `container`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[jobs.job.container](jobs-job-container.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resource name. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `services`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string name/value pairs
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Container resources to run as a service container. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `templateContext`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
templateContext
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


<!-- Remarks -->


## Examples

```YAML
jobs:
  # track deployments on the environment
- deployment: DeployWeb
  displayName: deploy Web App
  pool:
    vmImage: ubuntu-latest
  # creates an environment if it doesn't exist
  environment: 'smarthotel-dev'
  strategy:
    # default deployment strategy, more coming...
    runOnce:
      deploy:
        steps:
        - script: echo my first deployment
```


<!-- See also -->
