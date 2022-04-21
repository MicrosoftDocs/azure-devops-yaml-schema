---
title: resources.repositories.repository definition
description: resources.repositories.repository definition reference.
ms.date: 04/21/2022
monikerRange: "= azure-pipelines || = azure-pipelines-2019 || = azure-pipelines-2019.1 || = azure-pipelines-2020 || = azure-pipelines-2020.1"
---

# resources.repositories.repository definition


The `repository` keyword lets you specify an external repository.


:::moniker range="= azure-pipelines-2019"

<!-- :::api-definition signature="repositoryResource{repository}" version="azure-pipelines-2019"::: -->

```yaml
repositories:
- repository: string # Required as first property. ID of the external repository.  ([-_A-Za-z0-9]*)
  endpoint: string # ID of the service endpoint connecting to this repository. 
  name: string # string  # repository name (format depends on `type`). 
  type: string # Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
  ref: string # ref name to use; defaults to 'refs/heads/main'. 
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
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the external repository. Acceptable values: [_A-Za-z0-9]*
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
<!-- :::api-desc type="property"::: -->string  # repository name (format depends on `type`). 
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
<!-- :::api-desc type="property"::: -->ref name to use; defaults to 'refs/heads/main'. 
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
- repository: string # Required as first property. ID of the external repository.  ([-_A-Za-z0-9]*)
  endpoint: string # ID of the service endpoint connecting to this repository. 
  name: string # string  # repository name (format depends on `type`). 
  type: string # Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
  ref: string # ref name to use; defaults to 'refs/heads/main'. 
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
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the external repository. Acceptable values: [_A-Za-z0-9]*
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
<!-- :::api-desc type="property"::: -->string  # repository name (format depends on `type`). 
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
<!-- :::api-desc type="property"::: -->ref name to use; defaults to 'refs/heads/main'. 
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
- repository: string # Required as first property. ID of the external repository.  ([-_A-Za-z0-9]*)
  endpoint: string # ID of the service endpoint connecting to this repository. 
  trigger: trigger # CI trigger for this repository, no CI trigger if skipped (only works for Azure Repos).
  name: string # string  # repository name (format depends on `type`). 
  type: string # Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
  ref: string # ref name to use; defaults to 'refs/heads/main'. 
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
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the external repository. Acceptable values: [_A-Za-z0-9]*
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
<!-- :::api-desc type="property"::: -->string  # repository name (format depends on `type`). 
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
<!-- :::api-desc type="property"::: -->ref name to use; defaults to 'refs/heads/main'. 
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
- repository: string # Required as first property. ID of the external repository.  ([-_A-Za-z0-9]*)
  endpoint: string # ID of the service endpoint connecting to this repository. 
  trigger: trigger # CI trigger for this repository, no CI trigger if skipped (only works for Azure Repos).
  name: string # string  # repository name (format depends on `type`). 
  type: string # Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
  ref: string # ref name to use; defaults to 'refs/heads/main'. 
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
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the external repository. Acceptable values: [_A-Za-z0-9]*
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
<!-- :::api-desc type="property"::: -->string  # repository name (format depends on `type`). 
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
<!-- :::api-desc type="property"::: -->ref name to use; defaults to 'refs/heads/main'. 
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
- repository: string # Required as first property. ID of the external repository.  ([-_A-Za-z0-9]*)
  endpoint: string # ID of the service endpoint connecting to this repository. 
  trigger: trigger # CI trigger for this repository, no CI trigger if skipped (only works for Azure Repos).
  name: string # string  # repository name (format depends on `type`). 
  type: string # Type of repository: `git`, `github`, `githubenterprise`, and `bitbucket`. 
  ref: string # ref name to use; defaults to 'refs/heads/main'. 
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
<!-- :::api-desc type="property"::: -->Required as first parameter. ID of the external repository. Acceptable values: [-_A-Za-z0-9]*
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
<!-- :::api-desc type="property"::: -->string  # repository name (format depends on `type`). 
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
<!-- :::api-desc type="property"::: -->ref name to use; defaults to 'refs/heads/main'. 
 <!-- :::api-desc-end::: -->
  :::column-end:::
:::row-end:::
<!-- :::api-property-end::: -->
___





<!-- :::api-definition-end::: -->

:::moniker-end


## Remarks

::: moniker range=">= azure-pipelines-2020"

> [!IMPORTANT]
> Repository resource triggers are supported for Azure Repos Git repositories only. For more information on `trigger` syntax, including [wildcard support](/azure/devops/pipelines/repos/azure-repos-git?tabs=yaml#wildcards) for [branches](/azure/devops/pipelines/repos/azure-repos-git?tabs=yaml#branches) and [tags](/azure/devops/pipelines/repos/azure-repos-git?tabs=yaml#tags), see [trigger definition](trigger.md) and [Build Azure Repos Git or TFS Git repositories](/azure/devops/pipelines/repos/azure-repos-git).

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

- If you specify `type: git`, the `name` value refers to another repository in the same project.
  An example is `name: otherRepo`.
  To refer to a repo in another project within the same organization, prefix the name with that project's name.
  An example is `name: OtherProject/otherRepo`.

- If you specify `type: github`, the `name` value is the full name of the GitHub repo and includes the user or organization.
  An example is `name: Microsoft/vscode`.
  GitHub repos require a [GitHub service connection](/azure/devops/pipelines/library/service-endpoints) for authorization.

- If you specify `type: bitbucket`, the `name` value is the full name of the Bitbucket Cloud repo and includes the user or organization.
  An example is `name: MyBitbucket/vscode`.
  Bitbucket Cloud repos require a [Bitbucket Cloud service connection](/azure/devops/pipelines/library/service-endpoints#bitbucket-cloud-service-connection) for authorization.



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



