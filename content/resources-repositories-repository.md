---
title: resources.repositories.repository definition
description: resources.repositories.repository definition reference.
ms.date: 09/20/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1 || = azure-pipelines-2022"
---

# resources.repositories.repository definition


The `repository` keyword lets you specify an external repository.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="repositoryResource{repository}" version="azure-pipelines-2019"::: -->

```yaml
repositories:
- repository: string # Required as first property. Alias for the specified repository.  ([-_A-Za-z0-9]*)
  endpoint: string # ID of the service endpoint connecting to this repository. 
  name: string # repository name (format depends on `type`); does not accept variables. 
  type: string # Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
  ref: string # ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables. 
```


Properties that use this definition: [resources.repositories](resources-repositories.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repository`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Alias for the specified repository. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `endpoint`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ID of the service endpoint connecting to this repository. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `name`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->repository name (format depends on `type`); does not accept variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `type`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `ref`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2019.1"

<!-- :::api-definition signature="repositoryResource{repository}" version="azure-pipelines-2019.1"::: -->

```yaml
repositories:
- repository: string # Required as first property. Alias for the specified repository.  ([-_A-Za-z0-9]*)
  endpoint: string # ID of the service endpoint connecting to this repository. 
  name: string # repository name (format depends on `type`); does not accept variables. 
  type: string # Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
  ref: string # ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables. 
```


Properties that use this definition: [resources.repositories](resources-repositories.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repository`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Alias for the specified repository. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `endpoint`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ID of the service endpoint connecting to this repository. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `name`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->repository name (format depends on `type`); does not accept variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `type`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `ref`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020"

<!-- :::api-definition signature="repositoryResource{repository}" version="azure-pipelines-2020"::: -->

```yaml
repositories:
- repository: string # Required as first property. Alias for the specified repository.  ([-_A-Za-z0-9]*)
  endpoint: string # ID of the service endpoint connecting to this repository. 
  trigger: trigger # CI trigger for this repository, no CI trigger if skipped (only works for Azure Repos).
  name: string # repository name (format depends on `type`); does not accept variables. 
  type: string # Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
  ref: string # ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables. 
```


Properties that use this definition: [resources.repositories](resources-repositories.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repository`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Alias for the specified repository. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `endpoint`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ID of the service endpoint connecting to this repository. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[trigger](trigger.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->CI trigger for this repository, no CI trigger if skipped (only works for Azure Repos). 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `name`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->repository name (format depends on `type`); does not accept variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `type`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `ref`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2020.1"

<!-- :::api-definition signature="repositoryResource{repository}" version="azure-pipelines-2020.1"::: -->

```yaml
repositories:
- repository: string # Required as first property. Alias for the specified repository.  ([-_A-Za-z0-9]*)
  endpoint: string # ID of the service endpoint connecting to this repository. 
  trigger: trigger # CI trigger for this repository, no CI trigger if skipped (only works for Azure Repos).
  name: string # repository name (format depends on `type`); does not accept variables. 
  type: string # Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
  ref: string # ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables. 
```


Properties that use this definition: [resources.repositories](resources-repositories.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repository`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Alias for the specified repository. Acceptable values: [_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `endpoint`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ID of the service endpoint connecting to this repository. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[trigger](trigger.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->CI trigger for this repository, no CI trigger if skipped (only works for Azure Repos). 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `name`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->repository name (format depends on `type`); does not accept variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `type`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `ref`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines-2022"

<!-- :::api-definition signature="repositoryResource{repository}" version="azure-pipelines-2022"::: -->

```yaml
repositories:
- repository: string # Required as first property. Alias for the specified repository.  ([-_A-Za-z0-9]*)
  endpoint: string # ID of the service endpoint connecting to this repository. 
  trigger: trigger # CI trigger for this repository, no CI trigger if skipped (only works for Azure Repos).
  name: string # repository name (format depends on `type`); does not accept variables. 
  type: string # Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
  ref: string # ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables. 
```


Properties that use this definition: [resources.repositories](resources-repositories.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repository`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Alias for the specified repository. Acceptable values: [-_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `endpoint`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ID of the service endpoint connecting to this repository. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[trigger](trigger.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->CI trigger for this repository, no CI trigger if skipped (only works for Azure Repos). 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `name`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->repository name (format depends on `type`); does not accept variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `type`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `ref`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end

:::moniker range="= azure-pipelines"

<!-- :::api-definition signature="repositoryResource{repository}" version="azure-pipelines"::: -->

```yaml
repositories:
- repository: string # Required as first property. Alias for the specified repository.  ([-_A-Za-z0-9]*)
  endpoint: string # ID of the service endpoint connecting to this repository. 
  trigger: trigger # CI trigger for this repository, no CI trigger if skipped (only works for Azure Repos).
  name: string # repository name (format depends on `type`); does not accept variables. 
  type: string # Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
  ref: string # ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables. 
```


Properties that use this definition: [resources.repositories](resources-repositories.md)

## Properties


<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `repository`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Required as first parameter. Alias for the specified repository. Acceptable values: [-_A-Za-z0-9]*
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `endpoint`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ID of the service endpoint connecting to this repository. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `trigger`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
[trigger](trigger.md)
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->CI trigger for this repository, no CI trigger if skipped (only works for Azure Repos). 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `name`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->repository name (format depends on `type`); does not accept variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `type`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___



<!-- :::api-property::: -->
:::row:::
  :::column:::
   <!-- :::api-property-name::: -->
   `ref`
   <!-- :::api-property-name-end::: -->
  :::column-end:::
  :::column span="3":::
<!-- :::api-property-type::: --> 
string
<!-- :::api-property-type-end::: -->  
<!-- :::api-desc type="property"::: -->ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

> [!IMPORTANT]
> Repository resource does not allow pipeline variables in `name` and `ref`. Wildcards are supported in triggers.

::: moniker range=">= azure-pipelines-2020"

> [!IMPORTANT]
> Repository resource triggers are supported for Azure Repos Git repositories only. For more information on `trigger` syntax, including [wildcard support](/azure/devops/pipelines/repos/azure-repos-git?tabs=yaml#wildcards) for [branches](/azure/devops/pipelines/repos/azure-repos-git?tabs=yaml#branches) and [tags](/azure/devops/pipelines/repos/azure-repos-git?tabs=yaml#tags), see [trigger definition](trigger.md) and [Build Azure Repos Git or TFS Git repositories](/azure/devops/pipelines/repos/azure-repos-git).
>
> `batch` is not supported in repository resource triggers.

::: moniker-end

::: moniker range=">= azure-pipelines-2019 <= azure-pipelines-2019.1"

If your pipeline has [templates in another repository](/azure/devops/pipelines/process/templates#using-other-repositories), you must let the system know about that repository.

::: moniker-end

::: moniker range=">= azure-pipelines-2020"

If your pipeline has [templates in another repository](/azure/devops/pipelines/process/templates#use-other-repositories), or if you want to use [multi-repo checkout](/azure/devops/pipelines/repos/multi-repo-checkout) with a repository that requires a service connection, you must let the system know about that repository.

::: moniker-end

### Types

Pipelines support the following values for the repository type: `git`, `github`, and `bitbucket`.
The `git` type refers to Azure Repos Git repos.

- If you specify `type: git`, the `name` value refers to the name of an Azure Repos Git repository.
  - If your pipeline is in the same Azure DevOps project as the repository, for example a repository named `tools`, you reference it using `name: tools`. 
  - If your pipeline is in the same Azure DevOps organization as the repository, but in a different Azure DevOps project, for example a project named `ToolsProject`, you must qualify the repository name with the project name: `name: ToolsProject/tools`.

- If you specify `type: github`, the `name` value is the full name of the GitHub repo and includes the user or organization.
  An example is `name: Microsoft/vscode`.
  GitHub repos require a [GitHub service connection](/azure/devops/pipelines/library/service-endpoints) for authorization.

- If you specify `type: bitbucket`, the `name` value is the full name of the Bitbucket Cloud repo and includes the user or organization.
  An example is `name: MyBitbucket/vscode`.
  Bitbucket Cloud repos require a [Bitbucket Cloud service connection](/azure/devops/pipelines/library/service-endpoints#bitbucket-cloud-service-connection) for authorization.

For more information about these types, see [Check out multiple repositories in your pipeline - Repository resource definition](/azure/devops/pipelines/repos/multi-repo-checkout#repository-resource-definition).


## Examples

```yaml
resources:
  repositories:
  - repository: common
    type: github
    name: Contoso/CommonTools
    endpoint: MyContosoServiceConnection
```


## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)



