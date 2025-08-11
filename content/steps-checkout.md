---
title: steps.checkout definition
description: Configure how the pipeline checks out source code.
ms.date: 08/11/2025
monikerRange: "<=azure-pipelines"
author: steved0x
ms.author: sdanie
---

# steps.checkout definition

<!-- :::description::: -->
:::moniker range="<=azure-pipelines"

<!-- :::editable-content name="description"::: -->
Use `checkout` to configure how the pipeline checks out source code.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::description-end::: -->

<!-- :::syntax::: -->
:::moniker range="=azure-pipelines"

```yaml
steps:
- checkout: string # Required as first property. Configures checkout for the specified repository.
  clean: true | false # If true, run git clean -ffdx followed by git reset --hard HEAD before fetching.
  fetchDepth: string # Depth of Git graph to fetch.
  fetchFilter: string # Filter Git history.
  fetchTags: string # Set to 'true' to sync tags when fetching the repo, or 'false' to not sync tags. See remarks for the default behavior.
  lfs: string # Set to 'true' to download Git-LFS files. Default is not to download them.
  persistCredentials: string # Set to 'true' to leave the OAuth token in the Git config after the initial fetch. The default is not to leave it.
  submodules: string # Set to 'true' for a single level of submodules or 'recursive' to get submodules of submodules. Default is not to fetch submodules.
  path: string # Where to put the repository. The root directory is $(Pipeline.Workspace).
  sparseCheckoutDirectories: string # Directories for sparse checkout in cone mode and prioritized over sparseCheckoutPatterns if both properties are provided.
  sparseCheckoutPatterns: string # Patterns for sparse checkout in non-cone mode that are ignored if sparseCheckoutDirectories is provided.
  workspaceRepo: true | false # When true, use the repository root directory as the default working directory for the pipeline. The default is false.
  condition: string # Evaluate this condition expression to determine whether to run this task.
  continueOnError: boolean # Continue running even on failure?
  displayName: string # Human-readable name for the task.
  target: string | target # Environment in which to run this task.
  enabled: boolean # Run this task when the job runs?
  env: # Variables to map into the process's environment.
    string: string # Name/value pairs
  name: string # ID of the step.
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it.
  retryCountOnTaskFailure: string # Number of retries if the task fails.
```

:::moniker-end

:::moniker range=">=azure-pipelines-2022.1 <=azure-pipelines-2022.2"

```yaml
steps:
- checkout: string # Required as first property. Configures checkout for the specified repository.
  clean: true | false # If true, run git clean -ffdx followed by git reset --hard HEAD before fetching.
  fetchDepth: string # Depth of Git graph to fetch.
  fetchTags: string # Set to 'true' to sync tags when fetching the repo, or 'false' to not sync tags. See remarks for the default behavior.
  lfs: string # Set to 'true' to download Git-LFS files. Default is not to download them.
  persistCredentials: string # Set to 'true' to leave the OAuth token in the Git config after the initial fetch. The default is not to leave it.
  submodules: string # Set to 'true' for a single level of submodules or 'recursive' to get submodules of submodules. Default is not to fetch submodules.
  path: string # Where to put the repository. The root directory is $(Pipeline.Workspace).
  condition: string # Evaluate this condition expression to determine whether to run this task.
  continueOnError: boolean # Continue running even on failure?
  displayName: string # Human-readable name for the task.
  target: string | target # Environment in which to run this task.
  enabled: boolean # Run this task when the job runs?
  env: # Variables to map into the process's environment.
    string: string # Name/value pairs
  name: string # ID of the step.
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it.
  retryCountOnTaskFailure: string # Number of retries if the task fails.
```

:::moniker-end

:::moniker range="=azure-pipelines-2022"

```yaml
steps:
- checkout: string # Required as first property. Configures checkout for the specified repository.
  clean: true | false # If true, run git clean -ffdx followed by git reset --hard HEAD before fetching.
  fetchDepth: string # Depth of Git graph to fetch.
  lfs: string # Set to 'true' to download Git-LFS files. Default is not to download them.
  persistCredentials: string # Set to 'true' to leave the OAuth token in the Git config after the initial fetch. The default is not to leave it.
  submodules: string # Set to 'true' for a single level of submodules or 'recursive' to get submodules of submodules. Default is not to fetch submodules.
  path: string # Where to put the repository. The root directory is $(Pipeline.Workspace).
  condition: string # Evaluate this condition expression to determine whether to run this task.
  continueOnError: boolean # Continue running even on failure?
  displayName: string # Human-readable name for the task.
  target: string | target # Environment in which to run this task.
  enabled: boolean # Run this task when the job runs?
  env: # Variables to map into the process's environment.
    string: string # Name/value pairs
  name: string # ID of the step.
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it.
  retryCountOnTaskFailure: string # Number of retries if the task fails.
```

