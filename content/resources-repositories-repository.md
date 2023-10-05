---
title: resources.repositories.repository definition
description: A repository resource is used to reference an additional repository in your pipeline.
ms.date: 09/12/2023
monikerRange: ">=azure-pipelines-2019"
---

# resources.repositories.repository definition

<!-- :::description::: -->
:::moniker range=">=azure-pipelines-2019"

<!-- :::editable-content name="description"::: -->
The `repository` keyword lets you specify an external repository. Use a repository resource to reference an additional repository in your pipeline.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range=">=azure-pipelines-2022.1"

```yaml
repositories:
- repository: string # Required as first property. Alias for the repository.
  endpoint: string # ID of the service endpoint connecting to this repository.
  trigger: none | trigger | [ string ] # CI trigger for this repository, no CI trigger if skipped (only works for Azure Repos).
  name: string # repository name (format depends on 'type'; does not accept variables).
  ref: string # ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires.
  type: string # Type of repository: git, github, githubenterprise, and bitbucket.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2020 <=azure-pipelines-2022"

```yaml
repositories:
- repository: string # Required as first property. Alias for the repository.
  endpoint: string # ID of the service endpoint connecting to this repository.
  trigger: none | trigger | [ string ] # CI trigger for this repository, no CI trigger if skipped (only works for Azure Repos).
  name: string # repository name (format depends on 'type'; does not accept variables).
  type: string # Type of repository: git, github, githubenterprise, and bitbucket.
  ref: string # ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2019.1"

```yaml
repositories:
- repository: string # Required as first property. Alias for the repository.
  endpoint: string # ID of the service endpoint connecting to this repository.
  name: string # repository name (format depends on 'type'; does not accept variables).
  type: string # Type of repository: git, github, githubenterprise, and bitbucket.
  ref: string # ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables.
```

:::moniker-end
<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range=">=azure-pipelines-2019"

Definitions that reference this definition: [resources.repositories](resources-repositories.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="repository"::: -->
:::moniker range=">=azure-pipelines-2019"

**`repository`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Alias for the specified repository. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="endpoint"::: -->
:::moniker range=">=azure-pipelines-2019"

**`endpoint`** string.<br><!-- :::editable-content name="propDescription"::: -->
ID of the service endpoint connecting to this repository.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="trigger"::: -->
:::moniker range=">=azure-pipelines-2020"

**`trigger`** [trigger](trigger.md).<br><!-- :::editable-content name="propDescription"::: -->
CI trigger for this repository, no CI trigger if skipped (only works for Azure Repos).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
:::moniker range=">=azure-pipelines-2019"

**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
Repository name. Format depends on 'type'; does not accept variables.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="ref"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`ref`** string.<br><!-- :::editable-content name="propDescription"::: -->
ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. [Template expressions are supported](/azure/devops/release-notes/2022/sprint-212-update#template-expressions-in-repository-resource-definition).
<!-- :::editable-content-end::: -->

:::moniker-end

:::moniker range=">=azure-pipelines-2019 <=azure-pipelines-2022"

**`ref`** string.<br><!-- :::editable-content name="propDescription"::: -->
ref name to checkout; defaults to 'refs/heads/main'. The branch checked out by default whenever the resource trigger fires. Does not accept variables.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="type"::: -->
:::moniker range=">=azure-pipelines-2019"

**`type`** string.<br><!-- :::editable-content name="propDescription"::: -->
Type of repository: git, github, githubenterprise, and bitbucket.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

::: moniker range="<= azure-pipelines-2022"

> [!IMPORTANT]
> Repository resource does not allow pipeline variables in `name` and `ref`. Wildcards are supported in triggers.

::: moniker-end

::: moniker range=">= azure-pipelines-2020"

[Template expressions are supported](/azure/devops/release-notes/2022/sprint-212-update#template-expressions-in-repository-resource-definition) for the `ref` property (but not the `name` property). Wildcards are supported in triggers.

> [!IMPORTANT]
> Repository resource triggers are supported for Azure Repos Git repositories only. For more information on `trigger` syntax, including [wildcard support](/azure/devops/pipelines/repos/azure-repos-git?tabs=yaml#wildcards) for [branches](/azure/devops/pipelines/repos/azure-repos-git?tabs=yaml#branches) and [tags](/azure/devops/pipelines/repos/azure-repos-git?tabs=yaml#tags), see [trigger definition](trigger.md) and [Build Azure Repos Git or TFS Git repositories](/azure/devops/pipelines/repos/azure-repos-git).

> [!IMPORTANT]
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

:::moniker range=">=azure-pipelines"
### Variables

In each run, the metadata for a repository resource is available to all jobs in the form of runtime variables. The `<Alias>` is the identifier that you gave for your repository resource.

```yaml
resources.repositories.<Alias>.name
resources.repositories.<Alias>.ref
resources.repositories.<Alias>.type
resources.repositories.<Alias>.id
resources.repositories.<Alias>.url
resources.repositories.<Alias>.version
```

The following example has a repository resource with an alias of `common`, and the repository resource variables are accessed using `resources.repositories.common.*`.

```yaml
resources:
  repositories:
    - repository: common
      type: git
      ref: main
      name: Repo

variables:
  ref: $[ resources.repositories.common.ref ]
  name: $[ resources.repositories.common.name ]
  id: $[ resources.repositories.common.id ]
  type: $[ resources.repositories.common.type ]
  url: $[ resources.repositories.common.url ]
  version: $[ resources.repositories.common.version ]

steps:
- bash: |
    echo "name = $(name)"
    echo "ref = $(ref)"
    echo "id = $(id)"
    echo "type = $(type)"
    echo "url = $(url)"
    echo "url = $(version)"
```

::: moniker-end

:::moniker range=">=azure-pipelines-2020 < azure-pipelines"

### Variables

In each run, the metadata for a repository resource is available to all jobs in the form of runtime variables. The `<Alias>` is the identifier that you gave for your repository resource.

```yaml
resources.repositories.<Alias>.name
resources.repositories.<Alias>.ref
resources.repositories.<Alias>.type
resources.repositories.<Alias>.id
resources.repositories.<Alias>.url
```

The following example has a repository resource with an alias of `common`, and the repository resource variables are accessed using `resources.repositories.common.*`.

```yaml
resources:
  repositories:
    - repository: common
      type: git
      ref: main
      name: Repo

variables:
  ref: $[ resources.repositories.common.ref ]
  name: $[ resources.repositories.common.name ]
  id: $[ resources.repositories.common.id ]
  type: $[ resources.repositories.common.type ]
  url: $[ resources.repositories.common.url ]

steps:
- bash: |
    echo "name = $(name)"
    echo "ref = $(ref)"
    echo "id = $(id)"
    echo "type = $(type)"
    echo "url = $(url)"
```

::: moniker-end
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

```yaml
resources:
  repositories:
  - repository: common
    type: github
    name: Contoso/CommonTools
    endpoint: MyContosoServiceConnection
```
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Add resources to a pipeline](/azure/devops/pipelines/process/resources)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