:::moniker-end

:::moniker range="<=azure-pipelines-2020.1"

```yaml
steps:
- checkout: string # Required as first property. Configures checkout for the specified repository.
  clean: true | false # If true, run git clean -ffdx followed by git reset --hard HEAD before fetching.
  fetchDepth: string # Depth of Git graph to fetch.
  lfs: string # Set to 'true' to download Git-LFS files. Default is not to download them.
  persistCredentials: string # Set to 'true' to leave the OAuth token in the Git config after the initial fetch. The default is not to leave it.
  submodules: string # Set to 'true' for a single level of submodules or 'recursive' to get submodules of submodules. Default is not to fetch submodules.
  path: string # Where to put the repository. The root directory is $(Pipeline.Workspace).
  condition: string # Evaluate this condition expression to determine whether to run this task.
  continueOnError: boolean # Continue running even on failure?
  displayName: string # Human-readable name for the task.
  target: string | target # Environment in which to run this task.
  enabled: boolean # Run this task when the job runs?
  env: # Variables to map into the process's environment.
    string: string # Name/value pairs
  name: string # ID of the step.
  timeoutInMinutes: string # Time to wait for this task to complete before the server kills it.
```

:::moniker-end

<!-- :::syntax-end::: -->

<!-- :::parents::: -->
:::moniker range="<=azure-pipelines"

Definitions that reference this definition: [steps](steps.md)

:::moniker-end
<!-- :::parents-end::: -->

## Properties

<!-- :::properties::: -->
<!-- :::item name="checkout"::: -->
:::moniker range="<=azure-pipelines"

**`checkout`** string. Required as first property.<br><!-- :::editable-content name="propDescription"::: -->
Configures checkout for the specified repository. Specify `self`, `none`, [repository name](/azure/devops/pipelines/repos/multi-repo-checkout#inline-syntax-checkout), or [repository resource](/azure/devops/pipelines/repos/multi-repo-checkout#repository-resource-definition). For more information, see [Check out multiple repositories in your pipeline](/azure/devops/pipelines/repos/multi-repo-checkout).

> [!NOTE]
> If no `checkout` step is present, it defaults to `self` for `jobs.job.step.checkout` and `none` for `jobs.deployment.steps.checkout`.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="clean"::: -->
:::moniker range="<=azure-pipelines"

**`clean`** string.<br><!-- :::editable-content name="propDescription"::: -->
If true, run git clean -ffdx followed by git reset --hard HEAD before fetching. true | false.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="fetchDepth"::: -->
:::moniker range="<=azure-pipelines"

**`fetchDepth`** string.<br><!-- :::editable-content name="propDescription"::: -->
Depth of Git graph to fetch.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="fetchFilter"::: -->
:::moniker range="=azure-pipelines"

**`fetchFilter`** string.<br><!-- :::editable-content name="propDescription"::: -->
Use `fetchFilter` to filter Git history for partial cloning. The `fetchFilter` setting supports treeless and blobless fetches. For a treeless fetch, specify `fetchFilter: tree:0` and to specify a blobless fetch, specify `fetchFilter: blob:none`. The default is no filtering.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="fetchTags"::: -->
:::moniker range=">=azure-pipelines-2022.1"

**`fetchTags`** string.<br><!-- :::editable-content name="propDescription"::: -->
Set to 'true' to sync tags when fetching the repo, or 'false' to not sync tags. See remarks for the default behavior.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="lfs"::: -->
:::moniker range="<=azure-pipelines"

**`lfs`** string.<br><!-- :::editable-content name="propDescription"::: -->
Set to 'true' to download Git-LFS files. Default is not to download them.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="persistCredentials"::: -->
:::moniker range="<=azure-pipelines"

**`persistCredentials`** string.<br><!-- :::editable-content name="propDescription"::: -->
Set to 'true' to leave the OAuth token in the Git config after the initial fetch. The default is not to leave it.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="submodules"::: -->
:::moniker range="<=azure-pipelines"

**`submodules`** string.<br><!-- :::editable-content name="propDescription"::: -->
Set to 'true' for a single level of submodules or 'recursive' to get submodules of submodules. Default is not to fetch submodules.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="path"::: -->
:::moniker range="<=azure-pipelines"

**`path`** string.<br><!-- :::editable-content name="propDescription"::: -->
Where to put the repository. The root directory is $(Pipeline.Workspace). By default this folder must be under the agent working directory structure. To set a path outside of the agent working directory, set a pipeline variable named `AZP_AGENT_ALLOW_WORK_DIRECTORY_REPOSITORIES` to true, and use the prefix `../` at the start of your checkout path. Supported on agent version 3.230.0 and higher.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sparseCheckoutDirectories"::: -->
:::moniker range="=azure-pipelines"

**`sparseCheckoutDirectories`** string.<br><!-- :::editable-content name="propDescription"::: -->
Specify a directory to enable sparse checkout in cone mode using directory matching. Separate multiple directories using a space. Supported on agent version 3.253.0/4.253.0 and higher with Git 2.25 or higher.

```yml
- checkout: repo
  sparseCheckoutDirectories: src
```

If both `sparseCheckoutDirectories` and `sparseCheckoutPatterns` are set, `sparseCheckoutDirectories` is used and the setting for `sparseCheckoutPatterns` is disregarded.

For more information on sparse checkout, see [Bring your monorepo down to size with sparse-checkout](https://github.blog/open-source/git/bring-your-monorepo-down-to-size-with-sparse-checkout/).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="sparseCheckoutPatterns"::: -->
:::moniker range="=azure-pipelines"

**`sparseCheckoutPatterns`** string.<br><!-- :::editable-content name="propDescription"::: -->
Specify a pattern to enable sparse checkout in non-cone mode using pattern matching. Separate multiple patterns using a space. Supported on agent version 3.253.0/4.253.0 and higher with Git 2.25 or higher.

```yml
- checkout: repo
  sparseCheckoutPatterns: /* !/img
```

If both `sparseCheckoutDirectories` and `sparseCheckoutPatterns` are set, `sparseCheckoutDirectories` is used and the setting for `sparseCheckoutPatterns` is disregarded.

For more information on sparse checkout, see [Bring your monorepo down to size with sparse-checkout](https://github.blog/open-source/git/bring-your-monorepo-down-to-size-with-sparse-checkout/).
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="workspaceRepo"::: -->
:::moniker range="=azure-pipelines"

**`workspaceRepo`** string.<br><!-- :::editable-content name="propDescription"::: -->
When true, use the repository root directory as the default working directory for the pipeline. The default is false.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="condition"::: -->
:::moniker range="<=azure-pipelines"

**`condition`** string.<br><!-- :::editable-content name="propDescription"::: -->
Evaluate this condition expression to determine whether to run this task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="continueOnError"::: -->
:::moniker range="<=azure-pipelines"

**`continueOnError`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Continue running even on failure?
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="displayName"::: -->
:::moniker range="<=azure-pipelines"

**`displayName`** string.<br><!-- :::editable-content name="propDescription"::: -->
Human-readable name for the task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="target"::: -->
:::moniker range="<=azure-pipelines"

**`target`** [target](target.md).<br><!-- :::editable-content name="propDescription"::: -->
Environment in which to run this task.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="enabled"::: -->
:::moniker range="<=azure-pipelines"

**`enabled`** [boolean](boolean.md).<br><!-- :::editable-content name="propDescription"::: -->
Run this task when the job runs?
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="env"::: -->
:::moniker range="<=azure-pipelines"

**`env`** string dictionary.<br><!-- :::editable-content name="propDescription"::: -->
Variables to map into the process's environment.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="name"::: -->
:::moniker range="<=azure-pipelines"

**`name`** string.<br><!-- :::editable-content name="propDescription"::: -->
ID of the step. Acceptable values: [-_A-Za-z0-9]*.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="timeoutInMinutes"::: -->
:::moniker range="<=azure-pipelines"

**`timeoutInMinutes`** string.<br><!-- :::editable-content name="propDescription"::: -->
Time to wait for this task to complete before the server kills it.

[!INCLUDE [task-timeout](./includes/task-timeout.md)]
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::item name="retryCountOnTaskFailure"::: -->
:::moniker range=">=azure-pipelines-2022"

**`retryCountOnTaskFailure`** string.<br><!-- :::editable-content name="propDescription"::: -->
Number of retries if the task fails.
<!-- :::editable-content-end::: -->

:::moniker-end
<!-- :::item-end::: -->
<!-- :::properties-end::: -->

<!-- :::remarks::: -->
<!-- :::editable-content name="remarks"::: -->
## Remarks

:::moniker range="azure-pipelines"

* [Shallow fetch](#shallow-fetch)
* [Clean property](#clean-property)
* [Sync tags](#sync-tags)

:::moniker-end

:::moniker range="<azure-pipelines"

* [Shallow fetch](#shallow-fetch)
* [Clean property](#clean-property)

:::moniker-end

### Shallow fetch

> [!NOTE]
> In some organizations, new pipelines created after the [September 2022 Azure DevOps sprint 209 update](/azure/devops/release-notes/2022/sprint-209-update) have **Shallow fetch** enabled by default and configured with a depth of 1. Previously the default was not to shallow fetch.
>
> To check your pipeline, view the **Shallow fetch** setting in the [pipeline settings UI](/azure/devops/pipelines/repos/azure-repos-git#shallow-fetch).

To disable shallow fetch, you can perform one of the following two options.

* Disable the **Shallow fetch** option in the [pipeline settings UI](/azure/devops/pipelines/repos/azure-repos-git#shallow-fetch).
* Explicitly set `fetchDepth: 0` in your `checkout` step.

To configure the fetch depth for a pipeline, you can either set the `fetchDepth` property in the `checkout` step, or configure the **Shallow fetch** setting in the [pipeline settings UI](/azure/devops/pipelines/repos/azure-repos-git#shallow-fetch).

> [!NOTE]
> If you explicitly set `fetchDepth` in your `checkout` step, that setting takes priority over the setting configured in the pipeline settings UI. Setting `fetchDepth: 0` fetches all history and overrides the **Shallow fetch** setting.

### Clean property

If the `clean` property is unset, then its default value is configured by the **clean** setting in the UI settings for YAML pipelines, which is set to true by default. In addition to the cleaning option available using `checkout`, you can also configure cleaning in a workspace. For more information about workspaces and clean options, see the [workspace](/azure/devops/pipelines/process/phases#workspace) topic in [Jobs](/azure/devops/pipelines/process/phases).

::: moniker range="= azure-pipelines"

### Sync tags

The checkout step uses the `--tags` option when fetching the contents of a Git repository. This causes the server to fetch all tags as well as all objects that are pointed to by those tags. This increases the time to run the task in a pipeline, particularly if you have a large repository with a number of tags. Furthermore, the checkout step syncs tags even when you enable the shallow fetch option, thereby possibly defeating its purpose. To reduce the amount of data fetched or pulled from a Git repository, Microsoft has added a new option to checkout to control the behavior of syncing tags. This option is available both in classic and YAML pipelines.

Whether to synchronize tags when checking out a repository can be configured in YAML by setting the `fetchTags` property, and in the UI by configuring the **Sync tags** setting.

To configure whether to synchronize tags when checking out a repository, you can either set the `fetchTags` property in the `checkout` step, or configure the **Sync tags** setting in the [pipeline settings UI](/azure/devops/pipelines/repos/azure-repos-git#sync-tags).

> [!NOTE]
> If you explicitly set `fetchTags` in your `checkout` step, that setting takes priority over the **Sync tags** setting configured in the [pipeline settings UI](/azure/devops/pipelines/repos/azure-repos-git#sync-tags).

To configure the setting in YAML, set the `fetchTags` property.

```YAML
steps:
- checkout: self
  fetchTags: true
```

To configure the setting in the pipeline UI, edit your YAML pipeline, and choose **More actions**, **Triggers**, **YAML**, **Get sources**, and check or uncheck the **Sync tags** checkbox. For more information, see [Sync tags](/azure/devops/pipelines/repos/azure-repos-git#sync-tags).

#### Default behavior

* For existing pipelines created before the release of [Azure DevOps sprint 209](/azure/devops/release-notes/2022/sprint-209-update#do-not-sync-tags-when-fetching-a-git-repository), released in September 2022, the default for syncing tags remains the same as the existing behavior before the **Sync tags** options was added, which is `true`.
* For new pipelines created after Azure DevOps sprint release 209, the default for syncing tags is `false`.

::: moniker-end
<!-- :::editable-content-end::: -->
<!-- :::remarks-end::: -->

<!-- :::examples::: -->
<!-- :::editable-content name="examples"::: -->
## Examples

There are three options for `checkout`. By default, Azure DevOps checks out the current repository with `self` for jobs. When you set `none`, no repository is checked out. If you specify another repository, that repository is checked out. To check out a different repository, set it up as a [repository resource first](resources-repositories-repository.md).

```yaml
# Checkout the current repository
steps:
- checkout: self

# Prevent checking out any source code
steps:
- checkout: none

# Checkout a different repository
steps:
- checkout: my-other-repo
```

To avoid syncing sources at all:

```yaml
steps:
- checkout: none
```

> [!NOTE]
> If you're running the agent in the Local Service account and want to modify the current repository by using git operations or loading git submodules, give the proper permissions to the Project Collection Build Service Accounts user.

```yaml
- checkout: self
  submodules: true
  persistCredentials: true
```

::: moniker range=">= azure-pipelines-2020"

To check out multiple repositories in your pipeline, use multiple `checkout` steps:

```yaml
- checkout: self
- checkout: git://MyProject/MyRepo
- checkout: MyGitHubRepo # Repo declared in a repository resource
```

For more information, see [Check out multiple repositories in your pipeline](/azure/devops/pipelines/repos/multi-repo-checkout).

::: moniker-end
<!-- :::editable-content-end::: -->
<!-- :::examples-end::: -->

<!-- :::see-also::: -->
<!-- :::editable-content name="seeAlso"::: -->
## See also

- [Supported source repositories](/azure/devops/pipelines/repos/)
<!-- :::editable-content-end::: -->
<!-- :::see-also-end::: -->
